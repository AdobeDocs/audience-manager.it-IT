---
description: Questo documento illustra gli aspetti tecnici relativi alla conformità alle normative sulla privacy dei dati per Audience Manager.
seo-description: Questo documento illustra gli aspetti tecnici relativi alla conformità alle normative sulla privacy dei dati per Audience Manager.
seo-title: Richieste sulla privacy dei dati
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Richieste sulla privacy dei dati
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 62%

---


# Richieste sulla privacy dei dati {#data-privacy-requests}

## Panoramica {#overview}

Questo documento fornisce una panoramica sulla gestione della privacy dei singoli dati e delle richieste di rifiuto che è possibile inviare a [!DNL Audience Manager] tramite l&#39; [interfaccia utente Privacy Service](https://privacyui.cloud.adobe.io/) e **[!DNL Privacy Service API]**.

Questi strumenti consentono di inviare richieste sulla privacy dei dati dei consumatori effettuate in [!DNL GDPR] e [!DNL CCPA].

Prima di leggere questo articolo, consigliamo di consultare il [RGPD Glossary](../data-security-and-privacy/aam-gdpr-glossary.md) e il [CCPA Glossary](aam-ccpa-glossary.md) per comprendere meglio la terminologia utilizzata.

È possibile inviare singole richieste per accedere ed eliminare i dati del consumatore da [!DNL Audience Manager] in due modi:

* Tramite la [Privacy Service UI](https://privacyui.cloud.adobe.io/). Consulta la documentazione [qui](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Attraverso la **[!DNL Privacy Service API]**. Consulta la documentazione [qui](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[!DNL API] e il riferimento [qui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Durante l&#39;invio di singole richieste di privacy dei dati, puoi inviare qualsiasi [!DNL Audience Manager] identificatori (ID), come descritto nella sezione **[ID Audience Manager](data-privacy-ids.md)**, insieme ai rispettivi ID dello spazio nomi (ID origine dati).

[Privacy Service](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html) supporta due tipi di richieste: richieste di accesso ai dati e di cancellazione dei dati.

## Richieste di accesso ai dati {#access-data}

Potete inviare singole richieste di accesso ai dati tramite l&#39; [interfaccia utente Privacy Service](https://privacyui.cloud.adobe.io) (documentazione [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) o chiamando l&#39;API Privacy Service (documentazione [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) e [!DNL API] riferimento [qui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La [Privacy Service UI](https://privacyui.cloud.adobe.io/) consente di creare nuove richieste di processi utilizzando il [!UICONTROL Request Builder] o caricando un file [!DNL JSON].

Per visualizzare l’aspetto di un file [!DNL JSON] valido, puoi [ scaricare un file JSON di esempio](../data-security-and-privacy/assets/access_request.json).

Comprendiamo il tuo impegno a soddisfare le richieste sulla privacy dei dati entro il termine stabilito dalla normativa.

## Richieste di cancellazione dei dati {#delete-data}

Potete inviare le richieste di eliminazione dei dati tramite l&#39; [interfaccia utente Privacy Service](https://privacyui.cloud.adobe.io) (documentazione [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) o chiamando l&#39;API Privacy Service (documentazione [qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) e [!DNL API] riferimento [qui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La [Privacy Service UI](https://privacyui.cloud.adobe.io/) consente di creare nuove richieste di processi utilizzando il [!UICONTROL Request Builder] o caricando un file [!DNL JSON].

Per visualizzare l’aspetto di un file [!DNL JSON] valido, puoi [ scaricare un file JSON di esempio](../data-security-and-privacy/assets/access_request.json).

Adobe comprende il tuo impegno a soddisfare le richieste dei clienti sulla privacy dei dati entro 30 giorni. Per questo motivo, [!DNL Adobe] si impegna a elaborare la richiesta di eliminazione dei dati il prima possibile.

In risposta alle richieste di eliminazione dei dati del consumatore, [!DNL Audience Manager] elimina le caratteristiche e i segmenti associati all&#39;identificatore [!DNL Audience Manager] incluso nella richiesta. Inoltre, i rispettivi identificatori [!DNL Audience Manager] per il singolo oggetto di rifiuto di ulteriore raccolta dati da parte di [!DNL Audience Manager] e le rispettive mappature ID verranno rimossi.

Quando invii ID dichiarati, come ID [!DNL CRM] di più dispositivi o ID di , nelle richieste sulla privacy dei dati,  eseguirà la cancellazione necessaria su tutti i dispositivi collegati (fino a 100 dispositivi per ID dichiarato).[!DNL cookie][!DNL Audience Manager]

[!DNL Audience Manager] tenta di avvisare i partner di attivazione riguardo le richieste di cancellazione inviando loro informazioni di rimozione dai segmenti per gli interessati che richiedono la cancellazione di determinati dati. Tuttavia, alcuni partner di attivazione:

1. Impossibile supportare richieste di segmento non segmentate (o rimuoverne) da [!DNL Audience Manager] e/o
2. Non sono in grado di ricevere aggiornamenti da [!DNL Audience Manager] con una frequenza inferiore a 30 giorni. In questi casi, i clienti [!DNL Audience Manager] non sono in grado di inviare le richieste di eliminazione ai partner di attivazione in modo automatico attraverso [!DNL Audience Manager].

In questi casi, non puoi inviare le richieste di cancellazione ai partner di attivazione in modo automatico tramite [!DNL Audience Manager].

Scarica il nostro [foglio Excel dei partner](assets/AAM-Partners-October2019.xlsx) per vedere quali partner di attivazione di supportano la rimozione dai segmenti.[!DNL Audience Manager]

## Richieste di rinuncia {#opt-out-requests}

[!DNL Audience Manager] sostiene gli standard a livello di settore per quanto riguarda la gestione del rifiuto. Continua a leggere per informazioni complete sui tipi di rinuncia supportati da [!DNL Audience Manager].

Mentre le richieste di accesso ed eliminazione dei dati vengono gestite tramite [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), le richieste di rifiuto sono attualmente supportate tramite [!DNL DCS API]. Continua a leggere per scoprire l&#39;aspetto delle chiamate di rifiuto [!DNL API].

### Richieste di rinuncia globale

La rinuncia globale rappresenta una rinuncia tra [!DNL Audience Manager] e altre soluzioni [!DNL Adobe Experience Cloud] per tutti i marchi. Nella tabella seguente sono elencati i metodi utilizzati per la rinuncia globale:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rinuncia per </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>La <a href="https://www.adobe.com/it/privacy/opt-out.html#customeruse" format="http" scope="external">pagina relativa alle scelte sulla privacy</a> fornisce funzionalità con 1 clic che consentono agli utenti finali di controllare e rinunciare alla raccolta di dati da parte delle soluzioni pubblicitarie Adobe Experience Cloud (incluso Audience Manager). Nello specifico, consulta la <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external">sezione per i clienti aziendali</a> della pagina relativa alle scelte sulla privacy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiamate API dirette ad Audience Manager </p> </td> 
   <td colname="col2"> <p>I tuoi utenti possono scegliere di rinunciare alla raccolta di dati da parte di tutti i brand di Audience Manager effettuando una chiamata all’API DCS illustrata di seguito e includendo l’<a href="../../reference/ids-in-aam.md">ID utente di Audience Manager</a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>In seguito a ciò, imposteremo i cookie <code>demdex=NOTARGET</code> e <code>dextp=NOTARGET</code> per l’ID utente di Audience Manager inviato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dispositivi mobili </p> </td> 
   <td colname="col2"> <p>Consulta le impostazioni di privacy e rinuncia per: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/it-IT/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external">Dispositivi Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/it-IT/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external">Dispositivi iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Gli utenti finali possono anche scegliere di rinunciare alla raccolta dati globale visitando i siti web dei nostri partner degli standard di settore.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

In seguito alle richieste di rinuncia descritte sopra:

* [!DNL Audience Manager] cessa tutte le attività di raccolta, segmentazione o attivazione dei dati, purché l’utente non cancelli i cookie del browser.
* I dati storici vengono rimossi dal profilo utente dopo 120 giorni.

### Rinuncia a livello di partner con chiamate di ID dichiarati

L&#39;opzione di rifiuto a livello di partner consente di escludere gli utenti dalla raccolta dei dati da parte di partner [!DNL Audience Manager] specifici. Puoi inviare richieste di rifiuto a livello di partner per ID cross-device, inclusi [!DNL CRM] ID e indirizzi e-mail con hash.

A seguito di una rinuncia a livello di partner con una chiamata di ID dichiarato:

* L’[ID del sistema di gestione delle relazioni con i clienti](../../reference/ids-in-aam.md) è escluso dalla raccolta dei dati;
* L’ultimo ID dispositivo ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) collegato all’[ID del sistema di gestione delle relazioni con i clienti](../../reference/ids-in-aam.md) viene escluso dalla raccolta dati.
* [!DNL Audience Manager] cesserà tutte le attività di raccolta, segmentazione o attivazione dei dati in corso per l&#39; [!DNL CRM] ID e l&#39;ultimo ID dispositivo collegato all&#39; [!DNL CRM] ID;
* [!DNL Audience Manager] separa l’ [!DNL CRM] ID del dispositivo e l’ultimo ID del dispositivo da tutti i segmenti;
* [!UICONTROL Destination] i partner ricevono la richiesta di segmento per l’ [!DNL CRM] ID e l’ultimo ID dispositivo. La rimozione dai segmenti funziona sia per le destinazioni [in tempo reale](data-privacy-requests.md#aam-partners-with-unsegmentation) che per quelle batch.
* Nessun dato storico viene eliminato.

Quando [!DNL Audience Manager] riceve una richiesta di rifiuto a livello di partner, la [!DNL JSON] restituita da [!DNL DCS] contiene il codice di errore [171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), con il messaggio [!UICONTROL "Encountered opt out tag"] invece dell&#39;ID utente [!DNL Audience Manager].

Puoi effettuare una richiesta di rinuncia con ID dichiarato con le coppie chiave-valore `d_cid` e `d_cid_ic`. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consulta [CID Replaces DPID and DPUUID](../../reference/cid.md). Negli esempi, il *corsivo* indica un segnaposto variabile.

#### Rifiuto con [!DNL CID] e [!DNL CID_IC]

Per una descrizione e una sintassi, consulta [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| Rinuncia tramite | Esempio di codice |
|--- |--- |
| Un ID provider di dati e un ID utente. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Un codice di integrazione e un ID utente. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Più coppie chiave-valore `d_cid` e `d_cid_ic`. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Rinuncia a livello di partner con chiamate ID dispositivo

L&#39;opzione di rifiuto a livello di partner consente di escludere gli utenti dalla raccolta dei dati da parte di partner [!DNL Audience Manager] specifici. Puoi rinunciare alla raccolta di dati su un determinato ID dispositivo per un brand effettuando le seguenti chiamate all’[API DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Rinuncia tramite | Esempio di codice |
|--- |--- |
| Un [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un ID [!DNL Experience Cloud] (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Ulteriori informazioni su `uuid`, `mid` e `imsOrgId` sono disponibili in [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

In seguito a una rinuncia a livello di partner con una chiamata ID dispositivo:

* L’ID dispositivo viene escluso dalla raccolta dati.
* [!DNL Audience Manager] cessa tutte le attività future di raccolta, segmentazione o attivazione dei dati da parte del partner per l’ID dispositivo.
* [!DNL Audience Manager] separa l&#39;ID dispositivo da tutti i segmenti;
* I partner di destinazione ricevono la richiesta di rimozione dai segmenti per l’ID dispositivo. La rimozione dai segmenti funziona sia per le destinazioni [in tempo reale](data-privacy-requests.md#aam-partners-with-unsegmentation) che per quelle batch.
* Nessun dato storico viene eliminato.

## [!DNL Audience Manager] Partner Con Funzionalità Di Dissegmentazione  {#aam-partners-with-unsegmentation}

Per facilitare l&#39;automazione delle richieste di privacy dei dati del consumatore, [!DNL Audience Manager] tenterà di notificare ai partner di attivazione le richieste di eliminazione da parte degli oggetti dati, inviando loro informazioni non segmentate (o rimuovendo segmenti).

Tuttavia, alcuni dei nostri partner di attivazione:

1. Impossibile supportare richieste non segmentate da [!DNL Audience Manager] e/o
2. Non sono in grado di ricevere aggiornamenti da [!DNL Audience Manager] più spesso di una volta ogni 30 giorni.

In questi casi, non puoi inviare le richieste di cancellazione ai partner di attivazione in modo automatico tramite [!DNL Audience Manager].

Consulta l’[elenco delle destinazioni basate su dispositivi](/help/using/features/destinations/device-based-destinations-list.md) per vedere quali partner di attivazione di supportano la rimozione dai segmenti.[!DNL Audience Manager]

## Richieste di correzione dei dati {#correction}

Poiché [!DNL Audience Manager] non è l&#39;origine dei dati, esiste un ruolo limitato per la correzione dei dati in [!DNL Audience Manager]. La correzione potrebbe significare che il consumatore ha richiesto di essere squalificato da un [!UICONTROL trait]/[!UICONTROL segment] errato o qualificato per la [!UICONTROL trait]/[!UICONTROL segment] desiderata.

[!DNL Audience Manager] i clienti possono scegliere di acquisire i segnali/caratteristiche/segmenti rilevanti in base ai profili utente e inviare tali informazioni tramite l&#39;inserimento  [offline ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) dei dati a  [!DNL Audience Manager]. L&#39;utente continuerà a essere qualificato per gli [!UICONTROL trait] e [!UICONTROL segments] originali se ripeterà il proprio comportamento.
