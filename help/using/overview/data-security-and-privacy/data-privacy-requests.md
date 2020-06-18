---
description: Il presente documento illustra gli aspetti tecnici relativi alla conformità alle normative sulla privacy per  Audience Manager.
seo-description: Il presente documento illustra gli aspetti tecnici relativi alla conformità alle normative sulla privacy per  Audience Manager.
seo-title: Richieste sulla privacy dei dati
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Richieste sulla privacy dei dati
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1487'
ht-degree: 1%

---


# Richieste sulla privacy dei dati {#data-privacy-requests}

## Panoramica {#overview}

Questo documento fornisce una panoramica sulla gestione della privacy dei singoli dati e delle richieste di rifiuto che potete inviare [!DNL Audience Manager] tramite l’interfaccia utente [](https://privacyui.cloud.adobe.io/) Privacy Service e **[!DNL Privacy Service API]**.

Questi strumenti consentono di inviare richieste sulla privacy dei dati dei consumatori effettuate in [!DNL GDPR] e [!DNL CCPA].

Prima di leggere questo articolo, consigliamo di consultare il Glossario [GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) e il Glossario [](aam-ccpa-glossary.md)CCPA, per comprendere meglio la terminologia utilizzata.

È possibile inviare singole richieste per accedere ed eliminare dati del consumatore da [!DNL Audience Manager], in due modi:

* Tramite l’interfaccia utente [di](https://privacyui.cloud.adobe.io/)Privacy Service. Consulta la documentazione [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Attraverso il **[!DNL Privacy Service API]**. Consulta la documentazione [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) e il [!DNL API] riferimento [qui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Quando si inviano richieste di privacy per singoli dati, è possibile inviare  identificatori Audience Manager (ID), come descritto nella sezione **[ID](data-privacy-ids.md)**Audience Manager, insieme ai rispettivi ID dello spazio nomi (ID origine dati).

L&#39; [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) supporta due tipi di richieste: richieste di accesso ai dati e di eliminazione dei dati.

## Richieste di accesso ai dati {#access-data}

Puoi inviare singole richieste di accesso ai dati tramite l’interfaccia utente [](https://privacyui.cloud.adobe.io/) Privacy Service ( [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)la documentazione) o chiamando [!DNL Privacy Service API] ( [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) la documentazione e [!DNL API] qui [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)il riferimento).

L’interfaccia utente [di](https://privacyui.cloud.adobe.io/) Privacy Service consente di creare nuove richieste di processo utilizzando il [!UICONTROL Request Builder] file o caricando un [!DNL JSON] file.

Per verificare l’aspetto di un [!DNL JSON] file valido, puoi [scaricare un JSON](../data-security-and-privacy/assets/access_request.json)di esempio.

Comprendiamo il tuo impegno a rispettare le tue richieste sulla privacy dei dati entro il termine stabilito dalla normativa.

## Richieste di eliminazione dati{#delete-data}

Puoi inviare richieste di eliminazione dei dati tramite l’interfaccia utente [](https://privacyui.cloud.adobe.io/) Privacy Service ( [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)la documentazione) o chiamando [!DNL Privacy Service API] ( [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) la documentazione e [qui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)il riferimento API).

L’interfaccia utente [di](https://privacyui.cloud.adobe.io/) Privacy Service consente di creare nuove richieste di processo utilizzando il [!UICONTROL Request Builder] file o caricando un [!DNL JSON] file.

Per verificare l’aspetto di un [!DNL JSON] file valido, puoi [scaricare un JSON](../data-security-and-privacy/assets/access_request.json)di esempio.

Adobe comprende il tuo impegno a rispettare le richieste dei clienti sulla privacy dei dati entro 30 giorni. Per questo motivo, [!DNL Adobe] si impegna a elaborare la richiesta di eliminazione dei dati il prima possibile.

In risposta alle richieste di eliminazione dei dati del consumatore, [!DNL Audience Manager] elimina le caratteristiche e i segmenti associati all’ [!DNL Audience Manager] identificatore incluso nella richiesta. Inoltre, verranno rimossi i rispettivi [!DNL Audience Manager] identificatori per il singolo oggetto che ha rinunciato a ulteriori operazioni di raccolta dati [!DNL Audience Manager] e le rispettive mappature ID.

Quando invii ID dichiarati, come [!DNL CRM] ID di dispositivi diversi o ID di cookie, nelle richieste di privacy dei dati, [!DNL Audience Manager] esegui l’eliminazione necessaria su tutti i dispositivi collegati (fino a 100 dispositivi per ID dichiarato).

[!DNL Audience Manager] tenterà di notificare ai partner di attivazione le richieste di eliminazione inviando loro informazioni di non segmentazione per gli interessati che richiedono l&#39;eliminazione di alcuni dati. Tuttavia, alcuni partner per l&#39;attivazione:

1. Impossibile supportare richieste non segmentate (o rimuovere segmenti) da [!DNL Audience Manager] e/o
2. Non sono in grado di ricevere aggiornamenti da [!DNL Audience Manager] con una frequenza inferiore a 30 giorni. In questi casi, [!DNL Audience Manager] i clienti non possono inviare le richieste di eliminazione ai partner di attivazione in modo automatico attraverso [!DNL Audience Manager].

In questi casi, non è possibile inviare le richieste di eliminazione ai partner di attivazione in modo automatico [!DNL Audience Manager].

Scarica il nostro foglio [Excel per](assets/AAM-Partners-October2019.xlsx) partner per vedere quali partner di [!DNL Audience Manager] attivazione supportano il segmento.

## Richieste di rifiuto {#opt-out-requests}

[!DNL Audience Manager] sostiene gli standard a livello di settore per quanto riguarda la gestione del rifiuto. Continua a leggere per informazioni complete sui tipi di rinuncia supportati da [!DNL Audience Manager].

Mentre le richieste di accesso e di eliminazione dei dati vengono gestite tramite [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), le richieste di rifiuto sono attualmente supportate tramite [!DNL DCS API]. Continua a leggere per capire come dovrebbero essere le [!DNL API] chiamate di rinuncia.

### Richieste di rifiuto globali

La rinuncia globale rappresenta un rifiuto tra [!DNL Audience Manager] e altre [!DNL Adobe Experience Cloud] soluzioni per tutti i marchi. Nella tabella seguente sono elencati i metodi utilizzati per la rinuncia globale:

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
   <td colname="col2"> <p>La pagina <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices </a> offre funzionalità con un solo clic che consentono agli utenti finali di controllare e rifiutare la raccolta dei dati da parte delle soluzioni pubblicitarie Adobe Experience Cloud (incluso  Audience Manager). Nello specifico, consulta la sezione <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Business customer </a> della pagina Privacy Choices. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiamate API dirette a  Audience Manager </p> </td> 
   <td colname="col2"> <p>Gli utenti possono scegliere di non partecipare alla raccolta dati da parte di tutti  marchi Audience Manager effettuando una chiamata all'API DCS di seguito e includendo l'ID utente Audience Manager <a href="../../reference/ids-in-aam.md"> </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Di conseguenza, imposteremo <code>demdex=NOTARGET</code> e <code>dextp=NOTARGET</code> cookie per l'ID utente Audience Manager  inviato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivi mobili </p> </td> 
   <td colname="col2"> <p>Consulta le impostazioni di privacy e rinuncia per: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Dispositivi Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> Dispositivi iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Gli utenti finali possono anche scegliere di non partecipare alla raccolta dati globale visitando i siti web dei nostri partner di settore.

* [Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

In base alle richieste di rifiuto descritte sopra:

* [!DNL Audience Manager] cesseranno tutte le attività di raccolta, segmentazione o attivazione dei dati, purché l&#39;utente non cancelli i cookie del browser.
* I dati storici vengono rimossi dal profilo utente dopo 120 giorni.

### Rinuncia a livello di partner con chiamate ID dichiarate

La rinuncia a livello di partner consente di escludere gli utenti dalla raccolta dei dati da parte di specifici [!DNL Audience Manager] partner. Puoi inviare richieste di rifiuto a livello di partner per ID cross-device, inclusi [!DNL CRM] ID e indirizzi e-mail con hash.

A seguito di una rinuncia a livello di partner con una chiamata ID dichiarata:

* L&#39;ID [](../../reference/ids-in-aam.md) CRM è escluso dalla raccolta dei dati;
* L&#39;ultimo ID dispositivo ([ID](../../reference/ids-in-aam.md)utente univoco Audience Manager) collegato all&#39;ID [](../../reference/ids-in-aam.md) CRM viene escluso dalla raccolta dati.
* [!DNL Audience Manager] cesseranno tutte le attività di raccolta, segmentazione o attivazione dei dati in corso per l&#39; [!DNL CRM] ID e l&#39;ultimo ID dispositivo collegato all&#39; [!DNL CRM] ID;
* [!DNL Audience Manager] separa l’ID [!DNL CRM] di rinuncia e l’ultimo ID dispositivo da tutti i segmenti;
* I partner di destinazione ricevono la richiesta di segmento per l&#39; [!DNL CRM] ID e l&#39;ultimo ID dispositivo. La segmentazione funziona sia per le destinazioni in tempo [](data-privacy-requests.md#aam-partners-with-unsegmentation) reale che per quelle batch.
* Nessun dato storico viene eliminato.

Quando [!DNL Audience Manager] riceve una richiesta di rifiuto a livello di partner, il messaggio [!DNL JSON] restituito dall&#39;utente [!DNL DCS] contiene il codice di [errore 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), con il messaggio [!UICONTROL "Encountered opt out tag"], invece dell&#39;ID [!DNL Audience Manager] utente.

Puoi effettuare una richiesta di rifiuto con ID dichiarato con le coppie `d_cid` `d_cid_ic` e valore chiave. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consultate [CID sostituisce DPID e DPUUID](../../reference/cid.md) Negli esempi, il *corsivo* indica un segnaposto variabile.

#### Rifiuto con CID e CID_IC

Per una descrizione e una sintassi, consultate Variabili [URL e sintassi per ID](../../features/declared-ids.md#variables-and-syntax)dichiarati.

| Rifiuto tramite | Esempio di codice |
|--- |--- |
| Un ID provider di dati e un ID utente. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Un codice di integrazione e un ID utente. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Più coppie `d_cid` e `d_cid_ic` chiave-valore. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Rinuncia a livello di partner con chiamate ID dispositivo

La rinuncia a livello di partner consente di escludere gli utenti dalla raccolta dei dati da parte di specifici [!DNL Audience Manager] partner. Puoi rifiutare la raccolta di dati su un determinato ID dispositivo per un marchio effettuando le seguenti chiamate all&#39;API [](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS:

| Rifiuto tramite | Esempio di codice |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Per saperne di più `uuid`, `mid` e `imsOrgId` nell’ [indice degli ID in  Audience Manager](/help/using/reference/ids-in-aam.md).

In seguito a una rinuncia a livello di partner con una chiamata ID dispositivo:

* L&#39;ID dispositivo viene escluso dalla raccolta dati.
* [!DNL Audience Manager] cesserà la raccolta di dati, la segmentazione o l&#39;attivazione per il partner, andando avanti per l&#39;ID dispositivo.
* [!DNL Audience Manager] separa l&#39;ID dispositivo da tutti i segmenti;
* I partner di destinazione ricevono la richiesta di segmento per l&#39;ID dispositivo. La segmentazione funziona sia per le destinazioni in tempo [](data-privacy-requests.md#aam-partners-with-unsegmentation) reale che per quelle batch.
* Nessun dato storico viene eliminato.

##  Partner Audience Manager Con Funzionalità Di Separazione {#aam-partners-with-unsegmentation}

Per facilitare l&#39;automazione delle richieste di privacy dei dati del consumatore, [!DNL Audience Manager] si tenterà di notificare ai partner di attivazione le richieste di eliminazione da parte degli oggetti dati inviando loro informazioni non segmentate (o rimuovendo segmenti).

Tuttavia, alcuni dei nostri partner per l&#39;attivazione:

1. Impossibile supportare richieste non segmentate da [!DNL Audience Manager] e/o
2. Non sono in grado di ricevere gli aggiornamenti [!DNL Audience Manager] più spesso di una volta in 30 giorni.

In questi casi, non è possibile inviare le richieste di eliminazione ai partner di attivazione in modo automatico [!DNL Audience Manager].

Consulta l’ [elenco delle destinazioni](/help/using/features/destinations/device-based-destinations-list.md) basate sui dispositivi per vedere quali partner di [!DNL Audience Manager] attivazione supportano i segmenti.

## Richieste di correzione dati {#correction}

Poiché non [!DNL Audience Manager] è l&#39;origine dei dati, esiste un ruolo limitato per la correzione dei dati in [!DNL Audience Manager]. La correzione potrebbe significare che il consumatore ha chiesto di essere squalificato da una caratteristica/segmento non corretta o qualificato per la caratteristica/segmento desiderata.

[!DNL Audience Manager] i clienti possono scegliere di acquisire i segnali/caratteristiche/segmenti rilevanti in base ai profili utente e inviare tali informazioni tramite l&#39;inserimento [di dati](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) offline a [!DNL Audience Manager]. L&#39;utente continuerà a essere qualificato per la caratteristica e i segmenti originali se ripeterà il proprio comportamento.
