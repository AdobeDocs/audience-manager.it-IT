---
description: Panoramica su come integrare Google Ad Manager utilizzando i tag publisher di Google (GPT).
seo-description: Panoramica su come integrare Google Ad Manager utilizzando i tag publisher (GPT, Google Publisher Tags) in Adobe Audience Manager (AAM).
seo-title: Integrare Google Ad Manager utilizzando Google Publisher Tags (GPT) in Adobe Audience Manager (AAM)
title: Integrare Google Ad Manager utilizzando i tag publisher di Google (GPT, Google Publisher Tags)
feature: Integrazione di terze parti
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Integrare [!DNL Google Ad Manager] (precedentemente DFP) utilizzando Google Publisher Tag (GPT)

Gli articoli elencati di seguito forniscono una panoramica su come integrare [!DNL Google Ad Manager] utilizzando Google Publisher Tag (GPT). Puoi utilizzare un’integrazione lato server oppure impostare GPT come destinazione per l’invio di dati di segmenti di Audience Manager a [!DNL Google Ad Manager]. Scoprirai anche i passaggi necessari per acquisire i file di registro [!DNL Google Ad Manager] per la generazione di rapporti in Audience Manager.

* [Requisiti e metodi per l’invio di segmenti a Google Ad Manager utilizzando Google Publisher Tag (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un’integrazione lato client o lato server. I requisiti e le informazioni correlate su entrambi i metodi sono elencati di seguito.

* [Creare una destinazione GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puoi inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un’integrazione lato client (lato browser) o lato server. Se scegli l’integrazione lato client, devi creare in Audience Manager una destinazione basata su cookie per i tag publisher di Google.

* [Modificare la chiamata API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Aggiungi un&#39;istruzione if per verificare la presenza di cookie di Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting .

* [Codice di Audience Manager per i tag publisher di Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt è una funzione JavaScript che legge i dati dei cookie di Audience Manager e invia tali informazioni a Google Publisher Tags.
