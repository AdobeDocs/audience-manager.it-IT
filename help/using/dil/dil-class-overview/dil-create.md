---
description: Crea un'istanza DIL specifica per il partner.
seo-description: Crea un'istanza DIL specifica per il partner.
seo-title: Creazione DIL
solution: Audience Manager
title: Creazione DIL
uuid: 6 e 054600-703 c -4 a 97-af 2 a -8207 c 50013 db
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Metodo DIL create{#dil-create}

## Creazione DIL {#dil-create-new}

Crea [!UICONTROL DIL] un&#39;istanza specifica per i partner.

**Firma funzione:**`DIL.create: function (initConfig) {}`

**Initconfig Elements**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>La `visitorService` proprietà è *sempre* obbligatoria. Altre proprietà elencate qui sono facoltative, a meno che non siano indicate diversamente.

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
   <td colname="col3"> <p>Questa proprietà imposta l'ID del contenitore utilizzato da <span class="keyword">Audience Manager</span> per la sincronizzazione degli ID. Potete impostare <code> containernsid </code> se <span class="wintitle"> il codice DIL </span> è implementato in più siti. Ciascuno di questi siti dispone di un proprio ID contenitore e sincronizzazioni ID. Se avete solo 1 sito, l'ID contenitore è 0 per impostazione predefinita e non è necessario impostarlo correttamente. Contatta il tuo consulente per ottenere un elenco dei tuoi siti e dei relativi ID contenitore. </p> <p>Nel servizio <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"></a>Experience Cloud ID, la proprietà <code> idsynccontainerid </code> corrisponde <code> a containernsid </code> in <span class="wintitle"> DIL </span>. Se utilizzi <span class="wintitle"> DIL </span><i>e</i> il servizio ID su più siti, tieni presente quanto segue: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Per ciascun sito, imposta gli stessi ID contenitore su <code> containernsid </code> e <code> idsynccontainerid </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Sia <span class="wintitle"> DIL </span> che il servizio ID tenteranno di inviare sincronizzazioni ID al nostro iframe di raccolta dati. Tuttavia, l'iframe fa sì che <span class="wintitle"> DIL </span> non attivi una sincronizzazione ID. In questo modo si evita la duplicazione. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Solo <span class="wintitle"> DIL </span> invia dati a una destinazione <a href="../../features/destinations/destinations.md"></a>URL. </li> 
     </ul> </p> <p>Vedi anche <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> idsynccontainerid </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Declaredid </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Invia le <a href="../../features/declared-ids.md"> variabili ID dichiarate </a> a tutte le chiamate di eventi ad <span class="keyword"> Audience Manager </span>. </p> 
    </draft-comment> <p> <code> Delcaredid </code> viene utilizzato per trasmettere: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID partner dati assegnato da <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: L'ID univoco per un utente. </li> 
    </ul> <p> <p>Importante: Usa solo valori non codificati per gli ID. La codifica crea identificatori con doppio codificatore. </p> </p> <p> <p>Nota: Se utilizzi il servizio <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"></a>Experience Cloud ID, imposta ID cliente con il <code> metodo setcustomerids </code> invece di <span class="wintitle"> DIL </span>. Consulta <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> ID cliente e stati </a>di autenticazione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Delayalluntilwindowload </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se true, ritarda tutte le richieste (IFRAME, chiamate evento, Sincronizzazione ID e creazione) da eseguire fino a quando l' <code> evento Page Load </code> (Caricamento pagina) non viene attivato. Il valore predefinito è <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Disabledeclareduuidcookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> False per impostazione predefinita, <span class="keyword"> ovvero Audience Manager </span> imposta un cookie nel dominio del partner (imposta un cookie first party). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Questo elemento è stato dichiarato obsoleto con <span class="wintitle"> la </span> versione DIL 8.0 (rilasciata agosto 2018). Utilizzate invece la <code></code><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> funzione </a> visitor. disableidsyncs nel servizio Experience Cloud ID. </p> </p> <p> Se <code> true </code>, non allega l'IFRAME di pubblicazione della destinazione alle destinazioni DOM o di attivazione. Il valore predefinito è <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Questo elemento è stato dichiarato obsoleto con <span class="wintitle"> la </span> versione DIL 8.0 (rilasciata agosto 2018). Utilizzate invece la <code></code><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> funzione </a> visitor. disableidsyncs nel servizio Experience Cloud ID. </p> </p> <p>Disattiva la sincronizzazione degli ID. Devi disabilitare le sincronizzazioni ID quando utilizzi DIL v 6.2 + e il servizio ID visitatore. La <code> funzione visitorservice </code> (vedi Codice di esempio riportato di seguito) gestisce l'operazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Enableerrorreporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Impostate <code> su true </code> per abilitare la generazione di rapporti degli errori per tutte <span class="wintitle"></span> le istanze DIL della pagina. Funziona solo con <code> true booleano </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: Questo elemento è stato dichiarato obsoleto con <span class="wintitle"> la </span> versione DIL 8.0 (rilasciata agosto 2018). Utilizza invece la <code></code><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"> funzione visitor. idsyncssluseakamai </a> nel servizio Experience Cloud ID. </p> </p> <p> Consente di stabilire se il modello di pubblicazione della destinazione deve utilizzare Akamai per le connessioni HTTPS. Consentito in base al partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappature </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Associa il valore da una coppia chiave-valore a un'altra. Consultate <a href="../../dil/dil-use-cases.md#map-key-values"> Mappare i valori chiave su altre chiavi </a>. Rilasciato con v 2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Obbligatorio. </p> <p>La <code> coppia chiave/ </code> valore dello spazio nomi contiene il tuo <span class="keyword"> ID </span> organizzazione Experience Cloud. Se non hai questo ID, puoi trovarlo nella sezione <span class="wintitle"> Amministrazione </span> della dashboard <span class="keyword"> Experience Cloud </span> . Per visualizzare il dashboard, dovete disporre delle autorizzazioni di amministratore. Consultate <a href="../../faq/faq-features.md"> le domande frequenti </a> sulle funzioni e sulle funzioni del prodotto <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> - Amministrazione utente e domande frequenti </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Obbligatorio. </p> <p> Nome partner fornito da <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Removefinishedscriptsandcallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Rimuove gli script e i callback. Il valore predefinito è <code> False </code>. Si applica solo all'istanza <span class="wintitle"> DIL </span> corrente. Rilasciato con v 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Uuidcookie </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Imposta un cookie con l'ID utente univoco restituito da <span class="keyword"> Audience Manager </span>. Consulta <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Proprietà </a>uuidcookie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Visitorservice </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Richiesto con <span class="wintitle"> DIL </span> 6.2 o versione successiva. </p> <p> DIL si basa sulla <code> funzione setcustomerids </code> nel servizio <span class="wintitle"> Experience Cloud ID </span> per trasmettere ID dichiarati in <span class="keyword"> Audience Manager </span>. Consulta <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external">ID cliente e stati di autenticazione</a> per ulteriori informazioni. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Codice di esempio**

Una [!UICONTROL DIL] chiamata di esempio potrebbe essere simile a quella di seguito:

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

Una risposta di successo restituisce l&#39; [!UICONTROL DIL] istanza. Un tentativo non riuscito restituisce un oggetto di errore (non restituito) se il codice è configurato in modo errato o quando si verifica un errore.

## Proprietà uuidcookie {#uuidcookie-props}

Definisce le proprietà utilizzate dalla `uuidCookie` variabile. Questa variabile fa parte del `DIL.create` metodo.

`uuidCookie` ha le proprietà seguenti:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nome | Descrizione |
|---|---|
| `name` | Il nome del cookie ( `aam_did` predefinito). |
| `days` | Durata cookie (100 giorni è predefinito). |
| `path` | Percorso cookie, `'/test'``/` ad esempio, (è predefinito). |
| `domain` | Il dominio impostato in, `'adobe.com'``'.'+document.domain` ad esempio, (è predefinito). |
| `secure` | Imposta un flag per inviare dati solo attraverso una connessione HTTPS. |

## Visitorservice Properties {#visitor-service-props}

Definisce le proprietà utilizzate dalla `visitorService` variabile. Questa variabile fa parte del `DIL.create` metodo.

`visitorService` ha le proprietà seguenti:

| Nome | Tipo | Descrizione |
|---|---|---|
| `namespace` | Stringa | Obbligatorio. Rappresenta l&#39;ID organizzazione Experience Cloud. È necessario per la funzionalità Servizio base di Experience Cloud. Stesso parametro utilizzato per creare un&#39;istanza della funzionalità ID visitatore. |

**Esempio di codice:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
