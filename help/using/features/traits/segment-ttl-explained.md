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
source-wordcount: '354'
ht-degree: 3%

---

# Spiegazione della durata di segmenti e caratteristiche {#segment-time-to-live-explained}

Quanta caratteristica [!UICONTROL time-to-live] ([!DNL TTL]) influisce sull’iscrizione al segmento.

<!-- segment-ttl-explained.xml -->

## Time to Live

[!DNL TTL] definisce per quanto tempo un visitatore del sito rimane in un segmento dopo l’ultimo evento di qualificazione delle caratteristiche. [!DNL TTL]Il è impostato sulle caratteristiche e non sui segmenti. I visitatori non rientrano in un segmento se non sono idonei per una caratteristica prima della fine del [!DNL TTL] intervallo. Il valore predefinito [!DNL TTL] per le nuove caratteristiche è di 120 giorni. Se impostata su 0 giorni, la caratteristica non scade mai. [Imposta il valore TTL](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) quando si crea o si modifica una caratteristica in [!UICONTROL Advanced Options] sezione dell’interfaccia per la creazione di caratteristiche.

### Spiegazione TTL di 1 giorno

Quando si imposta [!DNL TTL] a 1 giorno, il timer TTL inizia il giorno successivo alla realizzazione della caratteristica, senza contare le ore rimaste nel giorno di realizzazione della caratteristica.

Calcoli Audience Manager [!DNL TTL] scadenza per le caratteristiche con 1 giorno [!DNL TTL] in base alla formula seguente:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Esempio 1**: caratteristica realizzata all’1:00 [!DNL UTC], con un giorno [!DNL TTL]. [!DNL TTL] scadrà 24 + 24 - 1 = 47 ore dopo.
* **Esempio 2**: caratteristica realizzata alle 23:00 [!DNL UTC], con un giorno [!DNL TTL]. [!DNL TTL] scadrà 24 + 24 - 23 = 25 ore dopo.

## [!DNL TTL] e Abbandono di un segmento

Un utente esce da un segmento se non si qualifica per nessuna delle sue caratteristiche all’interno del [!DNL TTL] intervallo. Ad esempio, per un segmento con 1 caratteristica con 30 giorni [!DNL TTL], l’utente abbandonerà quel segmento se non si qualifica di nuovo per la caratteristica entro i successivi 30 giorni.

![](assets/ttl-explained.png)

## [!DNL TTL] e rinnovo del segmento

Il [!DNL TTL] reimposta e l’utente rimane in un segmento, se si qualifica per la caratteristica di quel segmento all’interno del [!DNL TTL] punto. Inoltre, perché la maggior parte dei segmenti contiene più caratteristiche con le proprie [!DNL TTL] intervalli, un utente può rimanere in un segmento e reimpostare il [!DNL TTL] purché continuino a qualificarsi per le caratteristiche associate al segmento.

Ad esempio, supponiamo che il segmento 1 sia composto dalla caratteristica A (30 giorni [!DNL TTL]) e caratteristica B (15 giorni [!DNL TTL]). Supponendo che un visitatore sia idoneo per ciascuna caratteristica una sola volta, l’illustrazione seguente delinea la [!DNL TTL] processo di rinnovo e durata totale nel segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] I TTL sono indipendenti dalle impostazioni TTL di terze parti

Ricorda, il [!DNL TTL] impostato su [!DNL Audience Manager] pixel funziona in modo indipendente dall&#39;unità [!DNL TTL] impostato su altri pixel utilizzati da terze parti ([!DNL DSP]s, ad networks, ecc.).

>[!MORELIKETHIS]
>
>* [Impostare un intervallo di scadenza delle caratteristiche](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

