---
description: ' Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze poste ai nostri sistemi da fonti esterne.'
seo-description: ' Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze poste ai nostri sistemi da fonti esterne.'
seo-title: Informazioni sul centro dati edge
solution: Audience Manager
title: Informazioni sul centro dati edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Informazioni sul centro dati edge{#understanding-the-edge-data-center}

 Audience Manager utilizza topologie distribuite e edge-computing per soddisfare le esigenze poste ai nostri sistemi da fonti esterne.

## Nozioni di base di Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge computing offre prestazioni migliori in risposta a una domanda diffusa su Internet, perché il &quot;edge&quot; stesso è un limite globale. Ciò significa che [!DNL Audience Manager] posiziona dinamicamente l&#39;elaborazione più vicina alle origini della domanda e restituisce i dati in base al percorso più breve possibile. Edge computing aiuta a mantenere le prestazioni del sito, che a sua volta preserva l&#39;esperienza dell&#39;utente sul sito Web. Il data center periferico è un gateway chiave per lo spostamento dei dati in entrata e in uscita da [!DNL Audience Manager].

Il centro dati [!DNL Audience Manager] Edge include:

* **Server di base:** questi sono i  [!DNL Audience Manager] sistemi principali. Essi aggiornano e forniscono i dati ai server periferici.

* **Server periferici:** in genere, si tratta di server applicazioni e/o Web. Si trovano al confine tra [!DNL Audience Manager] e Internet. I server periferici, come i [!DNL DCS] o i sistemi Akamai, in genere gestiscono dati e richieste che entrano ed escono da [!DNL Audience Manager].

* **Bilanci del carico:** gestire le richieste di elaborazione/elaborazione dispari inerenti alle applicazioni Internet. Questi bilanciamenti impediscono ai cluster di server di essere sovraccarichi mentre altri restano inattivi.

Nel diagramma seguente è illustrato l’ambiente  centro dati periferico del Audience Manager.

![](assets/edge_data_center.png)

## Distribuzione geografica e bilanciamento del carico {#geo-dist-balance}

Vedere la sezione [!DNL DCS] in [Componenti per la raccolta dati](../../reference/system-components/components-data-collection.md).
