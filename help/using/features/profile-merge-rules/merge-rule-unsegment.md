---
description: La rimozione dai segmenti descrive i processi che squalificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall’opzione dispositivo utilizzata per creare una regola di unione profili.
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: Regole di unione profili e processi di rimozione dei dispositivi dai segmenti
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# Regole di unione profili e processi di rimozione dei dispositivi dai segmenti {#profile-merge-rules-and-device-un-segmentation-processes}

La rimozione dai segmenti descrive i processi che squalificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall&#39;opzione del dispositivo utilizzata per creare [!UICONTROL Profile Merge Rule].

## Opzioni dispositivo disponibili {#device-options}

Come promemoria, i [!UICONTROL Device Options] sono disponibili nella sezione [!UICONTROL Profile Merge Rules Setup] quando crei o modifichi un [!UICONTROL Profile Merge Rule].

## Opzione profilo dispositivo corrente e rimozione dai segmenti del dispositivo {#current-device-profile-options}

**[!UICONTROL Device Profile]** è l&#39;opzione di profilo dispositivo predefinita per [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] può rimuovere un profilo dispositivo da un segmento quando [!UICONTROL Profile Merge Rule] utilizza l&#39;opzione **[!UICONTROL Device Profile]**. In queste condizioni, la rimozione dai segmenti si verifica quando:

* Il profilo del dispositivo è rimasto inattivo per 120 giorni. Un processo di pulizia dei dati settimanale rimuove i profili dispositivo inattivi dai segmenti.
* Il dispositivo non è più idoneo per un segmento perché gli aggiornamenti o le modifiche al profilo del dispositivo lo squalificano. Ciò si verifica quando i criteri di qualificazione del segmento cambiano, si applica un operatore [!DNL AND NOT] a una regola del segmento o si specificano [condizioni di recency e frequenza](../segments/recency-and-frequency.md) che utilizzano le impostazioni minore o uguale a. I casi di utilizzo sono descritti nella documentazione di [Instant Cross-Device Suppression](instant-cross-device-suppression.md).

![solo dispositivo](assets/device-only.png)

## Nessuna opzione di dispositivo e rimozione dei dispositivi dai segmenti {#no-device-option}

[!DNL Audience Manager] può rimuovere un ID multi-dispositivo da un segmento quando [!UICONTROL Profile Merge Rule] utilizza l&#39;opzione **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**. In queste condizioni, la rimozione dai segmenti si verifica quando l’ID multi-dispositivo non è più idoneo per un segmento perché gli aggiornamenti o le modifiche al profilo multi-dispositivo lo squalificano. Ciò si verifica quando i criteri di qualificazione del segmento cambiano, si applica un operatore [!UICONTROL AND NOT] a una regola del segmento o si specificano [condizioni di recency e frequenza](../segments/recency-and-frequency.md) che utilizzano le impostazioni minore o uguale a. I casi di utilizzo sono descritti nella documentazione di [Instant Cross-Device Suppression](instant-cross-device-suppression.md).

![](assets/current-no-device.png)

## Opzioni di Device Graph e rimozione dai segmenti del dispositivo {#device-graph-options-unsegmentation}

[!DNL Audience Manager] può rimuovere più profili dispositivo da un segmento quando [!UICONTROL Profile Merge Rule] utilizza un&#39;opzione del grafico dei dispositivi. La rimozione dai segmenti si verifica quando il profilo unito del dispositivo dal grafico dei dispositivi non è più idoneo per il segmento perché gli aggiornamenti o le modifiche a questo profilo unito lo squalificano dal segmento. Ciò si verifica quando i criteri di qualificazione del segmento cambiano, si applica un operatore [!UICONTROL AND NOT] a una regola del segmento o si specificano [condizioni di recency e frequenza](../segments/recency-and-frequency.md) che utilizzano le impostazioni minore o uguale a. I casi di utilizzo sono descritti nella documentazione di [Instant Cross-Device Suppression](instant-cross-device-suppression.md).

>[!NOTE]
>
>Limite di dispositivi **100 per la valutazione dei segmenti e l&#39;interdizione**.
>&#x200B;>Audience Manager unisce fino a 100 dispositivi durante la valutazione dei segmenti con una regola di unione profili che utilizza un grafico dei dispositivi. Audience Manager valuta il dispositivo corrente e fino a 99 dispositivi collegati al dispositivo corrente da un [profilo autenticato](../../reference/visitor-authentication-states.md) (ID multi-dispositivo). Se viene emesso il segnale di rimozione dai segmenti, il dispositivo corrente e i dispositivi aggiuntivi verranno rimossi dal segmento nella destinazione.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Domande frequenti su regole di unione profili e grafico dei dispositivi](../../faq/faq-profile-merge.md)
>* [Soppressione immediata su diversi dispositivi](instant-cross-device-suppression.md)
