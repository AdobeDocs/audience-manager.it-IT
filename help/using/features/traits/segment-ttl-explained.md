---
description: L’intervallo TTL (Trait time-to-live) ha effetto sull’appartenenza al segmento.
seo-description: L’intervallo TTL (Trait time-to-live) ha effetto sull’appartenenza al segmento.
seo-title: Segmento e tempo di caratteristiche per vivere spiegati
solution: Audience Manager
title: Tempo segmento per vivere spiegato
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Spiegazione dei tempi di trasmissione e delle caratteristiche {#segment-time-to-live-explained}

L’intervallo di caratteristiche [!UICONTROL time-to-live] ([!DNL TTL]) influisce sull’appartenenza al segmento.

<!-- segment-ttl-explained.xml -->

## Tempo di vita

[!DNL TTL] Definisce per quanto tempo un visitatore del sito rimane in un segmento dopo l’ultimo evento di qualificazione delle caratteristiche. [!DNL TTL] è impostato sulle caratteristiche e non sui segmenti. I visitatori non rientrano in un segmento se non vedono una caratteristica valida prima della fine dell' [!DNL TTL] intervallo. Il valore predefinito [!DNL TTL] per le nuove caratteristiche è 120 giorni. Se è impostata su 0 giorni, la caratteristica non scade mai. [Impostate il valore](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) TTL quando create o modificate una caratteristica nella [!UICONTROL Advanced Options] sezione dell’interfaccia di creazione delle caratteristiche.

## [!DNL TTL] e per uscire da un segmento

Un utente esce da un segmento se non ne vede alcuna caratteristica all'interno dell' [!DNL TTL] intervallo. Ad esempio, se hai un segmento con 1 caratteristica con 30 giorni [!DNL TTL], l’utente lascerà il segmento se non visualizza nuovamente la caratteristica entro 30 giorni.

![](assets/ttl_1.png)

## [!DNL TTL] e rinnovo dei segmenti

Se visualizzano la caratteristica di quel segmento nel [!DNL TTL] [!DNL TTL] periodo, l’utente viene reimpostato e resta in un segmento. Inoltre, poiché la maggior parte dei segmenti contiene più caratteristiche con [!DNL TTL] periodi specifici, un utente può restare in un segmento (e reimpostare l’ [!DNL TTL] intervallo) purché continui a visualizzare eventuali caratteristiche associate a un segmento. Ad esempio, supponiamo che il segmento 1 sia composto dalla caratteristica A (30 giorni [!DNL TTL]) e dalla caratteristica B (15 giorni [!DNL TTL]). Se l'utente visualizza ogni caratteristica solo una volta, l'illustrazione seguente delinea il processo di [!DNL TTL] rinnovo e la durata totale del segmento.

![](assets/ttl_2.png)

## [!DNL Audience Manager] TTL sono indipendenti dalle impostazioni TTL di terze parti

Il [!DNL TTL] set sul [!DNL Audience Manager] pixel funziona indipendentemente dal [!DNL TTL] set sugli altri pixel utilizzati da terze parti ([!DNL DSP]s, ad network, ecc.).

>[!MORE_LIKE_this]
>
>* [Imposta un intervallo di scadenza caratteristica](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

