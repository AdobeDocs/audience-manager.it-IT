---
description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un'integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.
seo-description: Puoi inviare segmenti qualificati a Google Ad Manager tramite un'integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.
seo-title: Requisiti e metodi per l'invio di segmenti a Google Ad Manager tramite i tag Google Publisher (GPT)
solution: Audience Manager
title: Requisiti e metodi per l'invio di segmenti a Google Ad Manager tramite i tag Google Publisher (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Requisiti e metodi per l&#39;invio di segmenti a Google Ad Manager con tag Google Publisher ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] (già DFP) tramite client o tramite un&#39;integrazione lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

## Integrazione lato client {#client-side-integration}

Per un&#39;integrazione lato client, è necessario impostare una destinazione [!DNL GPT] nel Audience Manager . Considerate quanto segue quando desiderate impostare [!DNL GPT] come destinazione di Audience Manager :

* **Aggiungi  [!UICONTROL DIL]:** distribuisci  [!UICONTROL Data Integration Library (DIL)] il codice su tutte le pagine di destinazione. [!UICONTROL DIL] scrive  dati del segmento di Audience Manager e ID utente nei cookie che vengono utilizzati  [!DNL GPT] per il targeting.

* **Crea un  [!UICONTROL Cookie Destination]:** [!DNL GPT] deve essere impostato come destinazione basata su cookie in  Audience Manager.

* **Implementa il codice di controllo del cookie:** Racchiudi il metodo  [!DNL GPT] `.setTargeting` API nel codice [ di controllo ](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)dei cookie consigliato. Questo codice aiuta a evitare errori cercando cookie AAM validi prima che venga richiamato il metodo `.setTargeting`.

* **Aggiungi la  `AamGpt` funzione:** il  `AamGpt` codice acquisisce i dati dai cookie  Audience Manager e li invia a  [!DNL GPT]. Posizionare il [ codice di Audience Manager per i tag di Google Publisher ](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) nella parte superiore della pagina o all&#39;interno del blocco di codice `<head>`.

   >[!NOTE]
   >
   >La funzione `AamGpt` non è necessaria se si utilizza il proprio codice per leggere  dati dei cookie di Audience Manager.

* **Invia registri di consegna a  Audience Manager:** se si desidera un rapporto sulla consegna dei segmenti (facoltativo), fornire  Audience Manager con un registro giornaliero contenente dati sulla consegna a livello di impression. I dati possono essere in formato non elaborato, ma ogni record deve contenere il Audience Manager  `UUID`.  Audience Manager può raccogliere o ricevere questi tramite [!DNL FTP].

### Solo i segmenti qualificati vengono inviati a GPT

La quantità di dati passati a [!DNL GPT] dipende dal numero di segmenti per i quali un particolare utente si qualifica. Ad esempio, supponiamo di impostare 100 segmenti di Audience Manager . Se un visitatore del sito è idoneo per cinque di essi, solo questi cinque segmenti vengono inviati a [!DNL GPT] (non tutti e 100).

>[!NOTE]
>
>Non ci sono limiti al numero di valori chiave che è possibile inviare, ma la richiesta [!DNL Google] [!DNL URL] non ha limiti al numero di caratteri che può accettare. Vedere [Impostazione del targeting e delle dimensioni con GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integrazione lato server {#server-side-integration}

Per impostare un&#39;integrazione lato server con [!DNL Google Ad Manager], rivolgiti al consulente  Audience Manager o all&#39;Assistenza clienti utilizzando [!DNL GPT]. Dovrai fornire il tuo [!DNL Google Ad Manager] ID di rete dell&#39;account e l&#39;ID collegamento pubblico.

>[!IMPORTANT]
>
>Se nelle pagine Web è in esecuzione la libreria [Pagine multimediali accelerate](https://www.ampproject.org/) ([!DNL AMP]), è necessario utilizzare l&#39;integrazione lato server con  Audience Manager. Se vi trovate su [!DNL AMP] e disponete di un&#39;integrazione lato client con [!DNL AMP], dovete eseguire la migrazione all&#39;integrazione lato server. Contatta il tuo consulente  Audience Manager o l&#39;Assistenza clienti per discutere della migrazione.

>[!MORELIKETHIS]
>
>* [Guida di riferimento API GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

