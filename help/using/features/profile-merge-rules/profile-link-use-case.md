---
description: Recommendations e casi d’uso per il retargeting dei segmenti e la qualificazione personalizzata dei segmenti con il grafico del dispositivo Collegamento profilo.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Casi di utilizzo del grafico dei dispositivi di collegamento dei profili
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 8%

---

# Casi di utilizzo del grafico dei dispositivi di collegamento dei profili {#profile-link-device-graph-use-cases}

Recommendations e casi d’uso per il retargeting dei segmenti e la qualificazione personalizzata dei segmenti con [!UICONTROL Profile Link Device Graph].

## Consigli {#recommendations}

Considera [!UICONTROL Profile Link] grafico dei dispositivi per campagne che:

* Hanno un elevato livello di autenticazione nelle loro proprietà digitali. Utilizza un [opzione grafico dei dispositivi esterno](merge-rule-definitions.md#device-options) se si dispone di una piccola quantità di utenti autenticati.
* Richiede un targeting accurato dei tipi di pubblico noti. Il [!UICONTROL Profile Link Device Graph] viene creato utilizzando dati autenticati di prime parti.
* Puoi indirizzare in tempo reale i tipi di pubblico noti ai diversi stati di autenticazione e non autenticazione.

![](assets/merge-rule-triangle2.png)

## Targeting tra dispositivi {#cross-device-personalization}

Supponiamo che John possieda tre dispositivi che utilizza regolarmente per cercare offerte di pacchetti per le vacanze: il suo laptop ([!DNL Device 1]), il suo smartphone ([!DNL Device 2]) e la sua tavoletta ([!DNL Device 3]). Tuttavia, John utilizza i suoi dispositivi per cercare diversi elementi delle offerte dei pacchetti:

* Utilizza il suo laptop per cercare voli;
* Usa il suo smartphone per cercare hotel;
* Usa il suo tablet per cercare visite guidate.

Anche se John non è autenticato su tutti e tre i dispositivi indicati sopra, utilizzando **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** regola, un provider di pacchetti vacanza può associare questi dispositivi al profilo autenticato di John, supponendo che sia stato l’ultima persona ad eseguire l’autenticazione su tutti e tre i dispositivi.

![last-device-graph](assets/last-device-graph.png)

Poiché Audience Manager qualifica per un segmento tutti i profili dispositivo che hanno preso parte all’unione profili, tutti e tre i profili dispositivo vengono segmentati. Il [!UICONTROL Profile Link Device Graph] consente ad Audience Manager di esaminare il comportamento tra tutti e tre i dispositivi e qualificare ogni dispositivo per un segmento per il quale nessun singolo profilo dispositivo si qualifica da solo.

Questo [!UICONTROL Profile Merge Rule] consente agli addetti al marketing di fornire un’esperienza coerente a tutti i dispositivi di proprietà di una sola persona, in base all’attività dell’utente anziché alla singola attività del dispositivo.

![cross-device-personalization](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Casi d’uso del grafico dei dispositivi esterno](external-graph-use-cases.md)
>* [Casi d’uso generali per le regole di unione profili](merge-rule-targeting-options.md)
>* [Domande frequenti sulle regole di unione profili](../../faq/faq-profile-merge.md)

