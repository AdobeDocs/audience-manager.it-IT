---
description: Panoramica su come integrare Google Ad Manager con i tag Google Publisher (GPT).
seo-description: Panoramica di come integrare Google Ad Manager con Google Publisher Tags (GPT) nel Adobe Audience Manager  (AAM).
seo-title: Integrare Google Ad Manager utilizzando i tag Google Publisher (GPT) nel Adobe Audience Manager  (AAM)
title: Integrare Google Ad Manager con i tag Google Publisher (GPT)
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Integrate [!DNL Google Ad Manager] (formerly DFP) using Google Publisher Tags (GPT)

Gli articoli elencati di seguito forniscono una panoramica su come effettuare l&#39;integrazione [!DNL Google Ad Manager] utilizzando i tag GPT (Google Publisher Tags). Puoi utilizzare un&#39;integrazione lato server, oppure impostare GPT come destinazione per l&#39;invio  dati del segmento Audience Manager a [!DNL Google Ad Manager]. Verranno inoltre illustrati i passaggi necessari per acquisire i file di [!DNL Google Ad Manager] registro per la creazione di report in  Audience Manager.

* [Requisiti e metodi per l&#39;invio di segmenti a Google Ad Manager tramite i tag Google Publisher (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puoi inviare segmenti qualificati [!DNL Google Ad Manager] sia tramite client che tramite un&#39;integrazione lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

* [Creare una destinazione GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puoi inviare segmenti qualificati [!DNL Google Ad Manager] tramite un&#39;integrazione lato client (lato browser) o lato server. Se scegliete l’integrazione sul lato client, dovete creare una destinazione basata su cookie per i tag Google Publisher in  Audience Manager.

* [Modificare la chiamata API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Aggiungete un&#39;istruzione if per verificare  cookie Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.

* [Codice di Audience Manager per i tag publisher di Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt è una funzione JavaScript che legge  i dati dei cookie Audience Manager e invia tali informazioni ai tag di Google Publisher.
