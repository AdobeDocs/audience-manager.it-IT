---
description: Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze dei nostri sistemi da fonti esterne.
seo-description: Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze dei nostri sistemi da fonti esterne.
seo-title: Informazioni su Edge Data Center
solution: Audience Manager
title: Informazioni su Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Informazioni su Edge Data Center{#understanding-the-edge-data-center}

Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze dei nostri sistemi da fonti esterne.

## Nozioni di base di Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge computing offre prestazioni migliori in risposta a una domanda diffusa su Internet, perché il "edge" stesso è un limite globale. Ciò significa che l'elaborazione posiziona [!DNL Audience Manager] dinamicamente più vicino alle origini della domanda e restituisce i dati in base al percorso più breve possibile. Edge computing aiuta a mantenere le prestazioni del sito, che a sua volta preserva l'esperienza utente sul sito Web. Il centro dati periferico è un gateway chiave per lo spostamento dei dati in entrata e in uscita [!DNL Audience Manager].

Il centro dati [!DNL Audience Manager] periferico include:

* **** Server core: Questi sono i [!DNL Audience Manager] sistemi principali. Essi aggiornano e forniscono i dati ai server periferici.

* **** Server periferici: In genere si tratta di server applicazioni e/o Web. Si siedono al confine tra [!DNL Audience Manager] e Internet. I server periferici, come i sistemi [!UICONTROL DCS] o Akamai, in genere gestiscono dati e richieste in entrata e in uscita [!DNL Audience Manager].

* **** Bilanci di carico: Gestire le richieste di elaborazione/elaborazione dispari inerenti alle applicazioni Internet. Questi bilanciamenti impediscono ai cluster di server di essere sovraccarichi mentre altri restano inattivi.

Il diagramma seguente illustra l’ambiente del centro dati periferico di Audience Manager.

![](assets/edge_data_center.png)

## Distribuzione geografica e bilanciamento del carico {#geo-dist-balance}

Vedere la [!UICONTROL DCS] sezione in Componenti [per la raccolta](../../reference/system-components/components-data-collection.md)dati.
