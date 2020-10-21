---
description: Crea un'istanza DIL specifica per il partner.
seo-description: Crea un'istanza DIL specifica per il partner.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 12%

---


# DIL create, metodo{#dil-create}

## DIL create {#dil-create-new}

Crea un’ [!UICONTROL DIL] istanza specifica per il partner.

**Firma funzione:** `DIL.create: function (initConfig) {}`

**initConfig Elements**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>La `visitorService` proprietà è *sempre* obbligatoria. Altre proprietà elencate sono facoltative, salvo diversa indicazione.

`initConfig` accetta i seguenti elementi:

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Questa proprietà imposta l'ID del contenitore utilizzato da <span class="keyword">Audience Manager</span> per la sincronizzazione degli ID. Impostereste <code> containerNSID </code> se avete <span class="wintitle"> DIL </span> distribuito su più siti. Ciascuno di questi siti avrà un proprio ID contenitore e sincronizzazioni ID. Se disponete di un solo sito, l'ID del contenitore è 0 per impostazione predefinita e non è necessario impostarlo correttamente. Contatta il tuo consulente per ottenere un elenco dei tuoi siti e dei loro ID contenitore. </p> <p>In <a href="https://docs.adobe.com/content/help/it-IT/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, la proprietà <code> idSyncContainerID </code> corrisponde a <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Nota quanto segue se utilizzi <span class="wintitle"> DIL </span> <i></i> e il servizio ID su più siti: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Per ogni sito, impostate gli stessi ID contenitore su <code> containerNSID </code> e <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Sia il <span class="wintitle"> </span> DIL che il servizio ID cercheranno di inviare le sincronizzazioni ID al nostro iFrame di raccolta dati. Tuttavia, l’iFrame garantisce che <span class="wintitle"> l’DIL </span> non attivi la sincronizzazione ID. Ciò impedisce la duplicazione. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Solo <span class="wintitle"> DIL </span> invia dati a una destinazione <a href="../../features/destinations/destinations.md"> URL </a>. </li> 
     </ul> </p> <p>Vedi anche <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Invia le variabili ID <a href="../../features/declared-ids.md"> dichiarato </a> per ogni chiamata di evento al Audience Manager <span class="keyword"> </span>. </p> 
    </draft-comment> <p> <code> delcaredId </code> viene utilizzato per trasmettere: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID partner dati assegnato dall' <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: L’ID univoco dell’utente. </li> 
    </ul> <p> <p>Importante:  Usa solo valori non codificati per gli ID. La codifica crea identificatori con doppia codifica. </p> </p> <p> <p>Nota:  Se utilizzate <a href="https://docs.adobe.com/content/help/it-IT/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, impostate gli ID cliente con il <code> setCustomerIDs </code> metodo invece del <span class="wintitle"> DIL </span>. See <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se true, differisce l'esecuzione di tutte le richieste (IFRAME, chiamate di eventi, sincronizzazione ID e destinazione) fino all'attivazione dell' <code> Page Load </code> evento. Il valore predefinito è <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> False per impostazione predefinita, <span class="keyword"> Audience Manager </span> imposta un cookie nel dominio del partner (imposta un cookie di prima parte). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Questo elemento è stato dichiarato obsoleto con la <span class="wintitle"> versione </span> DIL 8.0 (rilasciata nell’agosto 2018). Utilizzate invece la <code> visitor.disableIdSyncs </code> funzione <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> in Adobe Experience Platform Identity Service. </p> </p> <p> Se <code> true </code>, non allegherà la destinazione che pubblica IFRAME al DOM o alle destinazioni di attivazione. Il valore predefinito è <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Questo elemento è stato dichiarato obsoleto con la <span class="wintitle"> versione </span> DIL 8.0 (rilasciata nell’agosto 2018). Utilizzate invece la <code> visitor.disableIdSyncs </code> funzione <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> in Adobe Experience Platform Identity Service. </p> </p> <p>Disattiva la sincronizzazione degli ID. Devi disabilitare la sincronizzazione degli ID quando usi DIL v6.2+ e il servizio ID visitatori. La <code> visitorService </code> funzione (vedere il codice di esempio riportato di seguito) si occupa di questa operazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Impostato <code> true </code> per abilitare la segnalazione degli errori per tutte le <span class="wintitle"> istanze di DIL </span> sulla pagina. Funziona <code> true </code> solo con booleano. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante:  Questo elemento è stato dichiarato obsoleto con la <span class="wintitle"> versione </span> DIL 8.0 (rilasciata nell’agosto 2018). Utilizzate invece la <code> visitor.idSyncSSLUseAkamai </code> funzione <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> </a> in Adobe Experience Platform Identity Service. </p> </p> <p> Consente di stabilire se il modello di pubblicazione della destinazione deve utilizzare Akamai per le connessioni HTTPS. Consentito in base al partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Associa il valore da una coppia chiave-valore a un'altra. Consultate <a href="../../dil/dil-use-cases.md#map-key-values"> Mappare i valori chiave su altri tasti </a>. Rilasciato con v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Obbligatorio. </p> <p>La coppia <code> namespace </code> chiave-valore contiene l'ID organizzazione <span class="keyword"> Experience Cloud </span> . Se non disponete di questo ID, potete trovarlo nella sezione <span class="wintitle"> Amministrazione </span> del <span class="keyword"> dashboard di Experience Cloud di  </span> . Per visualizzare questo dashboard è necessario disporre delle autorizzazioni di amministratore. Consulta le Domande frequenti sulle funzioni del <a href="../../faq/faq-features.md"> prodotto </a> e sull' <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> amministrazione - Gestione utente e domande frequenti </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Obbligatorio. </p> <p> Nome del partner fornito dal <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Rimuove script e callback. Il valore predefinito è <code> False </code>. Si applica solo all'istanza <span class="wintitle"> DIL corrente </span> . Rilasciato con v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Imposta un cookie con l'ID utente univoco restituito dal <span class="keyword"> Audience Manager </span>. Consultate Proprietà <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Obbligatorio con <span class="wintitle"> DIL </span> 6.2 o versione successiva. </p> <p> Il DIL si basa sulla <code> setCustomerIDs </code> funzione di <span class="wintitle"> Adobe Experience Platform Identity Service </span> per trasmettere gli ID dichiarati a <span class="keyword">  Audience Manager </span>. Consulta <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">ID cliente e stati di autenticazione</a> per ulteriori informazioni. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Codice di esempio**

Una [!UICONTROL DIL] chiamata di esempio potrebbe essere simile alla seguente:

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

Una risposta corretta restituisce l’ [!UICONTROL DIL] istanza. Un tentativo non riuscito restituisce un oggetto errore (non generato) se il codice è configurato in modo errato o se si verifica un errore.

## proprietà uidCookie {#uuidcookie-props}

Definisce le proprietà utilizzate dalla `uuidCookie` variabile. Questa variabile fa parte del `DIL.create` metodo.

`uuidCookie` ha le seguenti proprietà:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nome | Descrizione |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | Durata del cookie (100 giorni è il valore predefinito). |
| `path` | Percorso del cookie, ad esempio `'/test'` ( `/` è predefinito). |
| `domain` | Il dominio in cui è impostato il cookie, ad es. `'adobe.com'` ( `'.'+document.domain` è predefinito). |
| `secure` | Imposta un flag per l&#39;invio di dati solo attraverso una connessione HTTPS. |

## visitorService Properties {#visitor-service-props}

Definisce le proprietà utilizzate dalla `visitorService` variabile. Questa variabile fa parte del `DIL.create` metodo.

`visitorService` ha le seguenti proprietà:

| Nome | Tipo | Descrizione |
|---|---|---|
| `namespace` | Stringa | Obbligatorio. Rappresenta L&#39;ID Organizzazione Experience Cloud . Questo è necessario per  funzionalità del servizio di base di Experience Cloud. Stesso parametro utilizzato per creare un&#39;istanza della funzionalità ID visitatore. |

**Esempio di codice:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
