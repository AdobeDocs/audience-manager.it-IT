---
description: Audience Manager utilizza topologie edge-computing distribuite per soddisfare le esigenze poste ai sistemi da fonti esterne.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Informazioni sul centro dati edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# Informazioni sul centro dati edge{#understanding-the-edge-data-center}

Audience Manager utilizza topologie edge-computing distribuite per soddisfare le esigenze poste ai sistemi da fonti esterne.

## Nozioni di base sui centri dati edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

L&#39;elaborazione Edge offre prestazioni migliori in risposta a una domanda diffusa a livello di Internet, perché il &quot;perimetro&quot; stesso è un limite globale. Ciò significa che [!DNL Audience Manager] posiziona dinamicamente l’elaborazione più vicina alle origini della domanda e restituisce i dati in base al percorso più breve possibile. L&#39;elaborazione Edge consente di mantenere le prestazioni del sito, il che, a sua volta, preserva l&#39;esperienza utente sul sito web. Il data center perimetrale è un gateway chiave per lo spostamento di dati in entrata e in uscita [!DNL Audience Manager].

Il [!DNL Audience Manager] il centro dati edge include:

* **Server core:** Questi sono i principali [!DNL Audience Manager] sistemi. che aggiornano e forniscono dati ai server perimetrali.

* **Server Edge:** Si tratta in genere di applicazioni e/o server web. Si siedono al confine tra [!DNL Audience Manager] e Internet. Server perimetrali, ad esempio [!DNL DCS] o sistemi Akamai, in genere gestiscono i dati e le richieste in entrata e in uscita [!DNL Audience Manager].

* **Bilanciatori di carico:** Gestire le richieste di elaborazione/elaborazione irregolari inerenti alle applicazioni Internet. Questi bilanciatori impediscono il sovraccarico dei cluster di server, mentre altri rimangono inattivi.

Il diagramma seguente illustra l’ambiente del centro dati edge di Audience Manager.

![](assets/edge_data_center.png)

## Distribuzione geografica e bilanciamento del carico {#geo-dist-balance}

Consulta la [!DNL DCS] sezione in [Componenti di raccolta dati](../../reference/system-components/components-data-collection.md).
