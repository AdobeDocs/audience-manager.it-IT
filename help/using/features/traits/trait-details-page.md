---
description: La pagina dei dettagli di una caratteristica specifica fornisce una panoramica delle informazioni come il nome della caratteristica, l’ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di controllo delle caratteristiche. Per visualizzare questi dettagli, vai Dati pubblico > Caratteristiche e fai clic sul nome della caratteristica con cui vuoi lavorare.
seo-description: La pagina dei dettagli di una caratteristica specifica fornisce una panoramica delle informazioni come il nome della caratteristica, l’ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di controllo delle caratteristiche. Per visualizzare questi dettagli, vai Dati pubblico > Caratteristiche e fai clic sul nome della caratteristica con cui vuoi lavorare.
seo-title: Pagina Dettagli caratteristica
solution: Audience Manager
title: Pagina Dettagli caratteristica
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Pagina Dettagli caratteristica {#trait-details-page}

La pagina dei dettagli di una caratteristica specifica fornisce una panoramica dei dettagli della caratteristica, come il nome della caratteristica, l’ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di controllo della caratteristica. Per visualizzare questi dettagli, passate a **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** e fate clic sul nome della caratteristica con cui desiderate lavorare.

## Strumenti di gestione delle caratteristiche {#trait-management-tools}

Nella parte superiore della pagina dei dettagli sulle caratteristiche sono disponibili gli strumenti che puoi utilizzare per gestire le caratteristiche:

1. **[!UICONTROL Add New]**: Utilizzate questa opzione per creare nuove caratteristiche basate su regola, algoritmiche o registrate.
2. **[!UICONTROL Edit]**: Utilizzare questa opzione per modificare la configurazione della caratteristica corrente.
3. **[!UICONTROL Delete]**: Utilizzate questa opzione per rimuovere la caratteristica corrente dall&#39;account Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: Utilizzate questa opzione per trovare caratteristiche simili a quelle che state visualizzando, dalle tariffe [!UICONTROL Audience Marketplace] dati alle quali non siete iscritti. Consulta [Audience Marketplace per gli acquirenti](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) di dati per scoprire come navigare nel mercato e trovare caratteristiche simili.

![informazioni sulle caratteristiche di base](assets/basic-trait-information.png)

## Informazioni sulle caratteristiche {#basics}

La [!UICONTROL Trait Information] sezione mostra i dettagli sui campi obbligatori e facoltativi completati al momento della creazione della caratteristica. Questo include caratteristiche come il tipo di caratteristica, l&#39;ID caratteristica, la descrizione, l&#39;origine dati e altri metadati. Questi dettagli variano a seconda del tipo di caratteristica (cartella, scheda aziendale o basata su regole).

## Grafico caratteristiche {#trait-graph}

Fornisce [!UICONTROL Trait Graph] metriche delle prestazioni a colpo d&#39;occhio per la caratteristica selezionata. Posizionare il cursore su una linea di tendenza per visualizzare i dati aggiuntivi per la caratteristica selezionata.

[!UICONTROL Unique Trait Realizations] rappresenta un numero di utenti univoci che hanno aggiunto questa caratteristica al proprio profilo nel periodo di tempo specificato. Indica [!UICONTROL Total Trait Population] il numero di utenti univoci attualmente qualificati per questa caratteristica.

* Per le caratteristiche basate su regola, la qualifica relativa alle caratteristiche viene eseguita in tempo reale, in quanto gli utenti hanno diritto a una caratteristica nel proprio browser.
* Per le caratteristiche registrate, la qualificazione delle caratteristiche viene eseguita dopo l&#39;elaborazione di un file in ingresso, ovvero il file in ingresso viene [immesso in Audience Manager](../../faq/faq-inbound-data-ingestion.md) , ovvero quando si verifica la qualifica relativa alle caratteristiche.
* **[!UICONTROL Unique Trait Realizations]**: Numero di utenti univoci che hanno aggiunto questa caratteristica al proprio profilo nel periodo di tempo specificato.
* **[!UICONTROL Total Trait Population]**: Il numero di utenti univoci attualmente qualificati per questa caratteristica.

   ![grafico a tratti](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: Le prime tre voci mostrano le prime tre origini dati cross-device con il numero di popolazione più elevato che sono state qualificate per la caratteristica, in ordine decrescente. La quarta voce mostra la somma di tutte le altre [!DNL DPUUIDs] ([!DNL CRM IDs]) qualificate per la caratteristica, dalle origini dati cross-device che non sono nelle prime tre. Questo rapporto viene visualizzato solo se selezionate ID cross-device nel menu a [!UICONTROL Show Results By] discesa in alto a destra della pagina. L&#39;opzione predefinita è [!UICONTROL Device ID], dove il rapporto non viene visualizzato.

   ![grafico a tratti](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager visualizza il [!UICONTROL Identity Type Breakdown] rapporto solo se disponi di ID cross-device qualificati per la caratteristica.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## Espressione caratteristica {#trait-expression}

Nella [!UICONTROL Trait Expression] sezione vengono visualizzati i criteri che gli utenti devono soddisfare per qualificarsi per la caratteristica. Queste regole vengono impostate al momento della [creazione o della modifica di una caratteristica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Segmenti di caratteristiche {#trait-segments}

Nella [!UICONTROL Segments with this Trait] sezione sono elencati tutti i segmenti a cui appartiene la caratteristica selezionata. Potete fare clic sul nome di un segmento per visualizzare i dettagli su di esso.

![](assets/traitSegments.png)

## Registro audit/cronologia caratteristiche {#trait-audit-history}

Per le caratteristiche basate su regola e registrate, vengono [!UICONTROL Trait Expression Change History] visualizzate le ultime 10 modifiche apportate alle regole di espressione delle caratteristiche e gli autori delle stesse. Se la caratteristica presenta più di 10 modifiche, fare clic **[!UICONTROL Export to CSV]** per scaricare l&#39;intero registro di controllo. Il registro di controllo non è disponibile per le caratteristiche della cartella o degli algoritmi.

>[!NOTE]
>
>[!UICONTROL Not Available] nella [!UICONTROL By User] colonna indica che l’account dell’utente è stato eliminato.

![](assets/traitHistory.png)