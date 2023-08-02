---
description: Crea un'istanza DIL specifica per il partner.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 9%

---

# metodo DIL create{#dil-create}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo del [!DNL Data Integration Library (DIL)] e [!DNL DIL] estensione.
>
>I clienti esistenti possono continuare a utilizzare [!DNL DIL] implementazione. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experienci Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) per la strategia di raccolta dei dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experienci Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) invece.

## DIL create {#dil-create-new}

Crea un partner specifico [!UICONTROL DIL] dell&#39;istanza.

**Firma funzione:** `DIL.create: function (initConfig) {}`

**elementi initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>Il `visitorService` la proprietà è *sempre* obbligatorio. Le altre proprietà elencate qui sono facoltative, se non diversamente indicato.

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
   <td colname="col3"> <p>Questa proprietà imposta l'ID del contenitore utilizzato da <span class="keyword">Audience Manager</span> per la sincronizzazione degli ID. Impostate <code> containerNSID </code> se ha <span class="wintitle"> DIL </span> distribuite su più siti. Ognuno di questi siti avrà il proprio ID contenitore e le sincronizzazioni ID. Se hai solo 1 sito, l’ID contenitore è 0 per impostazione predefinita e non è necessario impostarlo correttamente. Contatta il tuo consulente per ottenere un elenco dei tuoi siti e dei loro ID contenitore. </p> <p>In <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Servizio Adobe Experience Platform Identity </a>, la proprietà <code> idSyncContainerID </code> corrisponde a <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Nota quanto segue se utilizzi <span class="wintitle"> DIL </span> <i>e</i> il servizio ID su più siti: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Per ogni sito, imposta gli stessi ID contenitore su <code> containerNSID </code> e <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Entrambi <span class="wintitle"> DIL </span> e il servizio ID tenterà di inviare le sincronizzazioni ID al nostro iFrame di raccolta dati. Tuttavia, l'iFrame assicura che <span class="wintitle"> DIL </span> non attiverà una sincronizzazione ID. In questo modo si evitano duplicazioni. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Solo <span class="wintitle"> DIL </span> invia dati a un <a href="../../features/destinations/destinations.md"> Destinazione URL </a>. </li> 
     </ul> </p> <p>Vedi anche, <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> viene utilizzato per trasmettere: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID partner dati assegnato da <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: ID univoco per un utente. </li> 
    </ul> <p> <p>Importante: utilizza solo valori non codificati per gli ID. La codifica creerà identificatori con doppia codifica. </p> </p> <p> <p>Nota: se utilizzi il <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Servizio Adobe Experience Platform Identity </a>, imposta gli ID cliente con <code> setCustomerIDs </code> invece di <span class="wintitle"> DIL </span>. Consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> ID cliente e stati di autenticazione </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se è true, rinvia l’esecuzione di tutte le richieste (IFRAME, chiamate evento, sincronizzazione ID e destinazione) fino al <code> Page Load </code> l'evento viene attivato. Il valore predefinito è <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> False per impostazione predefinita, ovvero <span class="keyword"> Audience Manager </span> imposta un cookie nel dominio del partner (imposta un cookie di prima parte). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: questo elemento è stato dichiarato obsoleto con <span class="wintitle"> DIL </span> versione 8.0 (rilasciata nell’agosto 2018). Utilizza il <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> funzione </a> in Adobe Experience Platform Identity Service. </p> </p> <p> Se <code> true </code>, non allega la destinazione che pubblica IFRAME alle destinazioni DOM o fire. Il valore predefinito è <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: questo elemento è stato dichiarato obsoleto con <span class="wintitle"> DIL </span> versione 8.0 (rilasciata nell’agosto 2018). Utilizza il <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> funzione </a> in Adobe Experience Platform Identity Service. </p> </p> <p>Disattiva la sincronizzazione degli ID. Disattiva le sincronizzazioni ID quando utilizzi DIL v6.2+ e il servizio ID visitatore. Il <code> visitorService </code> questa funzione (vedi il codice di esempio di seguito) si occupa di questa operazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Imposta su <code> true </code> per abilitare la segnalazione degli errori per tutti <span class="wintitle"> DIL </span> sulla pagina. Funziona con il booleano <code> true </code> solo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: questo elemento è stato dichiarato obsoleto con <span class="wintitle"> DIL </span> versione 8.0 (rilasciata nell’agosto 2018). Utilizza il <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> funzione </a> in Adobe Experience Platform Identity Service. </p> </p> <p> Consente di stabilire se il modello di pubblicazione della destinazione deve utilizzare Akamai per le connessioni HTTPS. Consentito in base al partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Associa il valore da una coppia chiave-valore a un'altra. Consulta <a href="../../dil/dil-use-cases.md#map-key-values"> Mappare i valori delle chiavi ad altre chiavi </a>. Rilasciato con v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Obbligatorio. </p> <p>Il <code> namespace </code> coppia chiave-valore contiene <span class="keyword"> Experience Cloud </span> ID organizzazione. Se non disponi di questo ID, puoi trovarlo in <span class="wintitle"> Amministrazione </span> sezione del <span class="keyword"> Experience Cloud </span> dashboard. Per visualizzare questo dashboard sono necessarie le autorizzazioni di amministratore. Consulta la <a href="../../faq/faq-features.md"> Domande frequenti su funzioni e funzionalità del prodotto </a> e <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Amministrazione - Gestione utenti e domande frequenti </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Obbligatorio. </p> <p> Nome del partner fornito da <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Rimuove script e callback. Il valore predefinito è <code> False </code>. Si applica al <span class="wintitle"> DIL </span> solo istanza. Rilasciato con v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Imposta un cookie con l'ID utente univoco restituito da <span class="keyword"> Audience Manager </span>. Consulta <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Proprietà uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Obbligatorio con <span class="wintitle"> DIL </span> 6.2 o superiore. </p> <p> DIL si basa sulla <code> setCustomerIDs </code> funzione in <span class="wintitle"> Servizio Adobe Experience Platform Identity </span> per passare gli ID dichiarati in <span class="keyword"> Audience Manager </span>. Consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external">ID cliente e stati di autenticazione</a> per ulteriori informazioni. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Codice di esempio**

Un esempio [!UICONTROL DIL] La chiamata di potrebbe essere simile alla seguente:

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

Una risposta corretta restituisce [!UICONTROL DIL] dell&#39;istanza. Un tentativo non riuscito restituisce un oggetto errore (non generato) se il codice non è configurato correttamente o ogni volta che si verifica un errore.

## Proprietà uuidCookie {#uuidcookie-props}

Definisce le proprietà utilizzate da `uuidCookie` variabile. Questa variabile fa parte del `DIL.create` metodo.

`uuidCookie` ha le seguenti proprietà:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nome | Descrizione |
|---|---|
| `name` | Il nome del cookie ( `aam_did` è l&#39;impostazione predefinita). |
| `days` | Durata del cookie (100 giorni è l’impostazione predefinita). |
| `path` | Percorso del cookie, ad esempio `'/test'` ( `/` è l&#39;impostazione predefinita). |
| `domain` | Il dominio in cui è impostato il cookie, ad esempio `'adobe.com'` ( `'.'+document.domain` è l&#39;impostazione predefinita). |
| `secure` | Imposta un flag per inviare dati solo tramite una connessione HTTPS. |

## Proprietà visitorService {#visitor-service-props}

Definisce le proprietà utilizzate da `visitorService` variabile. Questa variabile fa parte del `DIL.create` metodo.

`visitorService` ha le seguenti proprietà:

| Nome | Tipo | Descrizione |
|---|---|---|
| `namespace` | Stringa | Obbligatorio. Rappresenta L’ID Dell’Organizzazione Experience Cloud. Questo è necessario, ad Experience Cloud, per la funzionalità del servizio core. Stesso parametro utilizzato per creare un’istanza della funzionalità ID visitatore. |

**Esempio di codice:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
