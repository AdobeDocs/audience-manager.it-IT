---
description: Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, URL di richiesta e altri riferimenti.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Guida introduttiva alle API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 95182160b37bb15df4867bbacd06d8d75c971fa3
workflow-type: tm+mt
source-wordcount: '1942'
ht-degree: 3%

---

# Guida introduttiva a [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, richiesta [!DNL URLs] e altri riferimenti.

<!-- c_rest_api_overview.xml -->

## Raccomandazioni e requisiti per l’utilizzo delle API {#api-requirements-recommendations}

Operazioni da eseguire con [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Quando lavori con il codice [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/), tieni presente quanto segue:

* **Parametri di richiesta:** tutti i parametri di richiesta sono richiesti, se non diversamente specificato.
* **Intestazioni** di richiesta: quando utilizzi  [Adobe I/](https://www.adobe.io/) Otokens, devi fornire l’ `x-api-key` intestazione . Puoi ottenere la tua chiave [!DNL API] seguendo le istruzioni contenute nella pagina [Integrazione account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) .
* **[!DNL JSON]tipo di contenuto:** specifica  `content-type: application/json`  **  `accept: application/json` e nel codice.
* **Richieste e risposte:** invia richieste come  [!DNL JSON] oggetto formattato correttamente. [!DNL Audience Manager] risponde con dati  [!DNL JSON] formattati. Le risposte del server possono contenere dati richiesti, un codice di stato o entrambi.
* **Accesso:** il tuo  [!DNL Audience Manager] consulente ti fornirà un ID cliente e una chiave che ti permetterà di effettuare  [!DNL API] richieste.
* **Documentazione ed esempi di codice:** il testo in  ** corsivo rappresenta una variabile fornita o passata durante la creazione o la ricezione  [!DNL API] dei dati. Sostituisci il testo *in corsivo* con codice, parametri o altre informazioni richieste.

## Autenticazione {#authentication}

I [!DNL Audience Manager] [!DNL REST APIs] supportano due metodi di autenticazione.

* [Autenticazione JWT (account di servizio) ](#jwt) tramite  [Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] è l&#39;ecosistema e la comunità di sviluppatori di Adobe. Include gli [strumenti per sviluppatori Adobe I/O e le API](https://www.adobe.io/apis/experienceplatform.html) e [API per tutti i prodotti Adobe](https://www.adobe.io/apis.html). Questo è il modo consigliato per configurare e utilizzare [!DNL Adobe] [!DNL APIs].
* [Autenticazione OAuth (obsoleta)](#oauth). Anche se questo metodo è obsoleto, i clienti con integrazioni [!DNL OAuth] esistenti possono continuare a utilizzare questo metodo.

>[!IMPORTANT]
>
>A seconda del metodo di autenticazione, è necessario regolare di conseguenza la richiesta [!DNL URLs]. Per informazioni dettagliate sui nomi host da utilizzare, consulta la sezione [Ambienti](#environments) .

## [!DNL JWT] ([!DNL Service Account]) Autenticazione tramite Adobe I/O {#jwt}

### Panoramica dell’Adobe I/O {#adobeio}

[!DNL Adobe I/O] è l&#39;ecosistema e la comunità di sviluppatori di Adobe. Include gli [strumenti per sviluppatori Adobe I/O e le API](https://www.adobe.io/apis/experienceplatform.html) e [API per tutti i prodotti Adobe](https://www.adobe.io/apis.html).

Questo è il modo consigliato per configurare e utilizzare [!DNL Adobe] [!DNL APIs].

### Prerequisiti {#prerequisites}

Prima di configurare l&#39;autenticazione [!DNL JWT], assicurati di avere accesso a [Adobe Developer Console](https://console.adobe.io/) in [Adobe I/O](https://www.adobe.io/). Per le richieste di accesso, contatta l’amministratore dell’organizzazione.

### Autenticazione {#auth}

Segui i passaggi seguenti per configurare l’autenticazione [!DNL JWT (Service Account)] utilizzando [!DNL Adobe I/O]:

1. Accedi a [Adobe Developer Console](https://console.adobe.io/).
1. Segui i passaggi descritti in [Connessione account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante il [passaggio 2: Aggiungi un&#39;API al tuo progetto utilizzando l&#39;opzione Autenticazione account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), scegli l&#39;opzione [!DNL Audience Manager] [!DNL API].
1. Prova la connessione effettuando la tua prima [!DNL API] chiamata in base alle istruzioni del [passaggio 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Per configurare e lavorare con [!DNL Audience Manager] [!DNL REST APIs] in modo automatico, puoi generare il [!DNL JWT] a livello di programmazione. Per istruzioni dettagliate, consulta [JWT (Service Account) Authentication](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) .

### Autorizzazioni RBAC dell&#39;account tecnico

Se il tuo account di Audience Manager utilizza [Controllo accessi basato su ruolo](../../features/administration/administration-overview.md), devi creare un account utente tecnico Audience Manager e aggiungerlo al gruppo RBAC di Audience Manager che effettuerà le chiamate API.

Segui i passaggi riportati di seguito per creare un account utente tecnico e aggiungerlo a un gruppo RBAC:

1. Effettua una chiamata `GET` a `https://aam.adobe.io/v1/users/self`. La chiamata crea un account utente tecnico visibile nella pagina [!UICONTROL Admin Console].[!UICONTROL Users]

   ![conto tecnico](assets/technical-account.png)

1. Accedi al tuo account di Audience Manager e [aggiungi l&#39;account utente tecnico](../../features/administration/administration-overview.md#create-group) al gruppo di utenti che effettuerà le chiamate API.

## [!DNL OAuth] Autenticazione (obsoleta) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] l’autenticazione e il rinnovo dei token tramite  [!DNL OAuth 2.0] è ora obsoleto.
>
> Utilizza invece [JWT (Service Account) Authentication](#jwt-service-account-authentication-jwt).

Il [!DNL Audience Manager] [!UICONTROL REST API] segue gli standard [!DNL OAuth 2.0] per l’autenticazione e il rinnovo dei token. Le sezioni seguenti descrivono come eseguire l&#39;autenticazione e iniziare a lavorare con gli [!DNL API]s.

### Creare un utente generico [!DNL API] {#requirements}

È consigliabile creare un account utente tecnico separato per l’utilizzo di [!DNL Audience Manager] [!DNL API]s. Si tratta di un account generico che non è associato o associato a un utente specifico della tua organizzazione. Questo tipo di account utente [!DNL API] consente di eseguire 2 operazioni:

* Identifica quale servizio sta chiamando il [!DNL API] (ad esempio, le chiamate dalle tue app che utilizzano i nostri [!DNL API]s o da altri strumenti che effettuano richieste [!DNL API]).
* Fornire l&#39;accesso ininterrotto ai [!DNL API]s. Un account associato a una persona specifica può essere cancellato quando lascia la tua azienda. Questo ti impedirà di lavorare con il codice [!DNL API] disponibile. Un account generico che non è legato a un particolare dipendente ti aiuta a evitare questo problema.

Come esempio o caso d&#39;uso per questo tipo di account, supponiamo che desideri cambiare un sacco di segmenti contemporaneamente con gli [Strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-management-intro.md). Beh, per fare questo, il tuo account utente ha bisogno di [!DNL API] accesso. Invece di aggiungere autorizzazioni a un utente specifico, crea un account utente [!DNL API] non specifico che disponga delle credenziali, della chiave e del segreto appropriati per effettuare chiamate [!DNL API]. Questa funzione è utile anche se si sviluppano applicazioni personalizzate che utilizzano [!DNL Audience Manager] [!DNL API]s.

Rivolgiti al tuo consulente [!DNL Audience Manager] per configurare un account utente generico [!DNL API] solo.

### Flusso di lavoro di autenticazione della password {#password-authentication-workflow}

Accesso protetto tramite autenticazione tramite password [!DNL REST API]. I passaggi seguenti delineano il flusso di lavoro per l’autenticazione tramite password da un client [!DNL JSON] nel browser.

>[!TIP]
>
>Cifra token di accesso e aggiornamento se li archivi in un database.

#### Passaggio 1: Richiedi accesso [!DNL API]

Contatta il tuo Partner Solutions Manager. Ti forniranno un [!DNL API] ID client e un segreto. L&#39;ID e il segreto ti autenticano nel [!DNL API].

Nota: Se desideri ricevere un token di aggiornamento, specifica che quando richiedi l’accesso a [!DNL API] .

#### Passaggio 2: Richiedere il token

Passa una richiesta di token con il client [!DNL JSON] preferito. Quando crei la richiesta:

* Utilizza un metodo `POST` per chiamare `https://api.demdex.com/oauth/token`.
* Converti l&#39;ID client e il segreto in una stringa con codifica base-64. Separa l’ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` vengono convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa i valori [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded` . Ad esempio, l’intestazione potrebbe avere l’aspetto seguente: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Imposta il corpo della richiesta come segue:
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

La chiave `expires_in` rappresenta il numero di secondi fino alla scadenza del token di accesso. Come best practice, utilizza brevi tempi di scadenza per limitare l’esposizione se il token è mai esposto.

### Aggiorna token {#refresh-token}

I token di aggiornamento rinnovano l’accesso [!DNL API] dopo la scadenza del token originale. Se richiesto, la risposta [!DNL JSON] nel flusso di lavoro della password include un token di aggiornamento. Se non ricevi un token di aggiornamento, creane uno nuovo tramite il processo di autenticazione tramite password.

Puoi anche utilizzare un token di aggiornamento per generare un nuovo token prima della scadenza del token di accesso esistente.

Se il token di accesso è scaduto, riceverai un `401 Status Code` e la seguente intestazione nella risposta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

I passaggi seguenti delineano il flusso di lavoro per l’utilizzo di un token di aggiornamento per creare un nuovo token di accesso da un client [!DNL JSON] nel browser.

#### Passaggio 1: Richiedere il nuovo token

Passa una richiesta di aggiornamento del token con il client [!DNL JSON] preferito. Quando crei la richiesta:

* Utilizza un metodo `POST` per chiamare `https://api.demdex.com/oauth/token`.
* Converti l&#39;ID client e il segreto in una stringa con codifica base-64. Separa l’ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` vengono convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa le intestazioni HTTP `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Ad esempio, l’intestazione potrebbe avere l’aspetto seguente: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Nel corpo della richiesta, specifica `grant_type:refresh_token` e passa il token di aggiornamento ricevuto nella richiesta di accesso precedente. La richiesta deve essere simile alla seguente: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Passaggio 2: Ricevere il nuovo token

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

Il [!DNL Audience Manager] [!UICONTROL REST API] supporta il codice di autorizzazione e l&#39;autenticazione implicita. Per utilizzare questi metodi di accesso, gli utenti devono accedere a `https://api.demdex.com/oauth/authorize` per ottenere i token di accesso e aggiornamento.

## Effettuare richieste [!DNL API] autenticate {#authenticated-api-requests}

Requisiti per la chiamata dei metodi [!DNL API] dopo aver ricevuto un token di autenticazione.

Per effettuare chiamate ai metodi [!DNL API] disponibili:

* Nell’intestazione `HTTP`, imposta `Authorization: Bearer <token>`.
* Quando utilizzi [JWT (Service Account) Authentication](#jwt), devi fornire l&#39;intestazione `x-api-key` , che sarà la stessa del tuo `client_id`. Puoi ottenere il tuo `client_id` dalla pagina [Integrazione Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) .
* Chiama il metodo [!DNL API] richiesto.

## Parametri di query [!DNL API] facoltativi {#optional-api-query-parameters}

Impostare i parametri facoltativi disponibili per i metodi che restituiscono tutte le proprietà di un oggetto.

È possibile utilizzare questi parametri facoltativi con metodi [!DNL API] che restituiscono le proprietà *all* per un oggetto. Imposta queste opzioni nella stringa di richiesta quando trasmetti la query in a [!DNL API].

| Parametro | Descrizione |
|--- |--- |
| `page` | Restituisce i risultati per numero di pagina. La numerazione inizia da 0. |
| `pageSize` | Imposta il numero di risultati di risposta restituiti dalla richiesta (10 è l’impostazione predefinita). |
| `sortBy` | Ordina e restituisce i risultati in base alla proprietà [!DNL JSON] specificata. |
| `descending` | Ordina e restituisce i risultati in ordine decrescente. `ascending` è il valore predefinito. |
| `search` | Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che tu voglia trovare risultati per tutti i modelli con la parola &quot;Test&quot; in uno qualsiasi dei campi di valore per quell’elemento. La richiesta di esempio potrebbe essere simile alla seguente:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Puoi cercare qualsiasi valore restituito da un metodo &quot;[!DNL get all]&quot;. |
| `folderId` | Restituisce tutti gli ID di [!UICONTROL traits] all&#39;interno della cartella specificata. Non disponibile per tutti i metodi. |
| `permissions` | Restituisce un elenco di segmenti in base all’autorizzazione specificata. `READ` è il valore predefinito. Le autorizzazioni includono:<ul><li>`READ` : Restituisce e visualizza informazioni su un segmento.</li><li>`WRITE` : Utilizza   `PUT`  per aggiornare un segmento.</li><li>`CREATE` : Utilizza   `POST`  per creare un segmento.</li><li>`DELETE` : Elimina un segmento. Richiede l’accesso alle caratteristiche sottostanti, se presenti. Ad esempio, se desideri rimuoverlo, avrai bisogno dei diritti per eliminare le caratteristiche che appartengono a un segmento.</li></ul><br>Specifica più autorizzazioni con coppie chiave-valore separate. Ad esempio, per restituire un elenco di segmenti solo con autorizzazioni `READ` e `WRITE` , passa `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Imposta su `true` per restituire le autorizzazioni per il segmento. Il valore predefinito è `false`. |

### Nota sulle opzioni di pagina

Quando le informazioni di pagina *non sono specificate*, la richiesta restituisce normale [!DNL JSON] restituisce un array. Se le informazioni di pagina *sono* specificate, l’elenco restituito viene racchiuso in un oggetto [!DNL JSON] che contiene informazioni sul risultato totale e sulla pagina corrente. La richiesta di esempio utilizzando le opzioni di pagina potrebbe avere un aspetto simile al seguente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] per richieste, ambienti di staging e produzione e versioni.

## Richiesta [!DNL URLs] {#request-urls}

Nella tabella seguente è riportato l’elenco della richiesta [!DNL URLs] utilizzata per trasmettere le richieste [!DNL API] tramite metodo .

A seconda del metodo di autenticazione utilizzato, è necessario regolare la richiesta [!DNL URLs] in base alle tabelle seguenti.

### Richiesta [!DNL URLs] di autenticazione [!DNL JWT] {#request-urls-jwt}

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

### Richiesta [!DNL URLs] di autenticazione [!DNL OAuth] (obsoleta) {#request-urls-oauth}

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

I [!DNL Audience Manager] [!DNL API]s consentono l&#39;accesso a diversi ambienti di lavoro. Questi ambienti consentono di testare il codice in base a database separati senza influire sui dati di produzione live. Nella tabella seguente sono elencati gli ambienti [!DNL API] disponibili e i nomi host delle risorse corrispondenti.

A seconda del metodo di autenticazione utilizzato, è necessario regolare l’ambiente [!DNL URLs] in base alla tabella seguente.

| Ambiente | Nome host per l’autenticazione [!DNL JWT] | Nome host per l’autenticazione [!DNL OAuth] |
|---|---|---|
| **Produzione** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L’ [!DNL Audience Manager] ambiente beta è una versione autonoma e su scala ridotta dell’ambiente di produzione. Tutti i dati da testare devono essere immessi e raccolti in questo ambiente.

## Versioni {#versions}

Le nuove versioni di questi [!DNL API]s vengono rilasciate regolarmente. Una nuova versione incrementa il numero di versione [!DNL API]. Il numero di versione è indicato nella richiesta [!DNL URL] come `v<version number>` come mostrato nell&#39;esempio seguente:

`https://<host>/v1/...`

## Codici di risposta definiti {#response-codes-defined}

`HTTP` codici di stato e testo di risposta restituiti da  [!DNL Audience Manager] [!UICONTROL REST API].

| ID codice di risposta | Testo di risposta | Definizione |
|---|---|---|
| `200` | `OK` | La richiesta è stata elaborata correttamente. Se necessario, restituirà il contenuto o i dati previsti. |
| `201` | `Created` | La risorsa è stata creata. Restituisce le richieste `PUT` e `POST` . |
| `204` | `No Content` | La risorsa è stata eliminata. Il corpo della risposta sarà vuoto. |
| `400` | `Bad Request` | Il server non ha capito la richiesta. Di solito a causa di sintassi non corretta. Controlla la richiesta e riprova. |
| `403` | `Forbidden` | Non hai accesso alla risorsa. |
| `404` | `Not Found` | Impossibile trovare la risorsa per il percorso specificato. |
| `409` | `Conflict` | Impossibile completare la richiesta a causa di un conflitto con lo stato della risorsa. |
| `500` | `Server Error` | Errore imprevisto del server che ne impediva l&#39;esecuzione della richiesta. |

>[!MORELIKETHIS]
>
>* [Autenticazione JWT (account di servizio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Autenticazione OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 semplificato](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

