---
description: Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza tramite la funzionalità Opt-in e il supporto del Transparency and Consent Framework (TCF) di IAB. In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager.
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: Plug-in di Audience Manager per IAB TCF
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '2367'
ht-degree: 34%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Panoramica

Un aspetto importante degli obblighi sulla privacy che puoi avere nei confronti degli utenti è l’acquisizione e la trasmissione delle scelte degli utenti su come i loro dati personali possono essere utilizzati (ad esempio, &quot;scopi&quot;) e da chi (ad esempio, &quot;aziende&quot;).

Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza tramite la [funzionalità Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) e il supporto del [Transparency and Consent Framework (TCF) di IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager.

>[!IMPORTANT]
>
>L’Audience Manager è registrato in [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) con l’ID fornitore 565.

Il plug-in di Audience Manager per IAB TCF utilizza la [funzionalità Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html), che a sua volta fa parte della libreria [Servizio Experience Platform Identity (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html).

## Ambito di applicazione e limitazioni {#scope-and-limitations}

In qualità di editore o inserzionista che lavora con Audience Manager, puoi trasmettere le scelte degli utenti ad Audience Manager secondo IAB TCF.

>[!IMPORTANT]
>
>I regolamenti IAB TCF si applicano solo ai visitatori che si trovano nello Spazio economico europeo.

Audience Manager ti aiuta a rispettare le scelte sulla privacy degli utenti e ti offre anche un modo semplice per comunicare queste scelte a tutti i partner con cui lavori.

Al momento, Audience Manager non supporta:

* Workflow di dispositivi mobili;
* Aggiunta del consenso alle esportazioni dei segmenti.

## Aggiornamento a [!DNL IAB TCF v2.0] {#upgrading}

Clienti che stanno aggiornando il loro [!DNL Audience Manager Plug-in for IAB TCF] implementazione da [!DNL IAB TCF] da v1.1 a [!DNL IAB TCF] v2.0 o abilitazione [!DNL IAB TCF] v2.0 per la prima volta, tutti devono seguire le stesse linee guida sui prerequisiti e sull’implementazione, come descritto di seguito.

## Prerequisiti {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager supporta IAB TCF v2.0.
>
>Il supporto IAB TCF v1.1 terminerà il 15 agosto 2020.
>
> I clienti che desiderano continuare a utilizzare il plug-in Audience Manager per IAB TCF per la gestione del consenso devono effettuare l’aggiornamento alla versione più recente di [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) per un supporto continuo.
>
> Dopo l&#39;aggiornamento alla versione più recente [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) versione, le stringhe di consenso IAB TCF v1.1 non saranno più supportate, quindi assicurati di aggiornare la CMP prima di eseguire l’aggiornamento alla versione ECID più recente.

Per utilizzare il plug-in Audience Manager per IAB TCF è necessario soddisfare i seguenti prerequisiti con Audience Manager:

1. Devi usare la versione 5 o successiva dell’Adobe Experience Platform Identity Service (ECID). [Scarica](https://github.com/Adobe-Marketing-Cloud/id-service/releases) la versione di ECID più recente.
2. Devi usare Audience Manager [!DNL Data Integration Library] (DIL) versione 9.0 o successiva, scaricabile da [qui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leggi informazioni sulla [DIL nella documentazione di Audience Manager](../../dil/dil-overview.md). È consigliabile utilizzare [Estensione tag Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) per la più semplice implementazione DIL di Audience Manager.
3. In alternativa, se utilizzi [!DNL Server-Side Forwarding] (SSF) per importare dati in Audience Manager, devi eseguire l’aggiornamento alla versione più recente di AppMeasurement. Scarica AppMeasurement tramite [Analytics Code Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).
4. Devi utilizzare una piattaforma di gestione del consenso (CMP), commerciale o tua, integrata con IAB TCF v2.0 e registrata con IAB TCF. Consulta l’elenco delle [CMP registrate nel framework IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Se utilizzi una piattaforma di gestione del consenso (CMP) che non supporta IAB TCF v.2.0, Audience Manager invierà automaticamente il `gdpr=0` nelle sincronizzazioni ID, anche se i visitatori si trovano nell&#39;Unione Europea. Per determinare se la convalida RGPD è attiva, ti consigliamo di confermare con la tua piattaforma di gestione dei consensi (CMP) che supporta IAB TCF v2.0.

## Raccomandazioni e modalità di implementazione {#recommendations}

Per abilitare il supporto IAB TCF in Audience Manager, consulta la nostra documentazione sulla [configurazione di IAB con Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html).

Il modo più semplice per farlo è utilizzare [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) da aggiungere [!DNL ECID Opt-in] nelle proprietà. Leggi la documentazione di [Estensione Opt-in di ECID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) per scoprire come impostare l’estensione Tag.

## Workflow di scelta dell’utente quando si utilizza il framework IAB {#user-choice-workflow}

Quando visitano una proprietà web, gli utenti possono scegliere in che modo i loro dati devono essere utilizzati dall’editore e dai fornitori di terze parti con cui lavora l’editore.

Gli utenti forniscono le proprie scelte sotto forma di *consenso* e *interesse legittimo* ai fini di IAB: *fornitori di terze parti* registrati nell&#39;elenco globale dei fornitori.

L’immagine seguente rappresenta un esempio di una finestra di dialogo CMP visualizzata da un utente che visita un sito web per la prima volta. Tieni presente che questa finestra di dialogo può avere un spetto molto diverso in base all’implementazione del cliente.

![Finestra di dialogo CMP](assets/cmp-example.png)

I dettagli sulle varie finalità e autorizzazioni incluse in IAB TCF v2.0 sono trattati nel [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Gli utenti possono concedere il loro consenso o legittimo interesse (se disponibile) per una combinazione di finalità e fornitori. Ad esempio, gli utenti possono concedere il proprio consenso per la memorizzazione di informazioni su un dispositivo, lo sviluppo e il miglioramento di prodotti, e a tutti i fornitori di terze parti visualizzati dalla CMP.

Oppure, in un altro esempio, possono concedere il loro consenso o legittimo interesse per tutti gli scopi, ma solo il consenso o legittimo interesse ad alcuni dei venditori visualizzati dalla CMP.

Una volta che l’utente seleziona le proprie scelte sulla privacy, queste vengono registrate nella stringa TC IAB. La stringa TC IAB memorizza la combinazione di finalità e fornitori approvati, insieme ad altre informazioni sui metadati (vedi [Pagina IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) per ulteriori informazioni).

Ogni fornitore registrato in IAB TCF valuta la stringa TC IAB e prende decisioni in base alle scelte di privacy degli utenti. Tieni presente che le scelte relative alla privacy degli utenti sono valide per tutti i fornitori registrati con IAB TCF.

## Finalità richieste dall’Audience Manager {#aam-standard-purposes}

Audience Manager valuta le scelte degli utenti memorizzate nella stringa TC IAB per le seguenti finalità, definite nella [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Scopo 1**: memorizzare e/o accedere alle informazioni su un dispositivo;
* **Finalità 10**: sviluppare e migliorare i prodotti;
* **Uso speciale 1**: assicurati la sicurezza, evita le frodi ed esegui il debug.

>[!IMPORTANT]
>
>Per distribuire i cookie e avviare oppure rispettare le sincronizzazioni degli ID, Audience Manager richiede il consenso per Scopo 1, Scopo 10 e il consenso del fornitore.
>
>Per [Regolamenti IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), Special Purpose 1 (garantire la sicurezza, prevenire le frodi ed eseguire il debug) è sempre consentito e gli utenti non possono opporsi.

## Il comportamento di Audience Manager dipende dalla concessione del consenso da parte dell’utente {#aam-behavior-consent}

L’Audience Manager funziona in modo diverso a seconda che la stringa TC IAB includa o meno il consenso dell’utente per le due finalità (archiviare e/o accedere alle informazioni su un dispositivo e sviluppare e migliorare i prodotti).

Verifichiamo anche la presenza del consenso degli utenti per tutte le destinazioni con cui lavori in Audience Manager, purché tali destinazioni siano registrate con IAB TCF.

| Quando l’utente *fornisce il consenso*, Audience Manager: | Quando l’utente *nega* il consenso, Audience Manager: |
|---|---|
| <ul><li>Esegue tutti i casi di utilizzo di Audience Manager richiesti.</li><li>Trasmette il consenso a terze parti nelle sincronizzazioni ID (passando `gdpr = 1` e la stringa di consenso come `gdpr_consent` sulle chiamate di sincronizzazione ID).</li><li>Valuta e rispetta il consenso inviato da pixel di ad server.</li><li>Rispetta le sincronizzazioni ID avviate dai partner.</li></ul> | <ul><li>Non memorizza alcun nuovo dato utente nella tua istanza. Questo include ID partner, segnali, caratteristiche o dati pixel.</li><li>Non avvia sincronizzazioni ID di terze parti.</li><li>Non rispetta le sincronizzazioni ID avviate dai partner.</li><li>Rinuncia all’utente da ulteriori raccolte di dati.</li></ul> |

## Caso di utilizzo degli editori {#publisher-use-case}

Implementando il plug-in Audience Manager per IAB TCF, non è necessario mantenere un codice personalizzato per la gestione del consenso nelle proprietà web tramite un meccanismo diverso con Adobe o altri fornitori di terze parti. Il caso di utilizzo è descritto nell’immagine e nei passaggi seguenti. Inizia dalla parte sinistra dell’immagine:

1. Un utente visita una delle tue proprietà web. Se utilizzi le versioni più recenti delle librerie ECID e DIL (consulta [Prerequisiti](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), viene attivato il flusso di consenso.
2. Audience Manager controlla se il flusso IAB è applicabile (`isIabContext=true`). Consulta [Recommendations and how to implement](aam-iab-plugin.md#recommendations).
3. Audience Manager controlla se il RGPD è applicabile (`gdpr = 1`) e se è presente una CMP registrata con IAB TCF nella tua proprietà web. Ad esempio, ciò si applicherebbe agli utenti che visitano dall’Unione europea. In qualità di editore, sei responsabile dell’impostazione del flag RGPD.
4. Se il RGPD è applicabile, Audience Manager controlla la stringa TC IAB, passata nel `gdpr_consent` per il consenso richiesto. L&#39;Audience Manager necessita del consenso per archiviare e/o accedere alle informazioni su un dispositivo ([Scopo 1 del TCF IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), sviluppo e miglioramento dei prodotti ([Scopo IAB TCF 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), oltre al consenso del fornitore Audience Manager per archiviare, elaborare o attivare i dati.
5. Se la stringa TC IAB è presente e contiene il consenso richiesto, Audience Manager trasmette la stringa TC IAB al nostro [server di raccolta dati](../../reference/system-components/components-data-collection.md) (DCS)
6. L’Audience Manager risponde impostando un [cookie demdex](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) sul browser, e avvia e rispetta le sincronizzazioni ID di terze parti.
7. In alternativa, se la stringa TC IAB passata nel passaggio 4 non contiene tutte le autorizzazioni necessarie, Audience Manager non raccoglie, elabora o attiva dati utente e non rispetta o avvia sincronizzazioni ID. Inoltre, rinuncia all’utente dalle destinazioni con cui lavori.

>[!IMPORTANT]
>
>Se lavori con partner di destinazione Audience Manager che richiedono parametri IAB TCF, ma non disponi di una CMP che supporta IAB TCF sul tuo sito web, allora Audience Manager invia `gdpr=0` nelle sincronizzazioni ID. Ciò significa che il RGPD non si applica a tali utenti.
>
> Se non lo desideri, abilita la funzionalità IAB TCF in Audience Manager per inviare le stringhe IAB TC appropriate ai partner di destinazione.



![Caso di utilizzo degli editori](assets/publisher-use-case.png)

## Caso di utilizzo degli inserzionisti {#advertiser-use-case}

Audience Manager valuta e rispetta il consenso trasmesso nelle [chiamate pixel](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), in conformità con IAB TCF.

I pixel possono essere inseriti dai clienti Audience Manager sulle pagine dei loro partner o negli ad server da includere nella risposta dell’annuncio. Nel primo caso, il partner deve recuperare in modo programmatico il parametro di consenso e aggiungerlo al pixel prima di iniziare. Nel secondo caso, più comune e descritto in dettaglio di seguito, gli ad server aggiungono a tutti i pixel i parametri di consenso ricevuti dalla piattaforma lato offerta (SSP, Supply-Side Platform) o dagli ad server dell’editore.

Audience Manager usa due parametri per trasmettere il consenso degli utenti nelle chiamate pixel:

* `gdpr` può essere 0 (non si applica il RGPD) o 1 (si applica il RGPD);
* `gdpr_consent` è la stringa di consenso RGPD con codifica URL-safe base64 (consulta le [specifiche](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Una chiamata di esempio per un pixel di impression con i due parametri potrebbe essere simile a quella riportata di seguito:

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Il caso di utilizzo è descritto nell’immagine e nei passaggi seguenti. Inizia dalla parte sinistra dell’immagine:

1. L’utente riceve un’impression tramite un ad server. Questo si traduce in un [chiamata pixel](../../integration/media-data-integration/impression-data-pixels.md) ai nostri server di raccolta dati (DCS, Data Collection Servers).
2. Audience Manager controlla se è applicabile il flag RGPD. In caso contrario, Audience Manager memorizza i dati trasmessi nel `gdpr` e `gdpr_consent` variabili nelle chiamate pixel.
3. Se la stringa TC IAB è presente e contiene le autorizzazioni richieste, Audience Manager memorizza i dati trasmessi in `gdpr` e `gdpr_consent` variabili nelle chiamate pixel.
4. Se la stringa TC IAB manca o non dispone delle autorizzazioni necessarie, Audience Manager rilascia i dati trasmessi nel `gdpr` e `gdpr_consent` variabili nelle chiamate pixel.

![Caso di utilizzo degli inserzionisti](assets/advertiser-use-case.png)

## Partner di attivazione che supportano IAB TCF {#aam-activation-partners}

Il plug-in di Audience Manager per IAB TCF consente di inoltrare la stringa TC IAB ai partner di attivazione nel rispetto delle scelte sulla privacy degli utenti. Per informazioni su quali partner di attivazione supportano IAB TCF, consulta il nostro [elenco di destinazioni basate su dispositivi](/help/using/features/destinations/device-based-destinations-list.md).

## Aggiunta del consenso agli URL inviati alle destinazioni URL

L’integrazione di Audience Manager con IAB TCF v2.0 supporta l’aggiunta del consenso alle informazioni inviate a [Destinazioni URL](../../features/destinations/create-url-destination.md) integrati con IAB TCF v2.0. Tuttavia, questo processo non viene eseguito automaticamente da Audience Manager, per evitare di interrompere formati URL specifici.

Clienti che desiderano aggiungere il consenso ai dati inviati a [!DNL URL destinations] deve aggiungere manualmente `${GDPR}` e `${GDPR_CONSENT_XXXX}` macro nel relativo formato URL, sostituzione `XXXX` con l’ID partner di destinazione.

Esempio: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Consulta [Definizione delle macro di destinazione](../../features/destinations/destination-macros.md) per ulteriori dettagli sulle macro di destinazione supportate.

## Gestione del consenso tra dispositivi

Il plug-in di Audience Manager per IAB TCF rifiuta automaticamente gli ID presenti in una richiesta quando i visitatori del sito non forniscono le autorizzazioni appropriate. Se la richiesta contiene un [ID multi-dispositivo (CRM ID)](../../reference/ids-in-aam.md), Audience Manager rinuncia all’ID insieme all’ultimo dispositivo collegato a tale [ID multi-dispositivo (CRM ID)](../../reference/ids-in-aam.md).

## Testare l’implementazione IAB {#test-iab-implementation}

Per verificare di aver implementato correttamente il plug-in Audience Manager per IAB TCF, leggi [Caso d&#39;uso 4: convalida del servizio Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB e rinuncia in Audience Manager. Ordine di precedenza. {#iab-and-optout}

Un’altra opzione di privacy a disposizione degli utenti è la possibilità di rinunciare a tutte le attività di raccolta dati. Adobe fornisce agli utenti i mezzi per farlo all’interno della pagina relativa alle [scelte sulla privacy](https://www.adobe.com/it/privacy/opt-out.html#customeruse).

Audience Manager tratta le richieste di rinuncia in un [articolo separato nella nostra documentazione](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Gli utenti che hanno rinunciato a tutte le attività di raccolta dati dopo aver rifiutato il consenso non possono essere esclusi.

>[!NOTE]
>
>**Ordine di precedenza**: se l’utente rinuncia alla raccolta dei dati utilizzando uno strumento di rinuncia globale, come descritto nel collegamento riportato sopra, questo ha la precedenza sulle verifiche di consenso e IAB.

## Risorse aggiuntive {#additional-resources}

* [Opt-in del servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB Europe RGPD Transparency and Consent Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe RGPD Transparency and Consent Framework Technical Specifications](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF plugin - video demonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
