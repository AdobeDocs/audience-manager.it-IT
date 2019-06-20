---
description: Configurate Open Ad Server come destinazione e inviate i dati di Audience Manager a tale piattaforma.
seo-description: Configurate Open Ad Server come destinazione e inviate i dati di Audience Manager a tale piattaforma.
seo-title: OAS come destinazione di Audience Manager
solution: Audience Manager
title: OAS come destinazione di Audience Manager
uuid: 5891 a 063-5 a 4 b -4 ea 7-865 f-b 24 e 17 ca 735 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OAS come destinazione di Audience Manager {#oas-as-an-audience-manager-destination}

Configuralo [!DNL Open Ad Server] come destinazione e invia i dati di Audience Manager a quella piattaforma.

## Requisiti di destinazione OAS {#oas-requirements}

Standard per posizione del codice, formati chiave-valore supportati, rapporti e tipo di dati del segmento inviati [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Questo tipo di destinazione richiede quanto segue:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] il codice deve essere distribuito nell&#39;inventario. [!UICONTROL DIL] aiuta a eliminare la necessità di scrivere codici speciali per la raccolta di dati, l&#39;integrazione, i valori dei cookie di lettura e il recupero dei dati delle pagine.
* **`get_aamCookie`Funzione:** Codice che acquisisce l&#39;ID utente di Audience Manager e i dati del cookie. Posiziona [questo codice](../../features/destinations/get-aam-cookie-code.md) nella parte superiore della pagina o all&#39;interno del `<head>` blocco.
* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto sulla consegna del segmento (facoltativo), fornisci Audience Manager con un registro giornaliero contenente dati di consegna a livello di impression. I dati possono essere in un formato non elaborato, ma ogni record deve contenere Audience Manager [!UICONTROL UUID]. Audience Manager può scegliere o ricevere questi tramite [!DNL FTP].

### Formato cookie e Dati chiave chiave

Audience Manager può inviare dati di segmento a un cookie del browser come indicato di seguito:

* Tasti singoli (`x=1&x=2`);
* Più chiavi (`x=1&x=2&y=3&y=4`);
* Valori serializzati (`x=1,2,3`);
* Un delimitatore di valore standard utilizzato per separare le singole coppie chiave-valore.

### Solo i segmenti idonei vengono inviati a OAS

L&#39;entità dei dati passati [!DNL OAS] dipende dal numero di segmenti idonei a un particolare utente. Ad esempio, supponiamo di configurare 100 segmenti di Gestione pubblico. Se un visitatore del sito ne qualifica cinque cinque, solo questi cinque segmenti vengono inviati ad OAS (non all&#39;intero 100).

>[!MORE_ LIKE_ THIS]
>
>* [get_ aamcookie Code](../../features/destinations/get-aam-cookie-code.md)
>* [Coppie chiave-valore spiegate](../../reference/key-value-pairs-explained.md)


## Creare una destinazione OAS {#oas-dest-setup}

Crea una destinazione basata su cookie per [!DNL OAS] Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, una *destinazione* è qualsiasi altro sistema (server pubblicitario, [!DNL DSP]rete pubblicitaria ecc.) con cui condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire questi processi di consegna dei dati. Le funzioni di destinazione Audience Manager si trovano in *Audience Data &gt; Destinations*(Destinazioni). Per iniziare, fai clic **[!UICONTROL Add New Destination]** su ed effettua le operazioni seguenti.

### Passaggio 1: Informazioni di base

Per completare la [!UICONTROL Basic Information] sezione:

1. Denominate la destinazione.
1. Seleziona **[!UICONTROL "Cookie"]** dall&#39;elenco [!UICONTROL Type] a discesa.
1. Fare clic **[!UICONTROL Save]** su e passare alle [!UICONTROL Configuration] sezioni e [!UICONTROL Segment Mappings] viceversa.

### Passaggio 2: Informazioni sulla configurazione

Per completare la [!UICONTROL Configuration] sezione:

1. **Nome cookie:** Inserisci un nome breve e descrittivo per il cookie.
1. **Dominio cookie:** Lasciate vuoto per impostare un cookie nel dominio della pagina corrente dell&#39;utente. Se desiderate specificare un dominio, prefisso il nome con un punto `.mydomain.com`simile.
1. Scegliete un&#39;opzione di chiave nella [!UICONTROL Data Format] sezione.
1. Se le chiavi utilizzano dati con valori serializzati, selezionare il **[!UICONTROL Serialize]** controllo e specificare il delimitatore seriale (il carattere che separa i valori serializzati).
1. Fare clic **[!UICONTROL Save]** su ed espandere [!UICONTROL Segment Mappings] la sezione.

### Passaggio 3: Mappature segmento

Per aggiungere un segmento a una destinazione di cookie:

1. **Trova segmenti:** [!UICONTROL Segment Mappings] La sezione fornisce due strumenti di ricerca per individuare i segmenti. Per trovare un segmento:
   * Opzione 1: Inizia a digitare un nome di segmento nel campo di ricerca. Il campo si aggiorna automaticamente in base al testo. Fai clic **[!UICONTROL Add]** su un segmento che desideri usare.
   * Opzione 2: Fai clic per **[!UICONTROL Browse All Segments]** aprire una finestra che consente di sfogliare i segmenti per nome o posizione di archiviazione. Fate clic **[!UICONTROL Add Selected Segments]** su di essa.
1. **Aggiungi mappature:** Nella sezione delle mappature, immetti l&#39;ID segmento nel campo delle mappature e fai clic **[!UICONTROL Save]** su.
1. Fai clic su **[!UICONTROL Done]**.

## Configurazione OAS {#oas-code-setup}

Modifica [!DNL OAS] le impostazioni per lavorare con i dati del segmento Audience Manager.

<!-- aam-oas-code.xml -->

Per configurare [!DNL OAS]

* Installate [!UICONTROL DIL] il codice nel sito.
* Crea OAS come destinazione del cookie in Audience Manager.
* Posiziona la `get_aamCookie` funzione nella parte superiore della pagina, idealmente all&#39;interno del `<head>` blocco. `get_aamCookie` Il codice è disponibile [](../../features/destinations/get-aam-cookie-code.md)qui.
* Modificate il tag pubblicitario per chiamare la `get_aamCookie` funzione e includete il nome del cookie fornito al momento della configurazione della [!DNL OAS] destinazione. Ad esempio, se il cookie `test_cookie`viene chiamato, il tag pubblicitario deve chiamare `get_aamCookie` e fare riferimento al nome del cookie.
* Il tag di annunci potrebbe assomigliare all&#39;esempio seguente.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Ricordate di includere la `u=` variabile. Contiene l&#39;ID utente univoco effettivo ([!UICONTROL UUID]) trasmesso durante una chiamata ad annuncio.
