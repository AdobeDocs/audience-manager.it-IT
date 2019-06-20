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


# Comprendere il Centro dati Edge{#understanding-the-edge-data-center}

Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze poste sui nostri sistemi da origini esterne.

## Nozioni di base sul centro dati Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

L&#39;elaborazione Edge fornisce prestazioni migliorate in risposta a una domanda diffusa a livello di Internet, in quanto il «edge» stesso è un bordo globale. Ciò significa [!DNL Audience Manager] che posiziona dinamicamente l&#39;elaborazione più vicino alle origini di richiesta e restituisce dati mediante il più breve percorso possibile. L&#39;elaborazione Edge consente di mantenere le prestazioni del sito e, a sua volta, mantenere l&#39;esperienza utente sul sito Web. Il centro dati periferico è un gateway chiave per lo spostamento [!DNL Audience Manager]di dati.

Il centro dati [!DNL Audience Manager] periferico include:

* **Server core:** Questi sono i [!DNL Audience Manager] sistemi principali. Essi aggiornano e forniscono dati ai server periferici.

* **Server periferici:** Di solito, si tratta di server e/o server Web. Si trovano al confine tra [!DNL Audience Manager] e Internet. I server periferici, ad esempio [!UICONTROL DCS] i sistemi di Akamai, gestiscono in genere i dati e le richieste che entrano e escono [!DNL Audience Manager]da.

* **Sistema di bilanciamento del carico:** Gestire le richieste di elaborazione/elaborazione non necessarie nelle applicazioni Internet. Questi tipi di bilanciamento impediscono che cluster di server vengano sovraccarichi mentre altri rimangono inattivi.

Nel diagramma seguente è illustrato l&#39;ambiente datacenter di Audience Manager.

![](assets/edge_data_center.png)

## Distribuzione geografica e bilanciamento del carico {#geo-dist-balance}

Consulta [!UICONTROL DCS] la sezione in [Componenti raccolta dati](../../reference/system-components/components-data-collection.md).
