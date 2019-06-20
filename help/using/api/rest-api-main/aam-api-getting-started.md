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


# Guida introduttiva alle API REST {#getting-started-with-rest-apis}

Informazioni sui requisiti generali, l&#39;autenticazione, i parametri di query facoltativi, gli URL delle richieste e altri riferimenti.

<!-- c_rest_api_overview.xml -->

## Requisiti API e Recommendations {#api-requirements-recommendations}

Cosa dovete fare e che dovrebbero fare quando lavorate con Audience Manager [!DNL API].

<!-- aam-api-requirements.xml -->

Tenete presente quanto segue quando lavorate con [il codice API](https://bank.demdex.com/portal/swagger/index.html#/) di Audience Manager:

* **Parametri di richiesta:** Tutti i parametri di richiesta sono obbligatori, se non diversamente specificato.
* **[!DNL JSON]tipo di contenuto:** Specificate `content-type: application/json`*e* `accept: application/json` nel codice.

* **Richieste e risposte:** Invia richieste come oggetto formattato [!DNL JSON] correttamente. [!DNL Audience Manager] risponde con [!DNL JSON] dati formattati. Le risposte al server possono contenere dati richiesti, un codice di stato o entrambi.

* **Accesso:** [!DNL Audience Manager] Il vostro consulente fornirà un ID client e una chiave che vi consentirà di [!DNL API] effettuare richieste.

* **Documentazione ed esempi di codice:** Il testo *in corsivo* rappresenta una variabile che viene fornita o passata durante la creazione o la ricezione [!DNL API] di dati. Sostituire *il testo in corsivo* con codice, parametri o altre informazioni richieste.

## Recommendations: Creare un utente API generico {#requirements}

È consigliabile creare un account utente tecnico separato per lavorare con Audience Manager [!DNL API]. Si tratta di un account generico non collegato o associato a un utente specifico dell&#39;organizzazione. Questo tipo di [!DNL API] account utente consente di ottenere 2 elementi:

* Identificazione di quale servizio chiama ( [!DNL API] ad es., chiamate dalle app che utilizzano il nostro [!DNL API]s o da altri strumenti che eseguono [!DNL API] richieste).
* Accesso ininterrotto agli [!DNL API]s. Un account associato a una persona specifica può essere eliminato quando lascia la società. In questo modo potrete evitare di utilizzare il [!DNL API] codice disponibile. Un account generico non legato a un particolare dipendente aiuta a evitare questo problema.

Come esempio o utilizzo di questo tipo di account, diciamo che desideri modificare molti segmenti contemporaneamente con Strumenti di gestione [di massa](../../reference/bulk-management-tools/bulk-management-intro.md). A questo scopo, l&#39;account utente deve [!DNL API] avere accesso. Invece di aggiungere autorizzazioni a un utente specifico, create un account [!DNL API] utente non specifico che disponga delle credenziali, chiave e segreto appropriati per [!DNL API] effettuare chiamate. Questa funzione è utile anche se sviluppate applicazioni personalizzate che utilizzano Audience Manager [!DNL API].

Collabora con il tuo consulente Audience Manager per configurare un account [!DNL API]utente generico e unico.

## Autenticazione oauth {#oauth}

Audience Manager [!UICONTROL REST API] segue [!DNL OAuth 2.0] gli standard per l&#39;autenticazione token e il rinnovo. Le sezioni seguenti descrivono come eseguire l&#39;autenticazione e iniziare a lavorare con [!DNL API]le s.

## Flusso di lavoro autenticazione password {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. I passaggi seguenti delineano il flusso di lavoro per l&#39;autenticazione tramite password da un [!DNL JSON] client nel browser.

>[!TIP]
>
>Crittografa i token e aggiorna i token se li archiviate in un database.

### Passaggio 1: Richiedi accesso API

Contatta il responsabile Soluzioni Partner. Le forniranno un ID [!DNL API] client e un segreto. L&#39;ID e l&#39;autenticazione segreta si [!DNL API]autenticano.

Nota: Se desiderate ricevere un token di aggiornamento, specificatelo quando richiedete [!DNL API] l&#39;accesso.

### Passaggio 2: Richiedi token

Trasmettete una richiesta token con il [!DNL JSON] client preferito. Quando create la richiesta:

* Utilizzate un `POST` metodo da chiamare `https://api.demdex.com/oauth/token`.
* Convertite l&#39;ID client e il segreto in una stringa codificata base -64. Separa l&#39;ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa nelle [!DNL HTTP] intestazioni `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded` . Ad esempio, l&#39;intestazione potrebbe avere l&#39;aspetto seguente: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=`<br/>`Content-Type: application/x-www-form-urlencoded`
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

`expires_in` La chiave rappresenta il numero di secondi trascorsi dalla scadenza del token di accesso. Come procedura ottimale, utilizzate brevi tempi di scadenza per limitare l&#39;esposizione se il token viene esposto.

## Aggiorna token {#refresh-token}

L&#39;aggiornamento dei token viene rinnovato [!DNL API] al termine del token originale. Se richiesto, la risposta [!DNL JSON] nel flusso di lavoro password include un token aggiornato. Se non ricevete un token di aggiornamento, createne una nuova tramite il processo di autenticazione della password.

Potete anche utilizzare un token di aggiornamento per generare un nuovo token prima della scadenza del token di accesso esistente.

Se il token di accesso è scaduto, riceverete una `401 Status Code` risposta e la seguente intestazione nella risposta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

I passaggi seguenti delineano il flusso di lavoro per utilizzare un token di aggiornamento per creare un nuovo token di accesso da un [!DNL JSON] client nel browser.

### Passaggio 1: Richiedi nuovo token

Trasmettete una richiesta di token aggiornata con il [!DNL JSON] client preferito. Quando create la richiesta:

* Utilizzate un `POST` metodo da chiamare `https://api.demdex.com/oauth/token`.
* Convertite l&#39;ID client e il segreto in una stringa codificata base -64. Separa l&#39;ID e il segreto con due punti durante il processo di conversione. Ad esempio, le credenziali `testId : testSecret` convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa le intestazioni `Authorization:Basic <base-64 clientID:clientSecret>` HTTP e `Content-Type: application/x-www-form-urlencoded`. Ad esempio, l&#39;intestazione potrebbe avere l&#39;aspetto seguente: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* Nel corpo della richiesta, specificate il `grant_type:refresh_token` token di aggiornamento ricevuto nella richiesta di accesso precedente. La richiesta deve essere simile alla seguente: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

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

## Codice di autorizzazione e autenticazione implicita {#authentication-code-implicit}

Audience Manager [!UICONTROL REST API] supporta il codice di autorizzazione e l&#39;autenticazione implicita. Per utilizzare questi metodi di accesso, gli utenti devono accedere `https://api.demdex.com/oauth/authorize` per ottenere i token di accesso e aggiornamento.

>[!MORE_ LIKE_ THIS]
>
>* [Oauth 2.0](https://oauth.net/2/)
>* [Oauth 2 Semplificato](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Effettuare richieste API autenticate {#authenticated-api-requests}

Requisiti per la chiamata [!DNL API] dei metodi dopo aver ricevuto un token di autenticazione.

<!-- c_oauth_call_methods.xml -->

Per eseguire chiamate rispetto ai [!DNL API] metodi disponibili:

* Nell&#39; `HTTP` intestazione `Authorization: Bearer <token>`, impostate.
* Chiama il [!DNL API] metodo richiesto.

>[!MORE_ LIKE_ THIS]
>
>* [Autenticazione oauth](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Parametri query API opzionali {#optional-api-query-parameters}

Impostare i parametri facoltativi disponibili per i metodi che restituiscono tutte le proprietà di un oggetto.

<!-- c_rest_api_optional.xml -->

È possibile utilizzare questi parametri facoltativi con [!DNL API] metodi che restituiscono *tutte* le proprietà di un oggetto. Impostate queste opzioni nella stringa di richiesta quando trasferite la query all&#39; [!DNL API]oggetto.

| Parametro | Descrizione |
|--- |--- |
| page | Restituisce i risultati per numero di pagina. La numerazione inizia da 0. |
| Pagesize | Imposta il numero di risultati di risposta restituiti dalla richiesta (10 è predefinito). |
| Sortby | Ordina e restituisce i risultati in base alla [!DNL JSON] proprietà specificata. |
| decrescente | Ordina e restituisce i risultati in ordine decrescente. L&#39;incremento è predefinito. |
| search | Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che desideri trovare risultati per tutti i modelli con la parola &quot;Test&quot; in uno dei campi di valore per quell&#39;elemento. La richiesta di esempio potrebbe essere simile alla seguente: `GET https://api.demdex.com/v1/models/?search=Test`. È possibile cercare qualsiasi valore restituito da un metodo &quot;get all&quot;. |
| Folderid | Restituisce tutti gli ID per le caratteristiche all&#39;interno della cartella specificata. Non disponibile per tutti i metodi. |
| permissions | Restituisce un elenco di segmenti in base all&#39;autorizzazione specificata. READ is default. Le autorizzazioni includono:<ul><li>`READ` : Restituzione e visualizzazione di informazioni su un segmento.</li><li>`WRITE` : Utilizzate `PUT` per aggiornare un segmento.</li><li>`CREATE` : Utilizzate `POST` per creare un segmento.</li><li>`DELETE` : Elimina un segmento. Richiede l&#39;accesso alle caratteristiche sottostanti, se disponibili. Ad esempio, ti servirà i diritti per eliminare le caratteristiche che appartengono a un segmento, se desideri rimuoverla.</li></ul><br>Specificate più autorizzazioni con coppie chiave-valore separate. For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| Includepermissions | (Booleano) Impostate su true per restituire le autorizzazioni per il segmento. Il valore predefinito è false. |

### Nota sulle opzioni pagina

Quando non vengono *specificate informazioni* sulla pagina, la richiesta restituisce [!DNL JSON] risultati semplici in un array. Se vengono specificate informazioni *sulla pagina,* l&#39;elenco restituito viene racchiuso in un [!DNL JSON] oggetto contenente informazioni sul risultato totale e sulla pagina corrente. La richiesta di esempio utilizzando le opzioni della pagina potrebbe essere simile a quella riportata di seguito:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## URL dell&#39;API {#api-urls}

[!DNL URLs] per richieste, ambienti di pre-produzione e versioni e versioni.

<!-- r_rest_urls.xml -->

## URL di richiesta {#request-urls}

Nella tabella seguente sono elencati gli URL di richiesta utilizzati per trasmettere [!DNL API] le richieste, per metodo.

| [!DNL API] Metodi | Richiesta [!DNL URL] |
|--- |--- |
| Modellazione algoritmica | `https://api.demdex.com/v1/models/` |
| Origine dati | `https://api.demdex.com/v1/datasources/` |
| Segnali derivati | `https://api.demdex.com/v1/signals/derived/` |
| Destinazioni | `https://api.demdex.com/v1/destinations/` |
| Domains (Domini) | `https://api.demdex.com/v1/partner-sites/` |
| Cartelle | Caratteristiche: `https://api.demdex.com/v1/folders/traits /`<br>Segmenti: `https://api.demdex.com/v1/folders/segments /` |
| Schema | `https://api.demdex.com/v1/schemas/` |
| Segmenti | `https://api.demdex.com/v1/segments/` |
| Caratteristiche | `https://api.demdex.com/v1/traits/` |
| Tipi di caratteristiche | `https://api.demdex.com/v1/customer-trait-types` |
| Tassonomica | `https://api.demdex.com/v1/taxonomies/0/` |

## Ambienti {#environments}

Gli [!DNL Audience Manager][!DNL API]s forniscono l&#39;accesso a diversi ambienti di lavoro. Questi ambienti consentono di testare il codice da database separati, senza influire sui dati live e di produzione. Nella tabella seguente sono elencati gli [!DNL API] ambienti disponibili e i nomi host corrispondenti delle risorse.

| Ambiente | Nome host |
|---|---|
| **Produzione** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L&#39;ambiente beta di Audience Manager è una versione indipendente e standalone dell&#39;ambiente di produzione. Tutti i dati da sottoporre a test devono essere inseriti e raccolti in questo ambiente.

## Versioni {#versions}

Le nuove versioni [!DNL API]di questi s vengono rilasciate a scadenze regolari. Una nuova versione incrementa il numero [!DNL API] di versione. Nell&#39;URL della richiesta viene fatto riferimento al numero di versione come `v<version number>` illustrato nell&#39;esempio seguente:

`https://<host>/v1/...`

## Codici di risposta definiti {#response-codes-defined}

`HTTP` codici di stato e testo della risposta restituiti da Audience Manager [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| ID codice risposta | Testo di risposta | Definizione |
|---|---|---|
| 200 | OK | La richiesta è stata elaborata correttamente. Restituisce il contenuto o i dati previsti, se necessario. |
| 201 | Creato | La risorsa è stata creata. Restituisce per `PUT``POST` e richieste. |
| 204 | Nessun contenuto | La risorsa è stata eliminata. Il corpo della risposta sarà vuoto. |
| 400 | Richiesta non valida | Il server non ha capito la richiesta. Generalmente a causa di sintassi non formata. Controllate la richiesta e riprovate. |
| 403 | Proibito | Non potete accedere alla risorsa. |
| 404 | Non trovato | Impossibile trovare la risorsa per il percorso specificato. |
| 409 | Conflitto | La richiesta non è stata completata a causa di un conflitto con lo stato della risorsa. |
| 500 | Errore server | Il server ha riscontrato un errore imprevisto che impediva il soddisfacimento della richiesta. |