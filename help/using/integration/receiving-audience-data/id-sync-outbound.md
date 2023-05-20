---
description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra Audience Manager e un provider di dati di terze parti. Contatta il tuo consulente Adobe Audience Manager prima di tentare la prima sincronizzazione ID.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: Sincronizzazione ID per trasferimenti di dati in uscita
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 14%

---

# Sincronizzazione ID per trasferimenti di dati in uscita{#id-synchronization-for-outbound-data-transfers}

Descrive la sintassi e i parametri utilizzati nella `HTTP` Chiamata per sincronizzare gli ID utente tra Audience Manager e un provider di dati di terze parti. Contatta il tuo consulente Adobe Audience Manager prima di tentare la prima sincronizzazione ID.

<!-- c_id_sync_out.xml -->

## Scopo della sincronizzazione ID

La sincronizzazione ID è il primo passaggio del processo di trasferimento dati in uscita e asincrono. In questo passaggio, [!DNL Audience Manager] e il fornitore confronta e abbina gli ID per i rispettivi visitatori del sito. Ad esempio, un’ [!DNL Audience Manager] Il cliente potrebbe conoscere un utente in base all’ID 123. Tuttavia, il tuo partner dati potrebbe identificare questo utente con l’ID 456. Il processo di sincronizzazione [!DNL Audience Manager] e un fornitore di dati per riconciliare questi diversi ID e identificare gli utenti nei rispettivi sistemi. Una volta completato, [!DNL Audience Manager] e il provider di dati di terze parti deve avere gli ID corrispondenti per ogni utente univoco visualizzato sulle nostre reti.

## Sintassi URL

In uno scambio di ID, una [!DNL URL] la stringa deve essere simile alla seguente:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parametri URL

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
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">ID univoco del provider di dati (assegnato da <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> ID utente univoco. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Reindirizzamento URL codificato con la macro <code> ${DD_UUID}</code> incorporato al suo interno. <p><b>Nota:</b> Aggiunto solo quando il provider di dati avvia la chiamata. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> può essere 0 (non si applica il RGPD) o 1 (si applica il RGPD).</p><p><b>Nota:</b> <ul><li>Il <code>gdpr</code> e <code>gdpr_consent</code> I parametri vengono gradualmente implementati negli URL di sincronizzazione ID con i partner di attivazione. Consulta Partner di attivazione che supportano IAB TCF in <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Plug-in di Audience Manager per IAB TCF.</a></li><li>Questo parametro può essere utilizzato solo insieme a <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> è la stringa di consenso RGPD con codifica URL-safe base64 (vedi <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> Specifica IAB</a>).</p><p><b>Nota:</b> Questo parametro può essere utilizzato solo insieme a <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Metodi e codice dell’API Data Collection Server (DCS) ](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componenti di raccolta dei dati](../../reference/system-components/components-data-collection.md)

