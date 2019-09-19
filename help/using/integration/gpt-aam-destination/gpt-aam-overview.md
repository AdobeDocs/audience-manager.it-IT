---
description: Panoramica di come integrare DFP utilizzando i tag GPT (Google Publisher Tags).
seo-description: Panoramica su come integrare DFP utilizzando i tag GPT (Google Publisher Tags) in Adobe Audience Manager (AAM).
seo-title: Integrare DFP tramite Google Publisher Tags (GPT) in Adobe Audience Manager (AAM)
title: Integrare DFP utilizzando i tag Google Publisher (GPT)
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Integrare DFP utilizzando i tag Google Publisher (GPT)

Gli articoli elencati di seguito forniscono una panoramica su come integrare DFP utilizzando i tag GPT (Google Publisher Tags). Puoi utilizzare un'integrazione lato server oppure impostare GPT come destinazione per inviare i dati del segmento di Audience Manager a DFP. Scoprirai anche i passaggi necessari per assimilare i file di registro DFP per il reporting in Audience Manager.

* [Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puoi inviare segmenti qualificati a DFP tramite un'integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

* [Creare una destinazione GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puoi inviare segmenti qualificati a DFP tramite un'integrazione lato client (lato browser) o lato server. Se scegliete l’integrazione lato client, dovete creare una destinazione basata su cookie per i tag di Google Publisher in Audience Manager.

* [Modificare la chiamata API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Aggiungete un'istruzione if per controllare i cookie di Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.

* [Codice Audience Manager per i tag di Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt è una funzione JavaScript che legge i dati dei cookie di Audience Manager e invia tali informazioni ai tag di Google Publisher.
