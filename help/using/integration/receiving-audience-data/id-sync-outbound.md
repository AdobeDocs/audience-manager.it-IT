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


# ID Synchronization for Outbound Data Transfers{#id-synchronization-for-outbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between Audience Manager and a third-party data provider. Contatta il tuo consulente Adobe Audience Manager prima di tentare la prima sincronizzazione ID.

<!-- c_id_sync_out.xml -->

## Scopo della sincronizzazione ID

La sincronizzazione ID è il primo passaggio nel processo di trasferimento dati asincrono e in uscita. In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. Tuttavia, il tuo partner dati potrebbe identificare questo utente con ID 456. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks.

## Sintassi URL

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Parametri URL

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

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
   <td colname="col2">Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; ID_ UUID &gt;</i></code> </td> 
   <td colname="col2"> ID utente univoco. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2">An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. <p><b>Nota:</b> Aggiunto solo quando il provider di dati avvia la chiamata. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p><code>gdpr</code> can be 0 (GDPR does not apply) or 1 (GDPR apply).</p><p><b>Nota:</b> <ul><li>The <code>gdpr</code> and <code>gdpr_consent</code> parameters are being gradually rolled out in ID sync URLs with activation partners. See Activation partners that support IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
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

