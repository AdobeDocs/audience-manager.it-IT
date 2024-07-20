---
description: Panoramica dell’integrazione di Google Ad Manager tramite Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Integrare Google Ad Manager utilizzando Google Publisher Tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Integrare [!DNL Google Ad Manager] (precedentemente DFP) utilizzando Google Publisher Tags (GPT)

Gli articoli elencati di seguito forniscono una panoramica dell&#39;integrazione di [!DNL Google Ad Manager] mediante Google Publisher Tags (GPT). È possibile utilizzare un&#39;integrazione lato server oppure impostare GPT come destinazione per inviare i dati del segmento Audience Manager a [!DNL Google Ad Manager]. Scopri anche i passaggi necessari per acquisire i file di registro [!DNL Google Ad Manager] per il reporting in Audience Manager.

* [Requisiti e metodi per l’invio di segmenti a Google Ad Manager utilizzando Google Publisher Tag (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  È possibile inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un&#39;integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

* [Creare una destinazione GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  È possibile inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un&#39;integrazione lato client (lato browser) o lato server. Se si sceglie l&#39;integrazione lato client, è necessario creare una destinazione basata su cookie per i tag di Google Publisher nell&#39;Audience Manager.

* [Modificare la chiamata API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  Aggiungere un&#39;istruzione if per verificare la presenza di cookie di Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.

* [Codice Audience Manager per i tag publisher di Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt è una funzione di JavaScript che legge i dati dei cookie di Audience Manager e invia tali informazioni ai tag di Publisher di Google.
