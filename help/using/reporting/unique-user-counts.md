---
description: Descrive la variazione nei totali utente univoci tra i rapporti per la stessa caratteristica e per lo stesso periodo di tempo.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Conteggio degli utenti univoci nei report di sovrapposizione e generali
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '142'
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
