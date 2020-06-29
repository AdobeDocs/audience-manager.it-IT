---
description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra  Audience Manager e un provider di dati di terze parti. Contatta il tuo consulente  Adobe Audience Manager prima di tentare la tua prima sincronizzazione ID.
seo-description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra  Audience Manager e un provider di dati di terze parti. Contatta il tuo consulente  Adobe Audience Manager prima di tentare la tua prima sincronizzazione ID.
seo-title: Sincronizzazione ID per trasferimenti di dati in uscita
solution: Audience Manager
title: Sincronizzazione ID per trasferimenti di dati in uscita
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 4%

---


# Sincronizzazione ID per trasferimenti di dati in uscita{#id-synchronization-for-outbound-data-transfers}

Descrive la sintassi e i parametri utilizzati nella `HTTP` chiamata iniziale per sincronizzare gli ID utente tra  Audience Manager e un provider di dati di terze parti. Contatta il tuo consulente  Adobe Audience Manager prima di tentare la tua prima sincronizzazione ID.

<!-- c_id_sync_out.xml -->

## Scopo della sincronizzazione ID

La sincronizzazione ID è il primo passo del processo di trasferimento dati asincrono in uscita. In questo passaggio, [!DNL Audience Manager] e il fornitore confrontano e confrontano gli ID per i rispettivi visitatori del sito. Ad esempio, un [!DNL Audience Manager] cliente potrebbe conoscere un utente per ID 123. Tuttavia, il partner dati potrebbe identificare questo utente con l’ID 456. Il processo di sincronizzazione consente a un fornitore [!DNL Audience Manager] di dati di riconciliare questi diversi ID e identificare gli utenti nei rispettivi sistemi. Una volta completati, [!DNL Audience Manager] e il provider di dati di terze parti dovrebbe avere gli ID corrispondenti per ogni utente unico visto sulle nostre reti.

## Sintassi URL

In uno scambio di ID, una [!DNL URL] stringa formattata correttamente deve essere simile alla seguente:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parametri URL

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
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">ID univoco per il provider di dati (assegnato da <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> ID utente univoco. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Un URL codificato viene reindirizzato con la macro <code> ${DD_UUID}</code> incorporata al suo interno. <p><b>Nota:</b> Aggiunto solo quando il provider di dati avvia la chiamata. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> può essere 0 (non si applica il GDPR) o 1 (si applica il GDPR).</p><p><b>Nota:</b> <ul><li>I parametri <code>gdpr</code> e <code>gdpr_consent</code> i parametri vengono implementati gradualmente negli URL di sincronizzazione ID con i partner di attivazione. Consulta Partner di attivazione che supportano IAB TCF in <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in per IAB TCF.</a></li><li>Questo parametro può essere utilizzato solo insieme a <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> è la stringa di consenso GDPR con codifica URL-safe base64 (consultate la specifica <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"></a>IAB).</p><p><b>Nota:</b> Questo parametro può essere utilizzato solo insieme a <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Metodi e codice API per Data Collection Server (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componenti per la raccolta dati](../../reference/system-components/components-data-collection.md)

