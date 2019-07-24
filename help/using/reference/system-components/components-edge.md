---
description: Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze poste sui nostri sistemi da origini esterne.
seo-description: Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze poste sui nostri sistemi da origini esterne.
seo-title: Comprendere il Centro dati Edge
solution: Audience Manager
title: Comprendere il Centro dati Edge
uuid: 4177 e 666-99 f 4-453 d -94 dd -058 c 6182 c 8 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Understanding the Edge Data Center{#understanding-the-edge-data-center}

Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze poste sui nostri sistemi da origini esterne.

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

L'elaborazione Edge fornisce prestazioni migliorate in risposta a una domanda diffusa a livello di Internet, in quanto il «edge» stesso è un bordo globale. This means [!DNL Audience Manager] dynamically places processing closest to the sources of demand and returns data by the shortest possible path. L'elaborazione Edge consente di mantenere le prestazioni del sito e, a sua volta, mantenere l'esperienza utente sul sito Web. The edge data center is a key gateway for moving data in and out of [!DNL Audience Manager].

The [!DNL Audience Manager] edge data center includes:

* **Server core:** Questi sono i [!DNL Audience Manager] sistemi principali. Essi aggiornano e forniscono dati ai server periferici.

* **Server periferici:** Di solito, si tratta di server e/o server Web. They sit at the boundary between [!DNL Audience Manager] and the Internet. Edge servers, such as the [!UICONTROL DCS] or Akamai systems, typically handle data and requests flowing into and out of [!DNL Audience Manager].

* **Sistema di bilanciamento del carico:** Gestire le richieste di elaborazione/elaborazione non necessarie nelle applicazioni Internet. Questi tipi di bilanciamento impediscono che cluster di server vengano sovraccarichi mentre altri rimangono inattivi.

Nel diagramma seguente è illustrato l'ambiente datacenter di Audience Manager.

![](assets/edge_data_center.png)

## Geographic Distribution and Load Balancing {#geo-dist-balance}

See the [!UICONTROL DCS] section in [Data Collection Components](../../reference/system-components/components-data-collection.md).
