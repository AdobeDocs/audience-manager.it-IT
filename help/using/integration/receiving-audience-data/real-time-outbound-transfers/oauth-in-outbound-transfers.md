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

Quando si pubblicano segmenti alla destinazione partner tramite un&#39;integrazione server-to-server in tempo reale, Audience Manager può essere configurato per l&#39;autenticazione utilizzando [!DNL OAuth 2.0] le richieste. Ciò mostra la capacità di emettere richieste autenticate da Audience Manager all&#39;endpoint.

## Flusso di autenticazione {#auth-flow}

L&#39;implementazione dell&#39;autenticazione [!DNL Adobe Audience Manager][oauth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) si basa sul flusso di concessione Client Credentials ed effettua le seguenti operazioni:

1. È necessario fornire:
   * L&#39; [!DNL OAuth 2.0] endpoint che genera il token di autenticazione.
   * Le credenziali utilizzate per generare un token.
1. Un [!DNL Audience Manager] consulente configura la [destinazione](../../../features/destinations/destinations.md) utilizzando le informazioni fornite.
1. Una volta mappato un segmento su questa destinazione, il nostro sistema di trasferimento dati in tempo reale [, IRIS](../../../reference/system-components/components-data-action.md#iris), effettua una `POST` richiesta all&#39;endpoint token per scambiare le credenziali per un token di più persone.
1. Per ogni richiesta di pubblicazione del segmento all&#39;endpoint del partner [!UICONTROL IRIS] , utilizza il token del beator per l&#39;autenticazione.

![](assets/oauth2-iris.png)

## Requisiti {#auth-requirements}

In qualità [!DNL Audience Manager] di partner, sono necessari i seguenti endpoint per ricevere richieste autenticate:

### Endpoint 1 utilizzato da IRIS per ottenere un token per il visualizzatore

Questo endpoint accetta le credenziali fornite al passaggio 1 e genera un token bewards che verrà utilizzato per le richieste successive.

* L&#39;endpoint deve accettare `HTTP POST` richieste.
* L&#39;endpoint deve accettare e visualizzare l&#39; [!DNL Authorization] intestazione. Il valore di questa intestazione sarà: `Basic <credentials_provided_by_partner>`.
* L&#39;endpoint deve controllare l&#39; [!DNL Content-type] intestazione e convalidarne il valore `application/x-www-form-urlencoded ; charset=UTF-8`.
* Il corpo della richiesta `grant_type=client_credentials`sarà.

### Richiesta di esempio eseguita da Audience Manager all&#39;endpoint del partner per ottenere un token del besting

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

### Risposta di esempio dall&#39;endpoint partner

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

Il token beator generato dall&#39;endpoint 1 viene utilizzato per inviare richieste a questo endpoint. Il sistema di trasferimento dati [!DNL Audience Manager] in tempo reale [, IRIS,](../../../reference/system-components/components-data-action.md#iris)crea una richiesta HTTPS normale e include un&#39;intestazione di autorizzazione. Il valore di questa intestazione sarà: Bearer `<bearer token from step 1>`.

### Risposta di esempio dall&#39;endpoint partner

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

## Considerazioni importanti {#considerations}

### I token sono password

Le credenziali presentate dal partner e i token ottenuti da [!DNL Audience Manager] autenticazione tramite [!DNL OAuth 2.0] flusso sono informazioni sensibili e non devono essere condivise con terze parti.

### [!DNL SSL] è obbligatorio

[!DNL SSL] devono essere utilizzati per mantenere un processo di autenticazione protetto. Tutte le richieste, comprese quelle utilizzate per ottenere e utilizzare i token, devono utilizzare `HTTPS` gli endpoint.