---
description: Crea destinazioni con questi metodi API restful.
seo-description: Crea destinazioni con questi metodi API restful.
seo-title: Crea destinazioni
solution: Audience Manager
title: Crea destinazioni
uuid: 12 f 04151-ad 0 e -4 cb 6-8 f 3 b-b 5 c 427 dc 2 cef
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Crea destinazioni {#create-destinations}

Creare destinazioni con questi [!UICONTROL RESTful API] metodi.

<!-- c_create_destinations.xml -->

## Tipi di destinazione supportati: URL e solo cookie

I metodi disponibili `POST` consentono di creare [!UICONTROL URL][!UICONTROL cookie destinations] e solo. Attualmente non è possibile creare [!UICONTROL server-to-server destinations] con questi [!DNL REST API] metodi. Tuttavia, i metodi di destinazione `GET` correlati consentono di recuperare le informazioni sulla [!UICONTROL server-to-server destinations] creazione nell&#39;interfaccia utente.

>[!MORE_ LIKE_ THIS]
>
>* [Destinazioni](../../../features/destinations/destinations.md#destination-api-methods)
>* [Serializzazione destinazione](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Coppie chiave-valore spiegate](../../../reference/key-value-pairs-explained.md)


## Creare una destinazione URL non seriale {#create-nonserial-dest}

`POST` Metodo che consente di creare una destinazione che accetta segmenti composti da coppie chiave-valore singole (ad es. `gender=male` , o `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Questa richiesta crea una sola destinazione. Tutti i valori di richiesta sono obbligatori, se non diversamente indicato.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Risposta

Restituisce una richiesta di esito positivo `201 created` e la destinazione.

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

>[!MORE_ LIKE_ THIS]
>
>* [Serializzazione destinazione](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Creare una destinazione URL serializzata {#create-serial-url-dest}

`POST` Metodo che consente di creare una destinazione che accetta più valori associati a una singola chiave (ad es. `color=blue, red, green`,).

<!-- r_create_serial_url_destination.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Specificare il carattere di protezione e [!DNL URL] il delimitatore per la coppia chiave-valore passata alla destinazione. Tutti i valori di richiesta sono obbligatori, se non diversamente indicato.

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

Un aggiornamento riuscito restituisce il codice `201 created` di risposta e la destinazione.

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

>[!MORE_ LIKE_ THIS]
>
>* [Serializzazione destinazione](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Crea una destinazione cookie: Chiave singola, non serializzata {#create-cookie-dest-single}

`POST` Metodo che consente di creare uno [!UICONTROL cookie destination] che accetta segmenti composti da coppie chiave-valore singole (ad es. `gender=male` , o `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, se non diversamente indicato.

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

Un aggiornamento riuscito restituisce il codice `201 created` di risposta e la destinazione.

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

>[!MORE_ LIKE_ THIS]
>
>* [Serializzazione destinazione](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Coppie chiave-valore spiegate](../../../reference/key-value-pairs-explained.md)


## Crea una destinazione cookie: Chiave singola serializzata {#create-cookie-dest-single-serial}

`POST` Metodo che consente di creare una destinazione che accetta più valori associati a una singola chiave (ad es. `color=blue, red, green`,).

<!-- r_cookie_destination_singlekey_serial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, se non diversamente indicato.

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

Un aggiornamento riuscito restituisce il codice `201 created` di risposta e la destinazione.

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

>[!MORE_ LIKE_ THIS]
>
>* [Serializzazione destinazione](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Coppie chiave-valore spiegate](../../../reference/key-value-pairs-explained.md)


## Crea una destinazione cookie: Multi-Key, non serializzato {#create-cookie-dest-multi}

`POST` Metodo che consente di creare una destinazione che accetta segmenti contenenti più chiavi con valori diversi (ad es., `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, se non diversamente indicato.

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

Un aggiornamento riuscito restituisce il codice `201 created` di risposta e la destinazione.

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

## Crea una destinazione cookie: Multi-Key, serializzato {#create-cookie-dest-multi-serial}

`POST` Metodo che consente di creare una destinazione che accetta segmenti contenenti più chiavi e valori (ad es., `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Tutti i valori di richiesta sono obbligatori, se non diversamente indicato.

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

Un aggiornamento riuscito restituisce il codice `201 created` di risposta e la destinazione.

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

>[!MORE_ LIKE_ THIS]
>
>* [Serializzazione destinazione](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Coppie chiave-valore spiegate](../../../reference/key-value-pairs-explained.md)

