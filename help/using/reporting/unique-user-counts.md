---
description: Descrive la variazione in totali univoci dell'utente tra i rapporti per la stessa caratteristica e il medesimo periodo di tempo.
seo-description: Descrive la variazione in totali univoci dell'utente tra i rapporti per la stessa caratteristica e il periodo di tempo in Adobe Audience Manager
seo-title: Conteggio degli utenti univoci in Sovrapposizione e Rapporti generali in AAM
solution: Audience Manager
title: Conteggio degli utenti univoci in Sovrapposizione e Rapporti generali
uuid: 450 f 6 a 8 c-f 363-43 de-b 2 d 8-0 a 156 f 14 ecae
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Conteggio degli utenti univoci in Sovrapposizione e Rapporti generali{#counting-unique-users-in-overlap-and-general-reports}

Questa pagina descrive la variazione in totali univoci dell&#39;utente tra rapporti per la stessa caratteristica e il medesimo periodo di tempo.

<!-- 

c_unique_user_counts.xml

 -->

## Rapporto di sovrapposizione: Numero di utenti univoci

I rapporti di sovrapposizione contano gli utenti come univoci quando si qualificano per una caratteristica:

* Durante l&#39;intervallo di tempo selezionato per il report.
* Con un valore [time-to-live](../features/traits/segment-ttl-explained.md) più lungo dell&#39;intervallo di tempo selezionato per il report.
* Se sono visibili nel nostro sistema (ovvero, qualificato per qualsiasi altra caratteristica, avevano una sincronizzazione ID, ecc.) negli ultimi 60 giorni.

## Rapporto generale: Numero di utenti univoci

Il rapporto Generale conta i visitatori del sito come univoci se sono idonei per la caratteristica durante il periodo di tempo selezionato.

>[!MORE_ LIKE_ THIS]
>
>* [Rapporti interattivi](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapporti generali](../reporting/general-reports.md#general-reports-overview)

