---
description: Puoi inviare segmenti qualificati a DFP tramite un'integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.
seo-description: Puoi inviare segmenti qualificati a DFP tramite un'integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.
seo-title: Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT)
solution: Audience Manager
title: Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 7%

---


# Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puoi inviare segmenti qualificati [!DNL DFP] sia tramite client che tramite un&#39;integrazione lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

## Integrazione lato client {#client-side-integration}

Per un&#39;integrazione lato client, è necessario impostare una [!DNL GPT] destinazione in  Audience Manager. Considerate quanto segue quando desiderate impostare [!DNL GPT] come destinazione Audience Manager :

* **Aggiungi[!UICONTROL DIL]:** Distribuire [!UICONTROL Data Integration Library (DIL)] il codice su tutte le pagine di destinazione. [!UICONTROL DIL] scrive  i dati del segmento Audience Manager e gli ID utente nei cookie che vengono utilizzati [!DNL GPT] per il targeting.

* **Create un[!UICONTROL Cookie Destination]:** [!DNL GPT] deve essere impostato come destinazione basata su cookie in  Audience Manager.

* **Implementa il codice di controllo del cookie:** Racchiudete il metodo [!DNL GPT] API nel codice `.setTargeting` di controllo [](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)cookie consigliato. Questo codice aiuta a evitare errori cercando cookie AAM validi prima che il `.setTargeting` metodo venga richiamato.

* **Aggiungere la`AamGpt`funzione:** Il `AamGpt` codice acquisisce i dati  cookie Audience Manager e li invia a [!DNL GPT]. Posizionare il [codice Audience Manager per i tag](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) di Google Publisher ( `AamGpt`) nella parte superiore della pagina o all’interno del blocco di `<head>` codice.

   >[!NOTE]
   >
   >La `AamGpt` funzione non è necessaria se si utilizza il proprio codice per leggere  dati dei cookie Audience Manager.

* **Invia registri di consegna a  Audience Manager:** Se desiderate un rapporto sulla distribuzione dei segmenti (facoltativo), fornite  Audience Manager un registro giornaliero contenente i dati sulla distribuzione a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere l&#39;Audience Manager  `UUID`.  Audience Manager può raccogliere o ricevere questi tramite [!DNL FTP].

### Solo i segmenti qualificati vengono inviati a GPT

La quantità di dati passati dipende [!DNL GPT] dal numero di segmenti per i quali un particolare utente si qualifica. Ad esempio, supponiamo di impostare 100 segmenti  Audience Manager. Se un visitatore del sito si qualifica per cinque di essi, solo questi cinque segmenti vengono inviati a [!DNL GPT] (non tutti i 100).

>[!NOTE]
>
>Non esistono limiti al numero di valori chiave che è possibile inviare, ma la [!DNL Google] richiesta [!DNL URL] ha dei limiti al numero di caratteri che può accettare. Consultate [Impostazione del targeting e delle dimensioni con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integrazione lato server {#server-side-integration}

Rivolgiti al tuo consulente Audience Manager  o all&#39;Assistenza clienti per configurare un&#39;integrazione lato server con [!DNL DFP], utilizzando [!DNL GPT]. Dovrai fornire il tuo ID di rete [!DNL DFP] dell&#39;account e l&#39;ID collegamento pubblico.

>[!IMPORTANT]
>
>Se nelle pagine Web è in esecuzione la libreria [Pagine](https://www.ampproject.org/) multimediali[!DNL AMP]con accelerazione (), è necessario utilizzare l&#39;integrazione lato server con  Audience Manager. Se siete connessi [!DNL AMP] e disponete di un&#39;integrazione lato client con [!DNL AMP], dovete migrare all&#39;integrazione lato server. Contatta il tuo consulente Audience Manager  o l&#39;Assistenza clienti per discutere della migrazione.

>[!MORELIKETHIS]
>
>* [Guida di riferimento API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

