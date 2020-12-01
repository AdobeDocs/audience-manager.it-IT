---
description: Panoramica su come integrare Google Ad Manager con i tag Google Publisher (GPT).
seo-description: Panoramica di come integrare Google Ad Manager con i tag Google Publisher (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrare Google Ad Manager con i tag Google Publisher (GPT) in Adobe Audience Manager (AAM)
title: Integrare Google Ad Manager con i tag Google Publisher (GPT)
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Integrare [!DNL Google Ad Manager] (già DFP) utilizzando i tag Google Publisher (GPT)

Gli articoli elencati di seguito forniscono una panoramica su come integrare [!DNL Google Ad Manager] utilizzando i tag di Google Publisher (GPT). È possibile utilizzare un&#39;integrazione lato server, oppure impostare GPT come destinazione per inviare i dati del segmento  Audience Manager a [!DNL Google Ad Manager]. Verranno inoltre illustrati i passaggi necessari per assimilare i file di registro [!DNL Google Ad Manager] per la creazione di report in  Audience Manager.

* [Requisiti e metodi per l&#39;invio di segmenti a Google Ad Manager tramite i tag Google Publisher (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] sia tramite client che tramite un&#39;integrazione lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

* [Creare una destinazione GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un&#39;integrazione lato client (lato browser) o lato server. Se scegliete l’integrazione sul lato client, dovete creare una destinazione basata su cookie per i tag di Google Publisher in  Audience Manager.

* [Modificare la chiamata API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Aggiungete un&#39;istruzione if per verificare  cookie di Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.

* [Codice di Audience Manager per i tag publisher di Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt è una funzione JavaScript che legge  dati dei cookie di Audience Manager e invia tali informazioni ai tag di Google Publisher.
