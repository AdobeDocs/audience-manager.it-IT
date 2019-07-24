---
description: Configurate openx come destinazione e inviate i dati dei segmenti di Audience Manager a quella piattaforma.
seo-description: Configurate openx come destinazione e inviate i dati dei segmenti di Audience Manager a quella piattaforma.
seo-title: Openx come destinazione di Audience Manager
solution: Audience Manager
title: Openx come destinazione di Audience Manager
uuid: 5 e 86 ba 73-281 c -403 b-af 06-64 a 1 d 427526 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OpenX as an Audience Manager Destination{#openx-as-an-audience-manager-destination}

Set up [!DNL OpenX] as a destination and send Audience Manager segment data to that platform.

>[!NOTE]
>
>Solo per targeting on server onsite.

## OpenX Destination Requirements {#openx-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Review the following before setting up [!DNL OpenX] as an Audience Manager destination:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] il codice deve essere distribuito sul sito. [!UICONTROL DIL] aiuta a eliminare la necessità di scrivere codici speciali per la raccolta di dati, l'integrazione, i valori dei cookie di lettura e il recupero dei dati delle pagine.
* **`get_aamCookie`Funzione:** Codice che acquisisce l'ID utente di Audience Manager e i dati del cookie. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto sulla consegna del segmento (facoltativo), fornisci Audience Manager con un registro giornaliero contenente dati di consegna a livello di impression. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Dati chiave-valore: Requisiti di formattazione

Audience Manager invia i dati sotto forma di coppie chiave-valore. Create coppie chiave-valore in base alle seguenti specifiche:

* Preface keys with `c.` (e.g., `c.color` or `c.price`).
* Separate serialized values attached to a single key with a comma (e.g., `c.color = red, green, blue`).
* Separate multiple key-value pairs with an ampersand (e.g., `c.color=red & c.price = 100 & c.condition = new`).
* I nomi delle chiavi non devono contenere caratteri speciali quali accento e punteggiatura o altri simboli.

### Solo i segmenti idonei vengono inviati a openx

The amount data passed in to [!DNL OpenX] depends on how many segments a particular user qualifies for. Ad esempio, supponiamo di configurare 100 segmenti di Gestione pubblico. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL OpenX] (not all 100).

## Create an OpenX Destination {#openx-destination}

Create a cookie destination for [!DNL OpenX] in Audience Management.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) con cui condividere i dati. [!UICONTROL Destination Builder] fornisce gli strumenti che consentono di creare e gestire questi processi di consegna dei dati. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Passaggio 1: Informazioni di base

To complete the [!UICONTROL Basic Information] section:

1. Denominate la destinazione.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

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

## OpenX Setup {#openx-code-setup}

Modify [!DNL OpenX] settings to work with Audience Manager segment data.

<!-- aam-openx-code.xml -->

To set up [!DNL OpenX]:

* Install [!UICONTROL DIL] code across your site.
* Create [!DNL OpenX] as a cookie destination in Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` Il codice è disponibile [](../../features/destinations/get-aam-cookie-code.md)qui.
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OpenX] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* Il tag di annunci potrebbe assomigliare all'esempio seguente.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Remember to include `xid=` . It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.

La chiamata ad annuncio completa potrebbe essere simile a quella riportata di seguito:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
