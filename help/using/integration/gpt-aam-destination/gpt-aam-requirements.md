---
description: Puoi inviare segmenti qualificati a DFP tramite un'integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.
seo-description: Puoi inviare segmenti qualificati a DFP tramite un'integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.
seo-title: Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT)
solution: Audience Manager
title: Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e67790b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puoi inviare segmenti qualificati [!DNL DFP] sia tramite client che tramite un'integrazione lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

## Integrazione lato client {#client-side-integration}

Per un’integrazione lato client, è necessario impostare una [!DNL GPT] destinazione in Audience Manager. Considerate quanto segue quando desiderate configurare [!DNL GPT] come destinazione Audience Manager:

* **[!UICONTROL DIL]Aggiungi**: Distribuire [!UICONTROL Data Integration Library (DIL)] il codice su tutte le pagine di destinazione. [!UICONTROL DIL] scrive i dati del segmento di Audience Manager e gli ID utente nei cookie utilizzati [!DNL GPT] per il targeting.

* **[!UICONTROL Cookie Destination]Create un**: In Audience Manager [!DNL GPT] deve essere impostata come destinazione basata su cookie.

* **** Implementa il codice di controllo del cookie: Racchiudete il metodo [!DNL GPT] API nel codice `.setTargeting` di controllo [](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)cookie consigliato. Questo codice aiuta a evitare errori cercando cookie AAM validi prima che il `.setTargeting` metodo venga richiamato.

* **`AamGpt`Aggiungere la** funzione: Il `AamGpt` codice acquisisce i dati dai cookie di Audience Manager e li invia a [!DNL GPT]. Inserite il codice [Audience Manager per i tag](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) di Google Publisher ( `AamGpt`) nella parte superiore della pagina o all’interno del blocco di `<head>` codice.

   >[!NOTE]
   >
   >La `AamGpt` funzione non è necessaria se utilizzate il vostro codice per leggere i dati dei cookie di Audience Manager.

* **** Invia registri di consegna ad Audience Manager: Se desiderate un rapporto sulla distribuzione dei segmenti (facoltativo), fornite ad Audience Manager un registro giornaliero contenente dati sulla distribuzione a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere Audience Manager `UUID`. Audience Manager può recuperarli o riceverli tramite [!DNL FTP].

### Solo i segmenti qualificati vengono inviati a GPT

La quantità di dati passati dipende [!DNL GPT] dal numero di segmenti per i quali un particolare utente si qualifica. Ad esempio, supponiamo di aver impostato 100 segmenti di Audience Manager. Se un visitatore del sito si qualifica per cinque di essi, solo questi cinque segmenti vengono inviati a [!DNL GPT] (non tutti i 100).

>[!NOTE]
>
>Non esistono limiti al numero di valori chiave che è possibile inviare, ma la [!DNL Google] richiesta [!DNL URL] contiene limiti al numero di caratteri che può accettare. Consultate [Impostazione del targeting e delle dimensioni con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integrazione lato server {#server-side-integration}

Consulta il tuo consulente Audience Manager o l’Assistenza clienti per configurare un’integrazione lato server con [!DNL DFP], utilizzando [!DNL GPT]. Dovrai fornire il tuo ID di rete [!DNL DFP] dell'account e l'ID collegamento pubblico.

>[!IMPORTANT]
>
>Se le pagine Web eseguono la libreria [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]), devi utilizzare l’integrazione lato server con Audience Manager. Se siete connessi [!DNL AMP] e disponete di un'integrazione lato client con [!DNL AMP], dovete migrare all'integrazione lato server. Contatta il tuo consulente Audience Manager o l'Assistenza clienti per discutere della migrazione.

>[!MORE_LIKE_this]
>
>* [Guida di riferimento API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

