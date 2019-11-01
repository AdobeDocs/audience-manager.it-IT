---
description: Mappatura dei segmenti sulle destinazioni con questi metodi RESTful API.
seo-description: Mappatura dei segmenti sulle destinazioni con questi metodi RESTful API.
seo-title: Mappare i segmenti su una destinazione
solution: Audience Manager
title: Mappare i segmenti su una destinazione
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Mappare i segmenti su una destinazione {#map-segments-to-a-destination}

Mappatura dei segmenti sulle destinazioni con questi [!DNL RESTful API] metodi.

<!-- c_api_map_seg_dest.xml -->

## Tipi di destinazione supportati: Solo URL e cookie

I `POST` metodi disponibili consentono di mappare i segmenti [!UICONTROL URL] solo su e [!UICONTROL cookie destinations] solo. Al momento non è possibile mappare i segmenti [!UICONTROL server-to-server destinations] con questi [!DNL REST API] metodi. Utilizzate invece l'interfaccia utente. Tuttavia, i `GET` metodi di destinazione correlati consentono di recuperare le informazioni [!UICONTROL server-to-server destinations] create nell'interfaccia utente.

## Mappatura di un segmento su una destinazione URL non serializzata {#map-segment-non-serial}

Metodo `POST` che consente di mappare un segmento su una destinazione non seriale [!UICONTROL URL] .

<!-- r_map_noserial_url.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### Risposta

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## Mappatura di un segmento su una destinazione URL serializzata {#map-segment-serial}

Metodo `POST` che consente di mappare un segmento a una destinazione serializzata [!UICONTROL URL] .

<!-- r_map_serialized_url.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Richiesta di esempio

Nella richiesta, il valore `traitAlias` corrisponde alla chiave in una coppia chiave-valore. Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Risposta

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Mappatura di un segmento su una destinazione cookie: Chiave singola, non serializzata {#map-segment-cookie-noserial}

Metodo `POST` che consente di mappare un segmento a una destinazione a chiave singola e non serializzata [!UICONTROL cookie] .

<!-- r_map_cookie_noserial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Richiesta di esempio

Nella richiesta, il valore `valueAlias` corrisponde al valore in una coppia chiave-valore. Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### Risposta

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Mappatura di un segmento su una destinazione cookie: Multi-chiave, non serializzata {#map-segment-cookie-multi-noserial}

Un `POST` metodo che consente di mappare un segmento a una destinazione multi-chiave non serializzata [!UICONTROL cookie] .

<!-- r_map_cookie_multikey_noserial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Richiesta di esempio

Nella richiesta, la chiave `traitAlias` e `valueAlias` il valore vengono impostati rispettivamente in una coppia chiave-valore. Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Risposta

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Mappatura di un segmento su una destinazione cookie: Multi-chiave, serializzata {#map-segment-cookie-multi-serial}

Un `POST` metodo che consente di mappare un segmento su un segmento con più chiavi e serializzato [!UICONTROL cookie destination].

<!-- r_map_cookie_multikey_serialized.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Richiesta di esempio

Nella richiesta, la chiave `traitAlias` e `valueAlias` il valore vengono impostati in una coppia chiave-valore. Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Risposta

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Mappatura di un segmento su una destinazione da server a server {#map-segment-s2s}

Metodo `POST` che consente di mappare un segmento a una destinazione esistente [!UICONTROL server-to-server] . Tuttavia, non è possibile creare [!UICONTROL server-to-server] destinazioni con questi [!DNL API] metodi attualmente disponibili.

<!-- r_map_segment_s2s.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Richiesta di esempio

Nella richiesta, il valore `traitAlias` corrisponde alla chiave in una coppia chiave-valore. Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Risposta

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## Creare in massa mappature di destinazione {#bulk-create}

Un `POST` metodo che consente di trasmettere un array di mappature [!UICONTROL cookie] o di [!UICONTROL URL] destinazione.

<!-- r_bulk_create.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Risposta

Una risposta corretta restituisce l'array di mappature create.

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Aggiunta di più segmenti a una destinazione {#add-segments-dest}

Metodo `POST` che consente di mappare più segmenti su una destinazione.

<!-- r_add_segments_to_destination.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### Richiesta di esempio

Creare più mappature di destinazione in un array. Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Risposta

Restituisce un array di mappature create.

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Aggiornamento di una destinazione per ID destinazione {#update-dest-data-order}

Metodo `PUT` che consente di aggiornare una destinazione esistente per `destinationId`.

<!-- r_update_destination_data_order_id.xml -->

### Richiesta

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Risposta

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## Aggiornare una mappatura a una destinazione mappando l’ID {#update-mapping-dest-id}

Metodo `PUT` che consente di aggiornare una mappatura a una destinazione in base al valore specificato `mappingId`.

<!-- r_update_destination_trait_data_order_id.xml -->

### Richiesta

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### Risposta

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```

>[!MORELIKETHIS]
>
>* [Destinazioni](../../../features/destinations/destinations.md)
>* [Serializzazione delle destinazioni](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Spiegazione delle coppie chiave-valore](../../../reference/key-value-pairs-explained.md)

