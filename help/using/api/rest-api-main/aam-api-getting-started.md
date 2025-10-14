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
source-wordcount: '2563'
ht-degree: 1%

---

# Guida introduttiva a [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informazioni su requisiti generali, autenticazione, parametri di query facoltativi, richiesta [!DNL URLs] e altri riferimenti.

## Raccomandazioni e requisiti per l’utilizzo delle API {#api-requirements-recommendations}

Quando si lavora con il codice [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/), tieni presente quanto segue:

* **Parametri di richiesta:** tutti i parametri di richiesta sono obbligatori se non specificato diversamente.
* **Intestazioni richiesta**: quando utilizzi [token Adobe Developer](https://www.adobe.io/), devi fornire l&#39;intestazione `x-api-key`. Puoi ottenere la tua chiave [!DNL API] seguendo le istruzioni riportate nella pagina [Integrazione account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Tipo di contenuto **[!DNL JSON]:** Specificare `content-type: application/json` *e* `accept: application/json` nel codice.
* **Richieste e risposte:** Inviare richieste come oggetto [!DNL JSON] formattato correttamente. [!DNL Audience Manager] risponde con [!DNL JSON] dati formattati. Le risposte del server possono contenere i dati richiesti, un codice di stato o entrambi.
* **Accesso:** Il consulente [!DNL Audience Manager] ti fornirà un ID client e una chiave che ti consente di effettuare [!DNL API] richieste.
* **Esempi di documentazione e codice:** Il testo in *corsivo* rappresenta una variabile fornita o trasmessa quando si creano o si ricevono dati [!DNL API]. Sostituisci il testo *in corsivo* con il tuo codice, i tuoi parametri o altre informazioni richieste.

## Autenticazione {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] supporta tre metodi di autenticazione.

* [!BADGE Consigliata]{type=positive} [Autenticazione server-to-server OAuth](#oauth-adobe-developer) tramite [la console per sviluppatori Adobe](https://www.adobe.io/). [!DNL Adobe Developer] è l&#39;ecosistema e la community di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://developer.adobe.com/apis/). Si tratta del metodo consigliato per impostare e utilizzare [!DNL Adobe] [!DNL APIs]. Ulteriori informazioni sull&#39;[autenticazione server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) nella documentazione per gli sviluppatori di Adobe.
* [!BADGE Autenticazione &#x200B;]{type=negative} [JWT (account di servizio) &#x200B;](#jwt) obsoleta tramite la [console per sviluppatori Adobe](https://www.adobe.io/). [!DNL Adobe Developer] è l&#39;ecosistema e la community di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://developer.adobe.com/apis/).
* [!BADGE Obsoleta]{type=negative} [Autenticazione OAuth legacy](#oauth-deprecated). Anche se questo metodo è obsoleto, i clienti con integrazioni [!DNL OAuth] esistenti possono continuare a utilizzarlo.

>[!IMPORTANT]
>
>A seconda del metodo di autenticazione utilizzato, è necessario modificare di conseguenza la richiesta [!DNL URLs]. Consulta la sezione [Ambienti](#environments) per informazioni dettagliate sui nomi host da utilizzare.

## Autenticazione server-to-server OAuth tramite Adobe Developer {#oauth-adobe-developer}

Questa sezione illustra come raccogliere le credenziali necessarie per autenticare le chiamate API di Audience Manager, come descritto nel diagramma di flusso seguente. È possibile raccogliere la maggior parte delle credenziali richieste nella configurazione iniziale una tantum. Il token di accesso, tuttavia, deve essere aggiornato ogni 24 ore.

![Diagramma del flusso di autenticazione di Audience Manager.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Panoramica di Adobe Developer {#developer-overview}

[!DNL Adobe Developer] è l&#39;ecosistema e la community di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://developer.adobe.com/apis).

Si tratta del metodo consigliato per impostare e utilizzare [!DNL Adobe] [!DNL APIs].

### Prerequisiti {#prerequisites-server-to-server}

Prima di configurare l&#39;autenticazione di [!DNL OAuth Server-to-Server], verificare di avere accesso a [Adobe Developer Console](https://developer.adobe.com/console/home) in [Adobe Developer](https://developer.adobe.com/). Contatta l’amministratore dell’organizzazione per le richieste di accesso.

### Autenticazione {#oauth}

Per configurare l&#39;autenticazione di [!DNL OAuth Server-to-Server] tramite [!DNL Adobe Developer], attenersi alla procedura seguente:

1. Accedi a [Adobe Developer Console](https://developer.adobe.com/console/home).
1. Segui i passaggi descritti nella [Guida all&#39;implementazione delle credenziali server-to-server OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Durante il [passaggio 2: aggiungi un&#39;API al progetto utilizzando l&#39;autenticazione dell&#39;account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), scegli l&#39;opzione [!DNL Audience Manager] [!DNL API].
1. Provare la connessione effettuando la prima chiamata [!DNL API] in base alle istruzioni del [passaggio 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Per configurare e utilizzare [!DNL Audience Manager] [!DNL REST APIs] in modo automatico, è possibile ruotare i segreti client a livello di programmazione. Per istruzioni dettagliate, consulta [la documentazione per gli sviluppatori](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically).

### Aggiungere l’API Audience Manager a un progetto {#add-aam-api-to-project}

Vai a [Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) e accedi con il tuo Adobe ID. Quindi, segui i passaggi descritti nel tutorial su [creazione di un progetto vuoto](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) nella documentazione di Adobe Developer Console.

Dopo aver creato un nuovo progetto, selezionare **[!UICONTROL Add API]** nella schermata **[!UICONTROL Project Overview]**.

>[!TIP]
>
>Se disponi del provisioning per più organizzazioni, utilizza il selettore organizzazione nell’angolo superiore destro dell’interfaccia per assicurarti di essere nell’organizzazione necessaria.

![Schermata Developer Console con l&#39;opzione Aggiungi API evidenziata.](/help/using/api/rest-api-main/assets/add-api.png)

Viene visualizzata la schermata **[!UICONTROL Add an API]**. Selezionare l&#39;icona del prodotto per Adobe Experience Cloud, quindi scegliere **[!UICONTROL Audience Manager API]** prima di selezionare **[!UICONTROL Next]**.

![Seleziona API Audience Manager.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Seleziona l&#39;opzione **[!UICONTROL View docs]** per passare in una finestra del browser separata alla [documentazione di riferimento API di Audience Manager](https://bank.demdex.com/portal/swagger/index.html#) completa.

### Seleziona il tipo di autenticazione server-to-server OAuth {#select-oauth-server-to-server}

Quindi, seleziona il tipo di autenticazione per generare token di accesso e accedere all’API di Audience Manager.

>[!IMPORTANT]
>
>Selezionare il metodo **[!UICONTROL OAuth Server-to-Server]** in quanto questo sarà l&#39;unico metodo supportato per gli spostamenti in avanti. Metodo **[!UICONTROL Service Account (JWT)]** obsoleto. Anche se le integrazioni che utilizzano il metodo di autenticazione JWT continueranno a funzionare fino al 1° gennaio 2025, Adobe consiglia vivamente di migrare le integrazioni esistenti al nuovo metodo server-to-server OAuth prima di tale data.

![Seleziona metodo di autenticazione OAuth.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Selezionare i profili di prodotto per l’integrazione {#select-product-profiles}

Nella schermata **[!UICONTROL Configure API]**, selezionare i profili di prodotto desiderati. L’account di servizio della tua integrazione potrà accedere a funzioni granulari tramite i profili di prodotto selezionati qui.

![Seleziona i profili di prodotto per la tua integrazione.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Selezionare **[!UICONTROL Save configured API]** quando si è pronti.

### Raccogli le credenziali {#gather-credentials}

Dopo l&#39;aggiunta dell&#39;API al progetto, nella pagina **[!UICONTROL Audience Manager API]** per il progetto vengono visualizzate le credenziali seguenti, necessarie in tutte le chiamate alle API di Audience Manager:

![Informazioni sull&#39;integrazione dopo l&#39;aggiunta di un&#39;API in Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Generare un token di accesso {#generate-access-token}

Il passaggio successivo consiste nel generare una credenziale `{ACCESS_TOKEN}` da utilizzare nelle chiamate API di Audience Manager. A differenza dei valori per `{API_KEY}` e `{ORG_ID}`, è necessario generare un nuovo token ogni 24 ore per continuare a utilizzare le API di Audience Manager. Selezionare **[!UICONTROL Generate access token]**, come illustrato di seguito.

![Mostra come generare il token di accesso](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Testare una chiamata API {#test-api-call}

Dopo aver ottenuto il token di autenticazione bearer, esegui una chiamata API per verificare che ora puoi accedere alle API di Audience Manager.

1. Passa alla [documentazione di riferimento API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Selezionare **[!UICONTROL Authorize]** e incollare il token di accesso ottenuto nel passaggio [genera token di accesso](#generate-access-token).

   ![Autorizza chiamate API](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Eseguire una chiamata GET all&#39;endpoint API `/datasources` per recuperare un elenco di tutte le origini dati disponibili a livello globale, come indicato nella [documentazione di riferimento API](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Selezionare **[!UICONTROL Try it out]**, seguito da **[!UICONTROL Execute]**, come illustrato di seguito.

   ![Esecuzione chiamate API](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB Richiesta API]

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

## [!BADGE Autenticazione obsoleta]{type=negative} [!DNL JWT] ([!DNL Service Account]) con Adobe Developer {#jwt}

+++ Visualizza informazioni sul metodo [!DNL JWT] ([!DNL Service Account]) obsoleto per ottenere i token di autenticazione.

### Panoramica di Adobe Developer {#adobeio}

[!DNL Adobe Developer] è l&#39;ecosistema e la community di sviluppatori di Adobe. Include [API per tutti i prodotti Adobe](https://www.adobe.io/apis.html).

Si tratta del metodo consigliato per impostare e utilizzare [!DNL Adobe] [!DNL APIs].

### Prerequisiti {#prerequisites}

Prima di configurare l&#39;autenticazione di [!DNL JWT], verificare di avere accesso a [Adobe Developer Console](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). Contatta l’amministratore dell’organizzazione per le richieste di accesso.

### Autenticazione {#auth}

Per configurare l&#39;autenticazione di [!DNL JWT (Service Account)] tramite [!DNL Adobe Developer], attenersi alla procedura seguente:

1. Accedi a [Adobe Developer Console](https://console.adobe.io/).
1. Segui i passaggi descritti in [Connessione account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Durante il [passaggio 2: aggiungi un&#39;API al progetto utilizzando l&#39;autenticazione dell&#39;account di servizio](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), scegli l&#39;opzione [!DNL Audience Manager] [!DNL API].
1. Provare la connessione effettuando la prima chiamata [!DNL API] in base alle istruzioni del [passaggio 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Per configurare e utilizzare [!DNL Audience Manager] [!DNL REST APIs] in modo automatico, è possibile generare [!DNL JWT] a livello di programmazione. Per istruzioni dettagliate, consulta Autenticazione [JWT (account di servizio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md).

### Autorizzazioni RBAC dell’account tecnico

Se il tuo account Audience Manager utilizza [Controllo degli accessi basato sul ruolo](../../features/administration/administration-overview.md), devi creare un account utente tecnico di Audience Manager e aggiungerlo al gruppo RBAC di Audience Manager che effettuerà le chiamate API.

Per creare un account utente tecnico e aggiungerlo a un gruppo RBAC, effettua le seguenti operazioni:

1. Effettuare una chiamata `GET` a `https://aam.adobe.io/v1/users/self`. La chiamata creerà un account utente tecnico visibile in [!UICONTROL Admin Console], nella pagina [!UICONTROL Users].

   ![account tecnico](assets/technical-account.png)

1. Accedi al tuo account Audience Manager e [aggiungi l&#39;account utente tecnico](../../features/administration/administration-overview.md#create-group) al gruppo di utenti che effettuerà le chiamate API.

+++

## [!BADGE Autenticazione &#x200B;]{type=negative} Obsoleta[!DNL OAuth] (Obsoleta) {#oauth-deprecated}

+++ Visualizza informazioni sul metodo di autenticazione legacy [!DNL OAuth] obsoleto per ottenere i token di autenticazione.

>[!WARNING]
> L&#39;autenticazione e il rinnovo del token [!DNL Audience Manager] [!UICONTROL REST API] tramite [!DNL OAuth 2.0] sono ora obsoleti.
>
> Utilizza invece l&#39;autenticazione [JWT (account di servizio)](#jwt-service-account-authentication-jwt).

[!DNL Audience Manager] [!UICONTROL REST API] segue gli standard [!DNL OAuth 2.0] per l&#39;autenticazione e il rinnovo dei token. Le sezioni seguenti descrivono come eseguire l&#39;autenticazione e iniziare a lavorare con [!DNL API].

### Crea un utente [!DNL API] generico {#requirements}

È consigliabile creare un account utente tecnico separato per l&#39;utilizzo di [!DNL Audience Manager] [!DNL API]. Si tratta di un account generico non associato o associato a un utente specifico dell’organizzazione. Questo tipo di account utente [!DNL API] consente di eseguire 2 operazioni:

* Identifica il servizio che chiama [!DNL API] (ad esempio, chiamate dalle app che utilizzano [!DNL API] o da altri strumenti che effettuano [!DNL API] richieste).
* Fornisci accesso ininterrotto a [!DNL API]. Un account associato a una persona specifica può essere cancellato quando lascia la tua azienda. In questo modo non sarà possibile utilizzare il codice [!DNL API] disponibile. Un account generico non legato a un dipendente specifico consente di evitare questo problema.

Come esempio o caso d&#39;uso per questo tipo di account, supponiamo che si desideri modificare molti segmenti contemporaneamente con i [Strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-management-intro.md). Bene, per fare questo, il tuo account utente ha bisogno dell&#39;accesso a [!DNL API]. Anziché aggiungere le autorizzazioni a un utente specifico, creare un account utente [!DNL API] non specifico con credenziali, chiave e segreto appropriati per effettuare chiamate a [!DNL API]. Questa funzione è utile anche se si sviluppano applicazioni personalizzate che utilizzano [!DNL Audience Manager] [!DNL API].

Rivolgiti al tuo consulente [!DNL Audience Manager] per configurare un account utente generico di [!DNL API].

### Flusso di lavoro di autenticazione password {#password-authentication-workflow}

Autenticazione password accesso sicuro [!DNL REST API]. I passaggi seguenti descrivono il flusso di lavoro per l&#39;autenticazione tramite password da un client [!DNL JSON] nel browser.

>[!TIP]
>
>Crittografare i token di accesso e di aggiornamento se vengono memorizzati in un database.

#### Passaggio 1: richiesta dell&#39;accesso [!DNL API]

Contatta il tuo Partner Solutions Manager. Ti forniranno un ID client [!DNL API] e un segreto. L&#39;ID e il segreto ti autenticano in [!DNL API].

Nota: se si desidera ricevere un token di aggiornamento, specificarlo quando si richiede l&#39;accesso [!DNL API].

#### Passaggio 2: richiedere il token

Trasmettere una richiesta token con il client [!DNL JSON] preferito. Quando crei la richiesta:

* Utilizzare un metodo `POST` per chiamare `https://api.demdex.com/oauth/token`.
* Converti l’ID client e il segreto in una stringa con codifica base 64. Durante il processo di conversione, separa l’ID e il segreto con due punti. Ad esempio, le credenziali `testId : testSecret` vengono convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Ad esempio, l&#39;intestazione potrebbe essere simile alla seguente: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Imposta il corpo della richiesta come segue:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Passaggio 3: ricevere il token

La risposta di [!DNL JSON] contiene il token di accesso. La risposta deve essere simile alla seguente:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

La chiave `expires_in` rappresenta il numero di secondi rimanenti alla scadenza del token di accesso. Come best practice, utilizza tempi di scadenza brevi per limitare l’esposizione se il token viene mai esposto.

### Aggiorna token {#refresh-token}

Aggiorna i token per rinnovare l&#39;accesso [!DNL API] dopo la scadenza del token originale. Se richiesto, la risposta [!DNL JSON] nel flusso di lavoro della password include un token di aggiornamento. Se non ricevi un token di aggiornamento, creane uno nuovo tramite il processo di autenticazione tramite password.

Puoi anche utilizzare un token di aggiornamento per generare un nuovo token prima della scadenza del token di accesso esistente.

Se il token di accesso è scaduto, nella risposta riceverai un `401 Status Code` e la seguente intestazione:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

I passaggi seguenti descrivono il flusso di lavoro per l&#39;utilizzo di un token di aggiornamento per creare un nuovo token di accesso da un client [!DNL JSON] nel browser.

#### Passaggio 1: richiesta del nuovo token

Trasmettere una richiesta di token di aggiornamento con il client [!DNL JSON] preferito. Quando crei la richiesta:

* Utilizzare un metodo `POST` per chiamare `https://api.demdex.com/oauth/token`.
* Converti l’ID client e il segreto in una stringa con codifica base 64. Durante il processo di conversione, separa l’ID e il segreto con due punti. Ad esempio, le credenziali `testId : testSecret` vengono convertite in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Passa le intestazioni HTTP `Authorization:Basic <base-64 clientID:clientSecret>` e `Content-Type: application/x-www-form-urlencoded`. Ad esempio, l&#39;intestazione potrebbe essere simile alla seguente: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Nel corpo della richiesta, specifica `grant_type:refresh_token` e passa il token di aggiornamento ricevuto nella richiesta di accesso precedente. La richiesta deve essere simile alla seguente: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Passaggio 2: ricevere il nuovo token

La risposta di [!DNL JSON] contiene il nuovo token di accesso. La risposta deve essere simile alla seguente:

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

[!DNL Audience Manager] [!UICONTROL REST API] supporta codice di autorizzazione e autenticazione implicita. Per utilizzare questi metodi di accesso, gli utenti devono accedere a `https://api.demdex.com/oauth/authorize` per accedere e aggiornare i token.

+++

## Effettua [!DNL API] richieste autenticate {#authenticated-api-requests}

Requisiti per la chiamata dei metodi [!DNL API] dopo la ricezione di un token di autenticazione.

Per effettuare chiamate ai metodi [!DNL API] disponibili:

* Nell&#39;intestazione `HTTP`, impostare `Authorization: Bearer <token>`.
* Quando si utilizza l&#39;autenticazione [JWT (account di servizio)](#jwt), è necessario fornire l&#39;intestazione `x-api-key`, che sarà la stessa di `client_id`. Puoi ottenere `client_id` dalla pagina [Integrazione Adobe Developer](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Chiama il metodo [!DNL API] richiesto.

## Parametri query [!DNL API] facoltativi {#optional-api-query-parameters}

Impostare i parametri facoltativi disponibili per i metodi che restituiscono tutte le proprietà di un oggetto.

È possibile utilizzare questi parametri facoltativi con i metodi [!DNL API] che restituiscono *tutte* le proprietà di un oggetto. Impostare queste opzioni nella stringa di richiesta quando si trasmette la query a [!DNL API].

| Parametro | Descrizione |
|--- |--- |
| `page` | Restituisce i risultati per numero di pagina. La numerazione inizia da 0. |
| `pageSize` | Imposta il numero di risultati di risposta restituiti dalla richiesta (10 è il valore predefinito). |
| `sortBy` | Ordina e restituisce i risultati in base alla proprietà [!DNL JSON] specificata. |
| `descending` | Ordina e restituisce i risultati in ordine decrescente. `ascending` è predefinito. |
| `search` | Restituisce risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che si desideri trovare i risultati per tutti i modelli che hanno la parola &quot;Test&quot; in uno qualsiasi dei campi di valore per quell&#39;elemento. La richiesta di esempio potrebbe essere simile alla seguente:   `GET https://aam.adobe.io/v1/models/?search=Test`.  È possibile eseguire ricerche in base a qualsiasi valore restituito da un metodo &quot;[!DNL get all]&quot;. |
| `folderId` | Restituisce tutti gli ID per [!UICONTROL traits] all&#39;interno della cartella specificata. Non disponibile per tutti i metodi. |
| `permissions` | Restituisce un elenco di segmenti in base all’autorizzazione specificata. `READ` è predefinito. Le autorizzazioni includono:<ul><li>`READ` : restituisce e visualizza informazioni su un segmento.</li><li>`WRITE`: utilizzare `PUT` per aggiornare un segmento.</li><li>`CREATE` : utilizza `POST` per creare un segmento.</li><li>`DELETE` : elimina un segmento. Richiede l’accesso alle caratteristiche sottostanti, se presenti. Ad esempio, per rimuoverlo, dovrai disporre dei diritti necessari per eliminare le caratteristiche che appartengono a un segmento.</li></ul><br>Specificare più autorizzazioni con coppie chiave-valore separate. Ad esempio, per restituire un elenco di segmenti con solo le autorizzazioni `READ` e `WRITE`, passare in `"permissions":"READ"`, `"permissions":"WRITE"`. |
| `includePermissions` | ([!DNL Boolean]) Impostare su `true` per restituire le autorizzazioni per il segmento. Il valore predefinito è `false`. |

{style="table-layout:auto"}

### Nota Sulle Opzioni Di Pagina

Quando le informazioni di pagina *non sono specificate*, la richiesta restituisce [!DNL JSON] come risultato normale in un array. Se sono state specificate le informazioni di pagina *is*, l&#39;elenco restituito verrà racchiuso in un oggetto [!DNL JSON] contenente informazioni sul risultato totale e sulla pagina corrente. Un esempio di richiesta tramite le opzioni di pagina potrebbe essere simile al seguente:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] per richieste, ambienti di staging e produzione e versioni.

## Richiedi [!DNL URLs] {#request-urls}

Nella tabella seguente sono elencate le richieste [!DNL URLs] utilizzate per trasmettere [!DNL API] richieste, per metodo.

A seconda del metodo di autenticazione utilizzato, è necessario modificare la richiesta [!DNL URLs] in base alle tabelle seguenti.

### Richiedi [!DNL URLs] per il server OAuth [!BADGE Consigliato]{type=positive} e l&#39;autenticazione [!BADGE Obsoleta]{type=negative} [!DNL JWT] tramite Adobe Developer {#request-urls-jwt}

| Metodi [!DNL API] | Richiedi [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Caratteristiche: `https://aam.adobe.io/v1/folders/traits /`<br>Segmenti: `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

{style="table-layout:auto"}

### Richiedi [!DNL URLs] per l&#39;autenticazione [!BADGE &#x200B; legacy &#x200B;]{type=negative}Obsoleta[!DNL OAuth] {#request-urls-oauth}

| Metodi [!DNL API] | Richiedi [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Caratteristiche: `https://api.demdex.com/v1/folders/traits /`<br>Segmenti: `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

{style="table-layout:auto"}

## Ambienti {#environments}

I [!DNL Audience Manager] [!DNL API] forniscono l&#39;accesso a diversi ambienti di lavoro. Questi ambienti consentono di testare il codice su database separati senza influire sui dati live e di produzione. Nella tabella seguente sono elencati gli ambienti [!DNL API] disponibili e i nomi host delle risorse corrispondenti.

A seconda del metodo di autenticazione utilizzato, è necessario modificare l&#39;ambiente [!DNL URLs] in base alla tabella seguente.

| Ambiente | Nome host per autenticazione [!DNL JWT] | Nome host per autenticazione [!DNL OAuth] |
|---|---|---|
| **Produzione** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>L&#39;ambiente beta [!DNL Audience Manager] è una versione standalone su scala ridotta dell&#39;ambiente di produzione. Tutti i dati che desideri verificare devono essere immessi e raccolti in questo ambiente.

## Versioni {#versions}

Le nuove versioni di questi [!DNL API] vengono rilasciate regolarmente. Una nuova versione incrementa il numero di versione [!DNL API]. Nella richiesta [!DNL URL] viene fatto riferimento al numero di versione come `v<version number>`, come illustrato nell&#39;esempio seguente:

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
>* Autenticazione [JWT (account di servizio)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [Autenticazione OAuth](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 semplificato](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
