---
description: Influenza dell’intervallo TTL (time-to-live) delle caratteristiche sull’appartenenza al segmento.
seo-description: Influenza dell’intervallo TTL (time-to-live) delle caratteristiche sull’appartenenza al segmento.
seo-title: Spiegazione della durata di segmenti e caratteristiche
solution: Audience Manager
title: Spiegazione della durata del segmento
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: 'Caratteristiche '
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---

# Spiegazione della durata di segmenti e caratteristiche {#segment-time-to-live-explained}

Influenza dell’intervallo di caratteristiche [!UICONTROL time-to-live] ([!DNL TTL]) sull’appartenenza al segmento.

<!-- segment-ttl-explained.xml -->

## Time to Live

[!DNL TTL] definisce per quanto tempo un visitatore del sito rimane in un segmento dopo l’ultimo evento di qualificazione delle caratteristiche. [!DNL TTL]Il è impostato sulle caratteristiche e non sui segmenti. I visitatori abbandonano un segmento se non si qualificano per una caratteristica prima della fine dell’ [!DNL TTL] intervallo . Il valore predefinito [!DNL TTL] per le nuove caratteristiche è 120 giorni. Se lo imposti su 0 giorni, la caratteristica non scade mai. [Imposta il ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) valore TTL quando crei o modifichi una caratteristica nella  [!UICONTROL Advanced Options] sezione dell’interfaccia di creazione della caratteristica.

### 1 giorno TTL spiegato

Quando si imposta il valore [!DNL TTL] a 1 giorno, il timer TTL inizia il giorno successivo alla realizzazione della caratteristica, senza contare le ore rimaste nel giorno di realizzazione della caratteristica.

Audience Manager calcola la scadenza di [!DNL TTL] per le caratteristiche con 1 giorno [!DNL TTL] in base alla formula seguente:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Esempio 1**: Una caratteristica realizzata all’1:00  [!DNL UTC], con un giorno  [!DNL TTL]. [!DNL TTL] scadrà 24 + 24 - 1 = 47 ore dopo.
* **Esempio 2**: Una caratteristica realizzata alle 23:00  [!DNL UTC], con un giorno  [!DNL TTL]. [!DNL TTL] scadrà 24 + 24 - 23 = 25 ore dopo.

## [!DNL TTL] e uscire da un segmento

Un utente esce da un segmento se non è idoneo per nessuna delle sue caratteristiche entro l’ intervallo [!DNL TTL] . Ad esempio, se disponi di un segmento con 1 caratteristica con 30 giorni [!DNL TTL], l’utente abbandonerà tale segmento se non si qualifica nuovamente per la caratteristica entro i successivi 30 giorni.

![](assets/ttl-explained.png)

## [!DNL TTL] e rinnovo dei segmenti

Il [!DNL TTL] viene reimpostato e l’utente rimane in un segmento, se si qualifica per la caratteristica di quel segmento entro il [!DNL TTL] periodo. Inoltre, poiché la maggior parte dei segmenti contiene più caratteristiche con i propri [!DNL TTL] intervalli, un utente può rimanere in un segmento e reimpostare l’ [!DNL TTL] intervallo, purché continui a qualificarsi per eventuali caratteristiche associate al segmento.

Ad esempio, supponiamo che il segmento 1 sia composto dalla caratteristica A (30 giorni [!DNL TTL]) e dalla caratteristica B (15 giorni [!DNL TTL]). Supponendo che un visitatore sia idoneo per ogni caratteristica una sola volta, l’illustrazione seguente illustra il processo di [!DNL TTL] rinnovo e la durata totale nel segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] I TTL sono indipendenti dalle impostazioni TTL di terze parti

Ricorda che il [!DNL TTL] impostato sul pixel [!DNL Audience Manager] funziona indipendentemente dal [!DNL TTL] impostato sugli altri pixel utilizzati da terze parti ([!DNL DSP]s, reti di annunci, ecc.).

>[!MORELIKETHIS]
>
>* [Impostare un intervallo di scadenza delle caratteristiche](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

