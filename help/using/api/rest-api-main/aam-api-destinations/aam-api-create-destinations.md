---
description: Create le destinazioni con questi metodi RESTful API.
seo-description: Create le destinazioni con questi metodi RESTful API.
seo-title: Creare destinazioni
solution: Audience Manager
title: Creare destinazioni
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 9%

---


# Creare destinazioni {#create-destinations}

Create le destinazioni con questi metodi [!UICONTROL RESTful API].

<!-- c_create_destinations.xml -->

## Tipi di destinazione supportati: Solo URL e cookie

I metodi `POST` disponibili consentono di creare solo [!UICONTROL URL] e [!UICONTROL cookie destinations]. Al momento non è possibile creare [!UICONTROL server-to-server destinations] con questi metodi [!DNL REST API]. Tuttavia, i metodi `GET` di destinazione correlati consentono di recuperare informazioni su [!UICONTROL server-to-server destinations] creati nell&#39;interfaccia utente.

## Creare una destinazione URL non seriale {#create-nonserial-dest}

Metodo `POST` che consente di creare una destinazione che accetta segmenti composti da coppie chiave-valore singole (ad esempio, `gender=male` o `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Questa richiesta crea una singola destinazione. Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Risposta

Una richiesta corretta restituisce `201 created` e la destinazione.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## Creare una destinazione URL serializzata {#create-serial-url-dest}

Un metodo `POST` che consente di creare una destinazione che accetta più valori associati a una singola chiave (ad es. `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Specificare il carattere di delimitazione [!DNL URL] protetto per la coppia chiave-valore passata alla destinazione. Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### Risposta

Un aggiornamento riuscito restituisce il codice di risposta `201 created` e la destinazione.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## Crea una destinazione cookie: Chiave singola, non serializzata {#create-cookie-dest-single}

Metodo `POST` che consente di creare un [!UICONTROL cookie destination] che accetta segmenti composti da coppie chiave-valore singole (ad esempio, `gender=male` o `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### Risposta

Un aggiornamento riuscito restituisce il codice di risposta `201 created` e la destinazione.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## Crea una destinazione cookie: Chiave singola, serializzata {#create-cookie-dest-single-serial}

Un metodo `POST` che consente di creare una destinazione che accetta più valori associati a una singola chiave (ad es. `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Risposta

Un aggiornamento riuscito restituisce il codice di risposta `201 created` e la destinazione.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## Crea una destinazione cookie: Multi-chiave, non serializzata {#create-cookie-dest-multi}

Metodo `POST` che consente di creare una destinazione che accetta segmenti contenenti più chiavi con valori diversi (ad esempio, `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### Risposta

Un aggiornamento riuscito restituisce il codice di risposta `201 created` e la destinazione.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Crea una destinazione cookie: Più chiavi, serializzate {#create-cookie-dest-multi-serial}

Metodo `POST` che consente di creare una destinazione che accetta segmenti contenenti più chiavi e valori (ad esempio, `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Risposta

Un aggiornamento riuscito restituisce il codice di risposta `201 created` e la destinazione.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [Destinazioni ](../../../features/destinations/destinations.md)
>* [Serializzazione delle destinazioni](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Spiegazione delle coppie chiave-valore](../../../reference/key-value-pairs-explained.md)

