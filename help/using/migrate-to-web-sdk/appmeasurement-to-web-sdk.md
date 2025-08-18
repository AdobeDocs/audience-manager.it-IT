---
title: Aggiorna la libreria di raccolta dati per Audience Manager dalla libreria AppMeasurement JavaScript alla libreria Web SDK JavaScript.
description: Comprendi i passaggi per aggiornare la libreria di raccolta dati per Audience Manager dalla libreria AppMeasurement JavaScript alla libreria Web SDK JavaScript.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f180e423d4bdf5535d8dcc000e1d0f908bc54d7b
workflow-type: tm+mt
source-wordcount: '3385'
ht-degree: 0%

---


# Aggiornare la libreria di raccolta dati per Audience Manager da AppMeasurement a Web SDK

## Pubblico previsto {#intended-audience}

Questa pagina è destinata ai clienti Audience Manager e Adobe Analytics che utilizzano la libreria JavaScript [!DNL AppMeasurement] per inviare dati Web ad Audience Manager.

Per istruzioni sui passaggi di migrazione a Web SDK, a seconda del metodo di raccolta dati corrente, consulta la tabella seguente.

| Il metodo di raccolta dati esistente | Istruzioni per la migrazione a Web SDK |
|---------|----------|
| Libreria JavaScript [!DNL AppMeasurement] con modulo AudienceManagement | Seguire le istruzioni riportate in questa guida. |
| [!DNL Audience Manager] [estensione tag](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Segui le istruzioni riportate in [aggiornamento della libreria di raccolta dati dall&#39;estensione tag Audience Manager all&#39;estensione tag Web SDK](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] libreria JavaScript + [!DNL Audience Manager] [libreria DIL](../dil/dil-overview.md) autonoma | Segui le istruzioni riportate in [aggiornamento della libreria di raccolta dati dall&#39;estensione tag Audience Manager all&#39;estensione tag Web SDK](dil-extension-to-web-sdk.md). |

## Panoramica sulla migrazione {#overview}

La migrazione da [!DNL AppMeasurement] a [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) è principalmente una migrazione Adobe Analytics. Per i clienti Audience Manager, questa migrazione include anche Audience Manager. È necessario migrare entrambi insieme. Se lavori principalmente con Audience Manager, assicurati di coinvolgere il team di Analytics in questa migrazione.

Se utilizzi [!DNL AppMeasurement] per la raccolta dati di Audience Manager, stai utilizzando l&#39;approccio [!DNL Server-side Forwarding (SSF)] per inviare dati di Analytics ad Audience Manager. In questa configurazione, la richiesta di raccolta dati di Analytics viene inoltrata ad Audience Manager, che gestisce anche la risposta di Audience Manager alla pagina.

Questo è stato l’approccio standard per molti anni ed è probabile che la tua configurazione corrente. Se la libreria [!DNL AppMeasurement] contiene il modulo `AudienceManagement` e le chiamate di raccolta dati includono il percorso `/10/` nella richiesta (`/b/ss/examplereportsuite/10/`), questa guida fa per te.

## Inoltro lato server (SSF) e flussi di dati Web SDK {#data-flows}

Comprendere le differenze di flusso dei dati tra Analytics e Audience Manager durante il passaggio a Web SDK (e Edge Network) è fondamentale per le istruzioni di seguito.

Con l’inoltro lato server, il nodo di raccolta dati regionale di Analytics raccoglie i dati, li trasforma in un segnale accettato da Audience Manager, li invia ad Audience Manager e restituisce la risposta di Audience Manager alla pagina. Il modulo [!DNL AudienceManagement] nella libreria [!DNL AppMeasurement] gestisce quindi la risposta (ad esempio, l&#39;eliminazione di cookie e l&#39;invio di destinazioni URL). Questo processo è denominato inoltro lato server perché Analytics inoltra i dati ad Audience Manager utilizzando i server Adobe.

Con Web SDK, Edge Network invia i dati ad Analytics e Audience Manager in azioni separate. Il Web SDK è un’unica libreria che invia dati a tutte le soluzioni e Edge Network trasforma i punti dati indipendenti dalle soluzioni in formati specifici.

In questo nuovo flusso di dati, tutti i dati vengono inviati a un [flusso di dati](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview) di Edge Network, che puoi [configurare](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) per inviare i dati alle soluzioni Adobe in base alle esigenze. Per Audience Manager, l&#39;abilitazione del servizio Audience Manager nel flusso di dati trasforma [!DNL XDM] e i dati di Analytics in segnali accettati da Audience Manager. Edge Network restituisce anche la risposta di Audience Manager alla pagina, in cui il Web SDK gestisce la risposta, in modo simile a come hanno fatto [!DNL AppMeasurement] e il modulo [!DNL AudienceManagement].

## Migrazione tag e non tag {#tags-vs-non-tags}

Che si utilizzino i tag con l&#39;estensione [!DNL AppMeasurement], la libreria [!DNL AppMeasurement] in un altro sistema di gestione dei tag o si inserisca [!DNL AppMeasurement] direttamente nella pagina, i passaggi per la migrazione di Audience Manager al Web SDK sono gli stessi. Poiché la migrazione di Audience Manager dipende dalla migrazione di Analytics, i passaggi per la migrazione da [!DNL AppMeasurement] a Web SDK vengono determinati durante la migrazione di Analytics.

Queste informazioni sono trattate nella documentazione di Analytics per le implementazioni basate su [Tag](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) o [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk).

## XDM e i nodi `data.__adobe.` {#xdm-data-nodes}

Una delle funzioni principali di [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) consiste nell&#39;inviare dati a [Real-Time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home). Per ottenere questo e raccogliere comunque i dati per altre soluzioni Experience Cloud senza una reimplementazione completa, i dati specifici della soluzione vengono suddivisi nella chiamata al server di raccolta dati. Questa chiamata utilizza uno schema JSON standardizzato denominato [Experience Data Model (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Gli elementi indipendenti dalla soluzione, come le informazioni sul browser e sul dispositivo, vengono inviati ad Edge Network in una struttura XDM predeterminata. Edge Network trasforma questi dati in formati specifici della soluzione. Tuttavia, i dati specifici di Target, Analytics e Audience Manager vengono memorizzati in un nodo `data.__adobe` dedicato all’interno del payload XDM.

Ad esempio:

* La variabile di Analytics `s.eVar1` è rappresentata nel payload XDM come `data.__adobe.analytics.evar1`.
* Un parametro di Target relativo allo stato di fedeltà del cliente è memorizzato come `data.__adobe.target.loyaltyStatus`.

I dati nel nodo `__adobe` vengono inviati alle rispettive soluzioni (come Analytics e Audience Manager) senza essere inviati ad Experience Platform, anche se il servizio Experience Platform è abilitato nel flusso di dati. Ciò significa che puoi mantenere le configurazioni correnti per Analytics e Audience Manager, avendo al tempo stesso la flessibilità di mappare eventuali elementi di dati necessari agli elementi dello schema XDM per casi d&#39;uso in tempo reale in Experience Platform utilizzando [Preparazione dati per raccolta dati](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep).

Ad esempio, la stringa Analytics `s.products`, utilizzata per segnalare il contenuto del carrello durante l&#39;estrazione, può ancora essere inviata ad Analytics e Audience Manager nel suo formato originale. Allo stesso tempo, puoi utilizzare gli elementi di questa stringa per creare schemi di carrello XDM più intuitivi per i casi di utilizzo di Experience Platform.

Poiché la maggior parte delle implementazioni di Audience Manager si basa sui dati di Analytics inoltrati ad Audience Manager, molte delle espressioni delle caratteristiche di Audience Manager sono probabilmente basate sulle variabili di Analytics (`c_evar#`, `c_prop#` e `c_events`). Per evitare di ricostruire le espressioni delle caratteristiche utilizzando i formati XDM durante la migrazione, per impostazione predefinita Edge Network è configurato per trasformare in segnali Audience Manager tutte le variabili Analytics presenti nel nodo `data.__adobe.analytics`. Un processo di trasformazione simile si verifica nel flusso di lavoro di inoltro lato server.

Edge Network può eseguire questa trasformazione perché una singola chiamata di raccolta dati dalla pagina viene inviata a un singolo stream di dati che alimenta più soluzioni Adobe. Pertanto, la maggior parte delle migrazioni da [!DNL AppMeasurement] a Web SDK per Analytics e Audience Manager utilizzerà principalmente il nodo `data.__adobe.analytics`.

Edge Network trasforma i dati del dispositivo e del browser dalle intestazioni del payload XDM e dei pacchetti in segnali Audience Manager. Ciò ti consente di continuare a utilizzare le chiavi della piattaforma `h_` e `d_` nelle espressioni delle caratteristiche di Audience Manager.

## Nodo `data.__adobe.audiencemanager` {#data-note}

Il nodo `data.__adobe.audiencemanager` viene utilizzato per le implementazioni di Audience Manager che non si basano su Analytics. Memorizza coppie chiave/valore Audience Manager personalizzate che sono state precedentemente inviate tramite la libreria [DIL](../dil/dil-overview.md), come descritto nella [guida alla migrazione dell&#39;estensione tag](dil-extension-to-web-sdk.md).

Anche se il nodo `data.__adobe.audiencemanager` non è necessario per la migrazione descritta in questa guida, il nuovo flusso di dati qui spiegato consente di inviare dati ad Audience Manager senza registrarli in Analytics.

Se devi inviare una coppia chiave/valore personalizzata ad Audience Manager senza includerla, puoi utilizzare il nodo `data.__adobe.audiencemanager`. Tutti i set di dati in questo nodo verranno aggiunti ai dati di Analytics trasformati da Audience Manager nella chiamata al server di raccolta dati.

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo di questo approccio alla migrazione presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Utilizza l&#39;implementazione esistente**: anche se questo approccio richiede alcune modifiche di implementazione, non richiede un&#39;implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti con modifiche minime alla logica di implementazione.</li><li>**Non richiede uno schema**: per questa fase della migrazione al Web SDK non è necessario uno schema XDM. È invece possibile popolare l&#39;oggetto `data`, che invia i dati direttamente ad Audience Manager. Una volta completata la migrazione al Web SDK, puoi creare uno schema per la tua organizzazione e utilizzare la mappatura dello stream di dati per popolare i campi XDM applicabili. Se in questa fase del processo di migrazione fosse necessario uno schema, l’organizzazione sarebbe costretta a utilizzare uno schema XDM di Audience Manager. L’utilizzo di questo schema rende più difficile per l’organizzazione utilizzare il proprio schema in futuro.</li></ul> | <ul><li>**Debito tecnico per l&#39;implementazione**: poiché questo approccio utilizza una forma modificata dell&#39;implementazione esistente, può essere più difficile tenere traccia della logica di implementazione ed eseguire modifiche in futuro quando necessario.</li><li>**È necessaria la mappatura per inviare dati a Platform**: quando l&#39;organizzazione è pronta per utilizzare Real-Time CDP, è necessario inviare dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell&#39;oggetto `data` sia una voce nello strumento di mappatura dello stream di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita una sola volta per questo flusso di lavoro e non richiede l’apporto di modifiche all’implementazione. Si tratta tuttavia di un passaggio aggiuntivo non richiesto per l’invio di dati in un oggetto XDM.</li></ul> |

Adobe consiglia di seguire questo percorso di implementazione nei seguenti scenari:

* È disponibile un’implementazione esistente utilizzando la libreria JavaScript di Adobe Analytics AppMeasurement. Se disponi di un&#39;implementazione che utilizza l&#39;estensione tag Audience Manager, segui [Esegui migrazione dall&#39;estensione tag Audience Manager all&#39;estensione tag Web SDK](dil-extension-to-web-sdk.md).
* Intendi utilizzare Real-Time CDP in futuro, ma non desideri sostituire l’implementazione di Audience Manager con un’implementazione di Web SDK da zero. L’alternativa di sostituire l’implementazione da zero con il Web SDK richiede il massimo sforzo, in quanto è necessario ricreare tutte le caratteristiche Audience Manager per cercare dati in formato XDM. Tuttavia, è anche l’architettura di implementazione a lungo termine più redditizia. Se la tua organizzazione è disposta a eseguire un&#39;implementazione pulita di Web SDK, consulta la [documentazione di Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) invece di utilizzare questa guida, per ulteriori dettagli.

## Passaggi necessari per la migrazione al Web SDK

Segui i passaggi seguenti per migrare l’integrazione della raccolta dati a Web SDK.

+++**1. Pianifica la migrazione di Analytics**.

Collabora con il tuo team di Analytics per seguire i passaggi per la migrazione ad Analytics nelle implementazioni basate su [Tag](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) o [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk). Dopo aver pianificato la migrazione di Analytics, torna a questa guida e continua con i passaggi di Audience Manager per determinare cosa devi fare per Audience Manager in modo da distribuire la migrazione di Analytics e Audience Manager insieme.

+++

+++**2. Aggiungi il servizio Audience Manager allo stream di dati**

Aggiungi il servizio Audience Manager al flusso di dati in uso nella migrazione di Analytics indicata al passaggio 1.

1. Passa a [experience.adobe.com](https://experience.adobe.com) e accedi con le tue credenziali.
1. Utilizzare la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, selezionare **[!UICONTROL Datastreams]**.
1. Seleziona lo stream di dati creato durante la migrazione di Analytics al passaggio 1.
1. Selezionare **[!UICONTROL Add Service]**.
1. Nel menu a discesa del servizio, selezionare **[!UICONTROL Audience Manager]**.
1. Controllare le opzioni **[!UICONTROL Cookie Destinations Enabled]** e **[!UICONTROL URL Destinations Enabled]**. Queste opzioni consentono all’Edge Network di restituire alla pagina i tipi di destinazione Audience Manager.
1. Assicurarsi che **[!UICONTROL Enable XDM Flattened Fields]** sia disabilitato. Questa opzione disattiva la trasformazione automatica delle variabili di Analytics in segnali di Audience Manager. Questa opzione è progettata per mantenere la compatibilità con le versioni precedenti per gli utenti che hanno eseguito la migrazione a Web SDK prima che Edge Network trasformasse automaticamente i dati di Analytics in segnali Audience Manager.

   >[!NOTE]
   >
   >La migrazione al Web SDK con l&#39;opzione **[!UICONTROL Enabled XDM Flattened Fields]** abilitata richiede che tutti i dati necessari in Audience Manager formattati come XDM e tutte le caratteristiche Audience Manager che utilizzano prop, eVar o eventi vengano aggiornati per cercare dati in formato XDM. Adobe consiglia di lasciare questa opzione disattivata.


   ![Aggiungi servizio Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Selezionare **[!UICONTROL Save]** per salvare la configurazione dello stream di dati.

Il flusso di dati è ora pronto per ricevere e trasmettere dati ad Audience Manager. Prendi nota dell’ID dello stream di dati, in quanto questo ID è richiesto durante la configurazione del Web SDK nel codice.

+++

+++**3. Abilita le sincronizzazioni ID di terze parti e imposta l&#39;ID contenitore di Audience Manager**

1. Passa a [experience.adobe.com](https://experience.adobe.com) e accedi con le tue credenziali.
1. Utilizzare la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, selezionare **[!UICONTROL Datastreams]**.
1. Seleziona lo stream di dati creato durante la migrazione di Analytics al passaggio 1.
1. Seleziona **[!UICONTROL Edit]** nell&#39;angolo superiore destro della pagina di configurazione dello stream di dati.
1. Espandere il menu a discesa **[!UICONTROL Advanced Options]** e abilitare la funzionalità **[!UICONTROL Third Party ID Sync]** se non è già abilitata. Questa opzione comunica ad Edge Network di restituire le sincronizzazioni ID partner per i partner dati di Audience Manager e Experience Platform.

   ![Abilita sincronizzazione ID terze parti.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. Nella maggior parte dei casi è possibile lasciare vuoto il campo **[!UICONTROL Third Party ID Sync Container ID]**. Il valore predefinito sarà `0`. Tuttavia, se preferisci assicurarsi di utilizzare l’ID contenitore corretto, segui i passaggi successivi:
   * Apri una finestra del browser in modalità incognito o privata e passa a una pagina che fa parte della migrazione.
   * Utilizzare gli strumenti per gli sviluppatori del browser per filtrare la chiamata di rete a `dpm.demdex.net/id`. Questa chiamata verrà attivata solo sulla prima pagina di una prima visita, motivo per cui è necessario un browser in incognito o privato.
   * Visualizza il payload della richiesta. Se il parametro `d_nsid` è diverso da zero, copiarlo nel campo **[!UICONTROL Third Party ID Sync Container ID]**.

1. Selezionare **[!UICONTROL Save]**.

Il flusso di dati è ora pronto sia per inviare dati ad Audience Manager che per trasmettere le risposte di Audience Manager al Web SDK.

+++

+++**4. Aggiungi ID cliente alla mappa identità**

La maggior parte delle implementazioni di Audience Manager utilizza [regole di unione profili](../features/profile-merge-rules/merge-rules-overview.md) in scenari di personalizzazione tra dispositivi e per controllare quali segmenti i visitatori possono qualificarsi a seconda del loro stato di autenticazione (connesso o disconnesso). Le regole di unione profili richiedono l’invio ad Audience Manager di un identificatore di proprietà del cliente (ID del sistema di gestione delle relazioni con i clienti, numero account, ecc.) per ogni chiamata di raccolta dati dopo l’autenticazione. In precedenza, la funzione `setCustomerIDs` del servizio ID visitatore ([!DNL visitor.js]) veniva utilizzata per aggiungere gli ID cliente a ogni chiamata di raccolta dati di Analytics, che veniva quindi inoltrata ad Audience Manager.

Con il Web SDK, queste identità ora devono essere inviate ad Edge Network utilizzando un costrutto XDM speciale denominato [IdentityMap](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap).

Per passare correttamente le identità in una mappa di identità è necessario comprendere [gli spazi dei nomi di identità](https://experienceleague.adobe.com/it/docs/experience-platform/identity/features/namespaces) e considerare attentamente quali identità trasmettere, soprattutto quando si inviano dati a una sandbox di Experience Platform. [Questo articolo](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-21305) illustra queste considerazioni e istruzioni.

Dopo aver determinato le identità da trasmettere e quando, seguire le guide per l&#39;utilizzo dell&#39;[!UICONTROL Identity map] **[!UICONTROL Identity map]** [elemento dati](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map) all&#39;interno di Tags o impostarlo manualmente come descritto nella [panoramica dei dati delle identità](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/identity/overview) per allinearlo alla strategia di distribuzione di Web SDK.

+++

+++**5. (Facoltativo) Impostare il cookie `aam_uuid` di prime parti**

Una pratica standard per molti anni consisteva nell&#39;inserire l&#39;UUID di Audience Manager (il valore nel cookie demdex di terze parti) in un cookie di prima parte solitamente denominato `aam_uuid`.

Per impostare il cookie, è necessario immettere un nome di cookie nel campo **[!UICONTROL Name]** della sezione **[!UICONTROL Unique User ID Cookie]** dell&#39;estensione tag Analytics o nel campo `uuidCookie` durante la configurazione di `audienceManagementModule`. Anche se è comunemente configurato nel codice, il cookie è stato utilizzato raramente perché il valore UUID di Audience Manager è un identificatore specifico per il dispositivo e tra domini diversi utilizzato dalle piattaforme pubblicitarie e fornisce poco valore come identificatore di prima parte.

Se l&#39;implementazione richiede che il cookie `aam_uuid` continui a essere impostato dopo la migrazione al Web SDK, puoi recuperare l&#39;UUID di Audience Manager in due modi.

1. Ogni risposta dall&#39;[endpoint di interazione Edge Network](https://developer.adobe.com/data-collection-apis/docs/endpoints/interact/) contiene un payload con `id` nodi. Il nodo `id` del payload dello spazio dei nomi `CORE` contiene l&#39;UUID di Audience Manager.

2. Utilizzare il comando [getIdentity](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/getidentity) del Web SDK per recuperarlo. Utilizza lo spazio dei nomi `CORE` come descritto nella documentazione e recupera il valore dal campo `identity.CORE` nella risposta.

Indipendentemente dal metodo utilizzato per recuperare l’UUID di Audience Manager, spetta al team di sviluppo analizzare la risposta, recuperare l’UUID e impostare il cookie. Non esiste un modo automatico per impostare questo cookie tramite Web SDK.

+++

## Configurare Server-Side Forwarding e Audience Analytics nell’interfaccia utente di Analytics Report Suite Manager {#configure-ssf-analytics}

Se hai familiarità con la funzione di [inoltro lato server](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) di Analytics, potresti chiederti: &quot;*Disabilitare l&#39;impostazione di inoltro lato server nell&#39;interfaccia utente di Analytics Report Suite Manager per impedire l&#39;invio di dati Analytics ad Audience Manager due volte?*&quot;.

La risposta è no, non disabilitare questa impostazione per i motivi seguenti:

1. Quando il servizio Audience Manager è abilitato in un flusso di dati, Edge Network aggiunge la variabile `cm.ssf` a tutte le richieste di raccolta dati inviate ad Analytics. Questo impedisce l’invio dei dati di Analytics anche ad Audience Manager. Tutti i registri di Assurance utilizzati per convalidare la migrazione di Analytics mostreranno la variabile `cm.ssf=1` quando il servizio Audience Manager è abilitato nel flusso di dati. Per ulteriori dettagli, consulta la pagina dedicata alla conformità di [Analytics e RGPD sull&#39;inoltro lato server](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr).

1. Questa impostazione abilita anche il flusso di dati per l&#39;integrazione [!DNL Audience Analytics]. Come descritto nella [panoramica di Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam), per questa integrazione è necessario l&#39;inoltro lato server perché la risposta di Audience Manager al server di raccolta dati di Analytics viene aggiunta all&#39;hit di Analytics prima dell&#39;elaborazione. Un processo simile si verifica all’interno di Edge Network. Quando l’inoltro lato server è abilitato, Edge Network aggiunge i segmenti necessari dalla risposta di Audience Manager ai dati inviati ad Analytics.

In sintesi, è importante che questa impostazione rimanga abilitata in modo che Audience Analytics continui a funzionare con un’implementazione di Web SDK e che nessun dato venga conteggiato due volte in Audience Manager.

## Convalidare la migrazione {#validation}

Con tutte le soluzioni Adobe ora servite da una singola chiamata Web SDK, i passaggi per la convalida possono cambiare a seconda delle soluzioni servite da Web SDK.

Se Adobe Target o Adobe Journey Optimizer (incluso [!DNL Decisioning]) fanno parte dello stack di soluzioni gestito dall&#39;implementazione, nella pagina saranno presenti più chiamate di rete all&#39;Edge Network. Alcuni sono destinati al recupero di personalizzazioni e offerte, altri alla raccolta dati e al reporting.

Indipendentemente dall’implementazione, i principi generali riportati di seguito si applicano alla verifica del corretto flusso dei dati da e verso Audience Manager tramite Web SDK.

1. La prima chiamata di rete per un primo visitatore di prima pagina verrà effettuata al dominio `adobedc.demdex.net` e all&#39;endpoint `/interact`. Per visualizzare le chiamate di rete effettuate da Web SDK, aprire la scheda per sviluppatori nel browser Web, fare clic sulla scheda Rete e quindi filtrare `/interact`.
Esistono altri tipi di chiamate SDK Web, ma solo `interact` chiamate inviano dati a e ottengono un payload di risposta da Edge Network.

   ![Immagine di una scheda di rete del browser che mostra le chiamate di interazione.](assets/network.png)

1. La risposta alla prima chiamata di rete ha più payload. Uno di questi nodi del payload include diversi sottonodi di tipo `url`. Questi nodi `url` sono le sincronizzazioni ID di terze parti storicamente attivate dal servizio [!DNL Visitor ID]. Deve essere presente un nodo `url` per ogni sincronizzazione ID di terze parti configurata nel contenitore (vedi il passaggio 3 sopra).

   ![Immagine di una scheda di rete del browser che mostra i payload.](assets/payload.png)

   Inoltre, è possibile filtrare per `demdex` e rilevare che ciascuno degli URL a cui si fa riferimento nel payload ha generato una propria richiesta di rete per la sincronizzazione ID, proprio come ha fatto il servizio [!DNL Visitor ID]. Queste sincronizzazioni ID devono essere attivate solo sulla prima pagina di un nuovo visitatore e solo una volta ogni 14 giorni successivi.

1. Eventuali richieste `/interact` successive utilizzate per la raccolta dati di Analytics e Audience Manager devono contenere i nodi `data.__adobe.analytics` nel payload.

   ![Immagine di una scheda di rete del browser che mostra il nodo di Analytics nel payload.](assets/analytics-node.png)

   Le caratteristiche di Audience Manager che si basano su queste variabili di Analytics, nonché le caratteristiche che utilizzano le chiavi della piattaforma `h_` o `d_`, devono continuare a essere compilate.

   >[!TIP]
   >
   >È possibile creare una caratteristica di test con un&#39;espressione di regola che può essere espressa solo se i dati del Web SDK vengono raccolti. Poiché non esiste un ambiente Audience Manager di sviluppo e più siti potrebbero inviare dati alla stessa istanza di Audience Manager, solo l’analisi dei conteggi di popolazione complessivi potrebbe non fornire la convalida necessaria.

1. Nella stessa chiamata `/interact` in cui vengono passate le variabili Analytics, è possibile trovare qualsiasi cookie o destinazione URL nei nodi di payload della risposta. Le destinazioni URL si troveranno in payload di tipo `url` (come nelle sincronizzazioni ID di terze parti) e le destinazioni cookie si troveranno in payload di tipo `cookie`.

   ![Immagine di una scheda di rete del browser che mostra i dati del payload.](assets/destinations.png)

   Inoltre, accertati che i cookie siano stati inseriti nell’archivio dei cookie del browser.

   >[!TIP]
   >
   >Come nel passaggio di convalida precedente, l’idoneità di un segmento che deve restituire una destinazione cookie è un modo sicuro per garantire il flusso di dati da e verso Audience Manager.

1. Se devi passare ID cliente aggiuntivi tramite Identity Map, effettua l’autenticazione nel sito e assicurati che le identità e i relativi parametri associati vengano passati nel nodo Identity Map del payload della richiesta.

   ![Immagine di una scheda di rete del browser che mostra i dati di identityMap.](assets/pass-customer-ids.png)

   >[!TIP]
   >
   >Se Adobe Target è una delle soluzioni di ricezione e alcune attività di Target si basano su segmenti di Audience Manager che richiedono il passaggio dell&#39;identità corretta, assicurati che Identity Map sia passato nelle chiamate `/interact` utilizzate per recuperare personalizzazioni e non solo nelle chiamate di raccolta dati. Adobe Target utilizzerà tali identità nella chiamata lato server ad Audience Manager durante il recupero delle informazioni sui segmenti.

