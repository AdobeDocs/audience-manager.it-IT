---
description: Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, URL di richiesta e altri riferimenti.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Guida introduttiva alle API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Guida introduttiva [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, richiesta [!DNL URLs]e altri riferimenti.

<!-- c_rest_api_overview.xml -->

## Raccomandazioni e requisiti per l’utilizzo delle API {#api-requirements-recommendations}

Cose che devi e devi fare quando lavori con il [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Quando si lavora con , tieni presente quanto segue [API Audience Manager](https://bank.demdex.com/portal/swagger/index.html#/) codice:

* **Parametri di richiesta:** tutti i parametri di richiesta sono richiesti, salvo diversa indicazione.
* **Intestazioni di richiesta**: quando utilizzi [Adobe Developer](https://www.adobe.io/) token, devi fornire `x-api-key` intestazione. Potete ottenere il vostro [!DNL API] seguendo le istruzioni contenute in [Integrazione dell&#39;account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) pagina.
* **[!DNL JSON]tipo di contenuto:** Specifica `content-type: application/json`  *e*  `accept: application/json` nel codice.
* **Richieste e risposte:** Invia richieste come formattate correttamente [!DNL JSON] oggetto. [!DNL Audience Manager] risponde con [!DNL JSON] dati formattati. Le risposte del server possono contenere dati richiesti, un codice di stato o entrambi.
* **Accesso:** Le [!DNL Audience Manager] il consulente ti fornirà un ID cliente e una chiave che ti consentono di creare [!DNL API] richieste.
* **Documentazione ed esempi di codice:** Testo in *corsivo* rappresenta una variabile fornita o passata durante la creazione o la ricezione [!DNL API] dati. Sostituisci *corsivo* testo con codice, parametri o altre informazioni richieste.

## Autenticazione {#authentication}

La [!DNL Audience Manager] [!DNL REST APIs] supportano due metodi di autenticazione.

* [Autenticazione JWT (account di servizio)](#jwt) utilizzo [Adobe Developer](https://www.adobe.io/). [!DNL Adobe Developer] è l&#39;ecosistema e la comunità di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://www.adobe.io/apis.html). Questo è il modo consigliato per configurare e utilizzare [!DNL Adobe] [!DNL APIs].
* [Autenticazione OAuth (obsoleta)](#oauth). Anche se questo metodo è obsoleto, i clienti con [!DNL OAuth] le integrazioni possono continuare a utilizzare questo metodo.

>[!IMPORTANT]
>
>A seconda del metodo di autenticazione, è necessario regolare la richiesta [!DNL URLs] di conseguenza. Consulta la sezione [Ambienti](#environments) per informazioni dettagliate sui nomi host da utilizzare.

## [!DNL JWT] ([!DNL Service Account]) Autenticazione tramite Adobe Developer {#jwt}

### Panoramica di Adobe Developer {#adobeio}

[!DNL Adobe Developer] è l&#39;ecosistema e la comunità di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://www.adobe.io/apis.html).

Questo è il modo consigliato per configurare e utilizzare [!DNL Adobe] [!DNL APIs].

### Prerequisiti {#prerequisites}

Prima di configurare [!DNL JWT] autenticazione, assicurati di avere accesso al [Console Adobe Developer](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). Per le richieste di accesso, contatta l’amministratore dell’organizzazione.

### Autenticazione {#auth}

Segui i passaggi seguenti per configurare [!DNL JWT (Service Account)] autenticazione tramite [!DNL Adobe Developer]:

1. Accedi a [Console Adobe Developer](https://console.adobe.io/).
1. Segui i passaggi descritti in [Connessione account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Periodo [Passaggio 2: Aggiungere un’API al progetto utilizzando l’autenticazione dell’account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), scegli [!DNL Audience Manager] [!DNL API] opzione .
1. Prova la connessione facendo il tuo primo [!DNL API] in base alle istruzioni fornite da [Passaggio 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Per configurare e utilizzare [!DNL Audience Manager] [!DNL REST APIs] in modo automatizzato, puoi generare il [!DNL JWT] programmaticamente. Vedi [Autenticazione JWT (account di servizio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) per istruzioni dettagliate.

### Autorizzazioni RBAC dell&#39;account tecnico

Se il tuo account di Audience Manager utilizza [Controllo degli accessi basato sul ruolo](../../features/administration/administration-overview.md), devi creare un account utente tecnico di Audience Manager e aggiungerlo al gruppo RBAC di Audience Manager che effettuerà le chiamate API.

Segui i passaggi riportati di seguito per creare un account utente tecnico e aggiungerlo a un gruppo RBAC:

1. Crea un `GET` chiamare a `https://aam.adobe.io/v1/users/self`. La chiamata crea un account utente tecnico visibile nella [!UICONTROL Admin Console], nella [!UICONTROL Users] pagina.

   ![conto tecnico](assets/technical-account.png)

1. Accedi al tuo account Audience Manager e [aggiungi l’account utente tecnico](../../features/administration/administration-overview.md#create-group) al gruppo di utenti che effettua le chiamate API.

## [!DNL OAuth] Autenticazione (obsoleta) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] autenticazione e rinnovo dei token tramite [!DNL OAuth 2.0] è ora obsoleto.
>
> Utilizzare [Autenticazione JWT (account di servizio)](#jwt-service-account-authentication-jwt) invece.

La [!DNL Audience Manager] [!UICONTROL REST API] segue [!DNL OAuth 2.0] standard per l’autenticazione e il rinnovo dei token. Le sezioni seguenti descrivono come eseguire l&#39;autenticazione e iniziare a lavorare con [!DNL API]s.

### Creare un generico [!DNL API] Utente {#requirements}

È consigliabile creare un account utente tecnico separato per lavorare con [!DNL Audience Manager] [!DNL API]s. Si tratta di un account generico che non è associato o associato a un utente specifico della tua organizzazione. Questo tipo di [!DNL API] l’account utente consente di eseguire 2 operazioni:

* Identifica il servizio che chiama il [!DNL API] (ad esempio, chiamate dalle tue app che utilizzano il nostro [!DNL API]s o da altri strumenti [!DNL API] richieste).
* Fornire un accesso ininterrotto ai [!DNL API]s. Un account associato a una persona specifica può essere cancellato quando lascia la tua azienda. In questo modo non sarà più possibile utilizzare le [!DNL API] codice. Un account generico non legato a un particolare dipendente ti aiuta a evitare questo problema.

Ad esempio, per questo tipo di account, supponiamo che desideri cambiare un sacco di segmenti contemporaneamente con il [Strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-management-intro.md). Beh, per fare questo, il tuo account utente ha bisogno di [!DNL API] accesso. Invece di aggiungere autorizzazioni a un utente specifico, crea un [!DNL API] account utente con le credenziali, la chiave e il segreto appropriati da creare [!DNL API] chiamate. Questa funzione è utile anche se si sviluppano applicazioni personalizzate che utilizzano [!DNL Audience Manager] [!DNL API]s.

Lavora con il tuo [!DNL Audience Manager] consulente per la creazione di un generico, [!DNL API]- solo account utente.

### Flusso di lavoro di autenticazione della password {#password-authentication-workflow}

Accesso sicuro tramite autenticazione password [!DNL REST API]. I passaggi seguenti delineano il flusso di lavoro per l’autenticazione tramite password da un [!DNL JSON] nel browser.

>[!TIP]
>
>Cifra token di accesso e aggiornamento se li archivi in un database.

#### Passaggio 1: Richiesta [!DNL API] Accesso

Contatta il tuo Partner Solutions Manager. Ti forniranno un [!DNL API] ID client e segreto. L’ID e il segreto dell’autenticazione ti consentono di [!DNL API].

Nota: Se desideri ricevere un token di aggiornamento, specifica che quando richiedi [!DNL API] accesso.

#### Passaggio 2: Richiedere il token

Passa una richiesta di token con il tuo preferito [!DNL JSON] client. Quando crei la richiesta:

* Utilizza un `POST` metodo di chiamata `https://api.demdex.com/oauth/token`.
* Converti l&#39;ID client e il segreto in una stringa con codifica base-64. Separa l’ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` convertire in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa la [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded` . Ad esempio, l’intestazione potrebbe avere l’aspetto seguente: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Imposta il corpo della richiesta come segue:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Passaggio 3: Ricevere il token

La [!DNL JSON] La risposta contiene il token di accesso. La risposta dovrebbe essere simile alla seguente:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La `expires_in` key rappresenta il numero di secondi fino alla scadenza del token di accesso. Come best practice, utilizza brevi tempi di scadenza per limitare l’esposizione se il token è mai esposto.

### Aggiorna token {#refresh-token}

Rinnova token [!DNL API] accesso dopo la scadenza del token originale. Se richiesto, la risposta [!DNL JSON] nel flusso di lavoro password include un token di aggiornamento. Se non ricevi un token di aggiornamento, creane uno nuovo tramite il processo di autenticazione tramite password.

Puoi anche utilizzare un token di aggiornamento per generare un nuovo token prima della scadenza del token di accesso esistente.

Se il token di accesso è scaduto, riceverai un `401 Status Code` e la seguente intestazione nella risposta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

I passaggi seguenti delineano il flusso di lavoro per l’utilizzo di un token di aggiornamento per creare un nuovo token di accesso da un [!DNL JSON] nel browser.

#### Passaggio 1: Richiedere il nuovo token

Passa una richiesta di aggiornamento del token con il tuo preferito [!DNL JSON] client. Quando crei la richiesta:

* Utilizza un `POST` metodo di chiamata `https://api.demdex.com/oauth/token`.
* Converti l&#39;ID client e il segreto in una stringa con codifica base-64. Separa l’ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` convertire in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa le intestazioni HTTP `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Ad esempio, l’intestazione potrebbe avere l’aspetto seguente: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Nel corpo della richiesta, specifica il `grant_type:refresh_token` e passare il token di aggiornamento ricevuto nella richiesta di accesso precedente. La richiesta deve essere simile alla seguente: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Passaggio 2: Ricevere il nuovo token

La [!DNL JSON] La risposta contiene il nuovo token di accesso. La risposta dovrebbe essere simile alla seguente:

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

La [!DNL Audience Manager] [!UICONTROL REST API] supporta il codice di autorizzazione e l’autenticazione implicita. Per utilizzare questi metodi di accesso, gli utenti devono effettuare l&#39;accesso a `https://api.demdex.com/oauth/authorize` per ottenere token di accesso e aggiornamento.

## Rendi autenticato [!DNL API] Richieste {#authenticated-api-requests}

Requisiti per la chiamata [!DNL API] dopo aver ricevuto un token di autenticazione.

Per effettuare chiamate contro disponibili [!DNL API] metodi:

* In `HTTP` header, set `Authorization: Bearer <token>`.
* Quando utilizzi [Autenticazione JWT (account di servizio)](#jwt), devi fornire `x-api-key` intestazione, che sarà la stessa del tuo `client_id`. Potete ottenere il vostro `client_id` dal [Integrazione Adobe Developer](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) pagina.
* Richiama [!DNL API] metodo .

## Facoltativo [!DNL API] Parametri query {#optional-api-query-parameters}

Impostare i parametri facoltativi disponibili per i metodi che restituiscono tutte le proprietà di un oggetto.

Puoi utilizzare questi parametri facoltativi con [!DNL API] metodi che restituiscono *tutto* proprietà di un oggetto. Imposta queste opzioni nella stringa di richiesta quando trasmetti la query al [!DNL API].

| Parametro | Descrizione |
|--- |--- |
| `page` | Restituisce i risultati per numero di pagina. La numerazione inizia da 0. |
| `pageSize` | Imposta il numero di risultati di risposta restituiti dalla richiesta (10 è l’impostazione predefinita). |
| `sortBy` | Ordina e restituisce i risultati in base al valore specificato [!DNL JSON] proprietà. |
| `descending` | Ordina e restituisce i risultati in ordine decrescente. `ascending` è il valore predefinito. |
| `search` | Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che tu voglia trovare risultati per tutti i modelli con la parola &quot;Test&quot; in uno qualsiasi dei campi di valore per quell’elemento. La richiesta di esempio potrebbe essere simile alla seguente:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Puoi cercare qualsiasi valore restituito da un &quot;[!DNL get all]&quot;. |
| `folderId` | Restituisce tutti gli ID di [!UICONTROL traits] all’interno della cartella specificata. Non disponibile per tutti i metodi. |
| `permissions` | Restituisce un elenco di segmenti in base all’autorizzazione specificata. `READ` è il valore predefinito. Le autorizzazioni includono:<ul><li>`READ` : Restituisce e visualizza informazioni su un segmento.</li><li>`WRITE` : Utilizzo  `PUT`  per aggiornare un segmento.</li><li>`CREATE` : Utilizzo  `POST`  per creare un segmento.</li><li>`DELETE` : Elimina un segmento. Richiede l’accesso alle caratteristiche sottostanti, se presenti. Ad esempio, se desideri rimuoverlo, avrai bisogno dei diritti per eliminare le caratteristiche che appartengono a un segmento.</li></ul><br>Specifica più autorizzazioni con coppie chiave-valore separate. Ad esempio, per restituire un elenco di segmenti con  `READ`  e  `WRITE`  solo autorizzazioni, passare  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Imposta su `true` per restituire le autorizzazioni per il segmento. Il valore predefinito è `false`. |

### Nota sulle opzioni di pagina

Quando le informazioni sulla pagina *non* specificato, la richiesta restituisce normale [!DNL JSON] restituisce un array. Se le informazioni sulla pagina *è* specificato, l’elenco restituito viene racchiuso in un [!DNL JSON] oggetto che contiene informazioni sul risultato totale e sulla pagina corrente. La richiesta di esempio utilizzando le opzioni di pagina potrebbe avere un aspetto simile al seguente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] per richieste, ambienti di staging e produzione e versioni.

## Richiesta [!DNL URLs] {#request-urls}

Nella tabella seguente è riportato l’elenco della richiesta [!DNL URLs] usato per passare [!DNL API] richieste, per metodo.

A seconda del metodo di autenticazione utilizzato, è necessario regolare la richiesta [!DNL URLs] secondo le tabelle seguenti.

### Richiesta [!DNL URLs] per [!DNL JWT] Autenticazione {#request-urls-jwt}

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

### Richiesta [!DNL URLs] per [!DNL OAuth] Autenticazione (obsoleta) {#request-urls-oauth}

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

La [!DNL Audience Manager] [!DNL API]s consentono l&#39;accesso a diversi ambienti di lavoro. Questi ambienti consentono di testare il codice in base a database separati senza influire sui dati di produzione live. Nella tabella seguente sono elencati i [!DNL API] ambienti e nomi host delle risorse corrispondenti.

A seconda del metodo di autenticazione utilizzato, è necessario regolare l’ambiente [!DNL URLs] secondo la tabella seguente.

| Ambiente | Nome host per [!DNL JWT] autenticazione | Nome host per [!DNL OAuth] autenticazione |
|---|---|---|
| **Produzione** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>La [!DNL Audience Manager] l’ambiente beta è una versione autonoma e su scala ridotta dell’ambiente di produzione. Tutti i dati da testare devono essere immessi e raccolti in questo ambiente.

## Versioni {#versions}

Nuove versioni di questi [!DNL API]vengono rilasciati regolarmente. Una nuova versione incrementa il [!DNL API] numero di versione. Nella richiesta viene fatto riferimento al numero di versione [!DNL URL] come `v<version number>` come mostrato nell’esempio seguente:

`https://<host>/v1/...`

## Codici di risposta definiti {#response-codes-defined}

`HTTP` i codici di stato e il testo di risposta restituiti da [!DNL Audience Manager] [!UICONTROL REST API].

| ID codice di risposta | Testo di risposta | Definizione |
|---|---|---|
| `200` | `OK` | La richiesta è stata elaborata correttamente. Se necessario, restituirà il contenuto o i dati previsti. |
| `201` | `Created` | La risorsa è stata creata. Restituisce per `PUT` e `POST` richieste. |
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

