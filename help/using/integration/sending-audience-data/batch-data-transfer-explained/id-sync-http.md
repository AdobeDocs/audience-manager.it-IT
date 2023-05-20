---
description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra un fornitore e un Audience Manager. La sincronizzazione ID può iniziare dopo l’invio della tassonomia dei dati all’Audience Manager.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: Sincronizzazione ID per trasferimenti di dati in entrata
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 9%

---

# Sincronizzazione ID per trasferimenti di dati in entrata {#id-synchronization-for-inbound-data-transfers}

Descrive la sintassi e i parametri utilizzati nella `HTTP` chiamata per sincronizzare gli ID utente tra un fornitore e [!DNL Audience Manager]. La sincronizzazione ID può iniziare dopo l’invio della tassonomia dei dati a [!DNL Audience Manager].

La sincronizzazione ID è il primo passaggio del processo di trasferimento dati in entrata e asincrono. In questo passaggio, [!DNL Audience Manager] e il fornitore confronta e abbina gli ID per i rispettivi visitatori del sito. Ad esempio, un’ [!DNL Audience Manager] Il cliente potrebbe conoscere un utente in base all’ID 123. Tuttavia, il tuo partner dati potrebbe identificare questo utente con l’ID 456. Il processo di sincronizzazione [!DNL Audience Manager] e un fornitore di dati per riconciliare questi diversi ID e identificare gli utenti nei rispettivi sistemi. Una volta completato, [!DNL Audience Manager] e il tuo partner di terze parti deve avere gli ID corrispondenti per ogni utente univoco visualizzato sulle nostre reti.

Puoi utilizzare i seguenti metodi per inserire i dati in [!DNL Audience Manager]:

* [Richiesta HTTP di sincronizzazione ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Evento ID dichiarato](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Sincronizzazione ID da un&#39;immagine incorporata in un messaggio e-mail](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## Sincronizzazione ID `HTTP` Richiesta {#id-sync-http}

In uno scambio di ID, una [!DNL URL] la stringa deve essere simile alla seguente:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

Il [!DNL URL] per la chiamata di sincronizzazione ID in entrata deve contenere le variabili descritte nella tabella seguente.

>[!NOTE]
>
>Sostituisci il contenuto in corsivo con i valori effettivi dei parametri.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>ID univoco del provider di contenuti (assegnato da <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (percentuale) Rappresentazione codificata dell’ID utente univoco. Oltre ai caratteri ASCII riservati, tutti i caratteri non ASCII devono essere codificati in percentuale in base alla tabella di codifica dei caratteri UTF-8. </p> <p>Per ulteriori informazioni, vedere <a href="https://www.url-encode-decode.com" format="http" scope="external"> Codifica/Decodifica URL online</a> sito Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Reindirizzamento URL codificato con la macro <code> ${DD_UUID}</code> incorporato al suo interno. </p> <p>Nota: aggiunto solo quando il provider di contenuti avvia la chiamata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facoltativo. Aggiungi questo parametro se utilizzi il <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Plug-in di Audience Manager per IAB TCF.</a></p> <p><code> gdpr</code> può essere 0 (non si applica il RGPD) o 1 (si applica il RGPD). </p> <p> <b>Nota:</b> Questo parametro può essere utilizzato solo insieme a <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facoltativo. Aggiungi questo parametro se utilizzi il <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Plug-in di Audience Manager per IAB TCF.</a></p> <p><code>gdpr_consent</code> è la stringa di consenso RGPD con codifica URL-safe base64 (vedi <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> Specifica IAB</a>). </p> <p> <b>Nota:</b> Questo parametro può essere utilizzato solo insieme a <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Evento {#declared-id-event}

Per ulteriori informazioni, consulta [ID dichiarati](../../../features/declared-ids.md).

## Sincronizzazione ID da un&#39;immagine incorporata in un messaggio e-mail {#id-sync-email-image}

Il formato per gli ID corrispondenti tramite un’immagine e-mail è lo stesso mostrato sopra. Tuttavia, affinché questo funzioni, le immagini in un messaggio e-mail devono essere abilitate. Questo può influire sulla sincronizzazione ID tramite e-mail perché la maggior parte dei sistemi di posta disabilita le immagini per impostazione predefinita.

>[!MORELIKETHIS]
>
>* [Componenti di raccolta dei dati](../../../reference/system-components/components-data-collection.md)

