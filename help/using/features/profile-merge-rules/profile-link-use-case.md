---
description: Recommendations e casi d’uso per il retargeting dei segmenti e la qualificazione dei segmenti personalizzati con il grafico del dispositivo Collegamento profilo .
seo-description: Recommendations e casi d’uso per il retargeting dei segmenti e la qualificazione dei segmenti personalizzati con il grafico del dispositivo Collegamento profilo .
seo-title: Casi di utilizzo del grafico dei dispositivi di collegamento dei profili
solution: Audience Manager
title: Casi di utilizzo del grafico dei dispositivi di collegamento dei profili
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Unione profili
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 9%

---

# Casi di utilizzo del grafico dei dispositivi di collegamento dei profili {#profile-link-device-graph-use-cases}

Recommendations e casi d’uso per il retargeting dei segmenti e la qualificazione dei segmenti personalizzati con [!UICONTROL Profile Link Device Graph].

## Consigli {#recommendations}

Considera il grafico dei dispositivi [!UICONTROL Profile Link] per le campagne che:

* Avere un alto livello di autenticazione nelle loro proprietà digitali. Utilizza un&#39;opzione [grafico dei dispositivi esterno](merge-rule-definitions.md#device-options) se disponi di una piccola quantità di utenti autenticati.
* Richiedi un targeting accurato dei tipi di pubblico noti. Il [!UICONTROL Profile Link Device Graph] viene generato utilizzando dati di prime parti autenticati.
* Esegui il targeting in tempo reale dei tipi di pubblico noti nei loro stati di autenticazione e non autenticata.

![](assets/merge-rule-triangle2.png)

## Targeting tra dispositivi {#cross-device-personalization}

Supponiamo che John possieda tre dispositivi che utilizza regolarmente per cercare offerte di pacchetti vacanza: il suo laptop ([!DNL Device 1]), il suo smartphone ([!DNL Device 2]) e il suo tablet ([!DNL Device 3]). Tuttavia, John utilizza i suoi dispositivi per cercare diversi elementi del pacchetto offerte:

* Usa il suo portatile per cercare voli;
* Usa il suo smartphone per cercare gli alberghi;
* Usa il suo tablet per cercare visite guidate.

Anche se John non è autenticato su tutti e tre i dispositivi sopra menzionati, utilizzando la regola **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**, un provider di pacchetti vacanze può associare questi dispositivi al profilo autenticato di John, partendo dal presupposto che sia stato l&#39;ultima persona ad autenticarsi su tutti e tre i dispositivi.

![ultimo grafico a dispositivi](assets/last-device-graph.png)

Poiché Audience Manager qualifica ogni profilo dispositivo che ha preso parte all’unione dei profili per un segmento, tutti e tre i profili dispositivo sono segmentati. Il [!UICONTROL Profile Link Device Graph] consente ad Audience Manager di esaminare il comportamento in tutti e tre i dispositivi e di qualificare ogni dispositivo per un segmento per il quale nessun singolo profilo dispositivo è idoneo da solo.

Questo [!UICONTROL Profile Merge Rule] consente agli addetti al marketing di fornire un’esperienza coerente a tutti i dispositivi di proprietà di una persona, in base all’attività dell’utente invece che alla singola attività del dispositivo.

![personalizzazione tra dispositivi](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Casi d’uso del grafico dei dispositivi esterno](external-graph-use-cases.md)
* [Casi d’uso generali per le regole di unione profili](merge-rule-targeting-options.md)
* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

