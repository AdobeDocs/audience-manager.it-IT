---
description: Panoramica su come integrare DFP utilizzando i tag GPT (Google Publisher Tags).
seo-description: Panoramica di come integrare DFP utilizzando i tag GPT (Google Publisher Tags) nel Adobe Audience Manager  (AAM).
seo-title: Integrare DFP tramite Google Publisher Tags (GPT) nel Adobe Audience Manager  (AAM)
title: Integrare DFP utilizzando i tag Google Publisher (GPT)
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---


# Integrare DFP utilizzando i tag Google Publisher (GPT)

Gli articoli elencati di seguito forniscono una panoramica su come integrare DFP utilizzando i tag GPT (Google Publisher Tags). È possibile utilizzare un&#39;integrazione lato server, oppure impostare GPT come destinazione per inviare  dati del segmento Audience Manager a DFP. Verranno inoltre illustrati i passaggi necessari per acquisire i file di registro DFP per la creazione di report in  Audience Manager.

* [Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puoi inviare segmenti qualificati a DFP tramite un&#39;integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

* [Creare una destinazione GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puoi inviare segmenti qualificati a DFP tramite un&#39;integrazione lato client (lato browser) o lato server. Se scegliete l’integrazione sul lato client, dovete creare una destinazione basata su cookie per i tag Google Publisher in  Audience Manager.

* [Modificare la chiamata API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Aggiungete un&#39;istruzione if per verificare  cookie Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.

* [codice Audience Manager per i tag di Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt è una funzione JavaScript che legge  i dati dei cookie Audience Manager e invia tali informazioni ai tag di Google Publisher.
