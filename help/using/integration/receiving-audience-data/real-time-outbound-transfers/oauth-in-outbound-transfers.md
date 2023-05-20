---
description: Quando si pubblicano segmenti nella destinazione partner tramite un’integrazione server-to-server in tempo reale, è possibile configurare Audience Manager per l’autenticazione utilizzando OAuth 2.0 quando si effettuano le richieste. Questo offre la possibilità di emettere richieste autenticate da Audience Manager all’endpoint.
seo-description: When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using OAuth 2.0 when making the requests. This presents the ability to issue authenticated requests from Audience Manager to your endpoint.
seo-title: OAuth 2.0 Integration for Real-Time Outbound Transfers
solution: Audience Manager
title: Integrazione di OAuth 2.0 per trasferimenti in uscita in tempo reale
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# [!DNL OAuth 2.0] Integrazione per trasferimenti in uscita in tempo reale{#oauth-integration-for-real-time-outbound-transfers}

Quando si pubblicano segmenti nella destinazione partner tramite un’integrazione server-to-server in tempo reale, è possibile impostare un Audience Manager per l’autenticazione utilizzando [!DNL OAuth 2.0] quando eseguono le richieste. Questo offre la possibilità di emettere richieste autenticate da Audience Manager all’endpoint.

## Flusso di autenticazione {#auth-flow}

Il [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) L’implementazione dell’autenticazione si basa sul flusso di concessione delle credenziali client e segue questi passaggi:

1. Devi fornirci:
   * Il [!DNL OAuth 2.0] endpoint che genera il token di autenticazione.
   * Credenziali utilizzate per generare un token.
1. Un [!DNL Audience Manager] consulente imposta il [destinazione](../../../features/destinations/destinations.md) utilizzando le informazioni fornite.
1. Una volta mappato un segmento su questa destinazione, il nostro sistema di trasferimento dati in tempo reale, [IRIS](../../../reference/system-components/components-data-action.md#iris), rende un `POST` richiesta all’endpoint del token di scambiare le credenziali per un token Bearer.
1. Per ogni richiesta di pubblicazione di segmenti nell’endpoint partner, [!UICONTROL IRIS] utilizza il token Bearer per l’autenticazione.

![](assets/oauth2-iris.png)

## Requisiti {#auth-requirements}

Come un [!DNL Audience Manager] partner, per ricevere le richieste autenticate sono necessari i seguenti endpoint:

### Endpoint 1 utilizzato da IRIS per ottenere un token Bearer

Questo endpoint accetta le credenziali fornite al passaggio 1 e genera un token Bearer che verrà utilizzato nelle richieste successive.

* L’endpoint deve accettare `HTTP POST` richieste.
* L’endpoint deve accettare e esaminare [!DNL Authorization] intestazione. Il valore di questa intestazione sarà: `Basic <credentials_provided_by_partner>`.
* L’endpoint deve considerare [!DNL Content-type] e verifica che il relativo valore sia `application/x-www-form-urlencoded ; charset=UTF-8`.
* Il corpo della richiesta sarà `grant_type=client_credentials`.

### Esempio di richiesta effettuata da Audience Manager all’endpoint partner per ottenere un token Bearer

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### Esempio di risposta dall’endpoint del partner

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Endpoint 2 utilizzato da IRIS per pubblicare segmenti utilizzando il token Bearer

[!DNL Audience Manager] invia i dati a questo endpoint quasi in tempo reale, poiché gli utenti si qualificano per i segmenti. Inoltre, questo metodo può inviare batch di dati offline o onboarded ogni 24 ore.

Il token Bearer generato dall’endpoint 1 viene utilizzato per inviare richieste a questo endpoint. Il [!DNL Audience Manager] sistema di trasferimento dati in tempo reale, [IRIS](../../../reference/system-components/components-data-action.md#iris), crea una normale richiesta HTTPS e include un’intestazione Autorizzazione. Il valore di questa intestazione sarà: Bearer `<bearer token from step 1>`.

### Esempio di risposta dall’endpoint del partner

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>Questa richiesta contiene un payload standard (contenuto della richiesta).

## Considerazioni importanti {#considerations}

### I token sono password

Le credenziali presentate dal partner e i token ottenuti da [!DNL Audience Manager] durante l&#39;autenticazione tramite [!DNL OAuth 2.0] sono informazioni riservate e non devono essere condivise con terze parti.

### [!DNL SSL] è obbligatorio

[!DNL SSL] deve essere utilizzato per mantenere un processo di autenticazione sicuro. Tutte le richieste, incluse quelle utilizzate per ottenere e utilizzare i token, devono utilizzare `HTTPS` endpoint.
