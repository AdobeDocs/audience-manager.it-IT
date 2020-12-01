---
description: Questa mappa contiene i principali sistemi di Audience Manager . Rappresenta visivamente il modo in cui i dati fluiscono nei componenti di Audience Manager, da e tra  componenti.
seo-description: Questa mappa contiene i principali sistemi di Audience Manager . Rappresenta visivamente il modo in cui i dati fluiscono nei componenti di Audience Manager, da e tra  componenti.
seo-title: Mappa del flusso di dati dell'architettura della piattaforma
solution: Audience Manager
title: Mappa del flusso di dati dell'architettura della piattaforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 2%

---


# Architettura della piattaforma: mappa del flusso di dati{#platform-architecture-data-flow-map}

Questa mappa contiene i principali sistemi di Audience Manager . Rappresenta visivamente il modo in cui i dati fluiscono nei componenti di Audience Manager, da e tra  componenti.

## Come leggere questa mappa {#compmap}

<!-- 

c_compmap.xml

 -->

Nella mappa, la casella grigia contiene [!DNL Audience Manager] sistemi. Alcuni componenti sono completamente interni e altri si trovano sul confine tra [!DNL Audience Manager] e il mondo esterno. In qualità di [!DNL Audience Manager] cliente, i componenti interni sono spesso trasparenti o inaccessibili. Tuttavia, a volte è possibile interagire con questi sistemi tramite l&#39;interfaccia utente o integrazioni di dati. I sistemi sul bordo della scatola raccolgono e inviano dati tra [!DNL Audience Manager] e il mondo esterno.

I colori definiscono il tipo di dati che scorre dentro e fuori da [!DNL Audience Manager]. Il verde è dato dai clienti, il blu è dato dai clienti (persone che visitano il sito) e il blu è arancione è dato utilizzato per il reporting.

Per le descrizioni e i riepiloghi del sistema, vedere le sezioni [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md) e [tag management](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)

