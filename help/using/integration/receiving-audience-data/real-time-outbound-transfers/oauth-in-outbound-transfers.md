---
description: Quando si pubblicano i segmenti nella destinazione partner tramite un’integrazione server-to-server in tempo reale, è possibile impostare Audience Manager per l’autenticazione tramite OAuth 2.0 durante l’esecuzione delle richieste. Questo offre la possibilità di emettere richieste autenticate da Audience Manager all’endpoint.
seo-description: Quando si pubblicano i segmenti nella destinazione partner tramite un’integrazione server-to-server in tempo reale, è possibile impostare Audience Manager per l’autenticazione tramite OAuth 2.0 durante l’esecuzione delle richieste. Questo offre la possibilità di emettere richieste autenticate da Audience Manager all’endpoint.
seo-title: Integrazione di OAuth 2.0 per trasferimenti in uscita in tempo reale
solution: Audience Manager
title: Integrazione di OAuth 2.0 per trasferimenti in uscita in tempo reale
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Trasferimenti di dati in uscita
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 2%

---

# [!DNL OAuth 2.0] Integrazione per trasferimenti in uscita in tempo reale{#oauth-integration-for-real-time-outbound-transfers}

Quando si pubblicano i segmenti nella destinazione partner tramite un’integrazione server-to-server in tempo reale, è possibile configurare l’Audience Manager per l’autenticazione utilizzando [!DNL OAuth 2.0] durante l’esecuzione delle richieste. Questo offre la possibilità di emettere richieste autenticate da Audience Manager all’endpoint.

## Flusso di autenticazione {#auth-flow}

L’implementazione dell’autenticazione [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) si basa sul flusso di concessione delle credenziali client e segue questi passaggi:

1. Devi fornirci:
   * L&#39;endpoint [!DNL OAuth 2.0] che genera il token di autenticazione.
   * Le credenziali utilizzate per generare un token.
1. Un consulente [!DNL Audience Manager] imposta la [destinazione](../../../features/destinations/destinations.md) utilizzando le informazioni fornite.
1. Una volta mappato un segmento a questa destinazione, il nostro sistema di trasferimento dati in tempo reale, [IRIS](../../../reference/system-components/components-data-action.md#iris), invia una richiesta `POST` all’endpoint del token per scambiare le credenziali per un token portatore.
1. Per ogni richiesta di pubblicazione del segmento nell’endpoint partner, [!UICONTROL IRIS] utilizza il token portatore per l’autenticazione.

![](assets/oauth2-iris.png)

## Requisiti {#auth-requirements}

In qualità di partner [!DNL Audience Manager], per ricevere le richieste autenticate sono necessari i seguenti endpoint:

### Endpoint 1 utilizzato da IRIS per ottenere un token portatore

Questo endpoint accetta le credenziali fornite al passaggio 1 e genera un token portatore da utilizzare nelle richieste successive.

* L’endpoint deve accettare le richieste `HTTP POST` .
* L’endpoint deve accettare e guardare l’intestazione [!DNL Authorization] . Il valore di questa intestazione sarà: `Basic <credentials_provided_by_partner>`.
* L’endpoint deve esaminare l’intestazione [!DNL Content-type] e verificare che il relativo valore sia `application/x-www-form-urlencoded ; charset=UTF-8`.
* Il corpo della richiesta sarà `grant_type=client_credentials`.

### Esempio di richiesta effettuata dall’Audience Manager all’endpoint partner per ottenere un token portatore

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

### Risposta di esempio dall’endpoint partner

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Endpoint 2 utilizzato da IRIS per pubblicare segmenti utilizzando il token portatore

[!DNL Audience Manager] invia i dati a questo endpoint in tempo quasi reale, in quanto gli utenti si qualificano per i segmenti. Inoltre, questo metodo può inviare batch di dati offline o onboarded con la stessa frequenza di ogni 24 ore.

Il token portatore generato dall’endpoint 1 viene utilizzato per emettere richieste a questo endpoint. Il [!DNL Audience Manager] sistema di trasferimento dati in tempo reale, [IRIS](../../../reference/system-components/components-data-action.md#iris), costruisce una normale richiesta HTTPS e include un’intestazione di autorizzazione. Il valore di questa intestazione sarà: Portatore `<bearer token from step 1>`.

### Risposta di esempio dall’endpoint partner

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

Le credenziali presentate dal partner e i token ottenuti da [!DNL Audience Manager] durante l&#39;autenticazione tramite il flusso [!DNL OAuth 2.0] sono informazioni sensibili e non devono essere condivise con terze parti.

### [!DNL SSL] obbligatorio

[!DNL SSL] devono essere utilizzati per mantenere un processo di autenticazione sicuro. Tutte le richieste, comprese quelle utilizzate per ottenere e utilizzare i token, devono utilizzare gli endpoint `HTTPS` .
