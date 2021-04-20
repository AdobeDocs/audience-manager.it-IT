---
description: Questa mappa contiene i principali sistemi di Audience Manager. Rappresenta visivamente il modo in cui i dati scorrono nei componenti di Audience Manager, fuori e tra loro.
seo-description: Questa mappa contiene i principali sistemi di Audience Manager. Rappresenta visivamente il modo in cui i dati scorrono nei componenti di Audience Manager, fuori e tra loro.
seo-title: Mappa del flusso di dati dell’architettura di Platform
solution: Audience Manager
title: Mappa del flusso di dati dell’architettura di Platform
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# Architettura della piattaforma: mappa del flusso di dati{#platform-architecture-data-flow-map}

Questa mappa contiene i principali sistemi di Audience Manager. Rappresenta visivamente il modo in cui i dati scorrono nei componenti di Audience Manager, fuori e tra loro.

## Come leggere questa mappa {#compmap}

<!-- 

c_compmap.xml

 -->

Nella mappa, la casella grigia contiene i sistemi [!DNL Audience Manager]. Alcuni componenti sono completamente interni e altri si trovano al confine tra [!DNL Audience Manager] e il mondo esterno. In qualità di cliente [!DNL Audience Manager], i componenti interni sono spesso trasparenti o inaccessibili. Tuttavia, a volte è possibile interagire con questi sistemi tramite l’interfaccia utente o le integrazioni di dati. I sistemi sul bordo della scatola raccolgono e inviano dati tra [!DNL Audience Manager] e il mondo esterno.

I colori definiscono il tipo di dati che scorre dentro e fuori da [!DNL Audience Manager]. Il verde è dato dal cliente, il blu è dato dal cliente (persone che visitano il tuo sito) e l&#39;arancione è dato utilizzato per il reporting.

Per le descrizioni e i riepiloghi del sistema, vedere le sezioni [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md) e [tag management](../../reference/system-components/components-tag-management.md) .

![](assets/flowmap.png)
