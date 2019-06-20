---
description: Il modo in cui l'intervallo time-to-live (TTL) incide sull'appartenenza al segmento.
seo-description: Il modo in cui l'intervallo time-to-live (TTL) incide sull'appartenenza al segmento.
seo-title: Segmento e Tempo caratteristica in Live Explained
solution: Audience Manager
title: Tempo del segmento in Live Explained
uuid: 5 b 2 c 6911-50 b 9-4 b 68-9 dd 4-21128 d 112 eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Segmento e tempo delle caratteristiche - Spiegazioni dal vivo {#segment-time-to-live-explained}

Il modo in cui l&#39;intervallo trait [!UICONTROL time-to-live] ([!DNL TTL]) influisce sull&#39;appartenenza al segmento.

<!-- segment-ttl-explained.xml -->

## Tempo in diretta

[!DNL TTL] definisce per quanto tempo un visitatore del sito rimane in un segmento dopo l&#39;ultimo evento di qualifica. [!DNL TTL] è impostato sulle caratteristiche e non sui segmenti. I visitatori escono da un segmento se non vedono una caratteristica valida prima della fine [!DNL TTL] dell&#39;intervallo. Il valore predefinito [!DNL TTL] per le nuove caratteristiche è 120 giorni. Se è impostato su 0 giorni, la caratteristica non scade. [Impostate il valore TTL](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) quando create o modificate una caratteristica nella [!UICONTROL Advanced Options] sezione dell&#39;interfaccia di creazione delle caratteristiche.

## [!DNL TTL] e abbandono di un segmento

Un utente esce da un segmento se non visualizza alcuna caratteristica all&#39;interno dell [!DNL TTL] &#39;intervallo. Ad esempio, se hai un segmento a 1 caratteristiche con 30 giorni [!DNL TTL], l&#39;utente abbandona tale segmento se non visualizzano nuovamente la caratteristica entro i 30 giorni.

![](assets/ttl_1.png)

## [!DNL TTL] e rinnovo segmenti

I [!DNL TTL] reset e l&#39;utente rimangono in un segmento, se vedono la caratteristica di quel segmento nel [!DNL TTL] periodo. Inoltre, poiché la maggior parte dei segmenti contiene più caratteristiche con [!DNL TTL] i propri periodi, un utente può restare in un segmento (e reimpostare [!DNL TTL] l&#39;intervallo) purché continuino a visualizzare le caratteristiche associate a un segmento. Ad esempio, supponiamo che il segmento 1 sia composto da Caratteristica A (30 giorno [!DNL TTL]) e Trait B (15 giorno [!DNL TTL]). Se l&#39;utente visualizza ogni caratteristica solo una volta, l&#39;illustrazione seguente indica il [!DNL TTL] processo di rinnovo e la durata totale del segmento.

![](assets/ttl_2.png)

## [!DNL Audience Manager] I TTL sono indipendenti dalle impostazioni TTL di terze parti

Ricorda, il [!DNL TTL] set nel [!DNL Audience Manager] pixel opera indipendentemente dal [!DNL TTL] set su altri pixel utilizzati da terze parti ([!DNL DSP]s, reti pubblicitarie ecc.).

>[!MORE_ LIKE_ THIS]
>
>* [Impostare un intervallo di scadenza](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

