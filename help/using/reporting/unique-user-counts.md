---
description: Descrive la variazione dei totali utente univoci tra i rapporti per la stessa caratteristica e lo stesso periodo di tempo.
seo-description: Descrive la variazione dei totali utente univoci tra i rapporti per la stessa caratteristica e lo stesso periodo di tempo in Adobe Audience Manager
seo-title: Conteggio di utenti univoci in sovrapposizione e rapporti generali in AAM
solution: Audience Manager
title: Conteggio di utenti univoci in sovrapposizione e rapporti generali
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Conteggio di utenti univoci in sovrapposizione e rapporti generali{#counting-unique-users-in-overlap-and-general-reports}

Questa pagina descrive la variazione dei totali utente univoci tra i rapporti per la stessa caratteristica e lo stesso periodo di tempo.

<!-- 

c_unique_user_counts.xml

 -->

## Report sovrapposizione: Conteggio utenti univoco

I rapporti di sovrapposizione contano gli utenti come univoci quando si qualificano per una caratteristica:

* Durante l'intervallo di tempo selezionato per il report.
* che ha un valore [time-to-live](../features/traits/segment-ttl-explained.md) maggiore dell'intervallo di tempo selezionato per il report.
* Se sono considerati attivi nel nostro sistema (vale a dire qualificati per qualsiasi altro tratto, con sincronizzazione ID, ecc.) negli ultimi 60 giorni.

## Relazione Generale Conteggio utenti univoco

Il rapporto Generale considera univoci i visitatori del sito se si sono qualificati per la caratteristica nel periodo di tempo selezionato.

>[!MORELIKETHIS]
>
>* [Rapporti interattivi](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapporti generali](../reporting/general-reports.md#general-reports-overview)

