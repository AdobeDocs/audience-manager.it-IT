---
description: Questo documento illustra gli aspetti tecnici relativi alla conformità alle normative sulla privacy dei dati per Audience Manager.
seo-description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-title: Data Privacy Requests
solution: Audience Manager
keywords: Interfaccia utente RGPD, API RGPD, CCPA, privacy
title: Richieste sulla privacy dei dati
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
source-git-commit: 6b43885deddb0cdaeb3698051ea110f0a4eed44e
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 42%

---

# Richieste sulla privacy dei dati {#data-privacy-requests}

## Panoramica {#overview}

Questo documento fornisce una panoramica sulla gestione della privacy dei dati e delle richieste di rinuncia di singoli utenti che puoi inviare a [!DNL Audience Manager] tramite [l&#39;interfaccia utente Privacy Service](https://privacyui.cloud.adobe.io/) e **[!DNL Privacy Service API]**.

Questi strumenti ti consentono di inviare richieste sulla privacy dei dati dei consumatori effettuate in [!DNL GDPR] e [!DNL CCPA].

Prima di leggere questo articolo, consigliamo di consultare il [RGPD Glossary](../data-security-and-privacy/aam-gdpr-glossary.md) e il [CCPA Glossary](aam-ccpa-glossary.md) per comprendere meglio la terminologia utilizzata.

È possibile inviare singole richieste per accedere ed eliminare i dati dei consumatori da [!DNL Audience Manager] in due modi:

* Tramite la [Privacy Service UI](https://privacyui.cloud.adobe.io/). Consulta la documentazione [qui](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Attraverso la **[!DNL Privacy Service API]**. Consulta la documentazione [qui](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it) e il riferimento [!DNL API] [qui](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

Quando invii richieste sulla privacy dei dati di singoli utenti, puoi inviare qualsiasi [!DNL Audience Manager] identificatore (ID), come descritto nella sezione **[Audience Manager Identifiers](data-privacy-ids.md)**, insieme ai rispettivi ID dei namespace (ID dell&#39;origine dati).

[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it) supporta due tipi di richieste: richieste di accesso ai dati e di cancellazione dei dati.

## Richieste di accesso ai dati {#access-data}

Puoi inviare singole richieste di accesso ai dati tramite la [interfaccia utente Privacy Service](https://privacyui.cloud.adobe.io) (documentazione [qui](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=it) o chiamando l&#39;API Privacy Service (documentazione [qui](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it) e [!DNL API] di riferimento [qui](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

La [Privacy Service UI](https://privacyui.cloud.adobe.io/) consente di creare nuove richieste di processi utilizzando il [!UICONTROL Request Builder] o caricando un file [!DNL JSON].

Per visualizzare l’aspetto di un file [!DNL JSON] valido, puoi [ scaricare un file JSON di esempio](../data-security-and-privacy/assets/access_request.json).

Comprendiamo il tuo impegno a soddisfare le richieste sulla privacy dei dati entro il termine stabilito dalla normativa.

## Richieste di cancellazione dei dati {#delete-data}

Puoi inviare richieste di eliminazione dei dati tramite la [interfaccia utente Privacy Service](https://privacyui.cloud.adobe.io) (documentazione [qui](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=it) o chiamando l&#39;API Privacy Service (documentazione [qui](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it) e [!DNL API] di riferimento [qui](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

La [Privacy Service UI](https://privacyui.cloud.adobe.io/) consente di creare nuove richieste di processi utilizzando il [!UICONTROL Request Builder] o caricando un file [!DNL JSON].

Per visualizzare l’aspetto di un file [!DNL JSON] valido, puoi [ scaricare un file JSON di esempio](../data-security-and-privacy/assets/access_request.json).

Adobe comprende il tuo impegno a soddisfare le richieste dei clienti sulla privacy dei dati entro 30 giorni. Per questo motivo, [!DNL Adobe] si impegna a elaborare la richiesta di eliminazione dei dati il prima possibile.

In risposta alle richieste di eliminazione dei dati del consumatore, [!DNL Audience Manager] elimina caratteristiche e segmenti associati all&#39;identificatore [!DNL Audience Manager] incluso nella richiesta. Inoltre, i rispettivi identificatori [!DNL Audience Manager] per il singolo utente che ha rinunciato all&#39;ulteriore raccolta di dati da parte di [!DNL Audience Manager] e le rispettive mappature ID verranno rimossi.

Quando invii ID dichiarati, come ID [!DNL CRM] multi-dispositivo o ID [!DNL cookie], nelle richieste di privacy dei dati, [!DNL Audience Manager] eseguirà l&#39;eliminazione necessaria su tutti i dispositivi collegati (fino a 100 dispositivi per ID dichiarato).

[!DNL Audience Manager] tenterà di informare i partner di attivazione delle richieste di eliminazione inviando loro informazioni di rimozione dai segmenti per gli interessati che richiedono l&#39;eliminazione di alcuni dati. Tuttavia, alcuni partner di attivazione:

1. Impossibile supportare richieste di rimozione dai segmenti (o rimozione di segmenti) da [!DNL Audience Manager] e/o
2. Impossibile ricevere aggiornamenti da [!DNL Audience Manager] con una frequenza inferiore a 30 giorni. In questi casi, i clienti [!DNL Audience Manager] non possono inviare le richieste di eliminazione ai partner di attivazione in modo automatico tramite [!DNL Audience Manager].

In questi casi, non è possibile inviare le richieste di eliminazione ai partner di attivazione in modo automatico tramite [!DNL Audience Manager].

Consulta la [documentazione sull&#39;elenco delle destinazioni basate su dispositivi](assets/AAM-Partners-October2019.xlsx) per vedere quali partner di attivazione di [!DNL Audience Manager] supportano la rimozione dai segmenti.

## Richieste di rinuncia {#opt-out-requests}

[!DNL Audience Manager] supporta gli standard di settore per la gestione delle rinunce. Continuare a leggere per informazioni complete sui tipi di rinuncia supportati da [!DNL Audience Manager].

Mentre le richieste di accesso e di eliminazione dei dati vengono gestite tramite [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it), le richieste di rinuncia sono attualmente supportate tramite [!DNL DCS API]. Continua a leggere per scoprire l&#39;aspetto delle chiamate di rinuncia [!DNL API].

### Richieste di rinuncia globale

La rinuncia globale rappresenta una rinuncia in [!DNL Audience Manager] e altre soluzioni [!DNL Adobe Experience Cloud] per tutti i marchi. Nella tabella seguente sono elencati i metodi utilizzati per la rinuncia globale:

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
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html?lang=it" format="https" scope="external">Dispositivi Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html?lang=it" format="https" scope="external">Dispositivi iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Gli utenti finali possono anche scegliere di rinunciare alla raccolta dati globale visitando i siti web dei nostri partner degli standard di settore.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

In seguito alle richieste di rinuncia descritte sopra:

* [!DNL Audience Manager] cesserà tutte le attività di raccolta, segmentazione o attivazione dei dati, purché l&#39;utente non cancelli i cookie del browser.
* I dati storici vengono rimossi dal profilo utente dopo 120 giorni.

### Rinuncia a livello di partner con chiamate di ID dichiarati

La rinuncia a livello di partner consente di rinunciare alla raccolta di dati da parte di partner [!DNL Audience Manager] specifici. Puoi inviare richieste di rinuncia a livello di partner per ID multi-dispositivo, inclusi [!DNL CRM] ID e indirizzi e-mail con hash.

A seguito di una rinuncia a livello di partner con una chiamata di ID dichiarato:

* L’[ID del sistema di gestione delle relazioni con i clienti](../../reference/ids-in-aam.md) è escluso dalla raccolta dei dati;
* L’ultimo ID dispositivo ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) collegato all’[ID del sistema di gestione delle relazioni con i clienti](../../reference/ids-in-aam.md) viene escluso dalla raccolta dati.
* [!DNL Audience Manager] cesserà tutte le attività di raccolta dati, segmentazione o attivazione in corso per l&#39;ID [!DNL CRM] e l&#39;ultimo ID dispositivo collegato all&#39;ID [!DNL CRM];
* [!DNL Audience Manager] rimuove da tutti i segmenti l&#39;ID [!DNL CRM] e l&#39;ultimo ID dispositivo per cui è stata eseguita la rinuncia;
* I partner [!UICONTROL Destination] ricevono la richiesta di rimozione dai segmenti per l&#39;ID [!DNL CRM] e l&#39;ultimo ID dispositivo. La rimozione dai segmenti funziona sia per le destinazioni [in tempo reale](data-privacy-requests.md#aam-partners-with-unsegmentation) che per quelle batch.
* Nessun dato storico viene eliminato.

Quando [!DNL Audience Manager] riceve una richiesta di rinuncia a livello di partner, [!DNL JSON] restituito da [!DNL DCS] contiene il [codice di errore 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), con il messaggio [!UICONTROL "Encountered opt out tag"], invece dell&#39;ID utente [!DNL Audience Manager].

Puoi effettuare una richiesta di rinuncia con ID dichiarato con le coppie chiave-valore `d_cid` e `d_cid_ic`. I parametri legacy come `d_dpid` e `d_dpuuid` funzionano comunque, ma sono considerati obsoleti. Consulta [CID Replaces DPID and DPUUID](../../reference/cid.md). Negli esempi, il *corsivo* indica un segnaposto variabile.

#### Rinuncia con [!DNL CID] e [!DNL CID_IC]

Per una descrizione e una sintassi, consulta [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| Rinuncia tramite | Esempio di codice |
|--- |--- |
| Un ID provider di dati e un ID utente. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Un codice di integrazione e un ID utente. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Più coppie chiave-valore `d_cid` e `d_cid_ic`. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Rinuncia a livello di partner con chiamate ID dispositivo

La rinuncia a livello di partner consente di rinunciare alla raccolta di dati da parte di partner [!DNL Audience Manager] specifici. Puoi rinunciare alla raccolta di dati su un determinato ID dispositivo per un brand effettuando le seguenti chiamate all’[API DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Rinuncia tramite | Esempio di codice |
|--- |--- |
| Un [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un ID [!DNL Experience Cloud] (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Ulteriori informazioni su `uuid`, `mid` e `imsOrgId` sono disponibili in [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

In seguito a una rinuncia a livello di partner con una chiamata ID dispositivo:

* L’ID dispositivo viene escluso dalla raccolta dati.
* [!DNL Audience Manager] cesserà tutte le attività di raccolta dati, segmentazione o attivazione, per il partner, andando avanti per l&#39;ID dispositivo.
* [!DNL Audience Manager] rimuove l&#39;ID dispositivo da tutti i segmenti;
* I partner di destinazione ricevono la richiesta di rimozione dai segmenti per l’ID dispositivo. La rimozione dai segmenti funziona sia per le destinazioni [in tempo reale](data-privacy-requests.md#aam-partners-with-unsegmentation) che per quelle batch.
* Nessun dato storico viene eliminato.

## [!DNL Audience Manager] Partner Con Funzionalità Di Rimozione Dai Segmenti {#aam-partners-with-unsegmentation}

Per facilitare l&#39;automazione delle richieste sulla privacy dei dati dei consumatori, [!DNL Audience Manager] tenterà di avvisare i partner di attivazione delle richieste di eliminazione da parte degli interessati inviando loro informazioni di rimozione dai segmenti (o rimozione dei segmenti).

Tuttavia, alcuni dei nostri partner di attivazione:

1. Impossibile supportare richieste di rimozione dai segmenti da [!DNL Audience Manager] e/o
2. Impossibile ricevere aggiornamenti da [!DNL Audience Manager] più di una volta ogni 30 giorni.

In questi casi, non è possibile inviare le richieste di eliminazione ai partner di attivazione in modo automatico tramite [!DNL Audience Manager].

Consulta l&#39;[elenco di destinazioni basate su dispositivi](/help/using/features/destinations/device-based-destinations-list.md) per vedere quali partner di attivazione di [!DNL Audience Manager] supportano la rimozione dai segmenti.

## Richieste di correzione dei dati {#correction}

Dato che [!DNL Audience Manager] non è l&#39;origine dei dati, esiste un ruolo limitato per la correzione dei dati in [!DNL Audience Manager]. La correzione potrebbe significare che il consumatore ha richiesto l&#39;annullamento della qualifica per un [!UICONTROL trait]/[!UICONTROL segment] non corretto o la qualificazione per il [!UICONTROL trait]/[!UICONTROL segment] desiderato.

I clienti [!DNL Audience Manager] possono scegliere di acquisire segnali/caratteristiche/segmenti rilevanti in base ai profili utente e inviare tali informazioni tramite [acquisizione dati offline](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) in [!DNL Audience Manager]. L&#39;utente continuerà a essere qualificato per l&#39;originale [!UICONTROL trait] e [!UICONTROL segments] se ripeterà il proprio comportamento.
