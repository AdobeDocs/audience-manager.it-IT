---
description: La rimozione dai segmenti descrive i processi che squalificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall’opzione del dispositivo utilizzata per creare una regola di unione profili.
seo-description: La rimozione dai segmenti descrive i processi che squalificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall’opzione del dispositivo utilizzata per creare una regola di unione profili.
seo-title: Regole di unione profili e processi di rimozione dei dispositivi dai segmenti
solution: Audience Manager
title: Regole di unione profili e processi di rimozione dei dispositivi dai segmenti
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# Regole di unione profili e processi di rimozione dei dispositivi dai segmenti {#profile-merge-rules-and-device-un-segmentation-processes}

La rimozione dai segmenti descrive i processi che squalificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall’opzione del dispositivo utilizzata per creare un [!UICONTROL Profile Merge Rule].

## Opzioni dispositivo disponibili {#device-options}

Come promemoria, i [!UICONTROL Device Options] sono disponibili nella sezione [!UICONTROL Profile Merge Rules Setup] quando crei o modifichi un elemento [!UICONTROL Profile Merge Rule].

## Opzione profilo dispositivo corrente e rimozione dai segmenti dispositivo {#current-device-profile-options}

**[!UICONTROL Device Profile]** è l’opzione di profilo dispositivo predefinita per un  [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] può rimuovere un profilo dispositivo da un segmento quando  [!UICONTROL Profile Merge Rule] utilizzi l’ **[!UICONTROL Device Profile]** opzione . In queste condizioni, la segmentazione si verifica quando:

* Il profilo del dispositivo è rimasto inattivo per 120 giorni. Un processo settimanale di pulizia dei dati rimuove i profili dispositivo inattivi dai segmenti.
* Il dispositivo non è più idoneo per un segmento perché gli aggiornamenti o le modifiche al profilo del dispositivo lo qualificano. Questo accade quando i criteri di qualificazione dei segmenti cambiano, o quando applichi un operatore [!DNL AND NOT] a una regola di segmento, o quando specifichi le condizioni [recency e frequenza](../segments/recency-and-frequency.md) che utilizzano le impostazioni minore o uguale a. I casi di utilizzo sono descritti nella documentazione [Soppressione immediata su diversi dispositivi](instant-cross-device-suppression.md) .

![solo dispositivo](assets/device-only.png)

## Nessuna opzione dispositivo e rimozione dai segmenti del dispositivo {#no-device-option}

[!DNL Audience Manager] può rimuovere un ID multi-dispositivo da un segmento quando  [!UICONTROL Profile Merge Rule] utilizzi l’ **[!UICONTROL Current Authenticated Profiles]** opzione  **[!UICONTROL No Device Profile]** +. In queste condizioni, la segmentazione si verifica quando l’ID multi-dispositivo non è più idoneo per un segmento perché gli aggiornamenti o le modifiche al profilo multi-dispositivo lo qualificano. Questo accade quando i criteri di qualificazione dei segmenti cambiano, o quando applichi un operatore [!UICONTROL AND NOT] a una regola di segmento, o quando specifichi le condizioni [recency e frequenza](../segments/recency-and-frequency.md) che utilizzano le impostazioni minore o uguale a. I casi di utilizzo sono descritti nella documentazione [Soppressione immediata su diversi dispositivi](instant-cross-device-suppression.md) .

![](assets/current-no-device.png)

## Opzioni grafico dei dispositivi e rimozione dai segmenti dei dispositivi {#device-graph-options-unsegmentation}

[!DNL Audience Manager] può rimuovere più profili dispositivo da un segmento quando  [!UICONTROL Profile Merge Rule] utilizzi un’opzione grafico dei dispositivi. La segmentazione si verifica quando il profilo unito del dispositivo dal grafico dei dispositivi non è più idoneo per il segmento perché gli aggiornamenti o le modifiche a questo profilo unito lo qualificano dal segmento. Questo accade quando i criteri di qualificazione dei segmenti cambiano, o quando applichi un operatore [!UICONTROL AND NOT] a una regola di segmento, o quando specifichi le condizioni [recency e frequenza](../segments/recency-and-frequency.md) che utilizzano le impostazioni minore o uguale a. I casi di utilizzo sono descritti nella documentazione [Soppressione immediata su diversi dispositivi](instant-cross-device-suppression.md) .

>[!NOTE]
>
>**Limite di 100 dispositivi per la valutazione dei segmenti e l’annullamento della qualifica**.
>Audience Manager unisce fino a 100 dispositivi durante la valutazione dei segmenti con una regola di unione profili che utilizza un grafico dei dispositivi. L&#39;Audience Manager valuta il dispositivo corrente e fino a 99 dispositivi collegati al dispositivo corrente tramite un [profilo autenticato](../../reference/visitor-authentication-states.md) (ID multi-dispositivo). Se viene emesso il segnale di rimozione dai segmenti, il dispositivo corrente e i dispositivi aggiuntivi verranno rimossi dal segmento nella destinazione.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Domande frequenti su regole di unione profili e grafico dei dispositivi](../../faq/faq-profile-merge.md)
>* [Soppressione immediata su diversi dispositivi](instant-cross-device-suppression.md)

