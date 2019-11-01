---
description: Raccomandazioni e casi d’uso per il retargeting dei segmenti e la qualifica dei segmenti personalizzati con il grafico del dispositivo Collegamento profilo.
seo-description: Raccomandazioni e casi d’uso per il retargeting dei segmenti e la qualifica dei segmenti personalizzati con il grafico del dispositivo Collegamento profilo.
seo-title: Casi di utilizzo del grafico dei collegamenti profilo
solution: Audience Manager
title: Casi di utilizzo del grafico dei collegamenti profilo
uuid: bd5567fd-fcd5-40ba-b6f1-035d2dbcd3a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Casi di utilizzo del grafico dei collegamenti profilo {#profile-link-device-graph-use-cases}

Raccomandazioni e casi d’uso per il retargeting dei segmenti e la qualificazione dei segmenti personalizzati con l’ [!UICONTROL Profile Link Device Graph].

## Consigli {#recommendations}

Considerate il grafico del [!UICONTROL Profile Link] dispositivo per le campagne che:

* Avere un livello elevato di autenticazione nelle loro proprietà digitali. Utilizzate un'opzione [per grafico dispositivi](merge-rule-definitions.md#device-options) esterni se disponete di una piccola quantità di utenti autenticati.
* Richiedi un targeting accurato delle audience note. Il modulo [!UICONTROL Profile Link Device Graph] viene creato utilizzando dati autenticati di prime parti.
* Esegue il targeting in tempo reale dei tipi di pubblico noti per i rispettivi stati di autenticazione e non autenticazione.

![](assets/merge-rule-triangle2.png)

## Targeting tra dispositivi {#cross-device-personalization}

Diciamo che John possiede tre dispositivi che usa regolarmente per cercare offerte pacchetto vacanze: il suo portatile ([!DNL Device 1]), il suo smartphone ([!DNL Device 2]) e il suo tablet ([!DNL Device 3]). Tuttavia, John utilizza i suoi dispositivi per cercare diversi elementi delle offerte pacchetto:

* Utilizza il suo laptop per cercare i voli;
* Utilizza il suo smartphone per cercare gli hotel;
* Utilizza il suo tablet per cercare visite guidate.

Anche se John non è autenticato su tutti e tre i dispositivi sopra menzionati, utilizzando la regola **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** , un provider di pacchetti vacanze può associare questi dispositivi al profilo autenticato di John, supponendo che sia stato l'ultima persona ad autenticarsi su tutti e tre i dispositivi.

![last-device-graph](assets/last-device-graph.png)

Poiché Audience Manager qualifica ogni profilo dispositivo che ha partecipato all'unione del profilo per un segmento, tutti e tre i profili dispositivo sono segmentati. In [!UICONTROL Profile Link Device Graph] questo modo Audience Manager può esaminare il comportamento tra tutti e tre i dispositivi e classificare ogni dispositivo per un segmento per il quale nessun profilo dispositivo può essere qualificato autonomamente.

Questo [!UICONTROL Profile Merge Rule] consente agli esperti di marketing di fornire un'esperienza coerente a tutti i dispositivi di proprietà di una persona, in base all'attività dell'utente invece che alla singola attività del dispositivo.

![personalizzazione tra dispositivi](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Casi d'uso dei grafici dei dispositivi esterni](external-graph-use-cases.md)
>* [Casi di utilizzo generali per le regole di unione dei profili](merge-rule-targeting-options.md)
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

