---
title: Aggiorna la libreria di raccolta dati, ad Audience Manager dalla libreria JavaScript di AppMeasurement alla libreria JavaScript dell’SDK per web.
description: Scopri i passaggi per aggiornare la libreria di raccolta dati, ad Audience Manager dalla libreria JavaScript di AppMeasurement alla libreria JavaScript dell’SDK Web.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: 3ba980e97763866d82bdf94109068f1f1f8f63d2
workflow-type: tm+mt
source-wordcount: '2398'
ht-degree: 0%

---


# Aggiorna la libreria di raccolta dati, ad Audience Manager dalla libreria JavaScript di AppMeasurement alla libreria JavaScript dell’SDK per web

## Pubblico previsto {#intended-audience}

Questa pagina è destinata ai clienti Adobe Analytics, ad Audience Manager, che utilizzano la libreria JavaScript [!DNL AppMeasurement] per inviare dati Web ad Audience Manager.

Fai riferimento alla tabella seguente per istruzioni sui passaggi di migrazione a Web SDK, a seconda del metodo di raccolta dati corrente.

| Il metodo di raccolta dati esistente | Istruzioni per la migrazione di Web SDK |
|---------|----------|
| Libreria JavaScript [!DNL AppMeasurement] | Seguire le istruzioni riportate in questa guida. |
| [!DNL Audience Manager] [estensione tag](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Segui le istruzioni contenute in [aggiornamento della libreria di raccolta dati dall&#39;estensione tag di Audience Manager all&#39;estensione tag Web SDK](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] libreria JavaScript + [!DNL Audience Manager] [libreria DIL](../dil/dil-overview.md) | Segui le istruzioni contenute in [aggiornamento della libreria di raccolta dati dall&#39;estensione tag di Audience Manager all&#39;estensione tag Web SDK](dil-extension-to-web-sdk.md). |

## Panoramica sulla migrazione {#overview}

La migrazione da [!DNL AppMeasurement] a [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) è principalmente una migrazione Adobe Analytics. Ad Audience Manager, i clienti di questa migrazione includono anche Audience Manager. È necessario migrare entrambi insieme. Se lavori principalmente con Audience Manager, assicurati di coinvolgere il team Analytics in questa migrazione.

Se utilizzi [!DNL AppMeasurement] per la raccolta dati di Audience Manager, stai utilizzando l&#39;approccio [!DNL Server-side Forwarding (SSF)] per inviare dati di Analytics ad Audience Manager. In questa configurazione, la richiesta di raccolta dati di Analytics viene inoltrata ad Audience Manager, che gestisce anche la risposta dell&#39;Audience Manager alla pagina.

Questo è stato l’approccio standard per molti anni ed è probabile che la tua configurazione corrente. Se la libreria [!DNL AppMeasurement] contiene il modulo `AudienceManagement` e le chiamate di raccolta dati includono il percorso `/10/` nella richiesta (`/b/ss/examplereportsuite/10/`), questa guida fa per te.

## Inoltro lato server (SSF) e flussi di dati dell’SDK per web {#data-flows}

Comprendere le differenze di flusso dei dati tra Analytics e Audience Manager durante il passaggio a Web SDK (e l’Edge Network) è fondamentale per le istruzioni di seguito.

Con l’inoltro lato server, il nodo di raccolta dati regionale di Analytics raccoglie i dati, li trasforma in un segnale accettato da Audience Manager, li invia ad Audience Manager e restituisce la risposta dell’Audience Manager alla pagina. Il modulo [!DNL AudienceManagement] nella libreria [!DNL AppMeasurement] gestisce quindi la risposta (ad esempio, l&#39;eliminazione di cookie e l&#39;invio di destinazioni URL). Questo processo è denominato inoltro lato server perché Analytics inoltra i dati ad Audience Manager utilizzando Adobe Server.

Con Web SDK, l’Edge Network invia i dati ad Analytics e l’Audience Manager in azioni separate. L’SDK per web è una singola libreria che invia dati a tutte le soluzioni e l’Edge Network trasforma i punti dati indipendenti dalle soluzioni in formati specifici della soluzione.

In questo nuovo flusso di dati, tutti i dati vengono inviati a un [flusso di dati](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview) di Edge Network, che puoi [configurare](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) per inviare i dati alle soluzioni Adobe in base alle esigenze. Ad Audience Manager, l&#39;abilitazione del servizio Audience Manager nel flusso di dati trasforma i dati [!DNL XDM] e Analytics in segnali accettati da Audience Manager. L&#39;Edge Network restituisce anche la risposta dell&#39;Audience Manager alla pagina, in cui Web SDK gestisce la risposta, in modo simile a come hanno fatto [!DNL AppMeasurement] e il modulo [!DNL AudienceManagement].

## Migrazione tag e non tag {#tags-vs-non-tags}

Che si utilizzino i tag con l&#39;estensione [!DNL AppMeasurement], la libreria [!DNL AppMeasurement] in un altro sistema di gestione dei tag o si inserisca [!DNL AppMeasurement] direttamente nella pagina, i passaggi per la migrazione di Audience Manager a Web SDK sono gli stessi. Poiché la migrazione di Audience Manager dipende dalla migrazione di Analytics, i passaggi per migrare da [!DNL AppMeasurement] a Web SDK sono determinati durante la migrazione di Analytics.

Queste informazioni sono trattate nella documentazione di Analytics per le implementazioni basate su [Tag](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) o [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk).

## XDM e i nodi `data.__adobe.` {#xdm-data-nodes}

Una delle funzioni principali di [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) consiste nell&#39;inviare dati a [Real-time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home). Per ottenere questo e raccogliere comunque i dati per altre soluzioni Experience Cloud senza una reimplementazione completa, i dati specifici della soluzione vengono suddivisi in compartimenti all’interno della chiamata al server di raccolta dati. Questa chiamata utilizza uno schema JSON standardizzato denominato [Experience Data Model (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Gli elementi indipendenti dalla soluzione, come le informazioni sul browser e sul dispositivo, vengono inviati all’Edge Network in una struttura XDM predeterminata. L’Edge Network trasforma questi dati in formati specifici della soluzione. Tuttavia, i dati specifici di Target, Analytics e Audience Manager vengono memorizzati in un nodo `data.__adobe` dedicato all’interno del payload XDM.

Ad esempio:

* La variabile di Analytics `s.eVar1` è rappresentata nel payload XDM come `data.__adobe.analytics.evar1`.
* Un parametro di Target relativo allo stato di fedeltà del cliente è memorizzato come `data.__adobe.target.loyaltyStatus`.

I dati nel nodo `__adobe` vengono inviati alle rispettive soluzioni (come Analytics e Audience Manager) senza essere inviati ad Experience Platform, anche se il servizio Experience Platform è abilitato nello stream di dati. Ciò significa che puoi mantenere le configurazioni correnti per Analytics e Audience Manager, avendo al tempo stesso la flessibilità di mappare eventuali elementi di dati necessari agli elementi dello schema XDM per casi d&#39;uso in tempo reale, in Experience Platform utilizzando [Preparazione dati per raccolta dati](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep).

La stringa Analytics `s.products`, ad esempio, utilizzata per segnalare il contenuto del carrello durante l&#39;estrazione, può ancora essere inviata ad Analytics e Audience Manager nel suo formato originale. Allo stesso tempo, puoi utilizzare gli elementi di questa stringa per creare schemi di carrello XDM più intuitivi, ad Experience Platform casi d’uso.

Poiché la maggior parte delle implementazioni di Audience Manager si basa sui dati di Analytics inoltrati ad Audience Manager, molte delle espressioni di caratteristiche di Audience Manager sono probabilmente basate sulle variabili di Analytics (`c_evar#`, `c_prop#` e `c_events`). Per evitare di ricostruire le espressioni di caratteristiche utilizzando i formati XDM durante la migrazione, per impostazione predefinita l’Edge Network è configurato per trasformare in segnali di Audience Manager tutte le variabili Analytics trovate nel nodo `data.__adobe.analytics`. Questo processo è simile al flusso di lavoro di inoltro lato server.

L’Edge Network può eseguire questa trasformazione perché una singola chiamata di raccolta dati dalla pagina viene inviata a un singolo flusso di dati che alimenta più soluzioni Adobe. Pertanto, la maggior parte delle migrazioni da [!DNL AppMeasurement] a Web SDK per Analytics e Audience Manager utilizzerà principalmente il nodo `data.__adobe.analytics`.

L’Edge Network trasforma i dati del dispositivo e del browser dalle intestazioni del payload e dei pacchetti XDM in segnali di Audience Manager. Ciò ti consente di continuare a utilizzare le chiavi della piattaforma `h_` e `d_` nelle espressioni con caratteristiche Audienci Manager.

## Nodo `data.__adobe.audiencemanager` {#data-note}

Il nodo `data.__adobe.audiencemanager` viene utilizzato per implementazioni di Audience Manager che non si basano su Analytics. Memorizza coppie chiave/valore di Audience Manager personalizzate che sono state precedentemente inviate tramite la libreria [DIL](../dil/dil-overview.md), come descritto nella [guida alla migrazione dell&#39;estensione tag](dil-extension-to-web-sdk.md).

Anche se il nodo `data.__adobe.audiencemanager` non è necessario per la migrazione descritta in questa guida, il nuovo flusso di dati qui spiegato consente di inviare dati ad Audience Manager senza registrarli in Analytics.

Se devi inviare una coppia chiave/valore personalizzata ad Audience Manager senza includerla in Analytics, puoi utilizzare il nodo `data.__adobe.audiencemanager`. Tutti i set di dati in questo nodo verranno aggiunti ai dati di Analytics trasformati dall’Audience Manager nella chiamata al server di raccolta dati.

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo di questo approccio alla migrazione presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Utilizza l&#39;implementazione esistente**: anche se questo approccio richiede alcune modifiche di implementazione, non richiede un&#39;implementazione completamente nuova da zero. Puoi utilizzare il livello dati e il codice esistenti con modifiche minime alla logica di implementazione.</li><li>**Non richiede uno schema**: per questa fase della migrazione all&#39;SDK Web, non è necessario uno schema XDM. È invece possibile popolare l&#39;oggetto `data`, che invia i dati direttamente ad Audience Manager. Una volta completata la migrazione all’SDK per web, puoi creare uno schema per la tua organizzazione e utilizzare la mappatura dello stream di dati per popolare i campi XDM applicabili. Se in questa fase del processo di migrazione fosse necessario uno schema, l’organizzazione sarebbe costretta a utilizzare uno schema XDM di Audience Manager. L’utilizzo di questo schema rende più difficile per l’organizzazione utilizzare il proprio schema in futuro.</li></ul> | <ul><li>**Debito tecnico per l&#39;implementazione**: poiché questo approccio utilizza una forma modificata dell&#39;implementazione esistente, può essere più difficile tenere traccia della logica di implementazione ed eseguire modifiche in futuro quando necessario.</li><li>**È necessaria la mappatura per inviare dati a Platform**: quando l&#39;organizzazione è pronta per utilizzare Real-Time CDP, è necessario inviare dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell&#39;oggetto `data` sia una voce nello strumento di mappatura dello stream di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita una sola volta per questo flusso di lavoro e non richiede l’apporto di modifiche all’implementazione. Si tratta tuttavia di un passaggio aggiuntivo non richiesto per l’invio di dati in un oggetto XDM.</li></ul> |

L’Adobe consiglia di seguire questo percorso di implementazione nei seguenti scenari:

* È disponibile un’implementazione esistente utilizzando la libreria JavaScript di Adobe Analytics AppMeasurement. Se disponi di un&#39;implementazione che utilizza l&#39;estensione tag Audience Manager, segui [Esegui migrazione dall&#39;estensione tag Audience Manager all&#39;estensione tag Web SDK](dil-extension-to-web-sdk.md).
* Intendi utilizzare Real-Time CDP in futuro, ma non desideri sostituire l’implementazione Audience Manager con un’implementazione Web SDK da zero. La sostituzione dell’implementazione da zero su Web SDK richiede il massimo impegno, ma offre anche l’architettura di implementazione a lungo termine più efficiente. Se la tua organizzazione è disposta a eseguire un&#39;implementazione pulita di Web SDK, consulta la [documentazione di Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) per ulteriori dettagli.

## Passaggi necessari per migrare a Web SDK

Segui i passaggi seguenti per migrare l’integrazione della raccolta dati a Web SDK.

+++**1. Esegui la migrazione dell&#39;implementazione di Analytics**.

Collabora con il tuo team di Analytics per seguire i passaggi per la migrazione ad Analytics nelle implementazioni basate su [Tag](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) o [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk). Dopo aver migrato l’implementazione di Analytics, continua con il passaggio seguente.

+++

+++**2. Aggiungi il servizio Audience Manager allo stream di dati**

Aggiungi il servizio Audience Manager allo stream di dati creato durante il passaggio 1.

1. Passa a [experience.adobe.com](https://experience.adobe.com) e accedi con le tue credenziali.
1. Utilizzare la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, selezionare **[!UICONTROL Datastreams]**.
1. Seleziona lo stream di dati creato durante la migrazione di Analytics al passaggio 1.
1. Selezionare **[!UICONTROL Add Service]**.
1. Nel menu a discesa del servizio, selezionare **[!UICONTROL Audience Manager]**.
1. Controllare le opzioni **[!UICONTROL Cookie Destinations Enabled]** e **[!UICONTROL URL Destinations Enabled]**. Queste opzioni consentono all’Edge Network di restituire alla pagina i tipi di destinazione dell’Audience Manager.
1. Assicurarsi che **[!UICONTROL Enable XDM Flattened Fields]** sia disabilitato. Questa opzione disattiva la trasformazione automatica delle variabili di Analytics in segnali di Audience Manager. Questa opzione è progettata per mantenere la compatibilità con le versioni precedenti per gli utenti che hanno eseguito la migrazione a Web SDK prima che l’Edge Network trasformasse automaticamente i dati di Analytics in segnali di Audience Manager.

   >[!NOTE]
   >
   >La migrazione a Web SDK con l&#39;opzione **[!UICONTROL Enabled XDM Flattened Fields]** abilitata richiede che tutti i dati necessari in Audience Manager formattati come XDM e tutte le caratteristiche Audience Manager che utilizzano prop, eVar o eventi vengano aggiornati per cercare dati in formato XDM. Adobe consiglia di lasciare questa opzione disattivata.


   ![Aggiungi servizio Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Selezionare **[!UICONTROL Save]** per salvare la configurazione dello stream di dati.

Il flusso di dati è ora pronto per ricevere e trasmettere i dati ad Audience Manager. Prendi nota dell’ID dello stream di dati, in quanto questo ID è richiesto durante la configurazione dell’SDK web nel codice.

+++

+++**3. Abilita sincronizzazioni ID di terze parti e imposta l&#39;ID contenitore Audience Manager**

1. Passa a [experience.adobe.com](https://experience.adobe.com) e accedi con le tue credenziali.
1. Utilizzare la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, selezionare **[!UICONTROL Datastreams]**.
1. Seleziona lo stream di dati creato durante la migrazione di Analytics al passaggio 1.
1. Seleziona **[!UICONTROL Edit]** nell&#39;angolo superiore destro della pagina di configurazione dello stream di dati.
1. Espandere il menu a discesa **[!UICONTROL Advanced Options]** e abilitare la funzionalità **[!UICONTROL Third Party ID Sync]** se non è già abilitata. Questa opzione comunica all’Edge Network di restituire le sincronizzazioni ID partner, ad Audience Manager i partner dati di Experience Platform.

   ![Abilita sincronizzazione ID terze parti.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. Nella maggior parte dei casi è possibile lasciare vuoto il campo **[!UICONTROL Third Party ID Sync Container ID]**. Il valore predefinito sarà `0`. Tuttavia, se preferisci assicurarsi di utilizzare l’ID contenitore corretto, segui i passaggi successivi:
   * Apri una finestra del browser in modalità incognito o privata e passa a una pagina che fa parte della migrazione.
   * Utilizzare gli strumenti per gli sviluppatori del browser per filtrare la chiamata di rete a `dpm.demdex.net/id`. Questa chiamata verrà attivata solo sulla prima pagina di una prima visita, motivo per cui è necessario un browser in incognito o privato.
   * Visualizza il payload della richiesta. Se il parametro `d_nsid` è diverso da zero, copiarlo nel campo **[!UICONTROL Third Party ID Sync Container ID]**.

1. Selezionare **[!UICONTROL Save]**.

Il flusso di dati è ora pronto sia per inviare dati ad Audience Manager che per trasmettere le risposte di Audience Manager all’SDK per web.

+++

## Configurare Server-Side Forwarding e l’Audience Analytics nell’interfaccia utente di Analytics Report Suite Manager {#configure-ssf-analytics}

Se hai familiarità con la funzione di [inoltro lato server](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) di Analytics, potresti chiederti: &quot;*Disabilitare l&#39;impostazione di inoltro lato server nell&#39;interfaccia utente di Analytics Report Suite Manager per impedire l&#39;invio di dati di Analytics ad Audience Manager due volte?*&quot;.

La risposta è no, non disabilitare questa impostazione. Ecco il motivo:

Quando questa impostazione è abilitata e il modulo [!DNL AudienceManagement] viene aggiunto alla libreria [!DNL AppMeasurement] della pagina, anche tutti i dati inviati a tale suite di rapporti verranno trasmessi a Audience Manager.

Per rispettare le normative sulla privacy del RGPD, esistono scenari in cui i dati possono essere raccolti in Analytics ma non in Audience Manager. Inoltre, in alcuni casi coinvolgono suite di rapporti globali e casi d’uso specifici per area geografica, alcune chiamate di raccolta dati non devono essere inviate ad Audience Manager. Per risolvere questo problema, Adobe ha introdotto un &quot;pulsante off&quot; per l’inoltro lato server.

Come spiegato nella pagina di conformità di [Analytics e RGPD incentrata sull&#39;inoltro lato server](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr), l&#39;aggiunta della variabile di contesto `cm.ssf=1` a un server di raccolta dati di Analytics impedisce l&#39;inoltro della chiamata di raccolta dati a Audience Manager.

Per due motivi è consigliabile non disattivare questa impostazione.

1. Quando il servizio Audience Manager è abilitato in un flusso di dati, l&#39;Edge Network aggiunge la variabile `cm.ssf` a tutte le richieste di raccolta dati inviate ad Analytics. Questo impedisce l’invio dei dati di Analytics anche ad Audience Manager. Tutti i registri di Assurance utilizzati per convalidare la migrazione di Analytics mostreranno la variabile `cm.ssf=1` quando il servizio Audience Manager è abilitato nello stream di dati.
1. Questa impostazione abilita anche il flusso di dati per l&#39;integrazione [!DNL Audience Analytics]. Come descritto nell&#39;[panoramica dell&#39;Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam), per questa integrazione è necessario l&#39;inoltro lato server perché la risposta dell&#39;Audience Manager al server di raccolta dati di Analytics viene aggiunta all&#39;hit di Analytics prima dell&#39;elaborazione. Un processo simile si verifica all’interno dell’Edge Network. Quando l’inoltro lato server è abilitato, l’Edge Network aggiunge i segmenti necessari dalla risposta dell’Audience Manager ai dati inviati ad Analytics.

In sintesi, è importante che questa impostazione rimanga abilitata in modo che Audience Analytics continui a funzionare con un’implementazione dell’SDK web e che nessun dato venga conteggiato due volte in Audience Manager.
