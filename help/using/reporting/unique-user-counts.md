---
description: Descrive la variazione dei totali utente univoci tra i rapporti per la stessa caratteristica e lo stesso periodo di tempo.
seo-description: Descrive la variazione dei totali utente univoci tra i rapporti per la stessa caratteristica e lo stesso periodo di tempo  Adobe Audience Manager
seo-title: Conteggio di utenti univoci in sovrapposizione e rapporti generali in AAM
solution: Audience Manager
title: Counting Unique Users in Overlap and General Reports
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 10%

---


# Counting Unique Users in Overlap and General Reports{#counting-unique-users-in-overlap-and-general-reports}

Questa pagina descrive la variazione dei totali utente univoci tra i rapporti per la stessa caratteristica e lo stesso periodo di tempo.

<!-- 

c_unique_user_counts.xml

 -->

## Report sovrapposizione: Conteggio utenti univoco

I rapporti di sovrapposizione contano gli utenti come univoci quando si qualificano per una caratteristica:

* Durante l&#39;intervallo di tempo selezionato per il report.
* che ha un valore [time-to-live](../features/traits/segment-ttl-explained.md) più lungo dell&#39;intervallo di tempo selezionato per il report.
* Se sono considerati attivi nel nostro sistema (vale a dire qualificati per qualsiasi altro tratto, con sincronizzazione ID, ecc.) negli ultimi 60 giorni.

## Relazione Generale Conteggio utenti univoco

Il rapporto Generale considera univoci i visitatori del sito se si sono qualificati per la caratteristica durante il periodo di tempo selezionato.

>[!MORELIKETHIS]
>
>* [Rapporti interattivi](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapporti generali](../reporting/general-reports.md#general-reports-overview)

