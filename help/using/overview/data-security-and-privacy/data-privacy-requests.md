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

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

Prima di leggere questo articolo, consigliamo di consultare il [RGPD Glossary](../data-security-and-privacy/aam-gdpr-glossary.md) e il [CCPA Glossary](aam-ccpa-glossary.md) per comprendere meglio la terminologia utilizzata.

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* Tramite la [Privacy Service UI](https://privacyui.cloud.adobe.io/). Consulta la documentazione [qui](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Attraverso la **[!DNL Privacy Service API]**. Consulta la documentazione [qui](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[!DNL API] e il riferimento [qui](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)** section, along with their respective namespace IDs (data source IDs).

[Privacy Service](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html) supporta due tipi di richieste: richieste di accesso ai dati e di cancellazione dei dati.

## Richieste di accesso ai dati {#access-data}

You can send individual data access requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La [Privacy Service UI](https://privacyui.cloud.adobe.io/) consente di creare nuove richieste di processi utilizzando il [!UICONTROL Request Builder] o caricando un file [!DNL JSON].

Per visualizzare l’aspetto di un file [!DNL JSON] valido, puoi [ scaricare un file JSON di esempio](../data-security-and-privacy/assets/access_request.json).

Comprendiamo il tuo impegno a soddisfare le richieste sulla privacy dei dati entro il termine stabilito dalla normativa.

## Richieste di cancellazione dei dati {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

La [Privacy Service UI](https://privacyui.cloud.adobe.io/) consente di creare nuove richieste di processi utilizzando il [!UICONTROL Request Builder] o caricando un file [!DNL JSON].

Per visualizzare l’aspetto di un file [!DNL JSON] valido, puoi [ scaricare un file JSON di esempio](../data-security-and-privacy/assets/access_request.json).

Adobe comprende il tuo impegno a soddisfare le richieste dei clienti sulla privacy dei dati entro 30 giorni. For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

Quando invii ID dichiarati, come ID [!DNL CRM] di più dispositivi o ID di , nelle richieste sulla privacy dei dati,  eseguirà la cancellazione necessaria su tutti i dispositivi collegati (fino a 100 dispositivi per ID dichiarato).[!DNL cookie][!DNL Audience Manager]

[!DNL Audience Manager] tenta di avvisare i partner di attivazione riguardo le richieste di cancellazione inviando loro informazioni di rimozione dai segmenti per gli interessati che richiedono la cancellazione di determinati dati. Tuttavia, alcuni partner di attivazione:

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

In questi casi, non puoi inviare le richieste di cancellazione ai partner di attivazione in modo automatico tramite [!DNL Audience Manager].

Scarica il nostro [foglio Excel dei partner](assets/AAM-Partners-October2019.xlsx) per vedere quali partner di attivazione di supportano la rimozione dai segmenti.[!DNL Audience Manager]

## Richieste di rinuncia {#opt-out-requests}

[!DNL Audience Manager] sostiene gli standard a livello di settore per quanto riguarda la gestione del rifiuto. Continua a leggere per informazioni complete sui tipi di rinuncia supportati da [!DNL Audience Manager].

While data access and deletion requests are handled through the [Privacy Service](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html), opt-out requests are currently supported through the [!DNL DCS API]. Read on to learn what the opt-out [!DNL API] calls should look like.

### Richieste di rinuncia globale

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. Nella tabella seguente sono elencati i metodi utilizzati per la rinuncia globale:

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
   <td colname="col2"> <p>La <a href="https://www.adobe.com/it/privacy/opt-out.html#customeruse" format="http" scope="external">pagina relativa alle scelte sulla privacy</a> fornisce funzionalità con 1 clic che consentono agli utenti finali di controllare e rinunciare alla raccolta di dati da parte delle soluzioni pubblicitarie Adobe Experience Cloud (incluso Audience Manager). Nello specifico, consulta la <a href="https://www.adobe.com/it/privacy/opt-out.html#customeruse" format="http" scope="external">sezione per i clienti aziendali</a> della pagina relativa alle scelte sulla privacy. </p> </td> 
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

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

A seguito di una rinuncia a livello di partner con una chiamata di ID dichiarato:

* L’[ID del sistema di gestione delle relazioni con i clienti](../../reference/ids-in-aam.md) è escluso dalla raccolta dei dati;
* L’ultimo ID dispositivo ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) collegato all’[ID del sistema di gestione delle relazioni con i clienti](../../reference/ids-in-aam.md) viene escluso dalla raccolta dati.
* [!DNL Audience Manager] cesseranno tutte le attività di raccolta, segmentazione o attivazione dei dati in corso per l&#39; [!DNL CRM] ID e l&#39;ultimo ID dispositivo collegato all&#39; [!DNL CRM] ID;
* [!DNL Audience Manager] separa l’ID [!DNL CRM] di rinuncia e l’ultimo ID dispositivo da tutti i segmenti;
* [!UICONTROL Destination] i partner ricevono la richiesta di segmento per l’ [!DNL CRM] ID e l’ultimo ID dispositivo. La rimozione dai segmenti funziona sia per le destinazioni [in tempo reale](data-privacy-requests.md#aam-partners-with-unsegmentation) che per quelle batch.
* Nessun dato storico viene eliminato.

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

Puoi effettuare una richiesta di rinuncia con ID dichiarato con le coppie chiave-valore `d_cid` e `d_cid_ic`. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consulta [CID Replaces DPID and DPUUID](../../reference/cid.md). Negli esempi, il *corsivo* indica un segnaposto variabile.

#### Opzione di rifiuto con [!DNL CID] e [!DNL CID_IC]

Per una descrizione e una sintassi, consulta [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| Rinuncia tramite | Esempio di codice |
|--- |--- |
| Un ID provider di dati e un ID utente. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Un codice di integrazione e un ID utente. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Più coppie `d_cid` e `d_cid_ic` chiave-valore. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Rinuncia a livello di partner con chiamate ID dispositivo

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. Puoi rinunciare alla raccolta di dati su un determinato ID dispositivo per un brand effettuando le seguenti chiamate all’[API DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Rinuncia tramite | Esempio di codice |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Ulteriori informazioni su `uuid`, `mid` e `imsOrgId` sono disponibili in [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

In seguito a una rinuncia a livello di partner con una chiamata ID dispositivo:

* L’ID dispositivo viene escluso dalla raccolta dati.
* [!DNL Audience Manager] cessa tutte le attività future di raccolta, segmentazione o attivazione dei dati da parte del partner per l’ID dispositivo.
* [!DNL Audience Manager] separa l&#39;ID dispositivo da tutti i segmenti;
* I partner di destinazione ricevono la richiesta di rimozione dai segmenti per l’ID dispositivo. La rimozione dai segmenti funziona sia per le destinazioni [in tempo reale](data-privacy-requests.md#aam-partners-with-unsegmentation) che per quelle batch.
* Nessun dato storico viene eliminato.

## [!DNL Audience Manager] Partner Con Funzionalità Di Dissegmentazione {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

Tuttavia, alcuni dei nostri partner di attivazione:

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

In questi casi, non puoi inviare le richieste di cancellazione ai partner di attivazione in modo automatico tramite [!DNL Audience Manager].

Consulta l’[elenco delle destinazioni basate su dispositivi](/help/using/features/destinations/device-based-destinations-list.md) per vedere quali partner di attivazione di supportano la rimozione dai segmenti.[!DNL Audience Manager]

## Richieste di correzione dei dati {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] i clienti possono scegliere di acquisire i segnali/caratteristiche/segmenti rilevanti in base ai profili utente e inviare tali informazioni tramite l&#39;inserimento [di dati](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) offline a [!DNL Audience Manager]. Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.
