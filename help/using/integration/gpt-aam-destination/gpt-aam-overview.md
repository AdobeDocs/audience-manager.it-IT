---
description: Panoramica su come integrare DFP tramite i tag di Google Publisher (GPT).
seo-description: Panoramica su come integrare DFP utilizzando i tag di Google Publisher (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrare DFP tramite i tag di Google Publisher (GPT) in Adobe Audience Manager (AAM)
title: Integrare DFP tramite i tag di Google Publisher (GPT)
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Integrare DFP tramite i tag di Google Publisher (GPT)

Gli articoli elencati di seguito forniscono una panoramica su come integrare DFP utilizzando i tag di Google Publisher (GPT). Puoi utilizzare un'integrazione sul lato server, oppure puoi impostare GPT come destinazione per inviare i dati dei segmenti di Audience Manager in DFP. Scoprirai anche i passaggi necessari per assimilare i file di registro DFP per i rapporti in Audience Manager.

* [Requisiti e metodi per l’invio di segmenti a DFP utilizzando Google Publisher Tag (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Puoi inviare segmenti qualificati a DFP sia attraverso un lato client che tramite un'integrazione lato server. I requisiti e le informazioni correlate su entrambi i metodi sono elencati di seguito.

* [Creare una destinazione GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Puoi inviare segmenti qualificati a DFP tramite un'integrazione lato client (lato client) o un'integrazione sul lato server. Se scegliete l'integrazione lato client, dovete creare una destinazione basata su cookie per i tag Google Publisher in Audience Manager.

* [Modificare la chiamata GPT settargeting API](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Aggiungete un'istruzione if per controllare i cookie di Audience Manager prima di richiamare il metodo Google Publisher Tag. settargeting.

* [Codice Audience Manager per tag Editore Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   Aamgpt è una funzione javascript che legge i dati dei cookie di Audience Manager e invia tali informazioni ai tag di Google Publisher.
