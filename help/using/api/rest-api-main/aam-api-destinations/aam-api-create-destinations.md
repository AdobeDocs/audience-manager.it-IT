---
description: Create le destinazioni con questi metodi RESTful API.
seo-description: Create le destinazioni con questi metodi RESTful API.
seo-title: Crea destinazioni
solution: Audience Manager
title: Crea destinazioni
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Crea destinazioni {#create-destinations}

Creare destinazioni con questi [!UICONTROL RESTful API] metodi.

<!-- c_create_destinations.xml -->

## Tipi di destinazione supportati: Solo URL e cookie

I `POST` metodi disponibili consentono di creare [!UICONTROL URL] e [!UICONTROL cookie destinations] solo. Al momento non è possibile creare [!UICONTROL server-to-server destinations] con questi [!DNL REST API] metodi. Tuttavia, i `GET` metodi di destinazione correlati consentono di recuperare le informazioni [!UICONTROL server-to-server destinations] create nell'interfaccia utente.

## Creare una destinazione URL non seriale {#create-nonserial-dest}

Un `POST` metodo che consente di creare una destinazione che accetta segmenti composti da coppie chiave-valore singole (ad esempio, `gender=male` o `gender=female`).

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

Un `POST` metodo che consente di creare una destinazione che accetta più valori associati a una singola chiave (ad esempio, `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### Richiesta

`POST https://api.demdex.com/v1/destinations/`

### Richiesta di esempio

Specificare il carattere di delimitazione [!DNL URL] e di protezione per la coppia chiave-valore passata alla destinazione. Tutti i valori di richiesta sono obbligatori, salvo diversa indicazione.

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

Un `POST` metodo che consente di creare un [!UICONTROL cookie destination] che accetta segmenti composti da coppie chiave-valore singole (ad esempio, `gender=male` o `gender=female`).

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

Un `POST` metodo che consente di creare una destinazione che accetta più valori associati a una singola chiave (ad esempio, `color=blue, red, green`).

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

Un `POST` metodo che consente di creare una destinazione che accetta segmenti contenenti più chiavi con valori diversi (ad esempio, `gender=male; gender=female; color=blue; color=red`).

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

## Crea una destinazione cookie: Multi-chiave, serializzata {#create-cookie-dest-multi-serial}

Un `POST` metodo che consente di creare una destinazione che accetta segmenti contenenti più chiavi e valori (ad esempio, `gender=male, female; color=blue, red, green`).

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
>* [Destinazioni](../../../features/destinations/destinations.md)
>* [Serializzazione delle destinazioni](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Spiegazione delle coppie chiave-valore](../../../reference/key-value-pairs-explained.md)

