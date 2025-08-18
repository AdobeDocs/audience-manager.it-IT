---
description: Crea un’istanza DIL specifica per il partner.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 4%

---

# metodo DIL create{#dil-create}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo di [!DNL Data Integration Library (DIL)] e dell&#39;estensione [!DNL DIL].
>
>I clienti esistenti possono continuare a utilizzare l&#39;implementazione [!DNL DIL]. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it) per la strategia di raccolta dati a lungo termine.
>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=it).

## DIL create {#dil-create-new}

Crea un&#39;istanza [!UICONTROL DIL] specifica per il partner.

**Firma funzione:** `DIL.create: function (initConfig) {}`

**elementi initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>La proprietà `visitorService` è *always* obbligatoria. Le altre proprietà elencate qui sono facoltative, se non diversamente indicato.

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
   <td colname="col3"> <p>Questa proprietà imposta l'ID del contenitore utilizzato da <span class="keyword"> Audience Manager </span> per le sincronizzazioni ID. Impostare <code> containerNSID </code> se è stato distribuito <span class="wintitle"> DIL </span> in più siti. Ognuno di questi siti avrà il proprio ID contenitore e le sincronizzazioni ID. Se hai solo 1 sito, l’ID contenitore è 0 per impostazione predefinita e non è necessario impostarlo correttamente. Contatta il tuo consulente per ottenere un elenco dei tuoi siti e dei loro ID contenitore. </p> <p>Nel servizio Adobe Experience Platform Identity <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it" format="https" scope="external"> di </a>, la proprietà <code> idSyncContainerID </code> corrisponde a <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Se usi <span class="wintitle"> DIL </span> <i>e</i> il servizio ID in più siti, tieni presente quanto segue: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Per ogni sito, impostare gli stessi ID contenitore su <code> containerNSID </code> e <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Sia <span class="wintitle"> DIL </span> che il servizio ID tenteranno di inviare sincronizzazioni ID all'iFrame della raccolta dati. Tuttavia, l'iFrame assicura che <span class="wintitle"> DIL </span> non attivi una sincronizzazione ID. In questo modo si evitano duplicazioni. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Solo <span class="wintitle"> DIL </span> invia dati a una destinazione URL <a href="../../features/destinations/destinations.md"> </a>. </li> 
     </ul> </p> <p>Vedere anche <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=it" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> viene utilizzato per trasmettere: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID partner dati assegnato da <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: ID univoco per un utente. </li> 
    </ul> <p> <p>Importante: utilizza solo valori non codificati per gli ID. La codifica creerà identificatori con doppia codifica. </p> </p> <p> <p>Nota: se si utilizza il servizio <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it" format="https" scope="external"> Adobe Experience Platform Identity </a>, impostare gli ID cliente con il metodo <code> setCustomerIDs </code> anziché <span class="wintitle"> DIL </span>. Consulta <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=it" format="https" scope="external"> ID cliente e stati di autenticazione </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Se è true, rinvia l'esecuzione di tutte le richieste (IFRAME, chiamate evento, sincronizzazione ID e destinazione) fino all'attivazione dell'evento <code> Page Load </code>. Il valore predefinito è <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> False per impostazione predefinita, il che significa che <span class="keyword"> Audience Manager </span> imposta un cookie nel dominio del partner (imposta un cookie di prima parte). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: questo elemento è stato dichiarato obsoleto con <span class="wintitle"> DIL </span> versione 8.0 (rilasciata ad agosto 2018). Utilizzare la funzione <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=it" format="https" scope="external"> </a> nel servizio Adobe Experience Platform Identity. </p> </p> <p> Se <code> true </code>, non allegherà la destinazione di pubblicazione IFRAME alle destinazioni DOM o Fire. Il valore predefinito è <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: questo elemento è stato dichiarato obsoleto con <span class="wintitle"> DIL </span> versione 8.0 (rilasciata ad agosto 2018). Utilizzare la funzione <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=it" format="https" scope="external"> </a> nel servizio Adobe Experience Platform Identity. </p> </p> <p>Disattiva la sincronizzazione ID. Disattiva le sincronizzazioni ID quando utilizzi DIL v6.2+ e il servizio ID visitatore. La funzione <code> visitorService </code> (vedi il codice di esempio di seguito) si occupa di questa operazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Impostare su <code> true </code> per abilitare la segnalazione errori per tutte le <span class="wintitle"> istanze di DIL </span> nella pagina. Funziona solo con <code> true </code> booleano. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> <p>Importante: questo elemento è stato dichiarato obsoleto con <span class="wintitle"> DIL </span> versione 8.0 (rilasciata ad agosto 2018). Utilizzare la funzione <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=it" format="https" scope="external"> </a> nel servizio Adobe Experience Platform Identity. </p> </p> <p> Specifica se il modello di pubblicazione di destinazione deve utilizzare Akamai per le connessioni HTTPS. Consentito in base al partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Associa il valore da una coppia chiave-valore a un'altra. Vedi <a href="../../dil/dil-use-cases.md#map-key-values"> mappare i valori delle chiavi ad altre chiavi </a>. Rilasciato con v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Obbligatorio. </p> <p>La coppia chiave-valore <code> namespace </code> contiene l'ID organizzazione <span class="keyword"> Experience Cloud </span>. Se non disponi di questo ID, puoi trovarlo nella sezione <span class="wintitle"> dell'amministrazione </span> del dashboard <span class="keyword"> di Experience Cloud </span>. Per visualizzare questo dashboard sono necessarie le autorizzazioni di amministratore. Vedere le Domande frequenti sulle funzioni e le funzionalità del prodotto <a href="../../faq/faq-features.md"> </a> e <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=it" format="https" scope="external"> Amministrazione - Gestione utente e domande frequenti </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Obbligatorio. </p> <p> Nome partner fornito da <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booleano </p> </td> 
   <td colname="col3"> <p> Rimuove script e callback. Il valore predefinito è <code> False </code>. Si applica solo all'istanza <span class="wintitle"> di DIL </span> corrente. Rilasciato con v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Imposta un cookie con l'ID utente univoco restituito da <span class="keyword"> Audience Manager </span>. Vedi <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> proprietà uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Oggetto </p> </td> 
   <td colname="col3"> <p>Richiesto con <span class="wintitle"> DIL </span> 6.2 o versione successiva. </p> <p> DIL si basa sulla funzione <code> setCustomerIDs </code> nel servizio <span class="wintitle"> Adobe Experience Platform Identity </span> per passare gli ID dichiarati in <span class="keyword"> Audience Manager </span>. Per ulteriori informazioni, vedere <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=it" format="https" scope="external"> ID cliente e stati di autenticazione </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Codice di esempio**

Una chiamata [!UICONTROL DIL] di esempio potrebbe essere simile alla seguente:

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

In caso di esito positivo, la risposta restituisce l’istanza [!UICONTROL DIL]. Un tentativo non riuscito restituisce un oggetto errore (non generato) se il codice non è configurato correttamente o ogni volta che si verifica un errore.

## Proprietà uuidCookie {#uuidcookie-props}

Definisce le proprietà utilizzate dalla variabile `uuidCookie`. Questa variabile fa parte del metodo `DIL.create`.

`uuidCookie` ha le seguenti proprietà:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nome | Descrizione |
|---|---|
| `name` | Il nome del cookie ( `aam_did` è predefinito). |
| `days` | Durata del cookie (100 giorni è l’impostazione predefinita). |
| `path` | Percorso cookie, ad esempio `'/test'` ( `/` è il valore predefinito). |
| `domain` | Dominio in cui è impostato il cookie. Esempio: `'adobe.com'` (impostazione predefinita: `'.'+document.domain`). |
| `secure` | Imposta un flag per inviare dati solo tramite una connessione HTTPS. |

## Proprietà visitorService {#visitor-service-props}

Definisce le proprietà utilizzate dalla variabile `visitorService`. Questa variabile fa parte del metodo `DIL.create`.

`visitorService` ha le seguenti proprietà:

| Nome | Tipo | Descrizione |
|---|---|---|
| `namespace` | Stringa | Obbligatorio. Rappresenta L’ID Dell’Organizzazione Di Experience Cloud. Questo è necessario per la funzionalità del servizio core Experience Cloud. Stesso parametro utilizzato per creare un’istanza della funzionalità ID visitatore. |

**Esempio di codice:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
