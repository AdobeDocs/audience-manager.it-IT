---
description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un’integrazione lato client o lato server. I requisiti e le informazioni correlate su entrambi i metodi sono elencati di seguito.
seo-description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un’integrazione lato client o lato server. I requisiti e le informazioni correlate su entrambi i metodi sono elencati di seguito.
seo-title: Requisiti e metodi per l’invio di segmenti a Google Ad Manager utilizzando Google Publisher Tag (GPT)
solution: Audience Manager
title: Requisiti e metodi per l’invio di segmenti a Google Ad Manager utilizzando Google Publisher Tag (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Requisiti e metodi per l’invio di segmenti a Google Ad Manager utilizzando i tag publisher di Google ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] (precedentemente DFP) tramite un lato client o tramite un’integrazione lato server. I requisiti e le informazioni correlate su entrambi i metodi sono elencati di seguito.

## Integrazione lato client {#client-side-integration}

Per un’integrazione lato client, devi impostare una destinazione [!DNL GPT] in Audience Manager. Quando desideri impostare [!DNL GPT] come destinazione di Audience Manager, considera quanto segue:

* **Aggiungi  [!UICONTROL DIL]:** distribuisci  [!UICONTROL Data Integration Library (DIL)] il codice su tutte le pagine di cui desideri eseguire il targeting. [!UICONTROL DIL] scrive i dati dei segmenti di Audience Manager e gli ID utente nei cookie usati da  [!DNL GPT] per il targeting.

* **Crea un  [!UICONTROL Cookie Destination]:** [!DNL GPT] deve essere configurato come destinazione basata su cookie in Audience Manager.

* **Implementa il codice di controllo dei cookie:** Racchiudi il metodo  [!DNL GPT] `.setTargeting` API nel nostro codice di controllo  [dei cookie consigliato](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Questo codice aiuta a prevenire gli errori cercando cookie AAM validi prima che il metodo `.setTargeting` venga richiamato.

* **Aggiungi la  `AamGpt` funzione:** il  `AamGpt` codice acquisisce i dati dai cookie di Audience Manager e li invia a  [!DNL GPT]. Posiziona il [Codice di Audience Manager per Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) nella parte superiore della pagina o all’interno del blocco di codice `<head>`.

   >[!NOTE]
   >
   >La funzione `AamGpt` non è necessaria se utilizzi un codice personalizzato per leggere i dati dei cookie di Audience Manager.

* **Invia registri di consegna ad Audience Manager:** se desideri un rapporto di consegna dei segmenti (facoltativo), fornisci un Audience Manager di registro giornaliero contenente dati di consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere l&#39;Audience Manager `UUID`. Audience Manager può raccogliere o ricevere questi dati tramite [!DNL FTP].

### Solo i segmenti qualificati vengono inviati a GPT

La quantità di dati passati a [!DNL GPT] dipende dal numero di segmenti per i quali un particolare utente si qualifica. Ad esempio, supponiamo che tu abbia impostato 100 segmenti di Audience Manager. Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a [!DNL GPT] (non tutti i 100).

>[!NOTE]
>
>Non ci sono limiti al numero di valori chiave che puoi inviare, ma la richiesta [!DNL Google] [!DNL URL] ha dei limiti al numero di caratteri che può accettare. Consulta [Impostazione del targeting e delle dimensioni con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integrazione lato server {#server-side-integration}

Per impostare un’integrazione lato server con [!DNL Google Ad Manager], rivolgiti al tuo consulente di Audience Manager o all’Assistenza clienti utilizzando [!DNL GPT]. Devi fornire il tuo [!DNL Google Ad Manager] ID di rete dell&#39;account e l&#39;ID di collegamento dell&#39;audience.

>[!IMPORTANT]
>
>Se nelle pagine web è in esecuzione la libreria [Pagine multimediali accelerate](https://www.ampproject.org/) ([!DNL AMP]), è necessario utilizzare l&#39;integrazione lato server con Audience Manager. Se utilizzi [!DNL AMP] e disponi di un’integrazione lato client con [!DNL AMP], devi eseguire la migrazione all’integrazione lato server. Contatta il tuo consulente Audience Manager o l’Assistenza clienti per discutere della migrazione.

>[!MORELIKETHIS]
>
>* [Guida di riferimento dell’API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

