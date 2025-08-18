---
description: Come l’intervallo TTL (time-to-live) delle caratteristiche influisce sull’appartenenza ai segmenti.
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: Spiegazione del time-to-live del segmento
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Spiegazione della durata di segmenti e caratteristiche {#segment-time-to-live-explained}

Modalità di influenza dell&#39;intervallo [!UICONTROL time-to-live] ([!DNL TTL]) sull&#39;appartenenza ai segmenti.

<!-- segment-ttl-explained.xml -->

## Time to Live

[!DNL TTL] definisce per quanto tempo un visitatore del sito rimane in un segmento dopo l&#39;ultimo evento di qualificazione delle caratteristiche. [!DNL TTL] è impostato sulle caratteristiche e non sui segmenti. I visitatori non rientrano in un segmento se non sono idonei per una caratteristica prima della fine dell&#39;intervallo [!DNL TTL]. Il valore predefinito [!DNL TTL] per le nuove caratteristiche è 120 giorni. Se impostata su 0 giorni, la caratteristica non scade mai. [Imposta il valore TTL](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) quando crei o modifichi una caratteristica nella sezione [!UICONTROL Advanced Options] dell&#39;interfaccia di creazione caratteristica.

### Spiegazione TTL di 1 giorno

Quando si imposta [!DNL TTL] su 1 giorno, il timer TTL inizia il giorno successivo alla realizzazione della caratteristica, senza contare le ore rimaste nel giorno di realizzazione della caratteristica.

Audience Manager calcola la scadenza di [!DNL TTL] per le caratteristiche con 1 giorno [!DNL TTL] in base alla formula seguente:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Esempio 1**: caratteristica realizzata a 1:00 [!DNL UTC], con un giorno [!DNL TTL]. [!DNL TTL] scadrà 24 + 24 - 1 = 47 ore dopo.
* **Esempio 2**: una caratteristica realizzata in 23:00 [!DNL UTC], con un giorno [!DNL TTL]. [!DNL TTL] scadrà 24 + 24 - 23 = 25 ore dopo.

## [!DNL TTL] ed eliminazione di un segmento

Un utente esce da un segmento se non si qualifica per nessuna delle sue caratteristiche entro l&#39;intervallo [!DNL TTL]. Ad esempio, se hai un segmento con 1 caratteristica e 30 giorni [!DNL TTL], l&#39;utente lo abbandonerà se non è più idoneo per la caratteristica entro i successivi 30 giorni.

![](assets/ttl-explained.png)

## [!DNL TTL] e rinnovo del segmento

[!DNL TTL] si ripristina e l&#39;utente rimane in un segmento, se si qualifica per la caratteristica di quel segmento entro il periodo [!DNL TTL]. Inoltre, poiché la maggior parte dei segmenti contiene più caratteristiche con i propri intervalli di [!DNL TTL], un utente può rimanere in un segmento e reimpostare l&#39;intervallo di [!DNL TTL], purché continui a qualificarsi per qualsiasi caratteristica associata al segmento.

Ad esempio, supponiamo che tu abbia il segmento 1 composto dalla caratteristica A (30 giorni [!DNL TTL]) e dalla caratteristica B (15 giorni [!DNL TTL]). Supponendo che un visitatore sia idoneo per ogni caratteristica una sola volta, l&#39;illustrazione seguente delinea il processo di rinnovo [!DNL TTL] e la durata totale all&#39;interno del segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL sono indipendenti dalle impostazioni TTL di terze parti

Ricorda che il [!DNL TTL] impostato sul pixel [!DNL Audience Manager] funziona in modo indipendente dal [!DNL TTL] impostato su altri pixel utilizzati da terze parti ([!DNL DSP], reti pubblicitarie, ecc.).

>[!MORELIKETHIS]
>
>* [Imposta un intervallo di scadenza caratteristica](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)
