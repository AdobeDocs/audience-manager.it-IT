---
description: La segmentazione descrive i processi che qualificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall'opzione del dispositivo utilizzata per creare una regola di unione dei profili.
seo-description: La segmentazione descrive i processi che qualificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall'opzione del dispositivo utilizzata per creare una regola di unione dei profili.
seo-title: Regole di unione profili e processi di rimozione dei dispositivi dai segmenti
solution: Audience Manager
title: Regole di unione profili e processi di rimozione dei dispositivi dai segmenti
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 6%

---


# Regole di unione profili e processi di rimozione dei dispositivi dai segmenti {#profile-merge-rules-and-device-un-segmentation-processes}

La segmentazione descrive i processi che qualificano e rimuovono i profili dispositivo dai segmenti. La possibilità di rimuovere un profilo dispositivo da un segmento dipende dall&#39;opzione del dispositivo utilizzata per creare un [!UICONTROL Profile Merge Rule].

## Opzioni dispositivo disponibili {#device-options}

Come promemoria, [!UICONTROL Device Options] sono disponibili nella [!UICONTROL Profile Merge Rules Setup] sezione quando create o modificate un [!UICONTROL Profile Merge Rule].

## Opzione profilo dispositivo corrente e segmentazione dispositivo {#current-device-profile-options}

**[!UICONTROL Device Profile]** è l&#39;opzione di profilo dispositivo predefinita per un [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] può rimuovere un profilo dispositivo da un segmento quando [!UICONTROL Profile Merge Rule] si utilizza l&#39; **[!UICONTROL Device Profile]** opzione. In queste condizioni, la segmentazione si verifica quando:

* Il profilo del dispositivo è rimasto inattivo per 120 giorni. Un processo settimanale di pulizia dei dati rimuove i profili dispositivo inattivi dai tuoi segmenti.
* Il dispositivo non si qualifica più per un segmento perché gli aggiornamenti o le modifiche al profilo del dispositivo lo qualificano. Ciò si verifica quando i criteri di qualificazione del segmento cambiano, o si applica un [!DNL AND NOT] operatore a una regola del segmento, o si specificano le condizioni di [aggiornamento e frequenza](../segments/recency-and-frequency.md) che utilizzano le impostazioni minore di/uguale a. I casi di utilizzo sono descritti nella documentazione [Instant Cross-Device Suppression](instant-cross-device-suppression.md) .

![solo dispositivo](assets/device-only.png)

## Nessuna opzione dispositivo e nessuna segmentazione dispositivo {#no-device-option}

[!DNL Audience Manager] può rimuovere un ID cross-device da un segmento quando [!UICONTROL Profile Merge Rule] utilizza l&#39;opzione **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** . In queste condizioni, la segmentazione avviene quando l&#39;ID cross-device non si qualifica più per un segmento perché gli aggiornamenti o le modifiche al profilo cross-device non lo qualificano più. Ciò si verifica quando i criteri di qualificazione del segmento cambiano, o si applica un [!UICONTROL AND NOT] operatore a una regola del segmento, o si specificano le condizioni di [aggiornamento e frequenza](../segments/recency-and-frequency.md) che utilizzano le impostazioni minore di/uguale a. I casi di utilizzo sono descritti nella documentazione [Instant Cross-Device Suppression](instant-cross-device-suppression.md) .

![](assets/current-no-device.png)

## Opzioni di Device Graph e Separazione dispositivo {#device-graph-options-unsegmentation}

[!DNL Audience Manager] può rimuovere più profili dispositivo da un segmento quando [!UICONTROL Profile Merge Rule] si utilizza un&#39;opzione di grafico del dispositivo. La segmentazione avviene quando il profilo unito del dispositivo dal grafico del dispositivo non è più idoneo per il segmento, perché gli aggiornamenti o le modifiche a questo profilo unito non lo qualificano più dal segmento. Ciò si verifica quando i criteri di qualificazione del segmento cambiano, o si applica un [!UICONTROL AND NOT] operatore a una regola del segmento, o si specificano le condizioni di [aggiornamento e frequenza](../segments/recency-and-frequency.md) che utilizzano le impostazioni minore di/uguale a. I casi di utilizzo sono descritti nella documentazione [Instant Cross-Device Suppression](instant-cross-device-suppression.md) .

>[!NOTE]
>
>**Limite di 100 dispositivi per la valutazione del segmento e l&#39;esclusione**.
> Audience Manager unisce fino a 100 dispositivi durante la valutazione dei segmenti con una regola di unione dei profili che utilizza un grafico del dispositivo.  Audience Manager valuta il dispositivo corrente e fino a 99 dispositivi collegati al dispositivo corrente tramite un profilo [](../../reference/visitor-authentication-states.md) autenticato (ID cross-device). Se viene emesso il segnale di dissegmento, il dispositivo corrente e i dispositivi aggiuntivi verranno rimossi dal segmento nella destinazione.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Domande frequenti su regole di unione profili e grafico dei dispositivi](../../faq/faq-profile-merge.md)
>* [Soppressione immediata su diversi dispositivi](instant-cross-device-suppression.md)

