---
description: Questa mappa contiene i principali sistemi Audience Manager. Rappresenta visivamente il modo in cui i dati fluiscono dentro, fuori e tra i componenti di Audience Manager.
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: Mappa del flusso di dati dell’architettura della piattaforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# Architettura della piattaforma: mappa del flusso di dati{#platform-architecture-data-flow-map}

Questa mappa contiene i principali sistemi Audience Manager. Rappresenta visivamente il modo in cui i dati fluiscono dentro, fuori e tra i componenti di Audience Manager.

## Come leggere questa mappa {#compmap}

<!-- 

c_compmap.xml

 -->

Nella mappa, la casella grigia contiene [!DNL Audience Manager] sistemi. Alcuni componenti sono completamente interni e altri si trovano sul confine tra [!DNL Audience Manager] e il mondo esterno. In qualità di cliente [!DNL Audience Manager], i componenti interni sono spesso trasparenti o inaccessibili. Tuttavia, a volte è possibile interagire con questi sistemi tramite l’interfaccia utente o le integrazioni di dati. I sistemi ai margini della scatola raccolgono e inviano dati tra [!DNL Audience Manager] e il mondo esterno.

I colori definiscono il tipo di dati in entrata e in uscita da [!DNL Audience Manager]. Il verde è dato del cliente, il blu è dato del cliente (persone che visitano il tuo sito) e l’arancione è dato utilizzato per il reporting.

Per le descrizioni e i riepiloghi del sistema, vedere le sezioni [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md) e [tag management](../../reference/system-components/components-tag-management.md) relative ai dati.

![](assets/flowmap.png)
