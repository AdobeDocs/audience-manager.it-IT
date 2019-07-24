---
description: Quando si pubblicano segmenti alla destinazione partner tramite un'integrazione server-to-server in tempo reale, Audience Manager può essere configurato per l'autenticazione tramite oauth 2.0 al momento della creazione delle richieste. Ciò mostra la capacità di emettere richieste autenticate da Audience Manager all'endpoint.
seo-description: Quando si pubblicano segmenti alla destinazione partner tramite un'integrazione server-to-server in tempo reale, Audience Manager può essere configurato per l'autenticazione tramite oauth 2.0 al momento della creazione delle richieste. Ciò mostra la capacità di emettere richieste autenticate da Audience Manager all'endpoint.
seo-title: Integrazione oauth 2.0 per trasferimenti in tempo reale in tempo reale
solution: Audience Manager
title: Integrazione oauth 2.0 per trasferimenti in tempo reale in tempo reale
uuid: a 39 e 370 c-b 3 bd -4 b 06-a 1 af -60 a 024 ee 7 ee 4
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] Integrazione per trasferimenti in tempo reale in tempo reale{#oauth-integration-for-real-time-outbound-transfers}

When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using [!DNL OAuth 2.0] when making the requests. Ciò mostra la capacità di emettere richieste autenticate da Audience Manager all'endpoint.

## Authentication Flow {#auth-flow}

The [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) authentication implementation is based on the Client Credentials grant flow and follows these steps:

1. È necessario fornire:
   * The [!DNL OAuth 2.0] endpoint that generates the authentication token.
   * Le credenziali utilizzate per generare un token.
1. An [!DNL Audience Manager] consultant sets up the [destination](../../../features/destinations/destinations.md) using the information you provided.
1. Once a segment is mapped to this destination, our real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), makes a `POST` request to the token endpoint to exchange the credentials for a bearer token.
1. For each segment publishing request to the partner endpoint, [!UICONTROL IRIS] uses the bearer token to authenticate.

![](assets/oauth2-iris.png)

## Requisiti {#auth-requirements}

As an [!DNL Audience Manager] partner, the following endpoints are needed to receive authenticated requests:

### Endpoint 1 utilizzato da IRIS per ottenere un token per il visualizzatore

Questo endpoint accetta le credenziali fornite al passaggio 1 e genera un token bewards che verrà utilizzato per le richieste successive.

* The endpoint must accept `HTTP POST` requests.
* The endpoint must accept and look at the [!DNL Authorization] header. The value for this header will be: `Basic <credentials_provided_by_partner>`.
* The endpoint must look at the [!DNL Content-type] header and validate that its value is `application/x-www-form-urlencoded ; charset=UTF-8`.
* The body of the request will be `grant_type=client_credentials`.

### Richiesta di esempio eseguita da Audience Manager all'endpoint del partner per ottenere un token del besting

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

### Risposta di esempio dall'endpoint partner

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Endpoint 2 utilizzato da IRIS per pubblicare i segmenti utilizzando il token del visualizzatore

[!DNL Audience Manager] invia dati a questo endpoint in tempo reale, quando gli utenti si qualificano per i segmenti. Inoltre, questo metodo può inviare batch di dati offline o caricati ogni 24 ore.

Il token beator generato dall'endpoint 1 viene utilizzato per inviare richieste a questo endpoint. The [!DNL Audience Manager] real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), constructs a normal HTTPS request and includes an Authorization header. The value for this header will be: Bearer `<bearer token from step 1>`.

### Risposta di esempio dall'endpoint partner

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
>Questa richiesta contiene un payload standard (contenuto richiesta).

## Important Considerations {#considerations}

### I token sono password

The credentials presented by the partner and the tokens obtained by [!DNL Audience Manager] when authenticating using the [!DNL OAuth 2.0] flow, are sensitive information and must not be shared with third parties.

### [!DNL SSL] è obbligatorio

[!DNL SSL] devono essere utilizzati per mantenere un processo di autenticazione protetto. All requests, including the ones used to obtain and use the tokens must use `HTTPS` endpoints.