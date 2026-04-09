---
description: Panoramica dell’integrazione di Google Ad Manager tramite Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Integrare Google Ad Manager utilizzando Google Publisher Tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
TQID: https://experienceleague.adobe.com/29V5C3MbEondd3-qWLBfi3jaGid1I1UM9nYIl9nZWVo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 212
ht-degree: 0%

---

# Integrare [!DNL Google Ad Manager] (precedentemente DFP) utilizzando Google Publisher Tags (GPT)

Gli articoli elencati di seguito forniscono una panoramica dell&#39;integrazione di [!DNL Google Ad Manager] mediante Google Publisher Tags (GPT). È possibile utilizzare un&#39;integrazione lato server oppure impostare GPT come destinazione per inviare i dati del segmento Audience Manager a [!DNL Google Ad Manager]. Scoprirai anche i passaggi necessari per acquisire i file di registro [!DNL Google Ad Manager] per il reporting in Audience Manager.

* [Requisiti e metodi per l’invio di segmenti a Google Ad Manager utilizzando Google Publisher Tag (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  È possibile inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un&#39;integrazione lato client o lato server. I requisiti e le relative informazioni su entrambi i metodi sono elencati di seguito.

* [Creare una destinazione GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  È possibile inviare segmenti qualificati a [!DNL Google Ad Manager] tramite un&#39;integrazione lato client (lato browser) o lato server. Se scegli l’integrazione lato client, devi creare una destinazione basata su cookie per i tag publisher di Google in Audience Manager.

* [Modificare la chiamata API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  Aggiungere un&#39;istruzione if per verificare la presenza di cookie di Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.

* [Codice Audience Manager per i tag publisher Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt è una funzione di JavaScript che legge i dati dei cookie di Audience Manager e invia tali informazioni ai tag publisher di Google.
