---
description: La pagina dei dettagli per una singola caratteristica fornisce una panoramica di informazioni come il nome delle caratteristiche, l'ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di audit delle caratteristiche. Per richiamare questi dettagli, vai a Dati audience > Caratteristiche e fai clic sul nome della caratteristica con cui vuoi lavorare.
seo-description: La pagina dei dettagli per una singola caratteristica fornisce una panoramica di informazioni come il nome delle caratteristiche, l'ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di audit delle caratteristiche. Per richiamare questi dettagli, vai a Dati audience > Caratteristiche e fai clic sul nome della caratteristica con cui vuoi lavorare.
seo-title: Pagina dettagli caratteristica
solution: Audience Manager
title: Pagina dettagli caratteristica
uuid: 23301376-c 1 cc -4778-b 8 c 4-9831 f 6739 db 9
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Trait Details Page {#trait-details-page}

La pagina dei dettagli per una singola caratteristica fornisce una panoramica di informazioni come il nome delle caratteristiche, l'ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di audit delle caratteristiche. To vew these details, go to [!UICONTROL Audience Data > Traits] and click the name of the trait you want to work with.

## Informazioni di base {#basics}

The [!UICONTROL Basic Information] section shows details about required and optional fields you completed when building the trait. Ciò include elementi quali tipo caratteristica, ID caratteristica, descrizione, origine dati e altri metadati. Tali dettagli variano a seconda del tipo di caratteristica (cartella, registrazione o regola basata su regola).

![](assets/basicInfo.png)

## Trait Graph {#trait-graph}

The [!UICONTROL Trait Graph] provides at-a-glance performance metrics for your selected trait. Portate il cursore su una linea di tendenze per visualizzare ulteriori dati per la caratteristica selezionata.

[!UICONTROL Unique Trait Realizations] rappresenta un numero di utenti univoci che hanno aggiunto questa caratteristica al proprio profilo su un determinato intervallo di tempo. The [!UICONTROL Total Trait Population] indicates the number of unique users currently qualified for this trait.

* Per caratteristiche basate su regole, la qualifica caratteristica avviene in tempo reale, in quanto gli utenti si qualificano per una caratteristica nel browser.
* For onboarded traits, trait qualification happens after an inbound file is processed, i.e. the inbound file is [fed into Audience Manager](../../faq/faq-inbound-data-ingestion.md) and that is when the trait qualification happens.
* **Rappresentazione caratteristica univoca**: Un numero di utenti univoci che hanno aggiunto questa caratteristica al proprio profilo su un determinato intervallo di tempo.
* **Popolazione caratteristica totale**: Il numero di utenti univoci attualmente qualificati per questa caratteristica.

![](assets/traitGraph.png)

## Trait Expression {#trait-expression}

The [!UICONTROL Trait Expression] section shows you the criteria users must meet to qualify for the trait. These rules are set when you [create or edit a trait](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Trait Segments {#trait-segments}

The [!UICONTROL Segments with this Trait] section lists all the segments the selected trait belongs to. Puoi fare clic sul nome di un segmento per visualizzare i dettagli su tale segmento.

![](assets/traitSegments.png)

## Trait Audit/History Log {#trait-audit-history}

For rule-based and onboarded traits, the [!UICONTROL Trait Expression Change History] shows you the last 10 changes made to trait expression rules and who made them. If your trait has more than 10 changes, click **[!UICONTROL Export to CSV]** to download the entire audit log. Il registro di controllo non è disponibile per le caratteristiche della cartella o algoritmica.

>[!NOTE]
>
>[!UICONTROL Not Available] nella [!UICONTROL By User] colonna indica che l'account per quell'utente è stato eliminato.

![](assets/traitHistory.png)