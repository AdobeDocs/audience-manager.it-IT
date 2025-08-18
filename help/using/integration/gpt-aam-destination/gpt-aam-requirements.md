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
source-wordcount: '466'
ht-degree: 0%

---

# Requisiti e metodi per l’invio di segmenti a Google Ad Manager tramite i tag publisher di Google ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

È possibile inviare segmenti qualificati a [!DNL Google Ad Manager] (precedentemente DFP) tramite un&#39;integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

## Integrazione lato client {#client-side-integration}

Per un&#39;integrazione lato client, è necessario impostare una destinazione [!DNL GPT] in Audience Manager. Quando si desidera impostare [!DNL GPT] come destinazione Audience Manager, considerare i punti seguenti:

* **Aggiungi [!UICONTROL DIL]:** Distribuisci il codice [!UICONTROL Data Integration Library (DIL)] in tutte le pagine di destinazione. [!UICONTROL DIL] scrive i dati del segmento di Audience Manager e gli ID utente nei cookie utilizzati da [!DNL GPT] per il targeting.

* **Creare un [!UICONTROL Cookie Destination]:** [!DNL GPT] deve essere impostato come destinazione basata su cookie in Audience Manager.

* **Implementa codice di controllo cookie:** Racchiudi il metodo API [!DNL GPT] `.setTargeting` nel nostro codice di controllo cookie [consigliato](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Questo codice consente di evitare errori cercando cookie AAM validi prima che venga richiamato il metodo `.setTargeting`.

* **Aggiungi la funzione `AamGpt`:** Il codice `AamGpt` acquisisce i dati dai cookie di Audience Manager e li invia a [!DNL GPT]. Posiziona il [codice Audience Manager per i tag publisher di Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) nella parte superiore della pagina o all&#39;interno del blocco di codice `<head>`.

  >[!NOTE]
  >
  >La funzione `AamGpt` non è necessaria se si utilizza il proprio codice per leggere i dati dei cookie di Audience Manager.

* **Invia registri di consegna ad Audience Manager:** Se desideri un rapporto di consegna del segmento (facoltativo), fornisci ad Audience Manager un registro giornaliero che contenga dati di consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere Audience Manager `UUID`. Audience Manager può ritirarli o riceverli tramite [!DNL FTP].

### Solo i segmenti qualificati vengono inviati a GPT

La quantità di dati passati a [!DNL GPT] dipende dal numero di segmenti per i quali un determinato utente è idoneo. Ad esempio, supponi di impostare 100 segmenti di Audience Manager. Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a [!DNL GPT] (non tutti e 100).

>[!NOTE]
>
>Non sono previsti limiti al numero di valori chiave che è possibile inviare, ma la richiesta [!DNL Google] [!DNL URL] non ha limiti al numero di caratteri che può accettare. Vedi [Impostazione del targeting e delle dimensioni con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integrazione lato server {#server-side-integration}

Rivolgiti al tuo consulente Audience Manager o all&#39;Assistenza clienti se desideri configurare un&#39;integrazione lato server con [!DNL Google Ad Manager] utilizzando [!DNL GPT]. Devi fornire l&#39;ID di rete dell&#39;account [!DNL Google Ad Manager] e l&#39;ID di collegamento del pubblico.

>[!IMPORTANT]
>
>Se nelle pagine Web è in esecuzione la libreria [Pagine di contenuti multimediali accelerati](https://www.ampproject.org/) ([!DNL AMP]), è necessario utilizzare l&#39;integrazione lato server con Audience Manager. Se utilizzi [!DNL AMP] e disponi di un&#39;integrazione lato client con [!DNL AMP], devi migrare all&#39;integrazione lato server. Contatta il tuo consulente Audience Manager o l’Assistenza clienti per informazioni sulla migrazione.

>[!MORELIKETHIS]
>
>* [Guida di riferimento API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
