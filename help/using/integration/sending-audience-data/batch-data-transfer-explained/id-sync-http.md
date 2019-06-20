---
description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra un fornitore e Audience Manager. La sincronizzazione degli ID può iniziare dopo aver inviato la tassonomia di dati ad Audience Manager.
seo-description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra un fornitore e Audience Manager. La sincronizzazione degli ID può iniziare dopo aver inviato la tassonomia di dati ad Audience Manager.
seo-title: Sincronizzazione ID per trasferimenti di dati in entrata
solution: Audience Manager
title: Sincronizzazione ID per trasferimenti di dati in entrata
uuid: 037 e 74 a 6-acfd -4 cef-b 693-16 b 7 aaa 8 e 976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# Sincronizzazione ID per trasferimenti di dati in entrata{#id-synchronization-for-inbound-data-transfers}

Descrive la sintassi e i parametri utilizzati nella chiamata iniziale `HTTP` per sincronizzare gli ID utente tra un fornitore e Audience Manager. La sincronizzazione degli ID può iniziare dopo aver inviato la tassonomia di dati ad Audience Manager.

<!-- c_id_sync_in.xml -->

La sincronizzazione ID è il primo passaggio nel processo di trasferimento dei dati in ingresso e asincrono. In questo passaggio, Audience Manager e il fornitore confrontano e confrontano gli ID per i rispettivi visitatori del sito. Ad esempio, un [!DNL Audience Manager] cliente potrebbe conoscere un utente per ID 123. Tuttavia, il tuo partner dati potrebbe identificare questo utente con ID 456. Il processo di sincronizzazione consente [!DNL Audience Manager] a un fornitore di dati di riconciliare i diversi ID e identificare gli utenti nei rispettivi sistemi. Una volta completato, [!DNL Audience Manager] il tuo partner di terze parti deve avere ID corrispondenti per ogni utente unico visualizzato sulle nostre reti.

Per ottenere i dati in [!DNL Audience Manager]:

* [Richiesta HTTP sincronizzazione ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Evento ID dichiarato](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Sincronizzazione ID da un&#39;immagine incorporata e-mail](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## Richiesta sincronizzazione `HTTP` ID {#id-sync-http}

In uno scambio ID, una stringa formattata [!DNL URL] correttamente deve essere simile al seguente:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

La [!DNL URL] chiamata per la sincronizzazione ID in entrata deve contenere variabili descritte nella tabella seguente.

>[!NOTE]
>
>Sostituisce il contenuto in corsivo con i valori effettivi dei parametri.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code><i>&lt; ID_ ID &gt;</i></code> </td> 
   <td colname="col2"> <p>ID univoco per il fornitore di contenuti (assegnato da <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; ID_ UUID &gt;</i></code> </td> 
   <td colname="col2"> <p>URL (Percent (Percentuale)) Rappresentazione codificata dell'ID utente univoco. Oltre a codificare caratteri ASCII riservati, tutti i caratteri non ASCII devono essere codificati in base alla tabella di codifica caratteri UTF -8. </p> <p>Per ulteriori informazioni, consulta il sito Web Codifica <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL/Decode Online</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2"> <p>Un URL codificato viene reindirizzato con la macro <code> $ {DD_ UUID}</code> incorporata al suo interno. </p> <p>Nota: Aggiunto solo quando il fornitore del contenuto avvia la chiamata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p>Facoltativo. Aggiungete questo parametro se utilizzate il plug-in <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager per IAB TCF.</a></p> <p><code> gdpr</code> can be 0 (GDPR does not apply) or 1 (GDPR apply). </p> <p> <b>Nota:</b> Questo parametro può essere utilizzato solo insieme a <code>gdpr_ permission</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_ permission = &lt; STRING STRING &gt;</i></code> </td> 
   <td colname="col2"> <p>Facoltativo. Aggiungete questo parametro se utilizzate il plug-in <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager per IAB TCF.</a></p> <p><code>gdpr_ permission</code> is the URL-safe party 64-encoded GDPR permission string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>). </p> <p> <b>Nota:</b> Questo parametro può essere utilizzato solo insieme a <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Evento ID dichiarato {#declared-id-event}

Per ulteriori informazioni, vedi [ID dichiarati](../../../features/declared-ids.md).

## Sincronizzazione ID da un&#39;immagine incorporata e-mail {#id-sync-email-image}

Il formato degli ID corrispondenti tramite un&#39;immagine e-mail è lo stesso illustrato sopra. Tuttavia, per poter funzionare è necessario abilitare le immagini in un&#39;e-mail. Questo può influire sulla sincronizzazione ID tramite e-mail perché la maggior parte dei sistemi di posta elettronica disattiva le immagini per impostazione predefinita.

>[!MORE_ LIKE_ THIS]
>
>* [Componenti raccolta dati](../../../reference/system-components/components-data-collection.md)

