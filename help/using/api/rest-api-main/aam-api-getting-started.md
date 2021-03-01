---
description: Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, URL di richiesta e altri riferimenti.
seo-description: Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, URL di richiesta e altri riferimenti.
seo-title: Guida introduttiva alle API REST
solution: Audience Manager
title: Guida introduttiva alle API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: ab8745a8ba24154793201893a39a039b5a098833
workflow-type: tm+mt
source-wordcount: '1861'
ht-degree: 4%

---


# Guida introduttiva di [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, richiesta [!DNL URLs] e altri riferimenti.

<!-- c_rest_api_overview.xml -->

## Raccomandazioni e requisiti per l’utilizzo delle API {#api-requirements-recommendations}

Cose che è necessario e che è necessario fare quando si utilizzano gli [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Tenete presente quanto segue quando lavorate con il codice [ API Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/):

* **Parametri della richiesta:** tutti i parametri della richiesta sono obbligatori, se non diversamente specificato.
* **Intestazioni** richieste: quando utilizzate  [ I/](https://www.adobe.io/) Otokens Adobe, dovete fornire l’ `x-api-key` intestazione. È possibile ottenere la chiave [!DNL API] seguendo le istruzioni riportate nella pagina [Integrazione dell&#39;account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]tipo di contenuto:** specifica  `content-type: application/json`  **  `accept: application/json` e specifica il codice.
* **Richieste e risposte:** invia le richieste come  [!DNL JSON] oggetto formattato correttamente. [!DNL Audience Manager] risponde con dati  [!DNL JSON] formattati. Le risposte del server possono contenere i dati richiesti, un codice di stato o entrambi.
* **Accesso:** Il  [!DNL Audience Manager] consulente vi fornirà un ID cliente e una chiave che vi consentirà di effettuare  [!DNL API] richieste.
* **Documentazione ed esempi di codice:** il testo in  ** corsivo rappresenta una variabile che puoi fornire o trasmettere quando crei o ricevi  [!DNL API] dati. Sostituire il testo *in corsivo* con codice, parametri o altre informazioni necessarie.

## Autenticazione {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] supporta due metodi di autenticazione.

* [Autenticazione JWT (Service Account) ](#jwt) tramite  [ Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] è  Adobe  ecosistema e comunità di sviluppatori. Include gli [ strumenti per sviluppatori di Adobi I/O e le API](https://www.adobe.io/apis/experienceplatform.html) e [API per tutti i prodotti  Adobe](https://www.adobe.io/apis.html). Questo è il modo consigliato per configurare e utilizzare [!DNL Adobe] [!DNL APIs].
* [Autenticazione OAuth (obsoleta)](#oauth). Anche se questo metodo è obsoleto, i clienti con integrazioni [!DNL OAuth] esistenti possono continuare a utilizzare questo metodo.

>[!IMPORTANT]
>
>A seconda del metodo di autenticazione, è necessario regolare la richiesta [!DNL URLs] di conseguenza. Vedere la sezione [Ambienti](#environments) per informazioni dettagliate sui nomi host da utilizzare.

## [!DNL JWT] ([!DNL Service Account]Autenticazione tramite  Adobe I/O  {#jwt}

### Panoramica  Adobe I/O {#adobeio}

[!DNL Adobe I/O] è  Adobe  ecosistema e comunità di sviluppatori. Include gli [ strumenti per sviluppatori di Adobi I/O e le API](https://www.adobe.io/apis/experienceplatform.html) e [API per tutti i prodotti  Adobe](https://www.adobe.io/apis.html).

Questo è il modo consigliato per configurare e utilizzare [!DNL Adobe] [!DNL APIs].

### Prerequisiti {#prerequisites}

Prima di poter configurare l&#39;autenticazione [!DNL JWT], assicurarsi di avere accesso alla [ Developer Console](https://console.adobe.io/) del Adobe in [ Adobe I/O](https://www.adobe.io/). Contattate l’amministratore dell’organizzazione per le richieste di accesso.

### Autenticazione {#auth}

Seguite i passaggi indicati di seguito per configurare l&#39;autenticazione [!DNL JWT (Service Account)] utilizzando [!DNL Adobe I/O]:

1. Accedete alla [ Adobe Developer Console](https://console.adobe.io/).
1. Seguire i passaggi descritti in [Connessione account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante [Passaggio 2: Aggiungi un&#39;API al tuo progetto utilizzando l&#39;autenticazione dell&#39;account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), scegli l&#39;opzione [!DNL Audience Manager] [!DNL API].
1. Prova la connessione effettuando la tua prima [!DNL API] chiamata in base alle istruzioni fornite dal [Passaggio 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Per configurare e utilizzare il [!DNL Audience Manager] [!DNL REST APIs] in modo automatico, è possibile generare il [!DNL JWT] a livello di programmazione. Per istruzioni dettagliate, vedere [JWT (Service Account) Authentication](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md).

## [!DNL OAuth] Autenticazione (obsoleta)  {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] l&#39;autenticazione token e il rinnovo tramite  [!DNL OAuth 2.0] è ora obsoleto.
>
> Utilizzare invece l&#39;autenticazione [JWT (Service Account)](#jwt-service-account-authentication-jwt).

[!DNL Audience Manager] [!UICONTROL REST API] segue [!DNL OAuth 2.0] gli standard per l&#39;autenticazione e il rinnovo dei token. Le sezioni seguenti descrivono come autenticare e iniziare a lavorare con gli [!DNL API]s.

### Creare un utente [!DNL API] generico {#requirements}

È consigliabile creare un account utente tecnico separato per l&#39;utilizzo di [!DNL Audience Manager] [!DNL API]s. Si tratta di un account generico che non è associato o associato a un utente specifico nell&#39;organizzazione. Questo tipo di account utente [!DNL API] consente di eseguire 2 operazioni:

* Identificare quale servizio sta chiamando le [!DNL API] (ad esempio, chiamate dalle vostre app che utilizzano i nostri [!DNL API]s o da altri strumenti che effettuano richieste [!DNL API]).
* Fornire l&#39;accesso ininterrotto alle [!DNL API]s. Un account legato a una persona specifica può essere eliminato quando esce dalla società. In questo modo non sarà possibile utilizzare il codice [!DNL API] disponibile. Un account generico che non è legato a un particolare dipendente consente di evitare questo problema.

Ad esempio, per questo tipo di account, supponiamo che si desideri cambiare un sacco di segmenti contemporaneamente con gli [Strumenti di gestione di massa](../../reference/bulk-management-tools/bulk-management-intro.md). Beh, per fare questo, il tuo account utente ha bisogno di [!DNL API] accesso. Invece di aggiungere autorizzazioni a un utente specifico, create un account utente [!DNL API] non specifico con le credenziali, la chiave e il segreto appropriati per effettuare chiamate [!DNL API]. Questo è utile anche se si sviluppano applicazioni personalizzate che utilizzano i [!DNL Audience Manager] [!DNL API]s.

Consultate il vostro consulente [!DNL Audience Manager] per impostare un account utente generico, solo [!DNL API].

### Flusso di lavoro di autenticazione della password {#password-authentication-workflow}

Accesso protetto tramite autenticazione tramite password [!DNL REST API]. I passaggi riportati di seguito descrivono il flusso di lavoro per l&#39;autenticazione tramite password da un client [!DNL JSON] nel browser.

>[!TIP]
>
>Cifra i token di accesso e di aggiornamento se li si archivia in un database.

#### Passaggio 1: Richiedi accesso[!DNL API]

Contatta il tuo Partner Solutions Manager. Forniranno un ID client [!DNL API] e un segreto. L&#39;ID e il segreto vi autenticano nel percorso [!DNL API].

Nota: Se desiderate ricevere un token di aggiornamento, specificatelo quando richiedete l&#39;accesso a [!DNL API].

#### Passaggio 2: Richiedi il token

Passa una richiesta di token con il client [!DNL JSON] preferito. Al momento della creazione della richiesta:

* Utilizzare un metodo `POST` per chiamare `https://api.demdex.com/oauth/token`.
* Converti l&#39;ID client e il segreto in una stringa con codifica base 64. Separate l’ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` vengono convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passare in [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded` . Ad esempio, l’intestazione potrebbe essere simile al seguente: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Impostate il corpo della richiesta come segue:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Passaggio 3: Ricevere il token

La risposta [!DNL JSON] contiene il token di accesso. La risposta dovrebbe essere simile alla seguente:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La chiave `expires_in` rappresenta il numero di secondi fino alla scadenza del token di accesso. Come procedura ottimale, utilizzate brevi tempi di scadenza per limitare l&#39;esposizione se il token è mai esposto.

### Aggiorna token {#refresh-token}

I token di aggiornamento rinnovano l&#39;accesso [!DNL API] dopo la scadenza del token originale. Se richiesto, la risposta [!DNL JSON] nel flusso di lavoro della password include un token di aggiornamento. Se non ricevete un token di aggiornamento, createne uno nuovo tramite il processo di autenticazione tramite password.

Potete inoltre utilizzare un token di aggiornamento per generare un nuovo token prima della scadenza del token di accesso esistente.

Se il token di accesso è scaduto, nella risposta riceverete un `401 Status Code` e la seguente intestazione:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Nei passaggi seguenti viene delineato il flusso di lavoro per l&#39;utilizzo di un token di aggiornamento per creare un nuovo token di accesso da un client [!DNL JSON] nel browser.

#### Passaggio 1: Richiedi il nuovo token

Passa una richiesta di aggiornamento token con il client [!DNL JSON] preferito. Al momento della creazione della richiesta:

* Utilizzare un metodo `POST` per chiamare `https://api.demdex.com/oauth/token`.
* Converti l&#39;ID client e il segreto in una stringa con codifica base 64. Separate l’ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` vengono convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa le intestazioni HTTP `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Ad esempio, l’intestazione potrebbe essere simile al seguente: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Nel corpo della richiesta, specificate il `grant_type:refresh_token` e passate il token di aggiornamento ricevuto nella richiesta di accesso precedente. La richiesta deve essere simile alla seguente: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Passaggio 2: Ricevi il nuovo token

La risposta [!DNL JSON] contiene il nuovo token di accesso. La risposta dovrebbe essere simile alla seguente:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### Codice di autorizzazione e autenticazione implicita {#authentication-code-implicit}

Il [!DNL Audience Manager] [!UICONTROL REST API] supporta il codice di autorizzazione e l&#39;autenticazione implicita. Per utilizzare questi metodi di accesso, gli utenti devono accedere a `https://api.demdex.com/oauth/authorize` per ottenere l&#39;accesso e aggiornare i token.

## Richieste autenticate [!DNL API] {#authenticated-api-requests}

Requisiti per la chiamata dei metodi [!DNL API] dopo aver ricevuto un token di autenticazione.

Per effettuare chiamate ai metodi [!DNL API] disponibili:

* Nell&#39;intestazione `HTTP`, impostare `Authorization: Bearer <token>`.
* Quando si utilizza l&#39;autenticazione [JWT (Service Account)](#jwt), è necessario fornire l&#39;intestazione `x-api-key`, che sarà uguale al `client_id`. È possibile ottenere il `client_id` dalla pagina [ integrazione Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Chiama il metodo [!DNL API] richiesto.

## Parametri di query [!DNL API] facoltativi {#optional-api-query-parameters}

Impostare i parametri facoltativi disponibili per i metodi che restituiscono tutte le proprietà di un oggetto.

È possibile utilizzare questi parametri facoltativi con metodi [!DNL API] che restituiscono le proprietà *all* per un oggetto. Impostate queste opzioni nella stringa di richiesta quando passate la query in [!DNL API].

| Parametro | Descrizione |
|--- |--- |
| `page` | Restituisce i risultati per numero di pagina. La numerazione inizia da 0. |
| `pageSize` | Imposta il numero di risultati della risposta restituiti dalla richiesta (il valore predefinito è 10). |
| `sortBy` | Ordina e restituisce i risultati in base alla proprietà [!DNL JSON] specificata. |
| `descending` | Ordina e restituisce risultati in ordine decrescente. `ascending` è il valore predefinito. |
| `search` | Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che si desideri trovare risultati per tutti i modelli con la parola &quot;Test&quot; in uno qualsiasi dei campi di valore per l&#39;elemento. Esempio di richiesta:   `GET https://aam.adobe.io/v1/models/?search=Test`.  È possibile cercare qualsiasi valore restituito da un metodo &quot;[!DNL get all]&quot;. |
| `folderId` | Restituisce tutti gli ID di [!UICONTROL traits] all&#39;interno della cartella specificata. Non disponibile per tutti i metodi. |
| `permissions` | Restituisce un elenco di segmenti in base all&#39;autorizzazione specificata. `READ` è il valore predefinito. Le autorizzazioni includono:<ul><li>`READ` : Restituisce e visualizza informazioni su un segmento.</li><li>`WRITE` : Utilizzare   `PUT`  per aggiornare un segmento.</li><li>`CREATE` : Utilizzare   `POST`  per creare un segmento.</li><li>`DELETE` : Elimina un segmento. Richiede l&#39;accesso alle caratteristiche sottostanti, se presenti. Ad esempio, avrai bisogno di diritti per eliminare le caratteristiche che appartengono a un segmento se desideri rimuoverlo.</li></ul><br>Specificate più autorizzazioni con coppie chiave-valore separate. Ad esempio, per restituire un elenco di segmenti con autorizzazioni solo `READ` e `WRITE`, passare `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Impostare su `true` per restituire le autorizzazioni per il segmento. Il valore predefinito è `false`. |

### Una Nota Sulle Opzioni Pagina

Quando le informazioni di pagina *non sono specificate*, la richiesta restituisce un valore normale [!DNL JSON] restituisce un array. Se le informazioni di pagina *è* specificate, l&#39;elenco restituito viene racchiuso in un oggetto [!DNL JSON] che contiene informazioni sul risultato totale e sulla pagina corrente. La richiesta di esempio con le opzioni di pagina potrebbe essere simile alla seguente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] per richieste, ambienti di staging e produzione e versioni.

## Richiesta [!DNL URLs] {#request-urls}

Nella tabella seguente è riportato l&#39;elenco della richiesta [!DNL URLs] utilizzata per trasmettere le richieste [!DNL API] per metodo.

A seconda del metodo di autenticazione utilizzato, è necessario regolare la richiesta [!DNL URLs] in base alle tabelle riportate di seguito.

### Richiesta di [!DNL URLs] autenticazione [!DNL JWT] {#request-urls-jwt}

| [!DNL API] Metodi | Richiesta [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Caratteristiche:  `https://aam.adobe.io/v1/folders/traits /`<br>Segmenti:  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### Richiesta di [!DNL URLs] autenticazione [!DNL OAuth] (obsoleto) {#request-urls-oauth}

| [!DNL API] Metodi | Richiesta [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Caratteristiche:  `https://api.demdex.com/v1/folders/traits /`<br>Segmenti:  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## Ambienti {#environments}

I [!DNL Audience Manager] [!DNL API]s consentono l&#39;accesso a diversi ambienti di lavoro. Questi ambienti consentono di sottoporre a test il codice su database separati senza influire sui dati live di produzione. Nella tabella seguente sono elencati gli ambienti [!DNL API] disponibili e i nomi host delle risorse corrispondenti.

A seconda del metodo di autenticazione utilizzato, è necessario regolare l&#39;ambiente [!DNL URLs] in base alla tabella seguente.

| Ambiente | Nome host per l&#39;autenticazione [!DNL JWT] | Nome host per l&#39;autenticazione [!DNL OAuth] |
|---|---|---|
| **Produzione** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L&#39;ambiente [!DNL Audience Manager] beta è una versione autonoma e su scala ridotta dell&#39;ambiente di produzione. Tutti i dati da sottoporre a test devono essere immessi e raccolti in questo ambiente.

## Versioni {#versions}

Le nuove versioni di questi [!DNL API]s vengono rilasciate secondo una pianificazione regolare. Una nuova versione incrementa il numero di versione [!DNL API]. Il numero di versione è indicato nella richiesta [!DNL URL] come `v<version number>`, come illustrato nell&#39;esempio seguente:

`https://<host>/v1/...`

## Codici di risposta definiti {#response-codes-defined}

`HTTP` i codici di stato e il testo della risposta restituiti dal  [!DNL Audience Manager] [!UICONTROL REST API].

| ID codice di risposta | Testo della risposta | Definizione |
|---|---|---|
| `200` | `OK` | La richiesta è stata elaborata correttamente. Se necessario, restituirà il contenuto o i dati previsti. |
| `201` | `Created` | La risorsa è stata creata. Restituisce le richieste `PUT` e `POST`. |
| `204` | `No Content` | La risorsa è stata eliminata. Il corpo della risposta sarà vuoto. |
| `400` | `Bad Request` | Il server non ha capito la richiesta. Solitamente a causa di sintassi non corretta. Controlla la richiesta e riprova. |
| `403` | `Forbidden` | Non si dispone dell&#39;accesso alla risorsa. |
| `404` | `Not Found` | Impossibile trovare la risorsa per il percorso specificato. |
| `409` | `Conflict` | Impossibile completare la richiesta a causa di un conflitto con lo stato della risorsa. |
| `500` | `Server Error` | Il server ha rilevato un errore imprevisto che gli ha impedito di soddisfare la richiesta. |

>[!MORELIKETHIS]
>
>* [Autenticazione JWT (account di servizio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Autenticazione OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 semplificato](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

