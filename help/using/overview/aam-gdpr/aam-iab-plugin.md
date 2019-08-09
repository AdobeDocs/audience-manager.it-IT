---
description: Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza, tramite la Funzionalità di consenso e il supporto del Transparency and Consent Framework (TCF) di IAB. In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager.
seo-description: Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza, tramite la Funzionalità di consenso e il supporto del Transparency and Consent Framework (TCF) di IAB. In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager.
seo-title: Plug-in di Audience Manager per IAB TCF
solution: Audience Manager
title: Plug-in di Audience Manager per IAB TCF
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Plug-in di Audience Manager per IAB TCF {#aam-iab-plugin}

## Panoramica

Un aspetto importante degli obblighi sulla riservatezza nei confronti degli utenti è l’acquisizione e la diffusione delle scelte utente su come (ad esempio, “scopo”) e da parte di chi (ad esempio, “aziende”) vengono utilizzati i dati personali. 

Adobe consente di gestire e comunicare le scelte degli utenti in materia di riservatezza, tramite la [Funzionalità di consenso](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) e il supporto del [Transparency and Consent Framework (TCF) di IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

In questo articolo vengono descritti i casi di utilizzo di Audience Manager che supportano IAB TCF e come implementare tale supporto in Audience Manager. Audience Manager è registrato nell'IAB TCF con l'ID fornitore 565.

Il plug-in Audience Manager per IAB TCF utilizza la [funzionalità di consenso](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), che a sua volta fa parte della libreria Adobe [Experience Cloud ID (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) .

## Ambito e limitazioni {#scope-and-limitations}

In qualità di Editore o Advertiser che lavora con Audience Manager, potete trasmettere le scelte degli utenti ad Audience Manager come a IAB TCF. Questo offre un modo semplice e coerente per comunicare le scelte degli utenti a tutti i partner con cui lavorate e Audience Manager può aiutarti a rispettare le scelte sulla privacy degli utenti.

Il supporto IAB TCF descritto in questo articolo rappresenta la prima fase nel supporto pianificato di Audience Manager per il framework IAB. Attualmente Audience Manager non supporta:

* Flussi di lavoro per dispositivi mobili;
* Gestione del consenso tra dispositivi;
* Aggiunta del consenso agli URL inviati alle [destinazioni URL](/help/using/features/destinations/create-url-destination.md);
* Aggiunta del consenso ai segmenti.

## Prerequisiti {#prerequisites}

Per utilizzare l'IAB TCF con Audience Manager dovete soddisfare i seguenti prerequisiti:

1. Devi utilizzare il servizio Experience Cloud ID (ECID) versione 4.1 o successiva. [Scarica](https://github.com/Adobe-Marketing-Cloud/id-service/releases) la nostra ultima versione ECID.
2. 
   1. Devi utilizzare la libreria di integrazione dei dati di Audience Manager (DIL) versione 9.0 o successiva, scaricabile da [qui](https://github.com/Adobe-Marketing-Cloud/dil/releases). Leggi [DIL nella documentazione di Audience Manager](/help/using/dil/dil-overview.md).
   2. In alternativa, se utilizzi l'inoltro lato server (SSF) per importare dati in Audience Manager, devi effettuare l'aggiornamento alla versione più recente di appmeasurement. Scarica appmeasurement mediante [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
3. Dovete utilizzare una piattaforma di gestione del consenso (CMP), commerciale o personalizzata, che supporta IAB ed è registrata con IAB TCF. Consultate l'elenco dei [CMPS registrati nel framework IAB](https://advertisingconsent.eu/cmp-list/).

## Raccomandazioni e modalità di implementazione {#recommendations}

Per abilitare il supporto IAB TCF in Audience Manager, leggi la nostra documentazione su [come configurare IAB con Consenso](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Questa funzione è più semplice utilizzando [Adobe Launch](https://docs.adobelaunch.com/) per lo strumento ECID per le proprietà. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Flusso di lavoro di scelta utente quando si utilizza il framework IAB {#user-choice-workflow}

Quando si accede a una proprietà Web, gli utenti possono fornire le proprie scelte relative a come devono essere utilizzati dall'editore e dai fornitori di terze parti con cui l'editore funziona. Gli utenti forniscono le proprie opzioni sotto forma *di funzioni standard* e autorizzazioni a *fornitori di terze parti* registrati nell'elenco globale dei fornitori. L'immagine seguente rappresenta un esempio di una finestra di dialogo CMP, visualizzata a un nuovo visitatore di un sito Web. Tieni presente che questo tipo di dialogo può essere molto diverso, in base all'implementazione del cliente.

![Collaborazione CMP](/help/using/overview/aam-gdpr/assets/cmp.png)

Gli scopi standard nel framework IAB sono:

* Archiviazione e accesso alle informazioni
* Personalizzazione
* Selezione, consegna e reporting degli annunci
* Selezione, consegna e reporting dei contenuti
* Misura

Per una descrizione [dei cinque scopi standard, consultate la pagina](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) delle specifiche framework IAB.

Gli utenti possono concedere il consenso per una combinazione di scopi e fornitori standard. Ad esempio, gli utenti possono concedere il proprio consenso per l'archiviazione, la personalizzazione e la misurazione e concedere il proprio consenso a tutti i fornitori di terze parti visualizzati dalla CMP. Oppure, in un altro esempio, possono concedere il consenso per tutti e cinque i fini standard, ma autorizzare solo alcuni fornitori visualizzati dalla CMP.

Quando l'utente seleziona le relative opzioni di privacy, le scelte dell'utente vengono registrate nella stringa di autorizzazione IAB TCF. La stringa di autorizzazione IAB TCF memorizza la combinazione di scopi e fornitori approvati, insieme ad altre informazioni sui metadati (consultate la pagina [IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) per ulteriori informazioni). Ogni fornitore registrato nel protocollo IAB TCF valuta la stringa di autorizzazione IAB TCF ed effettua decisioni in base alle scelte sulla privacy dell'utente. Ricorda che le scelte sulla privacy degli utenti sono valide per tutti i fornitori approvati.

## Finalità standard richieste da Audience Manager {#aam-standard-purposes}

Audience Manager valuta le scelte degli utenti memorizzate nella stringa di consenso IAB TFC per:

* Archiviazione e accesso delle informazioni (scopo ID 1 nell'elenco dei fornitori [globale](https://vendorlist.consensu.org/vendorlist.json))
* Personalizzazione (ID attività 2)
* Misurazione (ID scopo 5)
* Il consenso del fornitore di Audience Manager consente di archiviare, elaborare o attivare i dati per un editore.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Il comportamento di Audience Manager dipende dal fatto che l'utente conceda il consenso {#aam-behavior-consent}

Audience Manager funziona in modo diverso a seconda che Audience Manager rilevi nella stringa di consenso IAB TCF che l'utente ha fornito il consenso per i tre scopi (archiviazione, personalizzazione, misura) o meno.

| Quando l'utente *fornisce il consenso*, Audience Manager: | Quando l'utente *rifiuta* il consenso, Audience Manager: |
|---|---|
| <ul><li>Esegue tutti i casi d'uso di Audience Manager richiesti.</li><li>Invia il consenso a terze parti nelle sincronizzazioni ID (passando gdpr = 1 e la stringa di consenso come gdpr_ permission sulle chiamate di sincronizzazione ID).</li><li>Valuta e rispetta il consenso passato dai pixel del server di annunci.</li><li>Rispetta le sincronizzazioni ID iniziate.</li></ul> | <ul><li>Non memorizza nessun nuovo dato utente nell'istanza. Ciò include ID partner, segnali, caratteristiche o dati pixel.</li><li>Non avvia sincronizzazioni ID terza parte.</li><li>Non rispetta le sincronizzazioni ID iniziate per partner.</li></ul> |



## Caso d'uso editore {#publisher-use-case}

Implementando IAB TCF, non è necessario mantenere il codice personalizzato per la gestione del consenso sulle proprietà Web tramite un meccanismo diverso con Adobe o altri fornitori di terze parti. Il caso d'uso è descritto nell'immagine e nei passaggi seguenti. Inizia da sinistra dell'immagine:

1. Un utente visita una delle vostre proprietà Web. Fintanto che utilizzate le versioni più recenti delle librerie ECID e DIL (consultate [Prerequisiti](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), viene attivato il flusso di consenso.
2. Audience Manager verifica se si applica il flusso IAB (`isIabContext=true`). Vedete [Recommendations e modalità di implementazione](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager controlla se GDPR apply (`gdpr = 1`) e se è presente una CMP, registrata con IAB, sulla proprietà Web. Ad esempio, questo vale per gli utenti che accedono all'area dell'Unione Europea. È responsabilità dell'editore impostare il flag GDPR.
4. Se si applica GDPR, Audience Manager verifica la stringa di autorizzazione IAB TCF, trasmesso nel parametro `gdpr_consent`, per le autorizzazioni necessarie. Audience Manager richiede autorizzazioni per archiviazione, personalizzazione, misurazione e consenso del fornitore Audience Manager per memorizzare, elaborare o attivare dati.
5. Se la stringa di autorizzazione IAB TCF è presente e contiene le autorizzazioni necessarie, Audience Manager trasmette la stringa di autorizzazione IAB TCF ai nostri [server di raccolta dati](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager risponde impostando un [cookie demdex](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) sul browser. Audience Manager viene inoltre avviato e rispettato le sincronizzazioni ID terza parte.
7. In alternativa, se la stringa di autorizzazione IAB TCF passata al passaggio 5 non contiene tutte le autorizzazioni necessarie, Audience Manager non raccoglie, elabora o attiva dati e non rispetta né avvia le sincronizzazioni ID.

![Caso d'uso editore](assets/publisher-use-case.png)

## Caso d'uso dell'inserzionista {#advertiser-use-case}

Audience Manager valuta e rispetta il consenso passato nelle [chiamate](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)pixel, in conformità con IAB TCF.

I pixel vengono generalmente inseriti dai clienti Audience Manager sulle pagine dei partner o inseriti nei server di annunci da includere nella risposta annuncio. Nel primo caso, il partner deve recuperare il parametro di consenso in modo programmatico e aggiungerlo al pixel prima dell'attivazione. Nel secondo caso, che è più comune ed è descritto in dettaglio qui sotto, i server di annunci aggiungono i parametri del consenso ricevuti dalla piattaforma di pubblicità Fornitura (SSP) o dai server pubblicitari editore a tutti i pixel.

Audience Manager usa due parametri per trasmettere il consenso utente nelle chiamate pixel:

* `gdpr` può essere 0 (GDPR non applicabile) o 1 (applicabile al GDPR);
* `gdpr_consent` is the URL-safe party 64-encoded GDPR permission string (see [specification](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Una chiamata di esempio per un pixel impression, con i due parametri potrebbe presentarsi come segue:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Il caso d'uso è descritto nell'immagine e nei passaggi seguenti. Inizia da sinistra dell'immagine:

1. L'utente riceve un'impression tramite un server pubblicitario. Questo si traduce in una chiamata pixel ai nostri server di raccolta dati (DCS).
1. Audience Manager verifica se il flag GDPR è applicabile. In caso contrario, Audience Manager memorizza i dati passati in variabili di macro nelle chiamate pixel.
1. Se la stringa di consenso è presente e contiene le autorizzazioni necessarie, Audience Manager memorizza i dati passati in variabili di macro nelle chiamate pixel.
1. Se la stringa di consenso risulta mancante o non mancano le autorizzazioni necessarie, Audience Manager rilascia i dati passati nelle variabili di macro nelle chiamate pixel.

![Caso d'uso dell'inserzionista](assets/advertiser-use-case.png)

## Partner di attivazione che supportano IAB TCF {#aam-activation-partners}

Il plug-in Audience Manager per IAB TCF consente di inoltrare la stringa di autorizzazione IAB TCF ai partner di attivazione rispettando le scelte sulla privacy degli utenti. Per informazioni su quali partner di attivazione supportano IAB TCF (preciso dal 7 luglio 2019), fare riferimento al nostro **[foglio di Excel](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**.

## Verificare l'implementazione dell'IAB {#test-iab-implementation}

Per verificare che sia stato implementato correttamente il plug-in Audience Manager per IAB TCF, leggi [Caso d'uso 4 nei metodi di convalida per l'implementazione Opt-in e IAB](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## IAB e Rinuncia in Audience Manager. Ordine di precedenza. {#iab-and-optout}

Un'altra opzione di privacy per l'eliminazione degli utenti è la capacità di rifiutare la raccolta di dati. Adobe fornisce agli utenti i mezzi necessari all'interno della [pagina Scelte](https://www.adobe.com/privacy/opt-out.html#customeruse) sulla privacy.

Audience Manager affronta la gestione di rinuncia in un [articolo separato nella nostra documentazione](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Ordine di precedenza** - Se l'utente esce dalla raccolta dati utilizzando uno strumento di rinuncia globale, come descritto nel collegamento qui sopra, questa ha la precedenza rispetto alle verifiche dell'IAB e dell'IAB.

## Risorse aggiuntive {#additional-resources}

* [Consenso al servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR Transparency and Permission Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR Transparency and Permission Framework Technical Specifications](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Plug-plugin IAB TCF - dimostrazione video](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)