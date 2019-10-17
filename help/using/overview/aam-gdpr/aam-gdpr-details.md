---
description: Questo documento illustra gli aspetti tecnici relativi al Regolamento generale sulla protezione dei dati (General Data Protection Regulation, GDPR) per Audience Manager e illustra come inviare le richieste GDPR ad Audience Manager.
seo-description: Questo documento illustra gli aspetti tecnici relativi al Regolamento generale sulla protezione dei dati (General Data Protection Regulation, GDPR) per Audience Manager e illustra come inviare le richieste GDPR ad Audience Manager.
seo-title: GDPR in Audience Manager
solution: Audience Manager
keywords: Interfaccia utente GDPR, API GDPR
title: GDPR in Audience Manager
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: b32283a6cb3d001f0a1fc85f3e63fba651f32760

---


# GDPR in Audience Manager{#gdpr-in-audience-manager}

Questo documento illustra gli aspetti tecnici relativi al Regolamento generale sulla protezione dei dati (General Data Protection Regulation, GDPR) per Audience Manager e illustra come inviare le richieste GDPR ad Audience Manager.

## Documentazione GDPR in Experience Cloud {#gdpr-documentation}

Prima di leggere le specifiche di Audience Manager, ti consigliamo di consultare il materiale Experience Cloud per il Regolamento generale sulla protezione dei dati (GDPR), collegato qui sotto:

* [GDPR e il tuo business](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [Whitaper GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [Terminologia RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

Le sezioni seguenti spiegano cosa significa GDPR per Audience Manager e come puoi inviare le richieste GDPR ad Audience Manager.

## Tipi di richieste GDPR e Come effettuare una richiesta GDPR {#types-of-gdpr-requests}

In qualità di cliente Audience Manager, puoi inviare singole richieste GDPR per accedere ed eliminare i dati dei clienti tramite l’interfaccia utente **del servizio** Privacy (collegamento all’[interfaccia utente qui](https://gdprui.cloud.adobe.io/) e [documentazione qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)) oppure chiamando l’API **del servizio** Privacy ([documentazione qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)e riferimento all’API per l’API). You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). In caso di domande, contattate l'Assistenza clienti all'indirizzo gdprsupport@adobe.com.

## Accedere ai dati {#access-data}

Comprendiamo il tuo impegno a soddisfare le richieste dei clienti GDPR entro 30 giorni dalla ricezione. Per questo motivo, cerchiamo di elaborare la tua richiesta di accesso ai dati il prima possibile.

**Richiesta**

Puoi registrare le richieste di accesso ai dati tramite l’interfaccia utente **del servizio** Privacy (collegamento all’[interfaccia utente qui](https://gdprui.cloud.adobe.io/) e [documentazione qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)) oppure chiamando l’API **del servizio** Privacy ([documentazione qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)e riferimento all’API). In entrambi i casi, devi caricare un JSON con gli identificatori Audience Manager per i quali stai inviando la richiesta di accesso ai dati. Per verificare l’aspetto di un JSON ben formato, potete **[scaricare un JSON](assets/access_request.json)** di esempio.

**Risposta**

Le risposte alle richieste di dati di accesso contengono un riepilogo del numero totale di caratteristiche e segmenti, del tipo di caratteristica, delle descrizioni delle caratteristiche e dei segmenti, insieme ai rispettivi nomi delle origini dati. La risposta di accesso includerà anche dati di seconda e terza parte accessibili al Titolare del trattamento insieme ai dati di prime parti. Quando [!UICONTROL declared IDs] come ID CRM per dispositivi diversi o ID cookie cliente vengono inviati nelle richieste GDPR, Audience Manager includerà la risposta di accesso da tutti i dispositivi collegati (fino a 100 dispositivi per ID dichiarato).

**Stato risposta**

Se nella risposta sono presenti errori da Audience Manager, questi vengono visualizzati come codici di errore nella risposta. Abbiamo un [elenco di codici](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)di errore, dove puoi trovare ulteriori informazioni sugli errori restituiti.

**Risposta di esempio**

Una risposta di accesso di esempio potrebbe essere simile a quella riportata di seguito. In questo esempio, l'ID dell'oggetto dati è un ID cookie. Sono qualificati per diverse caratteristiche e appartengono a alcuni segmenti. L'ID cookie è collegato a un ID mobile. L'esempio contiene anche i metadati per il telefono utilizzato.

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

La tabella seguente contiene le descrizioni di tutti i campi restituiti nella risposta di accesso ai dati, nell'ordine in cui sono visualizzati sopra.

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>ID utente per i dati seguenti. Si tratta di un ID fornito nella richiesta di accesso ai dati GDPR, o di un ID collegato a uno degli ID dichiarati forniti. I tipi di ID sono descritti nella sezione <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Denominato anche fonte di dati. Consultate la sezione <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (Identificatori</a> di Audience Manager). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>L'ID spazio dei nomi/sorgente dei dati. Consulta <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (ID)</a> per tutti i valori accettati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>I codici di integrazione sono nomi descrittivi per le origini dati e consentono di tenere traccia delle origini dati in modo più semplice rispetto all'utilizzo degli ID origine dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name </code> </p> </td> 
   <td colname="col2"> <p>Nome del proprietario dell'origine dati. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">Per i dati di prime parti, si tratta del nome della società del cliente. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">Per i dati di seconda parte, si tratta del nome della società partner. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">Per i dati di terze parti, si tratta del nome del partner dati. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>Tipo di ID per il quale è stato richiesto l'accesso ai dati RGPD. I tipi accettati sono elencati nella sezione <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> warnings</code> </p> </td> 
   <td colname="col2"> <p>Gli avvisi restituiscono ulteriori informazioni relative alla richiesta di accesso ai dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>Brevi informazioni sull’avviso. </p> <p>I due avvisi che possono essere ricevuti sono: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Dati dispositivo </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Richiesta incompleta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>Una descrizione più dettagliata dell’avviso ricevuto: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Dati dispositivo - Contiene i dati di tutti gli utenti del dispositivo </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Richiesta incompleta - Il recupero dei dati di Audience Manager non è stato completato. Potrebbero mancare alcune informazioni. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>Caratteristiche e segmenti associati a questo ID utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>Caratteristiche associate all'ID utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Nome della caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>Tipo di caratteristica. I valori possibili sono: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>Prima festa</i> per le tue caratteristiche. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Seconda parte</i> per le caratteristiche che appartengono ai tuoi partner. Leggi il nostro articolo <a href="../../overview/data-types-collected.md#second-party-data"> Dati</a> di seconda parte per maggiori informazioni. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Terza parte</i> per le caratteristiche ottenute dai partner di dati, tramite <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Alcune parole utili per descrivere lo scopo o la funzione della caratteristica. Questo campo è facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>I controlli <a href="../../features/data-export-controls.md"> di esportazione dei</a> dati applicati all'origine dati della caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>Nome del proprietario dell'origine dati a cui appartiene la caratteristica. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">Per i dati di prime parti, si tratta del nome della società del cliente. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">Per i dati di seconda parte, si tratta del nome della società partner. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">Per i dati di terze parti, si tratta del nome del partner dati. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>L'ora esatta in cui l'ultimo soggetto ha qualificato per questa caratteristica. Il formato della data è AAAA-MM-GG. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segments </code> </p> </td> 
   <td colname="col2"> <p>Segmenti a cui appartiene l’utente corrente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Nome del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Alcune parole utili per descrivere questo segmento. Questo campo è facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>I controlli <a href="../../features/data-export-controls.md"></a> di esportazione dei dati applicati all'origine dati di questo segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>Nome del proprietario dell'origine dati a cui appartiene il segmento. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">Per i dati di prime parti, si tratta del nome della società del cliente. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">Per i dati di seconda parte, si tratta del nome della società partner. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">Per i dati di terze parti, si tratta del nome del partner dati. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>L'ora esatta in cui l'ultimo oggetto dati è qualificato per questo segmento. Il formato della data è AAAA-MM-GG. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active</code> </p> </td> 
   <td colname="col2"> <p>Indica se l'oggetto dati è attualmente qualificato per questo segmento. Restituisce <code><i>true</i></code> o <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> links </code> </p> </td> 
   <td colname="col2"> <p>ID aggiuntivo a cui è stato collegato questo ID. Le informazioni vengono restituite in: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (origine dati) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">nome provider dati </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>Tutti questi campi sono descritti nelle prime righe della tabella. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>L’ora esatta in cui un evento di sincronizzazione ID ha creato il collegamento tra ID. Il formato della data è AAAA-MM-GG. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> device metadata </code> </p> </td> 
   <td colname="col2"> <p>Informazioni sul dispositivo. Queste informazioni includono i campi seguenti. Non tutti i campi vengono restituiti per tutti i tipi di dispositivi. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Informazioni hardware </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>produttore dispositivo </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>Nome di marketing del dispositivo </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>Il modello dispositivo </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>Nome del sistema operativo del dispositivo (OS) </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>Versione del sistema operativo </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>Il fornitore del dispositivo </p> </li> 
     </ul> </p> <p> <p>Nota: I metadati del dispositivo vengono restituiti solo quando si invia uno dei seguenti casi: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">ID per dispositivi mobili </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">ID di Audience Manager </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud ID </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cancellare i dati {#delete-data}

Comprendiamo il tuo impegno a soddisfare le richieste dei clienti GDPR entro 30 giorni dalla ricezione. Per questo motivo, cerchiamo di elaborare la richiesta di eliminazione dei dati il prima possibile.

**Richiesta**

Puoi registrare le richieste di eliminazione dei dati tramite l’interfaccia utente **del servizio** Privacy (collegamento all’[interfaccia utente qui](https://gdprui.cloud.adobe.io/) e [documentazione qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)) oppure chiamando l’API **del servizio** Privacy ([documentazione qui](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)e riferimento all’API). In entrambi i casi, devi caricare un JSON con gli identificatori Audience Manager per i quali stai inviando la richiesta di accesso ai dati. Per verificare l’aspetto di un JSON ben formato, potete **[scaricare un JSON](assets/delete_request.json)** di esempio.

**Risposta**

In risposta alle richieste di eliminazione dei dati, eliminiamo caratteristiche e segmenti associati al rispettivo identificatore Audience Manager. Inoltre, i rispettivi identificatori di Audience Manager per l'oggetto dati verranno definitivamente esclusi dall'ulteriore raccolta di dati da Audience Manager e le rispettive mappature ID verranno rimosse. Quando ID dichiarati come ID CRM per dispositivi diversi o ID cookie cliente vengono inviati nelle richieste GDPR, Audience Manager eseguirà le azioni di eliminazione necessarie su tutti i dispositivi collegati (fino a 100 dispositivi per ID dichiarato).

## Richiesta di rifiuto {#opt-out-request}

Per le richieste di rifiuto, consulta la nostra documentazione su Gestione del [rifiuto](../../overview/data-security-and-privacy/opt-out-management.md).

## ID (Audience Manager Identifiers) {#aam-ids}

Quando invii richieste GDPR ad Adobe Audience Manager, devi includere uno degli identificatori (ID) elencati di seguito. Puoi trovare ulteriori informazioni sui formati ID nel nostro [indice degli ID](../../reference/ids-in-aam.md)di Audience Manager.

###  ID utente univoco di Adobe Audience Manager

**ID** utente: aam_uid

**Definizione**: ID utente univoco di Adobe Audience Manager

**ID** spazio nomi: 0

>[!NOTE]
>
>È inoltre possibile utilizzare lo spazio dei nomi CORE. Vedi il secondo esempio JSON.

**Esempio in JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**ID** utente: mid

**Definizione**: Adobe Experience Cloud ID, precedentemente noto come Visitor ID o Marketing Cloud ID

**ID** spazio nomi: 4

>[!NOTE]
>
>È inoltre possibile utilizzare lo spazio dei nomi ECID. Vedi il secondo esempio JSON.

**Esempio in JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### ID cliente

**ID** utente: cid

**Definizione**: ID cliente, ad esempio un cookie impostato per i visitatori anonimi del sito o un ID CRM da un sistema offline o un nome utente con hash

**ID** spazio nomi: Specifico per il cliente. Trovalo dalla tua istanza Audience Manager.

**Esempio in JSON**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

### ID pubblicità mobile

**ID** utente: d_cid

**Definizione**: ID pubblicitari per dispositivi mobili.
>[!IMPORTANT]
>
> Se utilizzi l’SDK di Mobile, devi anche inviare l’Experience Cloud ID (MID) insieme agli ID pubblicitari per dispositivi mobili per ottenere risposte complete di accesso e eliminazione al GDPR.

**ID dello spazio dei nomi**:

* IDFA: 2015
* GAID: 2014

Per ulteriori informazioni, consulta [Origini](../../features/global-data-sources.md) dati globali.

**Esempio in JSON**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### Codice integrazione

**ID** utente: d_cid_ic

**Definizione**: Un codice di integrazione per l'origine dati. Questo può essere utilizzato al posto dell’ID origine dati/ID spazio nomi nella richiesta API al servizio core Adobe Experience Cloud Privacy.

**ID** spazio nomi: Non applicabile

Esempio in JSON:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
