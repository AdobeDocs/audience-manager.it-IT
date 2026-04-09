---
description: Descrive la variazione nei totali utente univoci tra i rapporti per la stessa caratteristica e per lo stesso periodo di tempo.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Conteggio degli utenti univoci nei report di sovrapposizione e generali
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
TQID: https://experienceleague.adobe.com/zQamEx1r5buK4Q4FN-meT3l-8-j3f9Q5Kw2RtO0iPQ8
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 1%

---

# Conteggio degli utenti univoci nei report di sovrapposizione e generali{#counting-unique-users-in-overlap-and-general-reports}

Questa pagina descrive la variazione nei totali utente univoci tra i rapporti per la stessa caratteristica e per lo stesso periodo di tempo.

<!-- 

c_unique_user_counts.xml

 -->

## Rapporto di sovrapposizione: conteggio utenti univoci

I rapporti di sovrapposizione contano gli utenti come univoci quando sono idonei per una caratteristica:

* Durante l’intervallo di tempo selezionato per il rapporto.
* Con un valore di [durata](../features/traits/segment-ttl-explained.md) superiore all&#39;intervallo di tempo selezionato per il report.
* Se vengono considerate attive nel nostro sistema (vale a dire qualificate per qualsiasi altra caratteristica, con sincronizzazione ID, ecc.) negli ultimi 60 giorni.

## Rapporto generale: conteggio utenti univoci

Il rapporto Generale considera i visitatori del sito come univoci se sono qualificati per la caratteristica durante il periodo di tempo selezionato.

>[!MORELIKETHIS]
>
>* [Rapporti interattivi](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapporti generali](../reporting/general-reports.md#general-reports-overview)
