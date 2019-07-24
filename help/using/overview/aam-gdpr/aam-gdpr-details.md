---
description: Questo documento descrive i tecnici correlati al Regolamento generale sulla protezione dei dati (GDPR) di Audience Manager e mostra come inviare richieste GDPR ad Audience Manager.
seo-description: Questo documento descrive i tecnici correlati al Regolamento generale sulla protezione dei dati (GDPR) di Audience Manager e mostra come inviare richieste GDPR ad Audience Manager.
seo-title: GDPR in Audience Manager
solution: Audience Manager
title: GDPR in Audience Manager
uuid: ed 23 a 478-32 be -460 d-bb 03-a 735317 f 7 c 0 f
translation-type: tm+mt
source-git-commit: b791e22e9c8c848a8fc14c6d6494f77c9e7335dc

---


# GDPR in Audience Manager{#gdpr-in-audience-manager}

Questo documento descrive i tecnici correlati al Regolamento generale sulla protezione dei dati (GDPR) di Audience Manager e mostra come inviare richieste GDPR ad Audience Manager.

## GDPR Documentation in the Experience Cloud {#gdpr-documentation}

Prima di leggere specifiche di Audience Manager, ti consigliamo di seguire il materiale Experience Cloud per il Regolamento generale sulla protezione dei dati europei (GDPR), collegato di seguito:

* [GDPR e Business](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [White paper GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [Terminologia RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

Le sezioni seguenti spiegano cosa significa il GDPR per Audience Manager e come puoi inviare richieste GDPR ad Audience Manager.

## Types of GDPR Requests and How to Make a GDPR Request {#types-of-gdpr-requests}

As an Audience Manager customer, you can submit individual GDPR requests to access and delete customer data, either through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)**. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). In caso di domande, contattate l'Assistenza clienti all'indirizzo gdprsupport@adobe.com.

## Accedere ai dati {#access-data}

Comprendiamo il tuo impegno a rispettare le richieste dei clienti GDPR entro 30 giorni dalla ricezione. Per questo motivo, provate a elaborare la richiesta di accesso ai dati il prima possibile.

**Richiesta**

You can log data access requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `access` action). In entrambi i casi, devi caricare un JSON con gli identificatori Audience Manager per i quali stai inviando la richiesta di accesso ai dati. See what a well-formed JSON looks like in the **[Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/access_request.json)**.

**Risposta**

Le risposte per l'accesso alle richieste dei dati contengono un riepilogo del numero totale di caratteristiche e segmenti, tipo di caratteristica, descrizioni di caratteristiche e segmenti insieme ai rispettivi nomi origine dati. La risposta di accesso includerà anche dati di seconda parte e di terze parti accessibili al Controller dati insieme ai dati di prime parti. When [!UICONTROL declared IDs] such as cross device CRM IDs or customer cookie IDs are sent in GDPR requests, Audience Manager will include the Access response from all the linked devices (up to 100 devices per declared ID).

**Stato risposta**

In caso di errori di Audience Manager nella risposta, questi vengono considerati codici di errore nella risposta. We have a [list of error codes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md), where you can find more information about the returned errors.

**Risposta di esempio**

Una risposta di accesso di esempio potrebbe essere simile a quella riportata di seguito. In questo esempio, l'ID del soggetto dati è un ID del cookie. Sono idonei per diverse caratteristiche e appartengono ad alcuni segmenti. L'ID del cookie è collegato a un ID mobile. L'esempio contiene inoltre metadati per il telefono utilizzato.

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

La tabella seguente contiene le descrizioni per tutti i campi restituiti nella risposta di accesso ai dati, nell'ordine in cui appaiono sopra.

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
   <td colname="col2"> <p>L'ID utente per i dati seguenti. Si tratta di un ID fornito nella richiesta di accesso ai dati GDPR o di un ID collegato a uno degli ID dichiarati che hai fornito. The ID types are described in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Denominato anche fonte di dati. See the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>L'ID spazio dei nomi/sorgente dei dati. See <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>I codici di integrazione sono nomi intuitivi per le tue origini dati e ti aiutano a tenere traccia delle origini dati più semplice rispetto all'uso degli ID di origine dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nome provider dati </code> </p> </td> 
   <td colname="col2"> <p>Nome del proprietario dell'origine dati. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">Per i dati di prime parti, si tratta del nome della società. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">Per i dati di seconda parte, si tratta del nome della società partner. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">Per i dati di terze parti, questo è il nome del partner dati. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>Tipo di ID per il quale è stato richiesto l'accesso ai dati RGPD. Accepted types are listed in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> avvisi</code> </p> </td> 
   <td colname="col2"> <p>Avvisi restituiscono ulteriori informazioni relative alla richiesta di accesso ai dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>Breve informazioni sull'avviso. </p> <p>I due avvisi che potete ricevere sono: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Dati dispositivo </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Richiesta incompleta </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>Una descrizione più dettagliata dell'avviso ricevuto: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Dati dispositivo - Contiene dati da tutti gli utenti del dispositivo </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Richiesta incompleta - Il recupero dei dati di Audience Manager non è stato completato. Alcune informazioni potrebbero essere mancanti. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dati </code> </p> </td> 
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
   <td colname="col2"> <p>Il tipo di caratteristica. I valori possibili sono: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>First party</i> for your own traits. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Seconda parte</i> per caratteristiche che appartengono ai tuoi partner. Read our <a href="../../overview/data-types-collected.md#second-party-data"> Second Party Data</a> article for more information. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Terza parte</i> per caratteristiche ottenute dai partner dati tramite <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Alcune parole utili per descrivere lo scopo o la funzione della caratteristica. Questo campo è facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> controlli per l'esportazione dei dati</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this trait's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nome provider dati</code> </p> </td> 
   <td colname="col2"> <p>Nome del proprietario dell'origine dati a cui appartiene. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">Per i dati di prime parti, si tratta del nome della società. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">Per i dati di seconda parte, si tratta del nome della società partner. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">Per i dati di terze parti, questo è il nome del partner dati. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>Esattamente il tempo in cui l'oggetto dati ha ottenuto l'ultima qualifica per questa caratteristica. Il formato della data è AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segmenti </code> </p> </td> 
   <td colname="col2"> <p>Segmenti a cui appartiene l'utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Il nome del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Alcune parole utili per descrivere questo segmento. Questo campo è facoltativo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> controlli per l'esportazione dei dati</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this segment's data source. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nome provider dati</code> </p> </td> 
   <td colname="col2"> <p>Nome del proprietario dell'origine dati a cui appartiene questo segmento. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">Per i dati di prime parti, si tratta del nome della società. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">Per i dati di seconda parte, si tratta del nome della società partner. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">Per i dati di terze parti, questo è il nome del partner dati. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>Il tempo esatto per cui l'oggetto dati ha avuto la precedenza per questo segmento. Il formato della data è AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active</code> </p> </td> 
   <td colname="col2"> <p>Indica se l'oggetto dati è attualmente qualificato per questo segmento. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> links </code> </p> </td> 
   <td colname="col2"> <p>ID aggiuntivo a cui è stato collegato questo ID. Le informazioni vengono restituite in: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (origine dati) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">ID spazio nomi </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">nome provider dati </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>Tutti questi campi sono descritti nelle prime righe di questa tabella. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> collegamento dati data</code> </p> </td> 
   <td colname="col2"> <p>L'ora esatta in cui un evento di sincronizzazione ID ha effettuato il collegamento tra ID. Il formato della data è AAAA-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> metadati del dispositivo </code> </p> </td> 
   <td colname="col2"> <p>Informazioni sul dispositivo. Queste informazioni includono i campi seguenti. Non tutti i campi vengono restituiti per tutti i tipi di dispositivi. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Informazioni hardware </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Produttore dispositivo </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>Nome marketing del dispositivo </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>Il modello dispositivo </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>Il nome del sistema operativo del dispositivo (OS) </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>Versione del sistema operativo </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>Il fornitore del dispositivo </p> </li> 
     </ul> </p> <p> <p>Nota: I metadati del dispositivo vengono restituiti solo quando si invia: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">ID mobili </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">ID Audience Manager </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">ID di Experience Cloud </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cancellare i dati {#delete-data}

Comprendiamo il tuo impegno a rispettare le richieste dei clienti GDPR entro 30 giorni dalla ricezione. Per questo motivo, proviamo a elaborare la richiesta di eliminazione dati il prima possibile.

**Richiesta**

You can log data deletion requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `delete` action). In entrambi i casi, devi caricare un JSON con gli identificatori Audience Manager per i quali stai inviando la richiesta di accesso ai dati. See what a well-formed JSON looks like in the [Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/delete_request.json)**.

**Risposta**

In risposta alle richieste di eliminazione dei dati, abbiamo eliminato caratteristiche e segmenti associati al rispettivo identificatore Audience Manager. Inoltre, i rispettivi identificatori Audience Manager per l'oggetto dati verranno sistematicamente rimossi da un'ulteriore raccolta di dati da Audience Manager e le rispettive mappature ID saranno rimosse. Quando vengono inviati ID dichiarati come ID CRM cross-device o ID di cookie cliente nelle richieste GDPR, Audience Manager eseguirà le azioni Elimina su tutti i dispositivi collegati (fino a 100 dispositivi per ID dichiarato).

## Opt-out Request {#opt-out-request}

For opt-out requests, please refer to our documentation on [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

## Audience Manager Identifiers (IDs) {#aam-ids}

Quando inviate richieste GDPR ad Adobe Audience Manager, dovete includere uno degli identificatori (ID) elencati di seguito. You can find more information on the ID formats in our [Index of Audience Manager IDs](../../reference/ids-in-aam.md).

### ID utente univoco di Adobe Audience Manager

**ID utente**: aam_ uuid

**Definizione**: ID utente univoco di Adobe Audience Manager

**ID spazio nomi**: 0

>[!NOTE]
>
>È inoltre possibile utilizzare lo spazio nomi CORE. Consulta il secondo esempio JSON.

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

**ID utente**: mid

**Definizione**: Adobe Experience Cloud ID, precedentemente noto come ID visitatore o Marketing Cloud ID

**ID spazio nomi**: 4

>[!NOTE]
>
>È inoltre possibile utilizzare lo spazio nomi ECID. Consulta il secondo esempio JSON.

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

**ID utente**: cid

**Definizione**: ID cliente, ad esempio un cookie impostato per i visitatori anonimi del sito o un ID CRM da un sistema offline o un nome utente hash

**ID spazio nomi**: Specifici del cliente. Please find it from your Audience Manager instance.

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

**ID utente**: d_ cid

**Definizione**: ID pubblicitari mobili.
>[!IMPORTANT]
>
> Se utilizzi l'SDK di Mobile, devi inviare anche l'Experience Cloud ID (MID) insieme agli ID pubblicitari mobili per le risposte complete ai GDPR Access ed Elimina.

**ID dello spazio dei nomi**:

* IDFA: 20915
* GAID: 20914

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

### Codice di integrazione

**ID utente**: d_ cid_ ic

**Definizione**: Un codice di integrazione per l'origine dati. Questo può essere utilizzato invece dell'ID di origine dati/ID spazio nomi nella richiesta API al servizio core privacy di Adobe Experience Cloud.

**ID spazio nomi**: Non applicabile

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
