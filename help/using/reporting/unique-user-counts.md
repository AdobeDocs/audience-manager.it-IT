---
description: Descrive la variazione dei totali utente univoci tra i rapporti per la stessa caratteristica e lo stesso periodo di tempo.
seo-description: Descrive la variazione dei totali utente univoci tra i rapporti per la stessa caratteristica e lo stesso periodo di tempo in Adobe Audience Manager
seo-title: Conteggio degli utenti univoci nei report di sovrapposizione e generali in AAM
solution: Audience Manager
title: Conteggio degli utenti univoci nei report di sovrapposizione e generali
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Riferimento per la generazione di rapporti
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# Counting Unique Users in Overlap and General Reports{#counting-unique-users-in-overlap-and-general-reports}

Questa pagina descrive la variazione dei totali utente univoci tra i rapporti per la stessa caratteristica e lo stesso periodo di tempo.

<!-- 

c_unique_user_counts.xml

 -->

## Rapporto di sovrapposizione: Conteggio utenti univoci

I rapporti di sovrapposizione contano gli utenti come univoci quando si qualificano per una caratteristica:

* Durante l&#39;intervallo di tempo selezionato per il rapporto.
* Questo ha un valore [time-to-live](../features/traits/segment-ttl-explained.md) più lungo dell&#39;intervallo di tempo selezionato per il rapporto.
* Se sono visti come attivi nel nostro sistema (vale a dire qualificati per qualsiasi altra caratteristica, avevano una sincronizzazione ID, ecc.) negli ultimi 60 giorni.

## Relazione generale Conteggio utenti univoci

Il rapporto Generale considera univoci i visitatori del sito se si sono qualificati per la caratteristica durante il periodo di tempo selezionato.

>[!MORELIKETHIS]
>
>* [Rapporti interattivi](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapporti generali](../reporting/general-reports.md#general-reports-overview)

