---
description: Evita di usare regole di unione profili con Device Graph per segmenti che hanno scarsa probabilità di disporre di una popolazione di segmenti in tempo reale.
seo-description: Evita di usare regole di unione profili con Device Graph per segmenti che hanno scarsa probabilità di disporre di una popolazione di segmenti in tempo reale.
seo-title: Considerazioni importanti sulle regole di unione profili con grafici dispositivo
title: Considerazioni importanti sulle regole di unione profili con grafici dispositivo
uuid: 93 cd 8861-210 d -4 c 52-9 cb 7-6 f 2 dd 7 dc 018 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Considerazioni importanti sulle regole di unione profili con grafici dispositivo {#important-considerations-for-profile-merge-rules-with-device-graphs}

Evitate di utilizzare [!UICONTROL Profile Merge Rules] con segmenti [!UICONTROL Device Graph] per segmenti che non hanno una popolazione di segmenti in tempo reale.

>[!IMPORTANT]
>
>Se la [!UICONTROL Profile Merge Rule] configurazione è errata, la popolazione del segmento esportata in destinazioni batch potrebbe essere notevolmente inferiore a quanto previsto.

I segmenti che utilizzano una [regola di unione profili con Device Graph](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) vengono valutati solo sui dispositivi visti in tempo reale sui [server periferici di Audience Manager](../../reference/system-components/components-edge.md) dopo che il segmento è stato creato.

Ricorda che una [!UICONTROL Profile Merge Rule] con una [!UICONTROL Device Graph] delle seguenti opzioni dispositivo è selezionata, come mostrato di seguito.

![](assets/pmr-considerations-1.png)

I dispositivi idonei per un segmento in tempo reale sono misurati dalla [popolazione in tempo reale del segmento](../../features/segments/segment-builder-data.md#segment-populations).

![](assets/pmr-considerations-2.png)

Una popolazione segmento in tempo reale bassa significa che pochissimi dei dispositivi idonei per il segmento vengono visualizzati in tempo reale. Per ottenere prestazioni ottimali, i segmenti con scarsa popolazione in tempo reale devono utilizzare un [!UICONTROL Profile Merge Rule] set per valutare l &#39; *[!UICONTROL Current Device]*, come nell&#39;immagine di seguito.

![](assets/pmr-considerations-3.png)

L&#39;impostazione della [!UICONTROL Profile Merge Rule] valutazione garantisce *[!UICONTROL Current Device]* che tutti i dispositivi (non solo quelli visualizzati in tempo reale) vengano valutati per il segmento. Tutti i dispositivi idonei per il segmento sono definiti dalla popolazione del segmento totale, come mostrato di seguito.

![](assets/pmr-considerations-4.png)