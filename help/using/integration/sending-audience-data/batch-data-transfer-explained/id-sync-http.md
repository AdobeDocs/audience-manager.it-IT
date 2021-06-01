---
description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra un fornitore e un Audience Manager. La sincronizzazione ID può iniziare dopo l’invio ad Audience Manager della tassonomia dei dati.
seo-description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra un fornitore e un Audience Manager. La sincronizzazione ID può iniziare dopo l’invio ad Audience Manager della tassonomia dei dati.
seo-title: Sincronizzazione ID per trasferimenti di dati in entrata
solution: Audience Manager
title: Sincronizzazione ID per trasferimenti di dati in entrata
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Trasferimenti di dati in entrata
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 9%

---

# Sincronizzazione ID per trasferimenti di dati in entrata {#id-synchronization-for-inbound-data-transfers}

Descrive la sintassi e i parametri utilizzati nella chiamata iniziale `HTTP` per sincronizzare gli ID utente tra un fornitore e [!DNL Audience Manager]. La sincronizzazione ID può iniziare dopo l’invio della tassonomia dei dati a [!DNL Audience Manager].

La sincronizzazione ID è il primo passaggio del processo di trasferimento dati in entrata e asincrono. In questo passaggio, [!DNL Audience Manager] e il fornitore confrontano e confrontano gli ID per i rispettivi visitatori del sito. Ad esempio, un cliente [!DNL Audience Manager] potrebbe conoscere un utente in base all’ID 123. Tuttavia, il tuo partner dati potrebbe identificare questo utente con l’ID 456. Il processo di sincronizzazione consente a [!DNL Audience Manager] e a un fornitore di dati di riconciliare questi diversi ID e identificare gli utenti nei rispettivi sistemi. Una volta completati, [!DNL Audience Manager] e il tuo partner di terze parti devono avere gli ID corrispondenti per ogni utente univoco visualizzato sulle nostre reti.

Puoi utilizzare i seguenti metodi per ottenere i dati in [!DNL Audience Manager]:

* [Richiesta HTTP di sincronizzazione ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Evento ID dichiarato](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Sincronizzazione ID da un&#39;immagine incorporata e-mail](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## Sincronizzazione ID `HTTP` Richiesta {#id-sync-http}

In uno scambio di ID, una stringa [!DNL URL] formattata correttamente deve avere l&#39;aspetto seguente:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

La [!DNL URL] per la chiamata di sincronizzazione ID in entrata deve contenere le variabili descritte nella tabella seguente.

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
   <td colname="col2"> <p>ID univoco per il provider di contenuti (assegnato da <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (percentuale): rappresentazione codificata dell’ID utente univoco. Oltre alla codifica di caratteri ASCII riservati, tutti i caratteri non ASCII devono essere codificati in percentuale in base alla tabella di codifica dei caratteri UTF-8. </p> <p>Per ulteriori informazioni, consulta il sito web <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Un URL codificato reindirizzato con la macro <code> ${DD_UUID}</code> incorporata al suo interno. </p> <p>Nota:  È stato aggiunto solo quando il provider di contenuti avvia la chiamata . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facoltativo. Aggiungi questo parametro se utilizzi il plug-in di Audience Manager <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">per IAB TCF.</a></p> <p><code> gdpr</code> può essere 0 (non si applica il RGPD) o 1 (si applica il RGPD). </p> <p> <b>Nota:</b> questo parametro può essere utilizzato solo insieme a  <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facoltativo. Aggiungi questo parametro se utilizzi il plug-in di Audience Manager <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">per IAB TCF.</a></p> <p><code>gdpr_consent</code> è la stringa di consenso RGPD con codifica URL-safe base64 (consulta <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> specifiche IAB</a>). </p> <p> <b>Nota:</b> questo parametro può essere utilizzato solo insieme a  <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Evento {#declared-id-event}

Per ulteriori informazioni, consulta [ID dichiarati](../../../features/declared-ids.md).

## Sincronizzazione ID da un&#39;immagine incorporata per e-mail {#id-sync-email-image}

Il formato per gli ID corrispondenti tramite un’immagine e-mail è lo stesso mostrato sopra. Tieni presente, tuttavia, che affinché questo funzioni è necessario abilitare le immagini in un messaggio e-mail. Questo può influenzare la sincronizzazione ID tramite e-mail perché la maggior parte dei sistemi di posta disabilitano le immagini per impostazione predefinita.

>[!MORELIKETHIS]
>
>* [Componenti di raccolta dei dati](../../../reference/system-components/components-data-collection.md)

