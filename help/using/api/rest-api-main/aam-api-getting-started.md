---
description: Informazioni sui requisiti generali, l'autenticazione, i parametri di query facoltativi, gli URL delle richieste e altri riferimenti.
seo-description: Informazioni sui requisiti generali, l'autenticazione, i parametri di query facoltativi, gli URL delle richieste e altri riferimenti.
seo-title: Guida introduttiva alle API REST
solution: Audience Manager
title: Guida introduttiva alle API REST
uuid: af 0 e 527 e -6 eec -449 c -9709-f 90 e 57 cd 188 d
translation-type: tm+mt
source-git-commit: 27800ce003a62733eece0d5de3b94737ed61133a

---


# Getting Started with REST APIs {#getting-started-with-rest-apis}

Informazioni sui requisiti generali, l'autenticazione, i parametri di query facoltativi, gli URL delle richieste e altri riferimenti.

<!-- c_rest_api_overview.xml -->

## API Requirements and Recommendations {#api-requirements-recommendations}

Things you must and should do when working with the Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

Note the following when working with [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **Parametri di richiesta:** Tutti i parametri di richiesta sono obbligatori, se non diversamente specificato.
* **[!DNL JSON]tipo di contenuto:** Specificate `content-type: application/json`*e* `accept: application/json` nel codice.

* **Richieste e risposte:** Invia richieste come oggetto formattato [!DNL JSON] correttamente. [!DNL Audience Manager] risponde con [!DNL JSON] dati formattati. Le risposte al server possono contenere dati richiesti, un codice di stato o entrambi.

* **Accesso:** [!DNL Audience Manager] Il vostro consulente fornirà un ID client e una chiave che vi consentirà di [!DNL API] effettuare richieste.

* **Documentazione ed esempi di codice:** Il testo *in corsivo* rappresenta una variabile che viene fornita o passata durante la creazione o la ricezione [!DNL API] di dati. Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#requirements}

We recommend you create a separate, technical user account for working with the Audience Manager [!DNL API]s. This is a generic account that is not tied to or associated with a specific user in your organization. This type of [!DNL API] user account helps you accomplish 2 things:

* Identify what service is calling the [!DNL API] (e.g., calls from your apps that use our [!DNL API]s or from other tools that make [!DNL API] requests).
* Provide uninterrupted access to the [!DNL API]s. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available [!DNL API] code. Un account generico non legato a un particolare dipendente aiuta a evitare questo problema.

As an example or use case for this type of account, let's say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-intro.md). Well, to do this, your user account needs [!DNL API] access. Rather than add permissions to a specific user, create a non-specific, [!DNL API] user account that has the appropriate credentials, key, and secret to make [!DNL API] calls. This is also useful if you develop your own applications that use the Audience Manager [!DNL API]s.

Work with your Audience Manager consultant to set up a generic, [!DNL API]-only user account.

## OAuth Authentication {#oauth}

The Audience Manager [!UICONTROL REST API] follows [!DNL OAuth 2.0] standards for token authentication and renewal. The sections below describe how to authenticate and start working with the [!DNL API]s.

## Password Authentication Workflow {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. The steps below outline the workflow for password authentication from a [!DNL JSON] client in your browser.

>[!TIP]
>
>Crittografa i token e aggiorna i token se li archiviate in un database.

### Passaggio 1: Richiedi accesso API

Contatta il responsabile Soluzioni Partner. They will provide you with an [!DNL API] client ID and secret. The ID and secret authenticate you to the [!DNL API].

Note: If you'd like to receive a refresh token, specify that when you request [!DNL API] access.

### Passaggio 2: Richiedi token

Pass in a token request with your preferred [!DNL JSON] client. Quando create la richiesta:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Convertite l'ID client e il segreto in una stringa codificata base -64. Separa l'ID e il segreto con due punti durante il processo di conversione. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the [!DNL HTTP] headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded` . For example, your header could look like this: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Configurate il corpo della richiesta come segue:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Passaggio 3: Ricevi il token

[!DNL JSON] La risposta contiene il token di accesso. La risposta deve essere simile alla seguente:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

`expires_in` La chiave rappresenta il numero di secondi trascorsi dalla scadenza del token di accesso. Come procedura ottimale, utilizzate brevi tempi di scadenza per limitare l'esposizione se il token viene esposto.

## Refresh Token {#refresh-token}

Refresh tokens renew [!DNL API] access after the original token expires. If requested, the response [!DNL JSON] in the password workflow includes a refresh token. Se non ricevete un token di aggiornamento, createne una nuova tramite il processo di autenticazione della password.

Potete anche utilizzare un token di aggiornamento per generare un nuovo token prima della scadenza del token di accesso esistente.

If your access token has expired, you receive a `401 Status Code` and the following header in the response:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

The following steps outline the workflow for using a refresh token to create a new access token from a [!DNL JSON] client in your browser.

### Passaggio 1: Richiedi nuovo token

Pass in a refresh token request with your preferred [!DNL JSON] client. Quando create la richiesta:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Convertite l'ID client e il segreto in una stringa codificata base -64. Separa l'ID e il segreto con due punti durante il processo di conversione. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the HTTP headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded`. For example, your header could look like this: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In the request body, specify the `grant_type:refresh_token` and pass in the refresh token you received in your previous access request. The request should look like this: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Passaggio 2: Ricevi il nuovo token

[!DNL JSON] La risposta contiene il nuovo token di accesso. La risposta deve essere simile alla seguente:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Authorization Code and Implicit Authentication {#authentication-code-implicit}

The Audience Manager [!UICONTROL REST API] supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens.

>[!MORE_ LIKE_ THIS]
>
>* [Oauth 2.0](https://oauth.net/2/)
>* [Oauth 2 Semplificato](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Make Authenticated API Requests {#authenticated-api-requests}

Requirements for calling [!DNL API] methods after you receive an authentication token.

<!-- c_oauth_call_methods.xml -->

To make calls against the available [!DNL API] methods:

* In the `HTTP` header, set `Authorization: Bearer <token>`.
* Call the required [!DNL API] method.

>[!MORE_ LIKE_ THIS]
>
>* [Autenticazione oauth](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optional API Query Parameters {#optional-api-query-parameters}

Impostare i parametri facoltativi disponibili per i metodi che restituiscono tutte le proprietà di un oggetto.

<!-- c_rest_api_optional.xml -->

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API].

| Parametro | Descrizione |
|--- |--- |
| page | Restituisce i risultati per numero di pagina. La numerazione inizia da 0. |
| Pagesize | Imposta il numero di risultati di risposta restituiti dalla richiesta (10 è predefinito). |
| Sortby | Sorts and returns results according to the specified [!DNL JSON] property. |
| decrescente | Ordina e restituisce i risultati in ordine decrescente. L'incremento è predefinito. |
| search | Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che desideri trovare risultati per tutti i modelli con la parola "Test" in uno dei campi di valore per quell'elemento. Your sample request could look like this:   `GET https://api.demdex.com/v1/models/?search=Test`.  È possibile cercare qualsiasi valore restituito da un metodo "get all". |
| Folderid | Restituisce tutti gli ID per le caratteristiche all'interno della cartella specificata. Non disponibile per tutti i metodi. |
| permissions | Restituisce un elenco di segmenti in base all'autorizzazione specificata. READ is default. Le autorizzazioni includono:<ul><li>`READ` : Restituzione e visualizzazione di informazioni su un segmento.</li><li>`WRITE` : Utilizzate `PUT` per aggiornare un segmento.</li><li>`CREATE` : Utilizzate `POST` per creare un segmento.</li><li>`DELETE` : Elimina un segmento. Richiede l'accesso alle caratteristiche sottostanti, se disponibili. Ad esempio, ti servirà i diritti per eliminare le caratteristiche che appartengono a un segmento, se desideri rimuoverla.</li></ul><br>Specificate più autorizzazioni con coppie chiave-valore separate. For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| Includepermissions | (Booleano) Impostate su true per restituire le autorizzazioni per il segmento. Il valore predefinito è false. |

### Nota sulle opzioni pagina

When page information *is not* specified, the request returns plain [!DNL JSON] results in an array. If page information *is* specified, then the returned list is wrapped in a [!DNL JSON] object that contains information about the total result and current page. La richiesta di esempio utilizzando le opzioni della pagina potrebbe essere simile a quella riportata di seguito:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## URL dell'API {#api-urls}

[!DNL URLs] per richieste, ambienti di pre-produzione e versioni e versioni.

<!-- r_rest_urls.xml -->

## Request URLs {#request-urls}

The following table lists the request URLs used to pass in [!DNL API] requests, by method.

| [!DNL API] Metodi | Richiesta [!DNL URL] |
|--- |--- |
| Modellazione algoritmica | `https://api.demdex.com/v1/models/` |
| Origine dati | `https://api.demdex.com/v1/datasources/` |
| Segnali derivati | `https://api.demdex.com/v1/signals/derived/` |
| Destinazioni | `https://api.demdex.com/v1/destinations/` |
| Domains (Domini) | `https://api.demdex.com/v1/partner-sites/` |
| Cartelle | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segments:  `https://api.demdex.com/v1/folders/segments /` |
| Schema | `https://api.demdex.com/v1/schemas/` |
| Segmenti | `https://api.demdex.com/v1/segments/` |
| Caratteristiche | `https://api.demdex.com/v1/traits/` |
| Tipi di caratteristiche | `https://api.demdex.com/v1/customer-trait-types` |
| Tassonomica | `https://api.demdex.com/v1/taxonomies/0/` |

## Environments {#environments}

The [!DNL Audience Manager] [!DNL API]s provide access to different working environments. Questi ambienti consentono di testare il codice da database separati, senza influire sui dati live e di produzione. The following table lists the available [!DNL API] environments and corresponding resource hostnames.

| Ambiente | Nome host |
|---|---|
| **Produzione** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L'ambiente beta di Audience Manager è una versione indipendente e standalone dell'ambiente di produzione. Tutti i dati da sottoporre a test devono essere inseriti e raccolti in questo ambiente.

## Versioni {#versions}

New versions of these [!DNL API]s are released on a regular schedule. A new release increments the [!DNL API] version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example:

`https://<host>/v1/...`

## Response Codes Defined {#response-codes-defined}

`HTTP` codici di stato e testo della risposta restituiti da Audience Manager [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| ID codice risposta | Testo di risposta | Definizione |
|---|---|---|
| 200 | OK | La richiesta è stata elaborata correttamente. Restituisce il contenuto o i dati previsti, se necessario. |
| 201 | Creato | La risorsa è stata creata. Returns for `PUT` and `POST` requests. |
| 204 | Nessun contenuto | La risorsa è stata eliminata. Il corpo della risposta sarà vuoto. |
| 400 | Richiesta non valida | Il server non ha capito la richiesta. Generalmente a causa di sintassi non formata. Controllate la richiesta e riprovate. |
| 403 | Proibito | Non potete accedere alla risorsa. |
| 404 | Non trovato | Impossibile trovare la risorsa per il percorso specificato. |
| 409 | Conflitto | La richiesta non è stata completata a causa di un conflitto con lo stato della risorsa. |
| 500 | Errore server | Il server ha riscontrato un errore imprevisto che impediva il soddisfacimento della richiesta. |