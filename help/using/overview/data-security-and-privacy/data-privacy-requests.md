---
description: Questo documento illustra gli aspetti tecnici relativi alla conformità alle normative sulla privacy dei dati per Audience Manager.
seo-description: Questo documento illustra gli aspetti tecnici relativi alla conformità alle normative sulla privacy dei dati per Audience Manager.
seo-title: Richieste sulla privacy dei dati
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Richieste sulla privacy dei dati
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: ff4bf70c9012f99289ea82824a552db97430fbf2

---


# Richieste sulla privacy dei dati {#data-privacy-requests}

## Panoramica {#overview}

Questo documento fornisce una panoramica sulla gestione della privacy dei singoli dati e delle richieste di rifiuto che potete inviare ad Audience Manager tramite l’interfaccia utente [del servizio](https://gdprui.cloud.adobe.io/) Privacy e l’ **[!DNL Privacy Service API]**.

Questi strumenti ti consentono di inviare richieste sulla privacy dei dati dei consumatori effettuate in conformità ai requisiti GDPR e CCPA.

Prima di leggere questo articolo, consigliamo di consultare il Glossario [GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) e il Glossario [](aam-ccpa-glossary.md)CCPA, per comprendere meglio la terminologia utilizzata.

Potete inviare singole richieste per accedere ed eliminare i dati dei consumatori da Audience Manager in due modi:

* Tramite l’interfaccia utente del servizio [Privacy](https://gdprui.cloud.adobe.io/). Consulta la documentazione [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Attraverso il **[!DNL Privacy Service API]**. Consulta la documentazione [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) e il riferimento API [qui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Quando inviate singole richieste di privacy dei dati, potete inviare qualsiasi ID Audience Manager, come descritto nella sezione Identificatori **[di](data-privacy-ids.md)** Audience Manager, insieme ai rispettivi ID dello spazio nomi (ID origine dati).

Il servizio [](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) Privacy supporta due tipi di richieste: richieste di accesso ai dati e di eliminazione dei dati.

## Richieste di accesso ai dati {#access-data}

Puoi inviare singole richieste di accesso ai dati tramite l’interfaccia utente [del servizio](https://gdprui.cloud.adobe.io/) Privacy ( [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)la documentazione) o chiamando [!DNL Privacy Service API] ( [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) la documentazione e [!DNL API] qui [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)il riferimento).

L’interfaccia utente [del servizio](https://gdprui.cloud.adobe.io/) Privacy consente di creare nuove richieste di processo utilizzando il [!UICONTROL Request Builder] file o caricando un [!DNL JSON] file.

Per verificare l’aspetto di un [!DNL JSON] file valido, puoi [scaricare un JSON](../data-security-and-privacy/assets/access_request.json)di esempio.

Comprendiamo il tuo impegno a rispettare le tue richieste sulla privacy dei dati entro il termine stabilito dalla normativa.

## Richieste di eliminazione dati{#delete-data}

Puoi inviare richieste di eliminazione dei dati tramite l’interfaccia utente [del servizio](https://gdprui.cloud.adobe.io/) Privacy ( [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)la documentazione) o chiamando [!DNL Privacy Service API] ( [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) la documentazione e [qui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)il riferimento API).

L’interfaccia utente [del servizio](https://gdprui.cloud.adobe.io/) Privacy consente di creare nuove richieste di processo utilizzando il [!UICONTROL Request Builder] file o caricando un [!DNL JSON] file.

Per verificare l’aspetto di un [!DNL JSON] file valido, puoi [scaricare un JSON](../data-security-and-privacy/assets/access_request.json)di esempio.

Adobe comprende il tuo impegno a rispettare le richieste dei clienti sulla privacy dei dati entro 30 giorni. Per questo motivo, Adobe si impegna a elaborare la richiesta di eliminazione dei dati il prima possibile.

In risposta alle richieste di eliminazione dei dati del consumatore, Audience Manager elimina le caratteristiche e i segmenti associati all’identificatore Audience Manager incluso nella richiesta. Inoltre, i rispettivi identificatori di Audience Manager per il singolo oggetto di rifiuto di ulteriore raccolta dati da parte di Audience Manager e le rispettive mappature ID verranno rimossi.

Quando invii ID dichiarati, come [!DNL CRM] ID di dispositivi diversi o ID di cookie, nelle richieste di privacy dei dati, Audience Manager eseguirà l'eliminazione necessaria su tutti i dispositivi collegati (fino a 100 dispositivi per ID dichiarato).

Audience Manager tenterà di notificare ai partner di attivazione le richieste di eliminazione inviando loro informazioni di non segmentazione per gli oggetti dati che richiedono l'eliminazione di alcuni dati. Tuttavia, alcuni partner per l'attivazione:

1. Impossibile supportare richieste non segmentate (o rimuovere segmenti) da Audience Manager e/o
2. Non sono in grado di ricevere aggiornamenti da Audience Manager con una frequenza inferiore a 30 giorni. In questi casi, i clienti di Audience Manager non possono inviare le richieste di eliminazione ai partner di attivazione in modo automatico tramite Audience Manager.

In questi casi, non è possibile inviare le richieste di eliminazione ai partner di attivazione in modo automatico tramite Audience Manager.

Scarica il nostro foglio [Excel per](assets/AAM-Partners-October2019.xlsx) partner per vedere quali partner di attivazione di Audience Manager supportano il segmento.

## Richieste di rifiuto {#opt-out-requests}

Audience Manager supporta gli standard di settore per la gestione delle rinunce. Continua a leggere per informazioni complete sui tipi di rinuncia supportati da Audience Manager.

Mentre le richieste di accesso ed eliminazione dei dati vengono gestite tramite il servizio [](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)Privacy, le richieste di rifiuto sono attualmente supportate tramite l'API DCS. Continua a leggere per capire come dovrebbero essere le chiamate API per la rinuncia.

### Richieste di rifiuto globali

La rinuncia globale rappresenta un rifiuto tra Audience Manager e altre soluzioni Adobe Experience Cloud per tutti i marchi. Nella tabella seguente sono elencati i metodi utilizzati per la rinuncia globale:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rifiuto per </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>La pagina <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices </a> offre funzionalità con un clic che consentono agli utenti finali di controllare e rifiutare la raccolta di dati dalle soluzioni pubblicitarie Adobe Experience Cloud (incluso Audience Manager). Nello specifico, consulta la sezione <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Business customer </a> della pagina Privacy Choices. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiamate API dirette ad Audience Manager </p> </td> 
   <td colname="col2"> <p>I vostri utenti possono scegliere di non partecipare alla raccolta di dati da parte di tutti i marchi di Audience Manager effettuando una chiamata all’API DCS di seguito e includendo l’ID utente di <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Di conseguenza, imposteremo <code>demdex=NOTARGET</code> e <code>dextp=NOTARGET</code> cookie per l’ID utente di Audience Manager inviato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivi mobili </p> </td> 
   <td colname="col2"> <p>Consulta le impostazioni di privacy e rinuncia per: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Dispositivi Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> Dispositivi iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Gli utenti finali possono anche scegliere di non partecipare alla raccolta dati globale visitando i siti web dei nostri partner di settore.

* [Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

In base alle richieste di rifiuto descritte sopra:

* Audience Manager cesserà tutte le attività di raccolta, segmentazione o attivazione dei dati, purché l'utente non cancelli i cookie del browser.
* I dati storici vengono rimossi dal profilo utente dopo 120 giorni.

### Rinuncia a livello di partner con chiamate ID dichiarate

La rinuncia a livello di partner consente di rifiutare la raccolta di dati da parte di partner Audience Manager specifici. Puoi inviare richieste di rifiuto a livello di partner per ID cross-device, inclusi ID CRM e indirizzi e-mail con hash.

A seguito di una rinuncia a livello di partner con una chiamata ID dichiarata:

* L'ID [](../../reference/ids-in-aam.md) CRM è escluso dalla raccolta dei dati;
* L'ultimo ID dispositivo (ID[utente univoco di](../../reference/ids-in-aam.md)Audience Manager) collegato all'ID [](../../reference/ids-in-aam.md) CRM viene escluso dalla raccolta dati.
* Audience Manager cesserà tutte le attività di raccolta, segmentazione o attivazione dei dati in corso per l'ID CRM e l'ultimo ID dispositivo collegato all'ID CRM;
* Audience Manager analizza l’ID CRM e l’ultimo ID dispositivo a cui è stata optata per la rinuncia da tutti i segmenti;
* I partner di destinazione ricevono la richiesta di segmento per l'ID CRM e l'ultimo ID dispositivo. La segmentazione funziona sia per le destinazioni in tempo [](data-privacy-requests.md#aam-partners-with-unsegmentation) reale che per quelle batch.
* Nessun dato storico viene eliminato.

Quando Audience Manager riceve una richiesta di rifiuto a livello di partner, il JSON restituito dal DCS contiene il codice di [errore 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), con il messaggio [!UICONTROL "Encountered opt out tag"], invece dell’ID utente di Audience Manager.

Puoi effettuare una richiesta di rifiuto con ID dichiarato con le coppie `d_cid` `d_cid_ic` e valore chiave. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consultate [CID sostituisce DPID e DPUUID](../../reference/cid.md) Negli esempi, il *corsivo* indica un segnaposto variabile.

#### Rifiuto con CID e CID_IC

Per una descrizione e una sintassi, consultate Variabili [URL e sintassi per ID](../../features/declared-ids.md#variables-and-syntax)dichiarati.

| Rifiuto tramite | Esempio di codice |
|--- |--- |
| ID provider di dati e ID utente. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Un codice di integrazione e un ID utente. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Più coppie d_cid e d_cid_ic chiave-valore. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Rinuncia a livello di partner con chiamate ID dispositivo

La rinuncia a livello di partner consente di rifiutare la raccolta di dati da parte di partner Audience Manager specifici. Puoi rifiutare la raccolta di dati su un determinato ID dispositivo per un marchio effettuando le seguenti chiamate all'API [](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS:

| Rifiuto tramite | Esempio di codice |
|--- |--- |
| Un ID Utente Univoco Audience Manager (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un Experience Cloud ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Ulteriori informazioni `uuid`e informazioni `mid` e `imsOrgId` informazioni sull’ [indice degli ID in Audience Manager](/help/using/reference/ids-in-aam.md).

In seguito a una rinuncia a livello di partner con una chiamata ID dispositivo:

* L'ID dispositivo viene escluso dalla raccolta dati.
* Audience Manager cesserà tutte le attività di raccolta, segmentazione o attivazione dei dati per il partner, andando avanti per l'ID dispositivo.
* Audience Manager svincola l'ID dispositivo da tutti i segmenti;
* I partner di destinazione ricevono la richiesta di segmento per l'ID dispositivo. La segmentazione funziona sia per le destinazioni in tempo [](data-privacy-requests.md#aam-partners-with-unsegmentation) reale che per quelle batch.
* Nessun dato storico viene eliminato.

## Partner Audience Manager Con Funzionalità Di Separazione {#aam-partners-with-unsegmentation}

Per facilitare l'automazione delle richieste di privacy dei dati dei consumatori, Audience Manager tenterà di inviare ai partner di attivazione notifiche sulle richieste di eliminazione da oggetti dati inviando loro informazioni non segmentate (o rimuovendo segmenti).

Tuttavia, alcuni dei nostri partner per l'attivazione:

1. Impossibile supportare richieste non segmentate da Audience Manager e/o
2. Non sono in grado di ricevere gli aggiornamenti da Audience Manager più spesso di una volta in 30 giorni.

In questi casi, non è possibile inviare le richieste di eliminazione ai partner di attivazione in modo automatico tramite Audience Manager.

Scarica il nostro foglio [Excel per](assets/AAM-Partners-December2019.xlsx) partner per vedere quali partner di attivazione di Audience Manager supportano il segmento.

## Richieste di correzione dati {#correction}

Poiché Audience Manager non è l’origine dei dati, in Audience Manager esiste un ruolo limitato per la correzione dei dati. La correzione potrebbe significare che il consumatore ha chiesto di essere squalificato da una caratteristica/segmento non corretta o qualificato per la caratteristica/segmento desiderata.

I clienti di Audience Manager possono scegliere di catturare i segnali/tratti/segmenti pertinenti in base ai profili utente e inviare tali informazioni tramite l’inserimento [di dati](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) offline ad Audience Manager. L'utente continuerà a essere qualificato per la caratteristica e i segmenti originali se ripeterà il proprio comportamento.
