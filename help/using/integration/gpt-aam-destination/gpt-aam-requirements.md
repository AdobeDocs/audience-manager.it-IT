---
description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un’integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Requisiti e metodi per l’invio di segmenti a Google Ad Manager utilizzando Google Publisher Tag (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Requisiti e metodi per l’invio di segmenti a Google Ad Manager tramite i tag publisher di Google ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] (precedentemente DFP) tramite un&#39;integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

## Integrazione lato client {#client-side-integration}

Per un’integrazione lato client, è necessario impostare un’ [!DNL GPT] destinazione in Audience Manager. Quando si desidera impostare, tenere presenti i seguenti punti [!DNL GPT] come destinazione di Audience Manager:

* **Aggiungi [!UICONTROL DIL]:** Distribuisci [!UICONTROL Data Integration Library (DIL)] su tutte le pagine di cui desideri eseguire il targeting. [!UICONTROL DIL] scrive i dati del segmento di Audience Manager e gli ID utente nei cookie utilizzati da [!DNL GPT] per il targeting.

* **Creare un [!UICONTROL Cookie Destination]:** [!DNL GPT] deve essere impostata come destinazione basata su cookie in Audience Manager.

* **Implementa codice di controllo cookie:** Racchiudi il [!DNL GPT] `.setTargeting` Metodo API nella sezione consigliata [codice di verifica dei cookie](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Questo codice aiuta a prevenire gli errori cercando cookie AAM validi prima che `.setTargeting` viene richiamato il metodo.

* **Aggiungi il `AamGpt` Funzione:** Il `AamGpt` il codice acquisisce i dati dai cookie Audience Manager e li invia a [!DNL GPT]. Posiziona [Codice Audience Manager per i tag publisher di Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) nella parte superiore della pagina o all&#39;interno del `<head>` blocco di codice.

   >[!NOTE]
   >
   >Il `AamGpt` La funzione non è necessaria se utilizzi un codice personalizzato per leggere i dati dei cookie di Audience Manager.

* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto sulla consegna dei segmenti (facoltativo), fornisci agli Audienci Manager un registro giornaliero che contiene dati di consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere l’Audience Manager `UUID`. Gli Audienci Manager possono riceverli tramite [!DNL FTP].

### Solo i segmenti qualificati vengono inviati a GPT

Quantità di dati passati a [!DNL GPT] dipende dal numero di segmenti per i quali un utente specifico si qualifica. Ad esempio, supponi di impostare 100 segmenti di Audience Manager. Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a [!DNL GPT] (non tutti i 100).

>[!NOTE]
>
>Non ci sono limiti al numero di valori chiave che puoi inviare, ma il [!DNL Google] richiesta [!DNL URL] ha limiti al numero di caratteri che può accettare. Consulta [Impostazione di targeting e dimensioni con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integrazione lato server {#server-side-integration}

Rivolgiti al tuo consulente Audience Manager o all&#39;Assistenza clienti per configurare un&#39;integrazione lato server con [!DNL Google Ad Manager], utilizzando [!DNL GPT]. Dovrai fornire il tuo [!DNL Google Ad Manager] ID di rete dell’account e ID di Audience Link.

>[!IMPORTANT]
>
>Se le pagine web eseguono [Pagine multimediali accelerate](https://www.ampproject.org/) ([!DNL AMP]), è necessario utilizzare l’integrazione lato server con Audience Manager. Se è attiva [!DNL AMP] e avere un’integrazione lato client con [!DNL AMP], è necessario eseguire la migrazione all’integrazione lato server. Contatta il tuo consulente di Audience Manager o l’Assistenza clienti per informazioni sulla migrazione.

>[!MORELIKETHIS]
>
>* [Guida di riferimento dell’API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

