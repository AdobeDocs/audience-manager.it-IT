---
description: Un metodo GET che restituisce la destinazione per l'ID di destinazione specificato.
seo-description: Un metodo GET che restituisce la destinazione per l'ID di destinazione specificato.
seo-title: Restituire una destinazione per ID destinazione
solution: Audience Manager
title: Restituire una destinazione per ID destinazione
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
exl-id: c0850e71-7830-4635-b773-e9a28ab5bd68
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 9%

---

# Restituire una destinazione per ID destinazione {#return-a-destination-by-destination-id}

Un metodo `GET` che restituisce la destinazione per il `destinationId` specificato.

<!-- r_get_all_destinations_order_id.xml -->

## Richiesta

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>Compilare il campo `mappings` passare `includeMappings=true` nell&#39;URL.

## Risposta

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Restituisci tutte le destinazioni {#return-all-destinations}

Un metodo `GET` che restituisce tutte le destinazioni per il partner specificato.

<!-- r_get_all_destinations.xml -->

### Richiesta

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Facoltativo)* Passa  `containsSegment=<sid>` per restituire un array di tutte le destinazioni mappate al segmento specificato. Ad esempio, la query potrebbe avere un aspetto simile al seguente: `GET .../destinations/?containsSegment=4321`.
   >
   >
* Non restituisce l&#39;oggetto di destinazione completo. Ottenere la destinazione in base all&#39;ordine dei dati se è necessario un oggetto completamente popolato.


### Parametri di query opzionali

Puoi utilizzare questi parametri facoltativi con metodi API che restituiscono le proprietà *all* per un oggetto. Imposta queste opzioni nella stringa di richiesta quando trasmetti la query in a [!DNL API]. Vedere [Parametri facoltativi](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th>
   <th colname="col2" class="entry"> Descrizione </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> Restituisce i risultati per numero di pagina. La numerazione inizia da 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> Imposta il numero di risultati di risposta restituiti dalla richiesta (10 è l’impostazione predefinita). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">Ordina e restituisce i risultati in base alla proprietà <span class="keyword"> JSON</span> specificata. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Ordina e restituisce i risultati in ordine decrescente. Crescente è l'impostazione predefinita. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che tu voglia trovare risultati per tutti i modelli con la parola "Test" in uno qualsiasi dei campi di valore per quell’elemento. La richiesta di esempio potrebbe essere simile alla seguente: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Puoi cercare qualsiasi valore restituito da un metodo "get all". </p> </td>
  </tr>
 </tbody>
</table>

### Risposta

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Restituire una mappatura di destinazione con l’ ID mappatura {#return-dest-mapping-id}

Un metodo `GET` che restituisce una mappatura di destinazione singola basata su `mappingId`.

<!-- r_get_destination_trait_data_order.xml -->

### Richiesta

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### Risposta

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Mappature di destinazione di ritorno {#return-dest-mappings}

Un metodo `GET` che restituisce le mappature di una destinazione.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>La mappatura restituita è specifica per il tipo di destinazione e la configurazione.

### Richiesta

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>Supporta i parametri di paging.

### Risposta

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Restituisci tutte le piattaforme di destinazione disponibili {#return-dest-platforms}

Un metodo `GET` che restituisce tutte le piattaforme di dispositivi disponibili per le destinazioni.

<!-- r_get_dest_platforms.xml -->

### Richiesta

`GET /destinations/configurations/available-platforms/`

### Risposta

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Restituire la cronologia dei processi di destinazione S2S e Bulk S2S {#return-job-history}

Un metodo `GET` che restituisce informazioni sulla cronologia dei processi di destinazione in uscita [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) e in massa [!UICONTROL S2S].

<!-- r_get_job_history.xml -->

### Richiesta

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Parametri di query richiesti: `startDate` = *&lt;`epochtime`>* e `endDate` = *&lt;`epochtime`>*.

### Risposta

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
