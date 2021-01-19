---
description: Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza tramite la funzionalità Opt-in e il supporto del Transparency and Consent Framework (TCF) di IAB. In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager.
seo-description: Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza tramite la funzionalità Opt-in e il supporto del Transparency and Consent Framework (TCF) di IAB. In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager.
seo-title: Plug-in di Audience Manager per IAB TCF
solution: Audience Manager
title: Plug-in di Audience Manager per IAB TCF
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: ab72f0875b132eaf333d1e5308322490ac035de3
workflow-type: tm+mt
source-wordcount: '2449'
ht-degree: 40%

---


# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Panoramica

Un aspetto importante degli obblighi in materia di privacy che potresti avere nei confronti dei tuoi utenti è l&#39;acquisizione e la trasmissione delle scelte degli utenti su come i loro dati personali possono essere utilizzati (cioè, &quot;scopi&quot;) e da chi (cioè, &quot;aziende&quot;).

Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza tramite la [funzionalità Opt-in](https://docs.adobe.com/content/help/it-IT/id-service/using/implementation/opt-in-service/optin-overview.html) e il supporto del [Transparency and Consent Framework (TCF) di IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager.

>[!IMPORTANT]
>
> Audience Manager è registrato in [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) con l&#39;ID fornitore 565.

Il plug-in di Audience Manager per IAB TCF utilizza la [funzionalità Opt-in](https://docs.adobe.com/content/help/it-IT/id-service/using/implementation/opt-in-service/iab.html), che a sua volta fa parte della libreria [Servizio Experience Platform Identity (ECID)](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html).

## Ambito di applicazione e limitazioni {#scope-and-limitations}

In qualità di editore o inserzionista che lavora con Audience Manager, puoi trasmettere le scelte degli utenti ad Audience Manager secondo IAB TCF.

>[!IMPORTANT]
>
>I regolamenti IAB TCF si applicano solo ai visitatori situati nello Spazio economico europeo.

 Audience Manager ti aiuta a rispettare le scelte sulla privacy degli utenti e ti offre anche un modo semplice per comunicare queste scelte a tutti i partner con cui lavori.

Al momento, Audience Manager non supporta:

* Workflow di dispositivi mobili;
* Appendere il consenso per segmentare le esportazioni.

## Aggiornamento a [!DNL IAB TCF v2.0] {#upgrading}

I clienti che stanno aggiornando l&#39;implementazione [!DNL Audience Manager Plug-in for IAB TCF] da [!DNL IAB TCF] v1.1 a [!DNL IAB TCF] v2.0 o abilitando [!DNL IAB TCF] v2.0 per la prima volta, devono seguire tutte le stesse linee guida sui prerequisiti e l&#39;implementazione come descritto di seguito.

## Prerequisiti {#prerequisites}

>[!IMPORTANT]
>
> Audience Manager supporta IAB TCF v2.0.
>
>Il supporto per IAB TCF v1.1 terminerà il 15 agosto 2020.
>
> I clienti che desiderano continuare a utilizzare il plug-in del Audience Manager  per la gestione del consenso IAB devono effettuare l&#39;aggiornamento alla versione più recente di [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) per continuare a supportare.
>
> Dopo l&#39;aggiornamento alla versione più recente di [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases), le stringhe di consenso IAB TCF v1.1 non saranno più supportate, pertanto accertatevi di aggiornare il CMP prima di eseguire l&#39;aggiornamento alla versione più recente di ECID.

Per utilizzare il plug-in del Audience Manager  per IAB TCF con  Audience Manager, è necessario soddisfare i seguenti prerequisiti:

1. Devi usare la versione 5 o successiva dell’Adobe Experience Platform Identity Service (ECID). [Scarica](https://github.com/Adobe-Marketing-Cloud/id-service/releases) la versione di ECID più recente.
2. È necessario utilizzare  Audience Manager [!DNL Data Integration Library] (DIL) versione 9.0 o successiva, scaricabile da [qui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leggi informazioni sulla [DIL nella documentazione di Audience Manager](../../dil/dil-overview.md). È consigliabile utilizzare [ Adobe Launch](https://docs.adobe.com/content/help/it-IT/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) per l&#39;implementazione DIL più semplice per  Audience Manager.
3. In alternativa, se utilizzate [!DNL Server-Side Forwarding] (SSF) per importare dati in  Audience Manager, dovete eseguire l&#39;aggiornamento alla versione più recente di AppMeasurement. Scarica AppMeasurement tramite [Analytics Code Manager](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/code-manager-admin.html).
4. È necessario utilizzare una piattaforma di gestione del consenso (CMP), commerciale o propria, integrata con IAB TCF v2.0, registrata con lo IAB TCF. Consulta l’elenco delle [CMP registrate nel framework IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Se utilizzi una piattaforma di gestione del consenso (CMP) che non supporta IAB TCF v.2.0,  Audience Manager invierà automaticamente il parametro `gdpr=0` nelle sincronizzazioni ID, anche se i visitatori si trovano nell’Unione europea. Per determinare se la convalida GDPR è attiva, si consiglia di confermare con la piattaforma di gestione del consenso (CMP) che supporta IAB TCF v2.0.

## Raccomandazioni e modalità di implementazione {#recommendations}

Per abilitare il supporto IAB TCF in Audience Manager, consulta la nostra documentazione sulla [configurazione di IAB con Opt-in](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

Il modo più semplice per farlo è utilizzare [ Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) per aggiungere [!DNL ECID Opt-in] alle proprietà. Leggi la documentazione relativa all’[estensione Opt-in di ECID](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) per informazioni su come configurare l’estensione di Launch.

## Workflow di scelta dell’utente quando si utilizza il framework IAB {#user-choice-workflow}

Quando visitano una proprietà web, gli utenti possono scegliere in che modo i loro dati devono essere utilizzati dall’editore e dai fornitori di terze parti con cui lavora l’editore.

Gli utenti forniscono le loro scelte sotto forma di *consenso* e *interesse legittimo* ai fini dell&#39;IAB a *fornitori di terze parti* registrati nell&#39;elenco dei fornitori globali.

L’immagine seguente rappresenta un esempio di una finestra di dialogo CMP visualizzata da un utente che visita un sito web per la prima volta. Tieni presente che questa finestra di dialogo può avere un spetto molto diverso in base all’implementazione del cliente.

![Finestra di dialogo CMP](assets/cmp-example.png)

I dettagli sui vari scopi e autorizzazioni inclusi in IAB TCF v2.0 sono trattati nelle [Politiche di trasparenza e consenso di IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Gli utenti possono concedere il loro consenso o il loro interesse legittimo (se disponibile) per una combinazione di scopi e venditori. Ad esempio, gli utenti possono concedere il loro consenso per l&#39;archiviazione delle informazioni su un dispositivo, lo sviluppo e il miglioramento dei prodotti e concedere il loro consenso a tutti i fornitori di terze parti visualizzati dal CMP.

Oppure, in un altro esempio, possono concedere il loro consenso o il loro interesse legittimo per tutti gli scopi, ma solo concedere il consenso o il legittimo interesse ad alcuni dei venditori esposti dal CMP.

Una volta che l&#39;utente seleziona le proprie scelte sulla privacy, le scelte dell&#39;utente vengono registrate nella stringa TC IAB. La stringa IAB TC memorizza la combinazione di scopi e fornitori approvati, insieme ad altre informazioni sui metadati (per ulteriori informazioni, vedere la [pagina IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)).

Ogni fornitore registrato nell&#39;IAB TCF valuta la stringa IAB TC e prende decisioni in base alle scelte di privacy degli utenti. Tenere presente che le scelte relative alla privacy degli utenti sono valide per tutti i fornitori registrati presso IAB TCF.

## Finalità richieste dal Audience Manager  {#aam-standard-purposes}

 Audience Manager valuta le scelte degli utenti memorizzate nella stringa IAB TC per i seguenti scopi, definiti in [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes). Inoltre, è possibile trovare gli scopi nella [lista di fornitori globali](https://vendorlist.consensu.org/vendorlist.json).

* **Finalità 1**: Archiviare e/o accedere alle informazioni su un dispositivo;
* **Finalità 10**: Sviluppare e migliorare i prodotti;
* **Scopo speciale 1**: Protezione, prevenzione di frodi e debug.

>[!IMPORTANT]
>
> Audience Manager necessita del consenso per lo scopo 1 e lo scopo 10, più il consenso del fornitore, al fine di distribuire i cookie e avviare o onorare le sincronizzazioni ID.
>
>In base alle [normative IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), lo scopo speciale 1 (garantire la sicurezza, prevenire frodi e debug) è sempre consentito e gli utenti non possono obiettare.

## Il comportamento di Audience Manager dipende dalla concessione del consenso da parte dell’utente {#aam-behavior-consent}

 Audience Manager funziona in modo diverso a seconda che la stringa TC IAB includa o meno il consenso dell&#39;utente per i due scopi (memorizzare e/o accedere alle informazioni su un dispositivo, e sviluppare e migliorare i prodotti).

Controlliamo inoltre il consenso degli utenti per tutte le destinazioni con cui lavorate nel  Audience Manager, purché tali destinazioni siano registrate con IAB TCF.

| Quando l’utente *fornisce il consenso*, Audience Manager: | Quando l’utente *nega* il consenso, Audience Manager: |
|---|---|
| <ul><li>Esegue tutti i casi di utilizzo di Audience Manager richiesti.</li><li>Invia il consenso a terzi nelle sincronizzazioni ID (passando `gdpr = 1` e la stringa di consenso come `gdpr_consent` nelle chiamate di sincronizzazione ID).</li><li>Valuta e rispetta il consenso inviato da pixel di ad server.</li><li>Rispetta le sincronizzazioni ID avviate dai partner.</li></ul> | <ul><li>Non memorizza alcun nuovo dato utente nella tua istanza. Questo include ID partner, segnali, caratteristiche o dati pixel.</li><li>Non avvia sincronizzazioni ID di terze parti.</li><li>Non rispetta le sincronizzazioni ID avviate dai partner.</li><li>Rifiuta all&#39;utente di effettuare ulteriori raccolte di dati.</li></ul> |

## Caso di utilizzo degli editori {#publisher-use-case}

Implementando il plug-in del Audience Manager  per IAB TCF, non è necessario mantenere codice personalizzato per la gestione del consenso sulle proprietà Web tramite un meccanismo diverso con  Adobe o altri fornitori di terze parti. Il caso di utilizzo è descritto nell’immagine e nei passaggi seguenti. Inizia dalla parte sinistra dell’immagine:

1. Un utente visita una delle tue proprietà web. Se utilizzi le versioni più recenti delle librerie ECID e DIL (consulta [Prerequisiti](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), viene attivato il flusso di consenso.
2. Audience Manager controlla se il flusso IAB è applicabile (`isIabContext=true`). Consulta [Recommendations and how to implement](aam-iab-plugin.md#recommendations).
3.  Audience Manager verifica se il GDPR è applicabile (`gdpr = 1`) e se è presente un CMP registrato con IAB TCF nella proprietà Web. Ad esempio, questo vale per gli utenti che visitano dall&#39;Unione europea. È responsabilità dell&#39;editore impostare il flag GDPR.
4. Se GDPR si applica,  Audience Manager controlla la stringa IAB TC, passata nel parametro `gdpr_consent`, per il consenso richiesto.  Audience Manager necessita del consenso per l&#39;archiviazione e/o l&#39;accesso alle informazioni su un dispositivo ([IAB TCF purpose 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), lo sviluppo e il miglioramento di prodotti ([IAB TCF purpose 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), più  consenso del fornitore del Audience Manager a memorizzare, elaborare o attivare i dati.
5. Se la stringa IAB TC è presente e contiene il consenso richiesto,  Audience Manager trasmette la stringa IAB TC ai nostri [server di raccolta dati](../../reference/system-components/components-data-collection.md) (DCS).
6.  Audience Manager risponde impostando un [cookie demdex](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-am.html) nel browser e avvia e rispetta le sincronizzazioni ID di terze parti.
7. In alternativa, se la stringa TC IAB passata al punto 4 non contiene tutte le autorizzazioni necessarie,  Audience Manager non raccoglie, elabora o attiva dati utente e non rispetta né avvia sincronizzazioni ID. Inoltre, esclude l’utente dalle destinazioni con cui lavori.

>[!IMPORTANT]
>
>Se state lavorando con  partner di destinazione di Audience Manager che richiedono parametri IAB TCF, ma non disponete di un CMP che supporti IAB TCF sul sito Web,  Audience Manager invia `gdpr=0` nelle sincronizzazioni ID. Ciò significa che il GDPR non si applica a tali utenti.
>
> Se questo non è desiderato, è necessario abilitare la funzionalità IAB TCF in  Audience Manager per inviare le stringhe IAB TC appropriate ai partner di destinazione.



![Caso di utilizzo degli editori](assets/publisher-use-case.png)

## Caso di utilizzo degli inserzionisti {#advertiser-use-case}

Audience Manager valuta e rispetta il consenso trasmesso nelle [chiamate pixel](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), in conformità con IAB TCF.

I pixel possono essere posizionati dai clienti  Audience Manager sulle pagine del proprio partner o inseriti nei server di annunci da includere nella risposta dell&#39;annuncio. Nel primo caso, il partner deve recuperare in modo programmatico il parametro di consenso e aggiungerlo al pixel prima di iniziare. Nel secondo caso, più comune e descritto in dettaglio di seguito, gli ad server aggiungono a tutti i pixel i parametri di consenso ricevuti dalla piattaforma lato offerta (SSP, Supply-Side Platform) o dagli ad server dell’editore.

Audience Manager usa due parametri per trasmettere il consenso degli utenti nelle chiamate pixel:

* `gdpr` può essere 0 (non si applica il RGPD) o 1 (si applica il RGPD);
* `gdpr_consent` è la stringa di consenso RGPD con codifica URL-safe base64 (consulta le [specifiche](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Una chiamata di esempio per un pixel di impression con i due parametri potrebbe essere simile a quella riportata di seguito:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Il caso di utilizzo è descritto nell’immagine e nei passaggi seguenti. Inizia dalla parte sinistra dell’immagine:

1. L’utente riceve un’impression tramite un ad server. Ciò si traduce in una [chiamata pixel](../../integration/media-data-integration/impression-data-pixels.md) ai nostri Data Collection Servers (DCS).
2. Audience Manager controlla se è applicabile il flag RGPD. In caso contrario,  Audience Manager memorizza i dati passati nelle variabili `gdpr` e `gdpr_consent` nelle chiamate pixel.
3. Se la stringa TC IAB è presente e contiene le autorizzazioni richieste,  Audience Manager memorizza i dati passati nelle variabili `gdpr` e `gdpr_consent` nelle chiamate in pixel.
4. Se la stringa TC IAB è mancante o mancano le autorizzazioni richieste,  Audience Manager elimina i dati passati nelle variabili `gdpr` e `gdpr_consent` nelle chiamate in pixel.

![Caso di utilizzo degli inserzionisti](assets/advertiser-use-case.png)

## Partner di attivazione che supportano IAB TCF {#aam-activation-partners}

Il plug-in del Audience Manager  per IAB TCF consente di inoltrare la stringa IAB TC ai partner di attivazione rispettando le scelte di privacy degli utenti. Per informazioni su quali partner di attivazione supportano IAB TCF, consulta il nostro [elenco di destinazioni basate su dispositivi](/help/using/features/destinations/device-based-destinations-list.md).

## Aggiunta del consenso agli URL inviati alle destinazioni URL

L&#39;integrazione  Audience Manager con IAB TCF v2.0 supporta l&#39;aggiunta del consenso alle informazioni inviate a [destinazioni URL](../../features/destinations/create-url-destination.md) integrate con IAB TCF v2.0. Tuttavia, questo processo non viene eseguito automaticamente da  Audience Manager, per evitare di interrompere formati URL specifici.

I clienti che desiderano aggiungere il consenso ai dati inviati a [!DNL URL destinations] devono aggiungere manualmente le macro `${GDPR}` e `${GDPR_CONSENT_XXXX}` al proprio formato URL, sostituendo `XXXX` con l&#39;ID partner di destinazione.

Esempio: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Per ulteriori informazioni sulle macro di destinazione supportate, vedere [Macro di destinazione definite](../../features/destinations/destination-macros.md).

## Gestione del consenso tra dispositivi

Il plug-in del Audience Manager  per IAB TCF esclude automaticamente gli ID presenti su una richiesta, quando i visitatori del sito non forniscono le autorizzazioni appropriate. Se la richiesta contiene un [ID cross-device (CRM ID)](../../reference/ids-in-aam.md),  Audience Manager esclude l&#39;ID, insieme all&#39;ultimo dispositivo collegato a tale [ID cross-device (CRM ID)](../../reference/ids-in-aam.md).

## Testare l’implementazione IAB {#test-iab-implementation}

Per verificare di aver implementato correttamente il plug-in del Audience Manager  per IAB TCF, leggere [Caso d&#39;uso 4 in Convalida del servizio di consenso](https://docs.adobe.com/content/help/it-IT/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB e rinuncia in Audience Manager. Ordine di precedenza. {#iab-and-optout}

Un’altra opzione di privacy a disposizione degli utenti è la possibilità di rinunciare a tutte le attività di raccolta dati. Adobe fornisce agli utenti i mezzi per farlo all’interno della pagina relativa alle [scelte sulla privacy](https://www.adobe.com/it/privacy/opt-out.html#customeruse).

Audience Manager tratta le richieste di rinuncia in un [articolo separato nella nostra documentazione](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Gli utenti che rifiutano la raccolta dei dati dopo che rifiutano il consenso non possono essere riammessi.

>[!NOTE]
>
>**Ordine di precedenza**: se l’utente rinuncia alla raccolta dei dati utilizzando uno strumento di rinuncia globale, come descritto nel collegamento riportato sopra, questo ha la precedenza sulle verifiche di consenso e IAB.

## Risorse aggiuntive {#additional-resources}

* [Opt-in del servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB Europe RGPD Transparency and Consent Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe RGPD Transparency and Consent Framework Technical Specifications](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF plugin - video demonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)