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

Puoi inviare segmenti qualificati a [!DNL DFP] lato client o attraverso un&#39;integrazione lato server. I requisiti e le informazioni correlate su entrambi i metodi sono elencati di seguito.

## Integrazione lato client {#client-side-integration}

Per un&#39;integrazione sul lato client, dovete configurare una [!DNL GPT] destinazione in Audience Manager. Quando vuoi impostare [!DNL GPT] come destinazione Audience Manager, prendi in considerazione i punti seguenti:

* **Aggiungi[!UICONTROL DIL]:** Distribuite [!UICONTROL Data Integration Library (DIL)] il codice su tutte le pagine che desiderate destinare. [!UICONTROL DIL] scrive i dati dei segmenti e gli ID utente di Audience Manager in cookie che vengono utilizzati da [!DNL GPT] per il targeting.

* **Create un[!UICONTROL Cookie Destination]:**[!DNL GPT] deve essere impostato come destinazione basata su cookie in Audience Manager.

* **Implementare il codice di verifica dei cookie:** Racchiudi il [!DNL GPT]`.setTargeting` metodo API nel nostro codice di verifica [dei cookie consigliato](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Questo codice aiuta a evitare errori ricercando cookie AAM validi prima che il `.setTargeting` metodo venga richiamato.

* **Aggiungere la`AamGpt`funzione:** `AamGpt` Il codice acquisisce i dati dai cookie di Audience Manager e li invia [!DNL GPT]a. Inserisci il [codice Audience Manager per i tag](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) Editore Google ( `AamGpt`) nella parte superiore della pagina o all&#39;interno del `<head>` blocco di codice.

   >[!NOTE]
   >
   >La `AamGpt` funzione non è necessaria se utilizzi un codice personalizzato per leggere i dati del cookie Audience Manager.

* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto sulla consegna del segmento (facoltativo), fornisci Audience Manager con un registro giornaliero contenente dati di consegna a livello di impression. I dati possono essere in un formato non elaborato, ma ogni record deve contenere Audience Manager `UUID`. Audience Manager può scegliere o ricevere questi tramite [!DNL FTP].

### Solo i segmenti idonei vengono inviati a GPT

La quantità di dati passati [!DNL GPT] dipende dal numero di segmenti idonei a un particolare utente. Ad esempio, supponiamo che tu imposti 100 segmenti Audience Manager. Se un visitatore del sito ne qualifica cinque, vengono inviati solo quei cinque segmenti [!DNL GPT] (non tutti i 100).

>[!NOTE]
>
>Non ci sono limiti al numero di valori chiave che è possibile inviare, ma la [!DNL Google] richiesta [!DNL URL] ha limiti al numero di caratteri che può accettare. Consultate [Impostazione di targeting e dimensioni con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integrazione lato server {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL DFP], using [!DNL GPT]. Dovrai fornire il tuo [!DNL DFP] account Network ID e l&#39;ID collegamento pubblico.

>[!IMPORTANT]
>
>Se le pagine Web eseguono la libreria [Accelerate Pagine](https://www.ampproject.org/) Media ([!DNL AMP]), dovete utilizzare l&#39;integrazione lato server con Audience Manager. Se vi trovate e [!DNL AMP] disponete di un&#39;integrazione sul lato client con [!DNL AMP], dovete effettuare la migrazione all&#39;integrazione sul lato server. Contatta il tuo consulente Audience Manager o l&#39;Assistenza clienti per discutere della migrazione.

>[!MORE_ LIKE_ THIS]
>
>* [Guida di riferimento API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

