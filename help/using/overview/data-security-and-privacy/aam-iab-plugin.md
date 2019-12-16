---
description: Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza, tramite la Funzionalità di consenso e il supporto del Transparency and Consent Framework (TCF) di IAB. In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager.
seo-description: Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza, tramite la Funzionalità di consenso e il supporto del Transparency and Consent Framework (TCF) di IAB. In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager.
seo-title: Plug-in di Audience Manager per IAB TCF
solution: Audience Manager
title: Plug-in di Audience Manager per IAB TCF
translation-type: tm+mt
source-git-commit: ff4bf70c9012f99289ea82824a552db97430fbf2

---


# Plug-in di Audience Manager per IAB TCF {#aam-iab-plugin}

## Panoramica

Un aspetto importante degli obblighi sulla riservatezza nei confronti degli utenti è l’acquisizione e la diffusione delle scelte utente su come (ad esempio, “scopo”) e da parte di chi (ad esempio, “aziende”) vengono utilizzati i dati personali. 

Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza, tramite la [Funzionalità di consenso](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) e il supporto del [Transparency and Consent Framework (TCF) di IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager. Audience Manager è registrato nell'IAB TCF con l'ID fornitore 565.

Il plug-in Audience Manager per IAB TCF utilizza la funzionalità [](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)di consenso, che a sua volta fa parte della libreria del servizio Adobe [Experience Cloud ID (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) .

## Ambito di applicazione e limitazioni {#scope-and-limitations}

In qualità di editore o inserzionista che lavora con Audience Manager, puoi trasmettere le scelte degli utenti ad Audience Manager in base a IAB TCF. Questo vi offre un modo semplice e coerente di comunicare le scelte degli utenti a tutti i partner con cui lavorate e Audience Manager può aiutarti a rispettare le scelte relative alla privacy degli utenti.

Il supporto IAB TCF descritto in questo articolo rappresenta la prima fase del supporto pianificato di Audience Manager per il framework IAB. Al momento, Audience Manager non supporta:

* Flussi di lavoro per dispositivi mobili;
* Gestione del consenso tra dispositivi;
* l’approvazione dell’approvazione degli URL inviati alle destinazioni [](../../features/destinations/create-url-destination.md)URL;
* Aggiunta del consenso ai segmenti.

## Prerequisiti {#prerequisites}

Per utilizzare lo IAB TCF con Audience Manager dovete soddisfare i seguenti prerequisiti:

1. Devi usare la versione 4.1 o successiva del servizio Experience Cloud ID. [Scarica](https://github.com/Adobe-Marketing-Cloud/id-service/releases) la versione più recente di ECID.
1. Devi utilizzare la libreria di integrazione dati di Audience Manager (DIL) versione 9.0 o successiva, scaricabile da [qui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leggi [DIL nella documentazione](../..//dil/dil-overview.md)di Audience Manager.
1. In alternativa, se utilizzate l'inoltro lato server (SSF) per importare dati in Audience Manager, dovete eseguire l'aggiornamento alla versione più recente di AppMeasurement. Scarica AppMeasurement tramite [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
1. È necessario utilizzare una piattaforma di gestione del consenso (CMP), commerciale o propria, che supporti la IAB TCF ed è registrata con la IAB TCF. Consultate l’elenco dei [CMP registrati nel framework](https://advertisingconsent.eu/cmp-list/)IAB.

## Raccomandazioni e modalità di implementazione {#recommendations}

Per abilitare il supporto IAB TCF in Audience Manager, consulta la nostra documentazione su [come configurare IAB con il consenso](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Ciò è più semplice grazie all'utilizzo di [Adobe Launch](https://docs.adobelaunch.com/) per lo strumento di consenso ECID sulle proprietà. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Flusso di lavoro di scelta dell’utente quando si utilizza il framework IAB {#user-choice-workflow}

Quando si visita una proprietà Web, gli utenti possono scegliere in che modo i loro dati devono essere utilizzati dall'editore e dai fornitori di terze parti con cui lavora l'editore. Gli utenti forniscono le proprie scelte sotto forma di finalità ** standard e autorizzazioni a fornitori *di* terze parti registrati nell'elenco dei fornitori globali. L’immagine seguente rappresenta un esempio di una finestra di dialogo CMP, visualizzata per la prima volta da un visitatore di un sito Web. Tieni presente che questa finestra di dialogo può essere molto diversa, in base all'implementazione del cliente.

![Finestra di dialogo CMP](assets/cmp.png)

Le finalità standard del quadro IAB sono:

* Archiviazione delle informazioni e accesso
* Personalizzazione
* Selezione, consegna e reporting di annunci
* Selezione, distribuzione e reporting dei contenuti
* Misurazione

Per una descrizione dei cinque scopi standard, fare riferimento alla pagina [delle specifiche del framework](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) IAB.

Gli utenti possono concedere il loro consenso per una combinazione di scopi e fornitori standard. Ad esempio, gli utenti possono concedere il loro consenso per lo storage, la personalizzazione e la misurazione e concedere il loro consenso a tutti i fornitori di terze parti visualizzati dal CMP. Oppure, in un altro esempio, possono concedere il loro consenso per tutti e cinque gli scopi standard, ma solo concedere il consenso ad alcuni dei venditori visualizzati dal CMP.

Una volta che l'utente seleziona le proprie scelte sulla privacy, le scelte dell'utente vengono registrate nella stringa di consenso IAB TCF. La stringa di consenso IAB TCF memorizza la combinazione di scopi approvati e fornitori, insieme ad altre informazioni sui metadati (vedere la pagina [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) IAB per ulteriori informazioni). Ogni fornitore registrato nell'IAB TCF valuta la stringa di consenso IAB TCF e prende decisioni in base alle scelte di privacy degli utenti. Tenere presente che le scelte relative alla privacy degli utenti sono valide per tutti i fornitori approvati.

## Finalità standard necessarie per Audience Manager {#aam-standard-purposes}

Audience Manager valuta le scelte degli utenti memorizzate nella stringa di consenso TFC IAB per:

* Archivio delle informazioni e accesso (ID scopo 1 nell'elenco [dei fornitori](https://vendorlist.consensu.org/vendorlist.json)globali)
* Personalizzazione (ID scopo 2)
* Misurazione (scopo ID 5)
* Il fornitore di Audience Manager acconsente a archiviare, elaborare o attivare i dati per un editore.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Il comportamento di Audience Manager dipende dal fatto che l'utente conceda o meno il consenso {#aam-behavior-consent}

Audience Manager funziona in modo diverso a seconda che Audience Manager rilevi o meno nella stringa di consenso IAB TCF che l'utente ha fornito il consenso per i tre scopi (archiviazione, personalizzazione, misurazione).

| Quando l'utente *fornisce il consenso*, Audience Manager: | Quando l'utente *rifiuta* il consenso, Audience Manager: |
|---|---|
| <ul><li>Esegue tutti i casi di utilizzo di Audience Manager richiesti.</li><li>Invia il consenso a terzi nelle sincronizzazioni ID (passando gdpr = 1 e la stringa di consenso come gdpr_consenso sulle chiamate di sincronizzazione ID).</li><li>Valuta e rispetta il consenso passato dai pixel del server di annunci.</li><li>Rispetta le sincronizzazioni ID avviate dai partner.</li></ul> | <ul><li>Non memorizza alcun nuovo dato utente nell'istanza. Questo include ID partner, segnali, caratteristiche o dati pixel.</li><li>Non avvia sincronizzazioni ID di terze parti.</li><li>Non rispetta le sincronizzazioni ID avviate dal partner.</li></ul> |

## Caso di utilizzo di Publisher {#publisher-use-case}

Implementando lo IAB TCF, non è necessario mantenere il codice personalizzato per la gestione del consenso sulle proprietà Web tramite un meccanismo diverso con Adobe o altri fornitori di terze parti. Il caso d’uso è descritto nell’immagine e nei passaggi seguenti. Iniziate da sinistra dell’immagine:

1. Un utente visita una delle proprietà Web dell’utente. Se si utilizzano le versioni più recenti delle librerie ECID e DIL (vedere [Prerequisiti](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), viene attivato il flusso di consenso.
2. Audience Manager controlla se il flusso IAB è applicabile (`isIabContext=true`). Consultate [Recommendations (Raccomandazioni e come implementarle](aam-iab-plugin.md#recommendations)).
3. Audience Manager controlla se il GDPR è applicabile (`gdpr = 1`) e se è presente un CMP registrato con IAB nella proprietà Web. Ad esempio, questo vale per gli utenti che visitano dall'area dell'Unione europea. È responsabilità dell'editore impostare il flag GDPR.
4. Se GDPR è applicabile, Audience Manager controlla la stringa di consenso IAB TCF, passata nel parametro `gdpr_consent`, per le autorizzazioni necessarie. Audience Manager necessita di autorizzazioni per l'archiviazione, la personalizzazione, la misurazione e il consenso del fornitore di Audience Manager per archiviare, elaborare o attivare i dati.
5. Se la stringa di consenso IAB TCF è presente e contiene le autorizzazioni richieste, Audience Manager trasmette la stringa di consenso IAB TCF ai nostri server [di raccolta](../../reference/system-components/components-data-collection.md) dati (DCS).
6. Audience Manager risponde impostando un cookie [demdex](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) sul browser. Audience Manager inoltre avvia e rispetta le sincronizzazioni ID di terze parti.
7. In alternativa, se la stringa di consenso IAB TCF passata nel passaggio 5 non contiene tutte le autorizzazioni necessarie, Audience Manager non raccoglie, elabora o attiva i dati e non rispetta o avvia sincronizzazioni ID.

![Caso di utilizzo di Publisher](assets/publisher-use-case.png)

## Caso di utilizzo dell'inserzionista {#advertiser-use-case}

Audience Manager valuta e rispetta il consenso passato nelle chiamate [in](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)pixel, in conformità con lo IAB TCF.

I pixel vengono generalmente posizionati dai clienti di Audience Manager sulle pagine del loro partner o vengono inseriti nei server di annunci da includere nella risposta dell’annuncio. Nel primo caso, il partner deve recuperare in modo programmatico il parametro di consenso e aggiungerlo al pixel prima di iniziare. Nel secondo caso, più comune e descritto in dettaglio di seguito, i server di annunci aggiungono i parametri di consenso ricevuti dai server di annunci dell'editore o della piattaforma di distribuzione (SSP) a tutti i pixel.

Audience Manager usa due parametri per trasmettere il consenso degli utenti nelle chiamate pixel:

* `gdpr` può essere 0 (non si applica il GDPR) o 1 (si applica il GDPR);
* `gdpr_consent` è la stringa di consenso GDPR con codifica URL-safe base64 (vedere [la specifica](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Una chiamata di esempio per un pixel di impression, con i due parametri potrebbe essere simile a quella riportata di seguito:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Il caso d’uso è descritto nell’immagine e nei passaggi seguenti. Iniziate da sinistra dell’immagine:

1. L'utente riceve un'impressione tramite un server di annunci. Questo si traduce in una chiamata in pixel ai nostri Data Collection Servers (DCS).
2. Audience Manager controlla se è valido il flag GDPR. In caso contrario, Audience Manager memorizza i dati passati nelle variabili delle macro nelle chiamate pixel.
3. Se la stringa di consenso è presente e contiene le autorizzazioni richieste, Audience Manager memorizza i dati passati nelle variabili delle macro nelle chiamate in pixel.
4. Se la stringa di consenso è mancante o mancano le autorizzazioni richieste, Audience Manager rilascia i dati passati nelle variabili delle macro nelle chiamate pixel.

![Caso di utilizzo dell'inserzionista](assets/advertiser-use-case.png)

## Partner di attivazione che supportano IAB TCF {#aam-activation-partners}

Il plug-in Audience Manager per IAB TCF consente di inoltrare la stringa di consenso IAB TCF ai partner di attivazione, nel rispetto delle scelte sulla privacy degli utenti. Per informazioni su quali partner di attivazione supportano IAB TCF, consultare il nostro **[Partner Excel sheet](/help/using/overview/data-security-and-privacy/assets/AAM-Partners-December2019.xlsx)**.

## Test dell’implementazione IAB {#test-iab-implementation}

Per verificare di aver implementato correttamente il plug-in Audience Manager per IAB TCF, leggi [Caso d’uso 4 in Metodi di convalida per l’implementazione](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)di tipoOpt-in e IAB.

## IAB e rinuncia in Audience Manager. Ordine di precedenza. {#iab-and-optout}

Un'altra opzione di privacy a disposizione degli utenti è la possibilità di rinunciare a tutte le attività di raccolta dei dati. Adobe fornisce agli utenti i mezzi per farlo all’interno della pagina [delle scelte](https://www.adobe.com/privacy/opt-out.html#customeruse) sulla privacy.

Audience Manager risolve le richieste di rifiuto in un articolo [separato nella nostra documentazione](data-privacy-requests.md).

>[!NOTE]
>
>**Ordine di precedenza** - Se l'utente rinuncia alla raccolta dei dati utilizzando uno strumento di rinuncia globale, come descritto nel collegamento precedente, questo ha la precedenza sulle verifiche opt-in e IAB.

## Risorse aggiuntive {#additional-resources}

* [Consenso del servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR Trasparenza e quadro di consenso](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR Trasparenza e Consenso Quadro Tecnico](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [plugin IAB TCF - dimostrazione video](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)