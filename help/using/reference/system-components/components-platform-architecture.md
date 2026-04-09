---
description: Questa mappa contiene i principali sistemi Audience Manager. Rappresenta visivamente il modo in cui i dati fluiscono dentro, fuori e tra i componenti di Audience Manager.
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: Mappa del flusso di dati dell’architettura della piattaforma
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
TQID: https://experienceleague.adobe.com/AuYZKnavjMq-XyilPWgEeWASzFB3K5HuAqx-wsE-H9k
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 170
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
