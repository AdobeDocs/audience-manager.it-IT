---
description: Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, URL di richiesta e altri riferimenti.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Guida introduttiva alle API REST
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2558'
ht-degree: 1%

---

# Guida introduttiva a [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, richiesta [!DNL URLs]e altri riferimenti.

## Requisiti API e Recommendations {#api-requirements-recommendations}

Quando si lavora con [API AUDIENCI MANAGER](https://bank.demdex.com/portal/swagger/index.html#/) codice:

* **Parametri di richiesta:** tutti i parametri di richiesta sono obbligatori se non diversamente specificato.
* **Intestazioni di richiesta**: quando si utilizza [Adobe Developer](https://www.adobe.io/) token, devi fornire `x-api-key` intestazione. Puoi ottenere il tuo [!DNL API] seguendo le istruzioni della sezione [Integrazione dell’account del servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) pagina.
* **[!DNL JSON]tipo di contenuto:** Specifica `content-type: application/json`  *e*  `accept: application/json` nel codice.
* **Richieste e risposte:** Inviare richieste come formattate correttamente [!DNL JSON] oggetto. [!DNL Audience Manager] risponde con [!DNL JSON] dati formattati. Le risposte del server possono contenere i dati richiesti, un codice di stato o entrambi.
* **Accesso:** Il tuo [!DNL Audience Manager] il consulente ti fornirà un ID cliente e una chiave che ti consentano di [!DNL API] richieste.
* **Documentazione ed esempi di codice:** Testo in *corsivo* rappresenta una variabile fornita o trasmessa quando si crea o si riceve [!DNL API] dati. Sostituisci *corsivo* testo con codice, parametri o altre informazioni obbligatorie.

## Autenticazione {#authentication}

Il [!DNL Audience Manager] [!DNL REST APIs] supporta tre metodi di autenticazione.

* [!BADGE Consigliato]{type=positive}[Autenticazione server-to-server OAuth](#oauth-adobe-developer) utilizzo [console per sviluppatori Adobe](https://www.adobe.io/). [!DNL Adobe Developer] è l’ecosistema e la comunità di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://developer.adobe.com/apis/). Si tratta del metodo consigliato per impostare e utilizzare [!DNL Adobe] [!DNL APIs]. Ulteriori informazioni su [Autenticazione server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) nella documentazione per gli sviluppatori Adobe.
* [!BADGE Obsoleto]{type=negative}[Autenticazione JWT (account di servizio)](#jwt) utilizzo [console per sviluppatori Adobe](https://www.adobe.io/). [!DNL Adobe Developer] è l’ecosistema e la comunità di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://developer.adobe.com/apis/).
* [!BADGE Obsoleto]{type=negative}[Autenticazione OAuth legacy](#oauth-deprecated). Anche se questo metodo è obsoleto, i clienti con [!DNL OAuth] le integrazioni possono continuare a utilizzare questo metodo.

>[!IMPORTANT]
>
>A seconda del metodo di autenticazione utilizzato, è necessario modificare la richiesta [!DNL URLs] di conseguenza. Consulta la [Ambienti](#environments) per i dettagli sui nomi host da utilizzare.

## Autenticazione server-to-server OAuth tramite Adobe Developer {#oauth-adobe-developer}

Questa sezione illustra come raccogliere le credenziali necessarie per autenticare le chiamate API Audienci Manager, come descritto nel diagramma di flusso seguente. È possibile raccogliere la maggior parte delle credenziali richieste nella configurazione iniziale una tantum. Il token di accesso, tuttavia, deve essere aggiornato ogni 24 ore.

![Audience Manager di diagramma del flusso di autenticazione.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Panoramica di Adobe Developer {#developer-overview}

[!DNL Adobe Developer] è l’ecosistema e la comunità di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://developer.adobe.com/apis).

Si tratta del metodo consigliato per impostare e utilizzare [!DNL Adobe] [!DNL APIs].

### Prerequisiti {#prerequisites-server-to-server}

Prima di configurare [!DNL OAuth Server-to-Server] autenticazione, assicurati di avere accesso al [Console Adobe Developer](https://developer.adobe.com/console/home) in [Adobe Developer](https://developer.adobe.com/). Contatta l’amministratore dell’organizzazione per le richieste di accesso.

### Autenticazione {#oauth}

Segui i passaggi seguenti per configurare [!DNL OAuth Server-to-Server] autenticazione tramite [!DNL Adobe Developer]:

1. Accedi a [Console Adobe Developer](https://developer.adobe.com/console/home).
1. Segui i passaggi descritti in [Guida all&#39;implementazione delle credenziali server-to-server di OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Durante [Passaggio 2: aggiungi un’API al progetto utilizzando l’autenticazione dell’account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), scegli il [!DNL Audience Manager] [!DNL API] opzione.
1. Prova la connessione effettuando la prima [!DNL API] effettua una chiamata in base alle istruzioni [Passaggio 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Per configurare e utilizzare [!DNL Audience Manager] [!DNL REST APIs] in modo automatico, puoi ruotare i segreti client a livello di programmazione. Consulta [la documentazione per gli sviluppatori](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) per istruzioni dettagliate.

### Aggiungere l’API Audienci Manager a un progetto {#add-aam-api-to-project}

Vai a [Console Adobe Developer](https://www.adobe.com/go/devs_console_ui) e accedi con il tuo Adobe ID. Quindi, segui i passaggi descritti nel tutorial su [creazione di un progetto vuoto](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) nella documentazione della console Adobe Developer.

Dopo aver creato un nuovo progetto, seleziona **[!UICONTROL Add API]** il **[!UICONTROL Project Overview]** schermo.

>[!TIP]
>
>Se disponi del provisioning per più organizzazioni, utilizza il selettore organizzazione nell’angolo superiore destro dell’interfaccia per assicurarti di essere nell’organizzazione necessaria.

![Nella schermata Console sviluppatori è evidenziata l’opzione Aggiungi API.](/help/using/api/rest-api-main/assets/add-api.png)

Il **[!UICONTROL Add an API]** viene visualizzata la schermata. Seleziona l’icona del prodotto per Adobe Experience Cloud, quindi scegli **[!UICONTROL Audience Manager API]** prima di selezionare **[!UICONTROL Next]**.

![Seleziona Audienci Manager API.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Seleziona la **[!UICONTROL View docs]** per passare in una finestra del browser separata al [Documentazione di riferimento dell’API Audienci Manager](https://bank.demdex.com/portal/swagger/index.html#).

### Seleziona il tipo di autenticazione server-to-server OAuth {#select-oauth-server-to-server}

Quindi, seleziona il tipo di autenticazione per generare token di accesso e accedere all’API Audienci Manager.

>[!IMPORTANT]
>
>Seleziona la **[!UICONTROL OAuth Server-to-Server]** poiché questo sarà l’unico metodo supportato per andare avanti. Il **[!UICONTROL Service Account (JWT)]** è obsoleto. Anche se le integrazioni che utilizzano il metodo di autenticazione JWT continueranno a funzionare fino al 1° gennaio 2025, Adobe consiglia vivamente di migrare le integrazioni esistenti al nuovo metodo server-to-server OAuth prima di tale data.

![Seleziona il metodo di autenticazione OAuth.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Selezionare i profili di prodotto per l’integrazione {#select-product-profiles}

In **[!UICONTROL Configure API]** , seleziona i profili di prodotto desiderati. L’account di servizio della tua integrazione potrà accedere a funzioni granulari tramite i profili di prodotto selezionati qui.

![Seleziona i profili di prodotto per la tua integrazione.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Seleziona **[!UICONTROL Save configured API]** quando sei pronto.

### Raccogli le credenziali {#gather-credentials}

Una volta aggiunta l’API al progetto, la **[!UICONTROL Audience Manager API]** Nella pagina del progetto vengono visualizzate le seguenti credenziali necessarie in tutte le chiamate alle API Audienci Manager:

![Informazioni sull’integrazione dopo l’aggiunta di un’API in Console sviluppatori.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Generare un token di accesso {#generate-access-token}

Il passaggio successivo consiste nel generare un `{ACCESS_TOKEN}` credenziali da utilizzare nelle chiamate API Audienci Manager. A differenza dei valori per `{API_KEY}` e `{ORG_ID}`, per continuare a utilizzare le API Audienci Manager, è necessario generare un nuovo token ogni 24 ore. Seleziona **[!UICONTROL Generate access token]**, come illustrato di seguito.

![Mostra come generare il token di accesso](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Testare una chiamata API {#test-api-call}

Dopo aver ottenuto il token Bearer di autenticazione, esegui una chiamata API per verificare che ora puoi accedere alle API Audienci Manager.

1. Accedi a [Documentazione di riferimento API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Seleziona **[!UICONTROL Authorize]** e incolla il token di accesso ottenuto in [genera token di accesso](#generate-access-token) passaggio.

   ![Autorizzare le chiamate API](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Effettuare una chiamata di GET al `/datasources` Endpoint API per recuperare un elenco di tutte le origini dati disponibili a livello globale, come indicato nella [Documentazione di riferimento API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Seleziona **[!UICONTROL Try it out]**, seguito da **[!UICONTROL Execute]**, come illustrato di seguito.

   ![Eseguire chiamate API](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB richiesta API]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB Risposta API in caso di utilizzo del token Bearer corretto]


Quando utilizzi un token di accesso funzionante, l’endpoint API restituisce una risposta 200 insieme a un corpo di risposta che include tutte le origini dati globali a cui l’organizzazione ha accesso.

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE Obsoleto]{type=negative}[!DNL JWT] ([!DNL Service Account]a) Autenticazione tramite Adobe Developer {#jwt}

+++ Visualizza informazioni su obsoleto [!DNL JWT] ([!DNL Service Account]) per ottenere i token di autenticazione.

### Panoramica di Adobe Developer {#adobeio}

[!DNL Adobe Developer] è l’ecosistema e la comunità di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://www.adobe.io/apis.html).

Si tratta del metodo consigliato per impostare e utilizzare [!DNL Adobe] [!DNL APIs].

### Prerequisiti {#prerequisites}

Prima di configurare [!DNL JWT] autenticazione, assicurati di avere accesso al [Console Adobe Developer](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). Contatta l’amministratore dell’organizzazione per le richieste di accesso.

### Autenticazione {#auth}

Segui i passaggi seguenti per configurare [!DNL JWT (Service Account)] autenticazione tramite [!DNL Adobe Developer]:

1. Accedi a [Console Adobe Developer](https://console.adobe.io/).
1. Segui i passaggi descritti in [Connessione account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante [Passaggio 2: aggiungi un’API al progetto utilizzando l’autenticazione dell’account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), scegli il [!DNL Audience Manager] [!DNL API] opzione.
1. Prova la connessione effettuando la prima [!DNL API] effettua una chiamata in base alle istruzioni [Passaggio 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Per configurare e utilizzare [!DNL Audience Manager] [!DNL REST APIs] in modo automatico, puoi generare il [!DNL JWT] a livello di programmazione. Consulta [Autenticazione JWT (account di servizio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) per istruzioni dettagliate.

### Autorizzazioni RBAC dell’account tecnico

Se il tuo account di Audience Manager utilizza [Controllo degli accessi basato sul ruolo](../../features/administration/administration-overview.md), devi creare un account utente tecnico Audienci Manager e aggiungerlo al gruppo RBAC Audienci Manager che effettuerà le chiamate API.

Per creare un account utente tecnico e aggiungerlo a un gruppo RBAC, effettua le seguenti operazioni:

1. Crea un `GET` chiama a `https://aam.adobe.io/v1/users/self`. La chiamata creerà un account utente tecnico che potrai visualizzare nella [!UICONTROL Admin Console], nella [!UICONTROL Users] pagina.

   ![account tecnico](assets/technical-account.png)

1. Accedi al tuo account Audienci Manager e [aggiungere l’account utente tecnico](../../features/administration/administration-overview.md#create-group) al gruppo di utenti che effettuerà le chiamate API.

+++

## [!BADGE Obsoleto]{type=negative}[!DNL OAuth] Autenticazione (obsoleto) {#oauth-deprecated}

+++ Visualizza informazioni sulla versione precedente obsoleta [!DNL OAuth] Metodo di autenticazione per ottenere i token di autenticazione.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] autenticazione e rinnovo dei token tramite [!DNL OAuth 2.0] è ora obsoleto.
>
> Utilizza [Autenticazione JWT (account di servizio)](#jwt-service-account-authentication-jwt) invece.

Il [!DNL Audience Manager] [!UICONTROL REST API] segue [!DNL OAuth 2.0] standard per l’autenticazione e il rinnovo dei token. Le sezioni seguenti descrivono come eseguire l’autenticazione e iniziare a utilizzare [!DNL API]s.

### Crea un generico [!DNL API] Utente {#requirements}

È consigliabile creare un account utente tecnico separato per l&#39;utilizzo di [!DNL Audience Manager] [!DNL API]s. Si tratta di un account generico non associato o associato a un utente specifico dell&#39;organizzazione. Questo tipo di [!DNL API] l’account utente ti consente di eseguire 2 operazioni:

* Identifica il servizio che chiama [!DNL API] (ad esempio, chiamate dalle app che utilizzano il nostro [!DNL API]s o da altri strumenti che [!DNL API] richieste).
* Fornire accesso ininterrotto al [!DNL API]s. Un account associato a una persona specifica può essere cancellato quando lascia la tua azienda. Questo ti impedirà di lavorare con i [!DNL API] codice. Un account generico non legato a un dipendente specifico consente di evitare questo problema.

Come esempio o caso d’uso per questo tipo di account, supponiamo che tu voglia modificare molti segmenti contemporaneamente con [Strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-management-intro.md). Bene, per fare questo, il tuo account utente ha bisogno di [!DNL API] accesso. Invece di aggiungere le autorizzazioni a un utente specifico, crea un’ [!DNL API] account utente con credenziali, chiave e segreto appropriati [!DNL API] chiamate. Questa funzione è utile anche per sviluppare applicazioni personalizzate che utilizzano [!DNL Audience Manager] [!DNL API]s.

Utilizzare [!DNL Audience Manager] consulente per la creazione di un generico, [!DNL API]account utente di sola lettura.

### Flusso di lavoro di autenticazione password {#password-authentication-workflow}

Autenticazione tramite password accesso sicuro [!DNL REST API]. I passaggi seguenti descrivono il flusso di lavoro per l’autenticazione tramite password da un [!DNL JSON] nel browser.

>[!TIP]
>
>Crittografare i token di accesso e di aggiornamento se vengono memorizzati in un database.

#### Passaggio 1: richiesta [!DNL API] Accesso

Contatta il tuo Partner Solutions Manager. Ti forniranno un [!DNL API] ID client e segreto. L’ID e il segreto ti autenticano nel [!DNL API].

Nota: se desideri ricevere un token di aggiornamento, specificalo quando richiedi [!DNL API] accesso.

#### Passaggio 2: richiedere il token

Passa una richiesta di token con il tuo preferito [!DNL JSON] client. Quando crei la richiesta:

* Utilizza un `POST` metodo di chiamata `https://api.demdex.com/oauth/token`.
* Converti l’ID client e il segreto in una stringa con codifica base 64. Durante il processo di conversione, separa l’ID e il segreto con due punti. Ad esempio, le credenziali `testId : testSecret` convertire in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa il [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded` . Ad esempio, l’intestazione potrebbe essere simile alla seguente: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Imposta il corpo della richiesta come segue:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Passaggio 3: ricevere il token

Il [!DNL JSON] la risposta contiene il token di accesso. La risposta deve essere simile alla seguente:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

Il `expires_in` key rappresenta il numero di secondi rimanenti alla scadenza del token di accesso. Come best practice, utilizza tempi di scadenza brevi per limitare l’esposizione se il token viene mai esposto.

### Aggiorna token {#refresh-token}

Aggiorna token di rinnovo [!DNL API] dopo la scadenza del token originale. Se richiesto, la risposta [!DNL JSON] nel flusso di lavoro della password è incluso un token di aggiornamento. Se non ricevi un token di aggiornamento, creane uno nuovo tramite il processo di autenticazione tramite password.

Puoi anche utilizzare un token di aggiornamento per generare un nuovo token prima della scadenza del token di accesso esistente.

Se il token di accesso è scaduto, viene visualizzato un messaggio `401 Status Code` e la seguente intestazione nella risposta:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

I passaggi seguenti descrivono il flusso di lavoro per l’utilizzo di un token di aggiornamento per creare un nuovo token di accesso da un [!DNL JSON] nel browser.

#### Passaggio 1: richiesta del nuovo token

Trasmettere una richiesta di token di aggiornamento con il token preferito [!DNL JSON] client. Quando crei la richiesta:

* Utilizza un `POST` metodo di chiamata `https://api.demdex.com/oauth/token`.
* Converti l’ID client e il segreto in una stringa con codifica base 64. Durante il processo di conversione, separa l’ID e il segreto con due punti. Ad esempio, le credenziali `testId : testSecret` convertire in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa le intestazioni HTTP `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Ad esempio, l’intestazione potrebbe essere simile alla seguente: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Nel corpo della richiesta, specifica `grant_type:refresh_token` e passa il token di aggiornamento ricevuto nella richiesta di accesso precedente. La richiesta deve essere simile alla seguente: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Passaggio 2: ricevere il nuovo token

Il [!DNL JSON] la risposta contiene il nuovo token di accesso. La risposta deve essere simile alla seguente:

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

Il [!DNL Audience Manager] [!UICONTROL REST API] supporta il codice di autorizzazione e l’autenticazione implicita. Per utilizzare questi metodi di accesso, gli utenti devono accedere a `https://api.demdex.com/oauth/authorize` per accedere e aggiornare i token.

+++

## Rendi autenticato [!DNL API] Richieste {#authenticated-api-requests}

Requisiti per il servizio di chiamata [!DNL API] metodi dopo aver ricevuto un token di autenticazione.

Per effettuare chiamate rispetto alla disponibilità [!DNL API] metodi:

* In `HTTP` intestazione, set `Authorization: Bearer <token>`.
* Quando si utilizza [Autenticazione JWT (account di servizio)](#jwt), devi fornire `x-api-key` , che sarà lo stesso dell&#39;intestazione `client_id`. Puoi ottenere il tuo `client_id` dal [Integrazione con Adobe Developer](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) pagina.
* Chiama il necessario [!DNL API] metodo.

## Facoltativo [!DNL API] Parametri di query {#optional-api-query-parameters}

Impostare i parametri facoltativi disponibili per i metodi che restituiscono tutte le proprietà di un oggetto.

Questi parametri facoltativi possono essere utilizzati con [!DNL API] metodi che restituiscono *tutto* proprietà di un oggetto. Imposta queste opzioni nella stringa di richiesta quando trasmetti la query al [!DNL API].

| Parametro | Descrizione |
|--- |--- |
| `page` | Restituisce i risultati per numero di pagina. La numerazione inizia da 0. |
| `pageSize` | Imposta il numero di risultati di risposta restituiti dalla richiesta (10 è il valore predefinito). |
| `sortBy` | Ordina e restituisce i risultati in base al [!DNL JSON] proprietà. |
| `descending` | Ordina e restituisce i risultati in ordine decrescente. `ascending` è l&#39;impostazione predefinita. |
| `search` | Restituisce risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che si desideri trovare i risultati per tutti i modelli che hanno la parola &quot;Test&quot; in uno qualsiasi dei campi di valore per quell&#39;elemento. La richiesta di esempio potrebbe essere simile alla seguente:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Puoi eseguire ricerche in base a qualsiasi valore restituito da un &quot;[!DNL get all]metodo &quot;. |
| `folderId` | Restituisce tutti gli ID per [!UICONTROL traits] nella cartella specificata. Non disponibile per tutti i metodi. |
| `permissions` | Restituisce un elenco di segmenti in base all’autorizzazione specificata. `READ` è l&#39;impostazione predefinita. Le autorizzazioni includono:<ul><li>`READ` : restituisce e visualizza informazioni su un segmento.</li><li>`WRITE` : Utilizzare  `PUT`  per aggiornare un segmento.</li><li>`CREATE` : Utilizzare  `POST`  per creare un segmento.</li><li>`DELETE` : elimina un segmento. Richiede l’accesso alle caratteristiche sottostanti, se presenti. Ad esempio, per rimuoverlo, dovrai disporre dei diritti necessari per eliminare le caratteristiche che appartengono a un segmento.</li></ul><br>Specifica più autorizzazioni con coppie chiave-valore separate. Ad esempio, per restituire un elenco di segmenti con  `READ`  e  `WRITE`  solo autorizzazioni, passare  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Impostate su `true` per restituire le autorizzazioni per il segmento. Il valore predefinito è `false`. |

{style="table-layout:auto"}

### Nota Sulle Opzioni Di Pagina

Quando le informazioni della pagina *non è* specificata, la richiesta restituisce solo [!DNL JSON] restituisce un array. Se le informazioni della pagina *è* specificato, l&#39;elenco restituito viene racchiuso in un [!DNL JSON] oggetto che contiene informazioni sul risultato totale e sulla pagina corrente. Un esempio di richiesta tramite le opzioni di pagina potrebbe essere simile al seguente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] per richieste, ambienti di staging e produzione e versioni.

## Richiesta [!DNL URLs] {#request-urls}

Nella tabella seguente sono elencate le richieste [!DNL URLs] utilizzato per trasmettere [!DNL API] richieste, per metodo.

A seconda del metodo di autenticazione utilizzato, è necessario modificare la richiesta [!DNL URLs] secondo le tabelle che seguono.

### Richiesta [!DNL URLs] per [!BADGE Consigliato]{type=positive}[!BADGE Obsoleto]{type=negative}[!DNL JWT] Autenticazione tramite Adobe Developer {#request-urls-jwt}

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

{style="table-layout:auto"}

### Richiesta [!DNL URLs] per [!BADGE Obsoleto]{type=negative}[!DNL OAuth] Autenticazione {#request-urls-oauth}

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

{style="table-layout:auto"}

## Ambienti {#environments}

Il [!DNL Audience Manager] [!DNL API]fornisce accesso a diversi ambienti di lavoro. Questi ambienti consentono di testare il codice su database separati senza influire sui dati live e di produzione. Nella tabella seguente sono elencate le opzioni [!DNL API] e i nomi host delle risorse corrispondenti.

A seconda del metodo di autenticazione utilizzato, è necessario modificare l’ambiente [!DNL URLs] secondo la tabella seguente.

| Ambiente | Nome host per [!DNL JWT] autenticazione | Nome host per [!DNL OAuth] autenticazione |
|---|---|---|
| **Produzione** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Il [!DNL Audience Manager] l’ambiente beta è una versione standalone dell’ambiente di produzione su scala ridotta. Tutti i dati che desideri verificare devono essere immessi e raccolti in questo ambiente.

## Versioni {#versions}

Nuove versioni di questi [!DNL API]vengono rilasciati regolarmente. Una nuova versione incrementa il [!DNL API] numero di versione. Nella richiesta viene fatto riferimento al numero di versione [!DNL URL] as `v<version number>` come mostrato nell&#39;esempio seguente:

`https://<host>/v1/...`

## Codici di risposta definiti {#response-codes-defined}

`HTTP` codici di stato e testo di risposta restituiti da [!DNL Audience Manager] [!UICONTROL REST API].

| ID codice di risposta | Testo di risposta | Definizione |
|---|---|---|
| `200` | `OK` | Richiesta elaborata correttamente. Se necessario, restituirà il contenuto o i dati previsti. |
| `201` | `Created` | La risorsa è stata creata. Restituisce per `PUT` e `POST` richieste. |
| `204` | `No Content` | Risorsa eliminata. Il corpo della risposta sarà vuoto. |
| `400` | `Bad Request` | Il server non ha compreso la richiesta. Di solito a causa di sintassi non valida. Verifica la richiesta e riprova. |
| `403` | `Forbidden` | Non hai accesso alla risorsa. |
| `404` | `Not Found` | Impossibile trovare la risorsa per il percorso specificato. |
| `409` | `Conflict` | Impossibile completare la richiesta a causa di un conflitto con lo stato della risorsa. |
| `500` | `Server Error` | Il server ha rilevato un errore imprevisto che ha impedito di soddisfare la richiesta. |

>[!MORELIKETHIS]
>
>* [Autenticazione JWT (account di servizio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Autenticazione OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 semplificato](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
