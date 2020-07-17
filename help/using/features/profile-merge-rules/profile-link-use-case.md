---
description: Raccomandazioni e casi d’uso per il retargeting dei segmenti e la qualifica dei segmenti personalizzati con il grafico del dispositivo Collegamento profilo.
seo-description: Raccomandazioni e casi d’uso per il retargeting dei segmenti e la qualifica dei segmenti personalizzati con il grafico del dispositivo Collegamento profilo.
seo-title: Casi di utilizzo del grafico dei dispositivi di collegamento dei profili
solution: Audience Manager
title: Casi di utilizzo del grafico dei dispositivi di collegamento dei profili
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 9%

---


# Casi di utilizzo del grafico dei dispositivi di collegamento dei profili {#profile-link-device-graph-use-cases}

Raccomandazioni e casi d’uso per il retargeting dei segmenti e la qualificazione dei segmenti personalizzati con l’ [!UICONTROL Profile Link Device Graph].

## Consigli {#recommendations}

Considerate il grafico del [!UICONTROL Profile Link] dispositivo per le campagne che:

* Avere un livello elevato di autenticazione nelle loro proprietà digitali. Utilizzate un&#39;opzione [per il grafico dei dispositivi](merge-rule-definitions.md#device-options) esterni se disponete di una piccola quantità di utenti autenticati.
* Richiedi un targeting accurato dei tipi di pubblico noti. Il modulo [!UICONTROL Profile Link Device Graph] viene creato utilizzando dati autenticati di prime parti.
* Audiences noti di Target nei rispettivi stati di autenticazione e non autenticazione in tempo reale.

![](assets/merge-rule-triangle2.png)

## Targeting tra dispositivi {#cross-device-personalization}

Diciamo che John possiede tre dispositivi che usa regolarmente per cercare offerte pacchetto vacanze: il suo portatile ([!DNL Device 1]), il suo smartphone ([!DNL Device 2]) e il suo tablet ([!DNL Device 3]). Tuttavia, John utilizza i suoi dispositivi per cercare diversi elementi delle offerte pacchetto:

* Utilizza il suo computer portatile per cercare i voli;
* Utilizza il suo smartphone per cercare gli alberghi;
* Utilizza il suo tablet per cercare visite guidate.

Anche se John non è autenticato su tutti e tre i dispositivi sopra menzionati, utilizzando la regola **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** , un provider di pacchetti vacanze può associare questi dispositivi al profilo autenticato di John, supponendo che sia stato l&#39;ultima persona ad autenticarsi su tutti e tre i dispositivi.

![last-device-graph](assets/last-device-graph.png)

Poiché  Audience Manager qualifica ogni profilo dispositivo che ha partecipato all&#39;unione del profilo per un segmento, tutti e tre i profili dispositivo sono segmentati. La funzione [!UICONTROL Profile Link Device Graph] consente  Audience Manager di esaminare il comportamento tra tutti e tre i dispositivi e di qualificare ogni dispositivo per un segmento per il quale nessun profilo dispositivo può essere qualificato autonomamente.

Questo [!UICONTROL Profile Merge Rule] consente agli esperti di marketing di fornire un&#39;esperienza coerente a tutti i dispositivi di proprietà di una persona, in base all&#39;attività dell&#39;utente invece che alla singola attività del dispositivo.

![personalizzazione tra dispositivi](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Casi d’uso del grafico dei dispositivi esterno](external-graph-use-cases.md)
>* [Casi d’uso generali per le regole di unione profili](merge-rule-targeting-options.md)
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

