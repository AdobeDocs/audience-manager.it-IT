---
description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra Audience Manager e un provider di dati terze parti. Contatta il tuo consulente Adobe Audience Manager prima di tentare la prima sincronizzazione ID.
seo-description: Descrive la sintassi e i parametri utilizzati nella chiamata HTTP iniziale per sincronizzare gli ID utente tra Audience Manager e un provider di dati terze parti. Contatta il tuo consulente Adobe Audience Manager prima di tentare la prima sincronizzazione ID.
seo-title: Sincronizzazione ID per trasferimenti di dati in uscita
solution: Audience Manager
title: Sincronizzazione ID per trasferimenti di dati in uscita
uuid: f 3849 be 8-1094-47 db -9296-7482 f 020 af 18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# Sincronizzazione ID per trasferimenti di dati in uscita{#id-synchronization-for-outbound-data-transfers}

Descrive la sintassi e i parametri utilizzati nella chiamata iniziale `HTTP` per sincronizzare gli ID utente tra Audience Manager e un provider di dati terze parti. Contatta il tuo consulente Adobe Audience Manager prima di tentare la prima sincronizzazione ID.

<!-- c_id_sync_out.xml -->

## Scopo della sincronizzazione ID

La sincronizzazione ID è il primo passaggio nel processo di trasferimento dati asincrono e in uscita. In questo passaggio [!DNL Audience Manager] , il fornitore confronta e confronta gli ID con i rispettivi visitatori del sito. Ad esempio, un [!DNL Audience Manager] cliente potrebbe conoscere un utente per ID 123. Tuttavia, il tuo partner dati potrebbe identificare questo utente con ID 456. Il processo di sincronizzazione consente [!DNL Audience Manager] a un fornitore di dati di riconciliare i diversi ID e identificare gli utenti nei rispettivi sistemi. Una volta completato, [!DNL Audience Manager] il provider di dati di terze parti deve avere ID corrispondenti per ogni utente unico visualizzato sulle nostre reti.

## Sintassi URL

In uno scambio ID, una stringa formattata [!DNL URL] correttamente deve essere simile al seguente:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parametri URL

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
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; ID_ ID &gt;</i></code> </td> 
   <td colname="col2">ID univoco per il provider di dati (assegnato da <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; ID_ UUID &gt;</i></code> </td> 
   <td colname="col2"> ID utente univoco. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2">Un URL codificato viene reindirizzato con la macro <code> $ {DD_ UUID}</code> incorporata al suo interno. <p><b>Nota:</b> Aggiunto solo quando il provider di dati avvia la chiamata. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p><code>gdpr</code> can be 0 (GDPR does not apply) or 1 (GDPR apply).</p><p><b>Nota:</b> <ul><li>I parametri <code>gdpr</code> e <code>gdpr_ permission</code> vengono gradualmente rollout negli URL di sincronizzazione ID con partner di attivazione. Consultate Partner di attivazione che supportano IAB TCF nel <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">plug-in Audience Manager per IAB TCF.</a></li><li>Questo parametro può essere utilizzato solo insieme a <code>gdpr_ permission.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_ permission = &lt; STRING STRING &gt;</i></code> </td> 
   <td colname="col2"><p><code>gdpr_ permission</code> is the URL-safe party 64-encoded GDPR permission string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>).</p><p><b>Nota:</b> Questo parametro può essere utilizzato solo insieme a <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Metodi e codice API di Data Collection Server (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componenti raccolta dati](../../reference/system-components/components-data-collection.md)

