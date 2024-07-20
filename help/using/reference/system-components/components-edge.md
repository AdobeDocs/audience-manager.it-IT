---
description: Audience Manager utilizza topologie edge-computing distribuite per soddisfare le esigenze poste ai sistemi da fonti esterne.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Informazioni sul data center di Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Informazioni sul data center di Edge{#understanding-the-edge-data-center}

Audience Manager utilizza topologie edge-computing distribuite per soddisfare le esigenze poste ai sistemi da fonti esterne.

## Nozioni di base sui data center di Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Il computing Edge offre prestazioni migliori in risposta a una domanda diffusa su Internet, perché il &quot;margine&quot; stesso è un limite globale. [!DNL Audience Manager] posiziona dinamicamente l&#39;elaborazione più vicina alle origini della domanda e restituisce i dati in base al percorso più breve possibile. Il computing Edge consente di mantenere le prestazioni del sito, il che a sua volta preserva l&#39;esperienza utente sul sito web. Il data center perimetrale è un gateway chiave per lo spostamento di dati da e verso [!DNL Audience Manager].

Il data center perimetrale [!DNL Audience Manager] include:

* **Server core:** Si tratta dei principali [!DNL Audience Manager] sistemi. che aggiornano e forniscono dati ai server perimetrali.

* **Server Edge:** In genere si tratta di applicazioni e/o server Web. Si trovano al confine tra [!DNL Audience Manager] e Internet. I server Edge, ad esempio i sistemi [!DNL DCS] o Akamai, in genere gestiscono i dati e le richieste che scorrono da e verso [!DNL Audience Manager].

* **Bilanciatori di carico:** gestire le richieste di elaborazione/elaborazione non uniformi inerenti alle applicazioni Internet. Questi bilanciatori impediscono il sovraccarico dei cluster di server, mentre altri rimangono inattivi.

Il diagramma seguente illustra l’ambiente del centro dati edge di Audience Manager.

![](assets/edge_data_center.png)

## Distribuzione geografica e bilanciamento del carico {#geo-dist-balance}

Vedere la sezione [!DNL DCS] in [Data Collection Components](../../reference/system-components/components-data-collection.md).
