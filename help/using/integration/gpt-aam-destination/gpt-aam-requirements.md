---
description: Puoi inviare segmenti qualificati a DFP sia attraverso un lato client che tramite un'integrazione lato server. I requisiti e le informazioni correlate su entrambi i metodi sono elencati di seguito.
seo-description: Puoi inviare segmenti qualificati a DFP sia attraverso un lato client che tramite un'integrazione lato server. I requisiti e le informazioni correlate su entrambi i metodi sono elencati di seguito.
seo-title: Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT)
solution: Audience Manager
title: Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT)
uuid: 4 b 2 ea 81 c -29 bb -42 d 3-93 d 3-1 d 8 e 677790 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

You can send qualified segments to [!DNL DFP] either through a client-side or through a server-side integration. I requisiti e le informazioni correlate su entrambi i metodi sono elencati di seguito.

## Client-Side Integration {#client-side-integration}

For a client-side integration, you need to set up a [!DNL GPT] destination in Audience Manager. Consider the following points when you want to set up [!DNL GPT] as an Audience Manager destination:

* **Aggiungi[!UICONTROL DIL]:** Distribuite [!UICONTROL Data Integration Library (DIL)] il codice su tutte le pagine che desiderate destinare. [!UICONTROL DIL] scrive i dati dei segmenti e gli ID utente di Audience Manager in cookie che vengono utilizzati da [!DNL GPT] per il targeting.

* **Create un[!UICONTROL Cookie Destination]:**[!DNL GPT] deve essere impostato come destinazione basata su cookie in Audience Manager.

* **Implementare il codice di verifica dei cookie:** Racchiudi il [!DNL GPT]`.setTargeting` metodo API nel nostro codice di verifica [dei cookie consigliato](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). This code helps prevent errors by looking for valid AAM cookies before the `.setTargeting` method gets invoked.

* **Aggiungere la`AamGpt`funzione:** `AamGpt` Il codice acquisisce i dati dai cookie di Audience Manager e li invia [!DNL GPT]a. Place the [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) at the top of the page or inside the `<head>` code block.

   >[!NOTE]
   >
   >The `AamGpt` function is not required if you use your own code to read Audience Manager cookie data.

* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto sulla consegna del segmento (facoltativo), fornisci Audience Manager con un registro giornaliero contenente dati di consegna a livello di impression. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Solo i segmenti idonei vengono inviati a GPT

The amount of data passed in to [!DNL GPT] depends on how many segments a particular user qualifies for. Ad esempio, supponiamo che tu imposti 100 segmenti Audience Manager. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL GPT] (not all 100).

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. See [Setting targeting and sizes with GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-Side Integration {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL DFP], using [!DNL GPT]. You'll need to provide your [!DNL DFP] account Network ID and Audience Link ID.

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. If you are on [!DNL AMP] and have a client-side integration with [!DNL AMP], you must migrate to the server-side integration. Contatta il tuo consulente Audience Manager o l'Assistenza clienti per discutere della migrazione.

>[!MORE_ LIKE_ THIS]
>
>* [Guida di riferimento API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

