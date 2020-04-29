---
description: Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, URL di richiesta e altri riferimenti.
seo-description: Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, URL di richiesta e altri riferimenti.
seo-title: Guida introduttiva alle API REST
solution: Audience Manager
title: Guida introduttiva alle API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: 1bbfa4b537a344d58f20763bb40ebe0827ad8698

---


# Guida introduttiva alle API REST {#getting-started-with-rest-apis}

Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, URL di richiesta e altri riferimenti.

<!-- c_rest_api_overview.xml -->

## Requisiti API e raccomandazioni {#api-requirements-recommendations}

Cose che devi e che devi fare quando lavori con Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

Tenete presente quanto segue quando lavorate con il codice API [di](https://bank.demdex.com/portal/swagger/index.html#/) Audience Manager:

* **Parametri di richiesta:** Tutti i parametri di richiesta sono obbligatori, se non diversamente specificato.
* **Intestazioni** richieste: quando utilizzate i token di I/O [di](https://www.adobe.io/) Adobe, dovete fornire l’ `x-api-key` intestazione. Puoi ottenere la chiave API seguendo le istruzioni riportate nella pagina Integrazione [account](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) servizio.
* **[!DNL JSON]tipo di contenuto:**Specificate`content-type: application/json`e *inserite*`accept: application/json`nel codice.

* **Richieste e risposte:** Invia le richieste come un [!DNL JSON] oggetto formattato correttamente. [!DNL Audience Manager] risponde con dati [!DNL JSON] formattati. Le risposte del server possono contenere i dati richiesti, un codice di stato o entrambi.

* **Accesso:** Il [!DNL Audience Manager] consulente vi fornirà un ID cliente e una chiave che vi consentirà di effettuare [!DNL API] richieste.

* **Documentazione ed esempi di codice:** Il testo in *corsivo* rappresenta una variabile fornita o passata durante la creazione o la ricezione di [!DNL API] dati. Sostituite il testo *in corsivo* con codice, parametri o altre informazioni personali.

## Autenticazione {#authentication}

Le API REST di Audience Manager supportano due metodi di autenticazione.

* [Autenticazione](#jwt)JWT (Service Account). Questo è il metodo di autenticazione consigliato.
* [Autenticazione OAuth (obsoleta)](#oauth). Anche se questo metodo è obsoleto, i clienti con integrazioni OAuth esistenti possono continuare a utilizzare questo metodo.

>[!IMPORTANT]
>
>A seconda del metodo di autenticazione, è necessario regolare gli URL della richiesta di conseguenza. Consulta la sezione [Ambienti](#environments) per informazioni dettagliate sui nomi host da utilizzare.

## Autenticazione JWT (account di servizio) {#jwt}

Per stabilire una sessione dell&#39;API Adobe I/O di servizio protetta, dovete creare un token Web JSON (JWT) che racchiuda l&#39;identità della vostra integrazione, quindi scambiarlo per un token di accesso. Ogni richiesta a un servizio Adobe deve includere il token di accesso nell’intestazione Autorizzazione, insieme alla chiave API (ID client) generata al momento della creazione dell’integrazione [dell’account di](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) servizio nella console [I/O di](https://console.adobe.io/)Adobe.

Per istruzioni dettagliate sulla configurazione dell&#39;autenticazione, consultate Autenticazione [](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) JWT (account di servizio).

## Autenticazione OAuth (obsoleta) {#oauth}

>[!WARNING]
> L&#39;autenticazione e il rinnovo dei [!UICONTROL REST API] token di Audience Manager tramite [!DNL OAuth 2.0] è ora obsoleto.
>
> Utilizzare invece l&#39;autenticazione [](#jwt-service-account-authentication-jwt) JWT (Service Account).

Audience Manager [!UICONTROL REST API] segue [!DNL OAuth 2.0] gli standard per l’autenticazione e il rinnovo dei token. Le sezioni seguenti descrivono come autenticarsi e iniziare a lavorare con gli [!DNL API]s.

### Creare un utente API generico {#requirements}

È consigliabile creare un account utente tecnico separato per l&#39;utilizzo con Audience Manager [!DNL API]s. Si tratta di un account generico che non è associato o associato a un utente specifico nell&#39;organizzazione. Questo tipo di account [!DNL API] utente consente di realizzare 2 operazioni:

* Identificare il servizio che sta chiamando [!DNL API] (ad es., chiamate dalle vostre app che utilizzano i nostri [!DNL API]o da altri strumenti che effettuano [!DNL API] richieste).
* Fornire l&#39;accesso ininterrotto agli [!DNL API]s. Un account legato a una persona specifica può essere eliminato quando esce dalla società. In questo modo non sarà possibile utilizzare il [!DNL API] codice disponibile. Un account generico che non è legato a un particolare dipendente consente di evitare questo problema.

Ad esempio, per questo tipo di account, supponiamo che tu voglia cambiare molti segmenti alla volta con gli Strumenti [di gestione](../../reference/bulk-management-tools/bulk-management-intro.md)di massa. Per fare questo, il vostro account utente ha bisogno di [!DNL API] accesso. Invece di aggiungere autorizzazioni a un utente specifico, create un account utente non specifico [!DNL API] con le credenziali, la chiave e il segreto appropriati per effettuare [!DNL API] le chiamate. Questa funzione è utile anche se sviluppate applicazioni personalizzate che utilizzano Audience Manager [!DNL API]s.

Consultate il vostro consulente Audience Manager per configurare un account utente generico [!DNL API]solo.

### Flusso di lavoro di autenticazione della password {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Accesso sicuro tramite autenticazione tramite password [!DNL REST API]. I passaggi riportati di seguito descrivono il flusso di lavoro per l&#39;autenticazione tramite password da parte di un [!DNL JSON] client nel browser.

>[!TIP]
>
>Cifra i token di accesso e di aggiornamento se li si archivia in un database.

#### Passaggio 1: Richiedi accesso API

Contatta il tuo Partner Solutions Manager. Forniranno un ID [!DNL API] cliente e un segreto. L’ID e il segreto vi autenticano nel [!DNL API]sito.

Nota: Se desiderate ricevere un token di aggiornamento, specificatelo quando richiedete [!DNL API] l&#39;accesso.

#### Passaggio 2: Richiedi il token

Passa una richiesta di token con il [!DNL JSON] client preferito. Al momento della creazione della richiesta:

* Utilizza un `POST` metodo per chiamare `https://api.demdex.com/oauth/token`.
* Converti l&#39;ID client e il segreto in una stringa con codifica base 64. Separate l’ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` vengono convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Trasmettere le [!DNL HTTP] intestazioni `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded` . Ad esempio, l’intestazione potrebbe essere simile al seguente: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Impostate il corpo della richiesta come segue:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Passaggio 3: Ricevere il token

La [!DNL JSON] risposta contiene il token di accesso. La risposta dovrebbe essere simile alla seguente:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La `expires_in` chiave rappresenta il numero di secondi fino alla scadenza del token di accesso. Come procedura ottimale, utilizzate brevi tempi di scadenza per limitare l&#39;esposizione se il token è mai esposto.

### Aggiorna token {#refresh-token}

Aggiorna token: [!DNL API] l&#39;accesso viene rinnovato dopo la scadenza del token originale. Se richiesto, la risposta [!DNL JSON] nel flusso di lavoro della password include un token di aggiornamento. Se non ricevete un token di aggiornamento, createne uno nuovo tramite il processo di autenticazione tramite password.

Potete inoltre utilizzare un token di aggiornamento per generare un nuovo token prima della scadenza del token di accesso esistente.

Se il token di accesso è scaduto, nella risposta riceverete una `401 Status Code` e la seguente intestazione:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Nei passaggi seguenti viene delineato il flusso di lavoro per l’utilizzo di un token di aggiornamento per creare un nuovo token di accesso da un [!DNL JSON] client nel browser.

#### Passaggio 1: Richiedi il nuovo token

Passa una richiesta di aggiornamento token con il [!DNL JSON] client preferito. Al momento della creazione della richiesta:

* Utilizza un `POST` metodo per chiamare `https://api.demdex.com/oauth/token`.
* Converti l&#39;ID client e il segreto in una stringa con codifica base 64. Separate l’ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` vengono convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Trasmettere le intestazioni `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Ad esempio, l’intestazione potrebbe essere simile al seguente: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* Nel corpo della richiesta, specificate il token di aggiornamento `grant_type:refresh_token` e trasmettetelo nella richiesta di accesso precedente. La richiesta deve essere simile alla seguente: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Passaggio 2: Ricevi il nuovo token

La [!DNL JSON] risposta contiene il nuovo token di accesso. La risposta dovrebbe essere simile alla seguente:

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

Audience Manager [!UICONTROL REST API] supporta il codice di autorizzazione e l&#39;autenticazione implicita. Per utilizzare questi metodi di accesso, gli utenti devono effettuare l&#39;accesso per `https://api.demdex.com/oauth/authorize` ottenere l&#39;accesso e aggiornare i token.

## Richieste di autenticazione API {#authenticated-api-requests}

Requisiti per i [!DNL API] metodi di chiamata dopo la ricezione di un token di autenticazione.

<!-- c_oauth_call_methods.xml -->

Per effettuare chiamate ai [!DNL API] metodi disponibili:

* Nell’ `HTTP` intestazione, impostate `Authorization: Bearer <token>`.
* Quando si utilizza l&#39;autenticazione [](#jwt)JWT (Service Account), è necessario fornire l&#39; `x-api-key` intestazione, che sarà la stessa dell&#39; `client_id`utente. Puoi ottenere informazioni `client_id` dalla pagina di integrazione [I/O di](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) Adobe.
* Chiama il [!DNL API] metodo richiesto.

## Parametri query API opzionali {#optional-api-query-parameters}

Impostare i parametri facoltativi disponibili per i metodi che restituiscono tutte le proprietà di un oggetto.

<!-- c_rest_api_optional.xml -->

È possibile utilizzare questi parametri facoltativi con [!DNL API] metodi che restituiscono *tutte* le proprietà di un oggetto. Impostate queste opzioni nella stringa di richiesta quando la query viene passata alla [!DNL API].

| Parametro | Descrizione |
|--- |--- |
| page | Restituisce i risultati per numero di pagina. La numerazione inizia da 0. |
| pageSize | Imposta il numero di risultati della risposta restituiti dalla richiesta (il valore predefinito è 10). |
| sortBy | Ordina e restituisce i risultati in base alla [!DNL JSON] proprietà specificata. |
| decrescente | Ordina e restituisce risultati in ordine decrescente. Ascendente è il valore predefinito. |
| search | Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che si desideri trovare risultati per tutti i modelli con la parola &quot;Test&quot; in uno qualsiasi dei campi di valore per l&#39;elemento. Esempio di richiesta:   `GET https://aam.adobe.io/v1/models/?search=Test`.  È possibile cercare qualsiasi valore restituito da un metodo &quot;get all&quot;. |
| folderId | Restituisce tutti gli ID per le caratteristiche all’interno della cartella specificata. Non disponibile per tutti i metodi. |
| permissions | Restituisce un elenco di segmenti in base all&#39;autorizzazione specificata.  READ è il valore predefinito. Le autorizzazioni includono:<ul><li>`READ` : Restituisce e visualizza informazioni su un segmento.</li><li>`WRITE` : Utilizzare `PUT` per aggiornare un segmento.</li><li>`CREATE` : Utilizzate `POST` per creare un segmento.</li><li>`DELETE` : Elimina un segmento. Richiede l&#39;accesso alle caratteristiche sottostanti, se presenti. Ad esempio, avrai bisogno di diritti per eliminare le caratteristiche che appartengono a un segmento se desideri rimuoverlo.</li></ul><br>Specificate più autorizzazioni con coppie chiave-valore separate. Ad esempio, per restituire un elenco di segmenti con `READ` e `WRITE` autorizzazioni, passate in `"permissions":"READ"`, `"permissions":"WRITE"` . |
| includePermissions | (Booleano) Impostate su true per restituire le autorizzazioni per il segmento. Il valore predefinito è false. |

### Una Nota Sulle Opzioni Pagina

Quando le informazioni sulla pagina non *sono* specificate, la richiesta restituisce [!DNL JSON] risultati semplici in un array. Se *sono* specificate le informazioni sulla pagina, l&#39;elenco restituito viene racchiuso in un [!DNL JSON] oggetto che contiene informazioni sul risultato totale e sulla pagina corrente. La richiesta di esempio con le opzioni di pagina potrebbe essere simile alla seguente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## URL dell&#39;API {#api-urls}

[!DNL URLs] per richieste, ambienti di staging e produzione e versioni.

<!-- r_rest_urls.xml -->

## Richiedi URL {#request-urls}

Nella tabella seguente sono elencati gli URL di richiesta utilizzati per trasmettere [!DNL API] le richieste, per metodo.

A seconda del metodo di autenticazione utilizzato, è necessario regolare gli URL di richiesta in base alle tabelle riportate di seguito.

### Richiedi URL per autenticazione JWT {#request-urls-jwt}

| [!DNL API] Metodi | Richiesta [!DNL URL] |
|--- |--- |
| Modellazione algoritmica | `https://aam.adobe.io/v1/models/` |
| Origine dati | `https://aam.adobe.io/v1/datasources/` |
| Segnali derivati | `https://aam.adobe.io/v1/signals/derived/` |
| Destinazioni  | `https://aam.adobe.io/v1/destinations/` |
| Domains (Domini) | `https://aam.adobe.io/v1/partner-sites/` |
| Cartelle | Caratteristiche:  `https://aam.adobe.io/v1/folders/traits /`<br>Segmenti:  `https://aam.adobe.io/v1/folders/segments /` |
| Schema | `https://aam.adobe.io/v1/schemas/` |
| Segmenti | `https://aam.adobe.io/v1/segments/` |
| Caratteristiche | `https://aam.adobe.io/v1/traits/` |
| Tipi di caratteristiche | `https://aam.adobe.io/v1/customer-trait-types` |
| Tassonomia | `https://aam.adobe.io/v1/taxonomies/0/` |

### Richiedi URL per autenticazione OAuth (obsoleto) {#request-urls-oauth}

| [!DNL API] Metodi | Richiesta [!DNL URL] |
|--- |--- |
| Modellazione algoritmica | `https://api.demdex.com/v1/models/` |
| Origine dati | `https://api.demdex.com/v1/datasources/` |
| Segnali derivati | `https://api.demdex.com/v1/signals/derived/` |
| Destinazioni  | `https://api.demdex.com/v1/destinations/` |
| Domains (Domini) | `https://api.demdex.com/v1/partner-sites/` |
| Cartelle | Caratteristiche:  `https://api.demdex.com/v1/folders/traits /`<br>Segmenti:  `https://api.demdex.com/v1/folders/segments /` |
| Schema | `https://api.demdex.com/v1/schemas/` |
| Segmenti | `https://api.demdex.com/v1/segments/` |
| Caratteristiche | `https://api.demdex.com/v1/traits/` |
| Tipi di caratteristiche | `https://api.demdex.com/v1/customer-trait-types` |
| Tassonomia | `https://api.demdex.com/v1/taxonomies/0/` |

## Ambienti {#environments}

Gli [!DNL Audience Manager] strumenti [!DNL API]consentono l&#39;accesso a diversi ambienti di lavoro. Questi ambienti consentono di sottoporre a test il codice su database separati senza influire sui dati live di produzione. Nella tabella seguente sono elencati gli [!DNL API] ambienti disponibili e i nomi host delle risorse corrispondenti.

A seconda del metodo di autenticazione utilizzato, è necessario regolare gli URL dell’ambiente in base alla tabella seguente.

| Ambiente | Nome host per l&#39;autenticazione JWT | Nome host per autenticazione OAuth |
|---|---|---|
| **Produzione** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |


>[!NOTE]
>
>L’ambiente beta di Audience Manager è una versione autonoma e su scala ridotta dell’ambiente di produzione. Tutti i dati da sottoporre a test devono essere immessi e raccolti in questo ambiente.

## Versioni {#versions}

Le nuove versioni [!DNL API]vengono rilasciate secondo una pianificazione regolare. Con una nuova versione viene incrementato il numero di [!DNL API] versione. Nell’URL della richiesta viene fatto riferimento al numero di versione, come `v<version number>` illustrato nell’esempio seguente:

`https://<host>/v1/...`

## Codici di risposta definiti {#response-codes-defined}

`HTTP` codici di stato e testo della risposta restituiti da Audience Manager [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| ID codice di risposta | Testo della risposta | Definizione |
|---|---|---|
| 200 | OK | La richiesta è stata elaborata correttamente. Se necessario, restituirà il contenuto o i dati previsti. |
| 201 | Creato | La risorsa è stata creata. Restituisce per `PUT` e `POST` le richieste. |
| 204 | Nessun contenuto | La risorsa è stata eliminata. Il corpo della risposta sarà vuoto. |
| 400 | Richiesta non valida | Il server non ha capito la richiesta. Solitamente a causa di sintassi non corretta. Controlla la richiesta e riprova. |
| 403 | Vietato | Non si dispone dell&#39;accesso alla risorsa. |
| 404 | Non trovato | Impossibile trovare la risorsa per il percorso specificato. |
| 409 | Conflitto | Impossibile completare la richiesta a causa di un conflitto con lo stato della risorsa. |
| 500 | Errore server | Il server ha rilevato un errore imprevisto che gli ha impedito di soddisfare la richiesta. |

>[!MORELIKETHIS]
>
>* [Autenticazione JWT (account di servizio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Autenticazione OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 semplificato](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

