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


# OAS as an Audience Manager Destination {#oas-as-an-audience-manager-destination}

Set up [!DNL Open Ad Server] as a destination and send Audience Manager data to that platform.

## OAS Destination Requirements {#oas-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Questo tipo di destinazione richiede quanto segue:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] il codice deve essere distribuito nell'inventario. [!UICONTROL DIL] aiuta a eliminare la necessità di scrivere codici speciali per la raccolta di dati, l'integrazione, i valori dei cookie di lettura e il recupero dei dati delle pagine.
* **`get_aamCookie`Funzione:** Codice che acquisisce l'ID utente di Audience Manager e i dati del cookie. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto sulla consegna del segmento (facoltativo), fornisci Audience Manager con un registro giornaliero contenente dati di consegna a livello di impression. The data can be in a raw format, but each record must contain the Audience Manager [!UICONTROL UUID]. Audience Manager can pick up or receive these via [!DNL FTP].

### Formato cookie e Dati chiave chiave

Audience Manager può inviare dati di segmento a un cookie del browser come indicato di seguito:

* Single keys (`x=1&x=2`);
* Multiple keys (`x=1&x=2&y=3&y=4`);
* Serialized values (`x=1,2,3`);
* Un delimitatore di valore standard utilizzato per separare le singole coppie chiave-valore.

### Solo i segmenti idonei vengono inviati a OAS

The amount data passed in to [!DNL OAS] depends on how many segments a particular user qualifies for. Ad esempio, supponiamo di configurare 100 segmenti di Gestione pubblico. Se un visitatore del sito ne qualifica cinque cinque, solo questi cinque segmenti vengono inviati ad OAS (non all'intero 100).

>[!MORE_ LIKE_ THIS]
>
>* [get_ aamcookie Code](../../features/destinations/get-aam-cookie-code.md)
>* [Coppie chiave-valore spiegate](../../reference/key-value-pairs-explained.md)


## Create an OAS Destination {#oas-dest-setup}

Create a cookie-based destination for [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) con cui condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire questi processi di consegna dei dati. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Passaggio 1: Informazioni di base

To complete the [!UICONTROL Basic Information] section:

1. Denominate la destinazione.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Save]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### Passaggio 2: Informazioni sulla configurazione

To complete the [!UICONTROL Configuration] section:

1. **Nome cookie:** Inserisci un nome breve e descrittivo per il cookie.
1. **Dominio cookie:** Lasciate vuoto per impostare un cookie nel dominio della pagina corrente dell'utente. If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`.
1. Choose a key option in the [!UICONTROL Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### Passaggio 3: Mappature segmento

Per aggiungere un segmento a una destinazione di cookie:

1. **Trova segmenti:** [!UICONTROL Segment Mappings] La sezione fornisce due strumenti di ricerca per individuare i segmenti. Per trovare un segmento:
   * Opzione 1: Inizia a digitare un nome di segmento nel campo di ricerca. Il campo si aggiorna automaticamente in base al testo. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.
1. **Aggiungi mappature:** Nella sezione delle mappature, immetti l'ID segmento nel campo delle mappature e fai clic **[!UICONTROL Save]** su.
1. Fai clic su **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Modify [!DNL OAS] settings to work with Audience Manager segment data.

<!-- aam-oas-code.xml -->

To set up [!DNL OAS]

* Install [!UICONTROL DIL] code across your site.
* Crea OAS come destinazione del cookie in Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` Il codice è disponibile [](../../features/destinations/get-aam-cookie-code.md)qui.
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OAS] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* Il tag di annunci potrebbe assomigliare all'esempio seguente.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Remember to include the `u=` variable. It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.
