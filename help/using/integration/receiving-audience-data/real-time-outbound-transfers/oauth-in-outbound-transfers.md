---
description: Quando si pubblicano segmenti nella destinazione partner tramite un'integrazione server-to-server in tempo reale, Audience Manager può essere configurato per l'autenticazione tramite OAuth 2.0 quando si effettuano le richieste. Questo consente di inviare richieste autenticate da Audience Manager all’endpoint.
seo-description: Quando si pubblicano segmenti nella destinazione partner tramite un'integrazione server-to-server in tempo reale, Audience Manager può essere configurato per l'autenticazione tramite OAuth 2.0 quando si effettuano le richieste. Questo consente di inviare richieste autenticate da Audience Manager all’endpoint.
seo-title: Integrazione OAuth 2.0 per trasferimenti in uscita in tempo reale
solution: Audience Manager
title: Integrazione OAuth 2.0 per trasferimenti in uscita in tempo reale
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] Integrazione per trasferimenti in uscita in tempo reale{#oauth-integration-for-real-time-outbound-transfers}

Quando si pubblicano segmenti nella destinazione partner tramite un'integrazione server-to-server in tempo reale, Audience Manager può essere configurato per l'autenticazione tramite [!DNL OAuth 2.0] quando si effettuano le richieste. Questo consente di inviare richieste autenticate da Audience Manager all’endpoint.

## Flusso di autenticazione {#auth-flow}

L'implementazione dell'autenticazione [!DNL Adobe Audience Manager] OAuth 2.0 [](https://tools.ietf.org/html/rfc6749#section-4.4) è basata sul flusso di concessione delle credenziali client ed effettua le seguenti operazioni:

1. Devi fornirci:
   * L' [!DNL OAuth 2.0] endpoint che genera il token di autenticazione.
   * Le credenziali utilizzate per generare un token.
1. Un [!DNL Audience Manager] consulente configura la [destinazione](../../../features/destinations/destinations.md) utilizzando le informazioni fornite.
1. Una volta mappato un segmento a questa destinazione, il nostro sistema di trasferimento dati in tempo reale, [IRIS](../../../reference/system-components/components-data-action.md#iris), effettua una `POST` richiesta all'endpoint token per scambiare le credenziali per un token portatore.
1. Per ogni richiesta di pubblicazione di segmenti all’endpoint del partner, [!UICONTROL IRIS] utilizza il token del portatore per l’autenticazione.

![](assets/oauth2-iris.png)

## Requisiti {#auth-requirements}

Come [!DNL Audience Manager] partner, per ricevere le richieste autenticate sono necessari i seguenti endpoint:

### Endpoint 1 utilizzato da IRIS per ottenere un token portatore

Questo endpoint accetta le credenziali fornite al passaggio 1 e genera un token al portatore che verrà utilizzato nelle richieste successive.

* L'endpoint deve accettare `HTTP POST` le richieste.
* L’endpoint deve accettare e guardare l’ [!DNL Authorization] intestazione. Il valore per questa intestazione sarà: `Basic <credentials_provided_by_partner>`.
* L’endpoint deve controllare l’ [!DNL Content-type] intestazione e verificare che il relativo valore sia `application/x-www-form-urlencoded ; charset=UTF-8`.
* Il corpo della richiesta sarà `grant_type=client_credentials`.

### Esempio di richiesta effettuata da Audience Manager all’endpoint del partner per ottenere un token del portatore

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

### Endpoint 2 utilizzato da IRIS per pubblicare segmenti utilizzando il token del portatore

[!DNL Audience Manager] invia dati a questo endpoint in tempo quasi reale, in quanto gli utenti sono idonei per i segmenti. Inoltre, questo metodo può inviare batch di dati offline o caricati con la stessa frequenza che ogni 24 ore.

Il token del portatore generato dall'endpoint 1 viene utilizzato per inviare richieste a questo endpoint. Il sistema [!DNL Audience Manager] di trasferimento dati in tempo reale, [IRIS](../../../reference/system-components/components-data-action.md#iris), crea una normale richiesta HTTPS e include un'intestazione Autorizzazione. Il valore per questa intestazione sarà: Portatore `<bearer token from step 1>`.

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
>Questa richiesta contiene un payload standard (contenuto della richiesta).

## Considerazioni importanti {#considerations}

### I token sono password

Le credenziali presentate dal partner e i token ottenuti [!DNL Audience Manager] al momento dell'autenticazione tramite il [!DNL OAuth 2.0] flusso, sono informazioni sensibili e non devono essere condivise con terzi.

### [!DNL SSL] obbligatorio

[!DNL SSL] devono essere utilizzati per mantenere un processo di autenticazione protetto. Tutte le richieste, comprese quelle utilizzate per ottenere e utilizzare i token, devono utilizzare `HTTPS` gli endpoint.