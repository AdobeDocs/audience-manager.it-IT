---
description: L’intervallo TTL (Trait time-to-live) ha effetto sull’appartenenza al segmento.
seo-description: L’intervallo TTL (Trait time-to-live) ha effetto sull’appartenenza al segmento.
seo-title: Segmento e tempo di caratteristiche per vivere spiegati
solution: Audience Manager
title: Tempo segmento per vivere spiegato
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 3%

---


# Spiegazione della durata di segmenti e caratteristiche {#segment-time-to-live-explained}

L’intervallo di caratteristiche [!UICONTROL time-to-live] ([!DNL TTL]) influisce sull’appartenenza al segmento.

<!-- segment-ttl-explained.xml -->

## Tempo di vita

[!DNL TTL] Definisce per quanto tempo un visitatore del sito rimane in un segmento dopo l’ultimo evento di qualificazione delle caratteristiche. [!DNL TTL]Il è impostato sulle caratteristiche e non sui segmenti. Visitors fall out of a segment if they do not qualify for a trait before the end of the [!DNL TTL] interval. Il valore predefinito [!DNL TTL] per le nuove caratteristiche è 120 giorni. Se è impostata su 0 giorni, la caratteristica non scade mai. [Impostate il valore](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) TTL quando create o modificate una caratteristica nella [!UICONTROL Advanced Options] sezione dell’interfaccia di creazione delle caratteristiche.

### 1 giorno TTL spiegato

Quando si imposta [!DNL TTL] su 1 giorno, il timer TTL inizia il giorno successivo alla realizzazione della caratteristica, senza contare le ore rimanenti nel giorno di realizzazione della caratteristica.

 Audience Manager calcola [!DNL TTL] la scadenza per le caratteristiche con 1 giorno [!DNL TTL] in base alla seguente formula:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Esempio 1**: Un tratto realizzato all&#39;1:00 [!DNL UTC], con 1 giorno [!DNL TTL]. [!DNL TTL] scadrà 24 + 24 - 1 = 47 ore dopo.
* **Esempio 2**: Un tratto realizzato alle 23:00 [!DNL UTC], con 1 giorno [!DNL TTL]. [!DNL TTL] Scadrà 24 + 24 - 23 = 25 ore dopo.

## [!DNL TTL] e per uscire da un segmento

Un utente esce da un segmento se non è idoneo per nessuna delle sue caratteristiche entro l’ [!DNL TTL] intervallo. Ad esempio, se hai un segmento con 1 caratteristica con 30 giorni [!DNL TTL], l’utente lascerà il segmento se non è più idoneo per la caratteristica entro i 30 giorni successivi.

![](assets/ttl-explained.png)

## [!DNL TTL] e rinnovo dei segmenti

Il [!DNL TTL] ripristino, e l&#39;utente resta in un segmento, se soddisfa le caratteristiche di quel segmento entro il [!DNL TTL] periodo. Inoltre, poiché la maggior parte dei segmenti contiene caratteristiche multiple con [!DNL TTL] intervalli propri, un utente può restare in un segmento e reimpostare l’ [!DNL TTL] intervallo, purché mantengano le caratteristiche idonee per qualsiasi caratteristica associata al segmento.

Ad esempio, supponiamo che il segmento 1 sia composto dalla caratteristica A (30 giorni [!DNL TTL]) e dalla caratteristica B (15 giorni [!DNL TTL]). Se un visitatore si qualifica per ogni caratteristica solo una volta, l&#39;illustrazione seguente delinea il processo di [!DNL TTL] rinnovo e la durata totale del segmento.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL sono indipendenti dalle impostazioni TTL di terze parti

Il [!DNL TTL] set sul [!DNL Audience Manager] pixel funziona indipendentemente dal [!DNL TTL] set sugli altri pixel utilizzati da terze parti ([!DNL DSP]s, ad network, ecc.).

>[!MORELIKETHIS]
>
>* [Imposta un intervallo di scadenza caratteristica](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

