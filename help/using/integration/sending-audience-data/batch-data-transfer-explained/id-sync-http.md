---
description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra un fornitore e  Audience Manager. La sincronizzazione ID può iniziare dopo l’invio della tassonomia dei dati ad  Audience Manager.
seo-description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra un fornitore e  Audience Manager. La sincronizzazione ID può iniziare dopo l’invio della tassonomia dei dati ad  Audience Manager.
seo-title: Sincronizzazione ID per trasferimenti di dati in entrata
solution: Audience Manager
title: Sincronizzazione ID per trasferimenti di dati in entrata
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 3%

---


# Sincronizzazione ID per trasferimenti di dati in entrata {#id-synchronization-for-inbound-data-transfers}

Descrive la sintassi e i parametri utilizzati nella `HTTP` chiamata iniziale per sincronizzare gli ID utente tra un fornitore e [!DNL Audience Manager]. La sincronizzazione ID può iniziare dopo l’invio della tassonomia dei dati a [!DNL Audience Manager].

La sincronizzazione ID è il primo passo del processo di trasferimento dati in entrata e asincrono. In questo passaggio, [!DNL Audience Manager] e il fornitore confrontano e confrontano gli ID per i rispettivi visitatori del sito. Ad esempio, un [!DNL Audience Manager] cliente potrebbe conoscere un utente per ID 123. Tuttavia, il partner dati potrebbe identificare questo utente con l’ID 456. Il processo di sincronizzazione consente a un fornitore [!DNL Audience Manager] di dati di riconciliare questi diversi ID e identificare gli utenti nei rispettivi sistemi. Una volta completati, [!DNL Audience Manager] e il tuo partner di terze parti dovrebbe avere gli ID corrispondenti per ogni utente unico visualizzato sulle nostre reti.

Per inserire i dati in [!DNL Audience Manager], è possibile utilizzare i metodi seguenti:

* [Richiesta HTTP di sincronizzazione ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Evento ID dichiarato](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Sincronizzazione ID da un’immagine incorporata per e-mail](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## Richiesta di sincronizzazione ID `HTTP` {#id-sync-http}

In uno scambio di ID, una [!DNL URL] stringa formattata correttamente deve essere simile alla seguente:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

La chiamata [!DNL URL] per la sincronizzazione ID in entrata deve contenere le variabili descritte nella tabella seguente.

>[!NOTE]
>
>Sostituire il contenuto in corsivo con valori di parametro effettivi.

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
   <td colname="col2"> <p>ID univoco per il fornitore del contenuto (assegnato da <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (percentuale) Rappresentazione codificata dell’ID utente univoco. Oltre alla codifica di caratteri ASCII riservati, tutti i caratteri non ASCII devono essere codificati in percentuale in base alla tabella di codifica dei caratteri UTF-8. </p> <p>Per ulteriori informazioni, consultate il sito Web <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Un URL codificato viene reindirizzato con la macro <code> ${DD_UUID}</code> incorporata al suo interno. </p> <p>Nota:  Aggiunto solo quando il fornitore del contenuto avvia la chiamata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facoltativo. Aggiungete questo parametro se utilizzate il plug-in <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager per IAB TCF.</a></p> <p><code> gdpr</code> può essere 0 (non si applica il GDPR) o 1 (si applica il GDPR). </p> <p> <b>Nota:</b> Questo parametro può essere utilizzato solo insieme a <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facoltativo. Aggiungete questo parametro se utilizzate il plug-in <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager per IAB TCF.</a></p> <p><code>gdpr_consent</code> è la stringa di consenso GDPR con codifica URL-safe base64 (consultate la specifica <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"></a>IAB). </p> <p> <b>Nota:</b> Questo parametro può essere utilizzato solo insieme a <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Evento {#declared-id-event}

Per ulteriori informazioni, vedi ID [dichiarati](../../../features/declared-ids.md).

## Sincronizzazione ID da un’immagine incorporata per e-mail {#id-sync-email-image}

Il formato per gli ID corrispondenti tramite un&#39;immagine e-mail è lo stesso mostrato sopra. Tuttavia, le immagini contenute in un messaggio e-mail devono essere abilitate affinché questo funzioni. Questo può influenzare la sincronizzazione ID tramite e-mail perché la maggior parte dei sistemi di posta elettronica disattiva le immagini per impostazione predefinita.

>[!MORELIKETHIS]
>
>* [Componenti per la raccolta dati](../../../reference/system-components/components-data-collection.md)

