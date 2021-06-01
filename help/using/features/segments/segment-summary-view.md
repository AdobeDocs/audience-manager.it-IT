---
description: Nella pagina di riepilogo dei segmenti sono visualizzati dettagli quali nome, caratteristiche del segmento, regole, dati sulle prestazioni e informazioni sulla mappatura della destinazione.
seo-description: Nella pagina di riepilogo dei segmenti sono visualizzati dettagli quali nome, caratteristiche del segmento, regole, dati sulle prestazioni e informazioni sulla mappatura della destinazione.
seo-title: Pagina dei dettagli del segmento
solution: Audience Manager
title: Pagina dei dettagli del segmento
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: suddivisione del tipo di identità, suddivisione dell'identità, reporting dell'identità del pubblico, tra dispositivi, ID multi-dispositivo, ID dispositivo
feature: 'Segmenti '
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Pagina dei dettagli del segmento {#segment-summary-view}

La pagina dei dettagli di un singolo segmento fornisce una panoramica dei dettagli del segmento, come il nome del segmento, l’ID, le metriche delle prestazioni, le regole che definiscono il segmento e le mappature di destinazione. Per visualizzare questi dettagli, vai su **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** e fai clic sul nome del segmento con cui desideri lavorare.

## Strumenti di gestione dei segmenti {#segment-management-tools}

Nella parte superiore della pagina dei dettagli del segmento sono inclusi gli strumenti che puoi utilizzare per gestire i segmenti:

1. **[!UICONTROL Add New]**: Utilizza questa opzione per attivare  [!UICONTROL Segment Builder] e creare nuovi segmenti.
2. **[!UICONTROL Edit]**: Utilizza questa opzione per modificare la configurazione del segmento corrente.
3. **[!UICONTROL Duplicate]**: Utilizza questa opzione per creare una copia del segmento corrente.
4. **[!UICONTROL Delete]**: Utilizza questa opzione per rimuovere il segmento corrente dal tuo account di Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**: Utilizza questa opzione per trovare segmenti simili a quelli che stai visualizzando, dai feed di  [!UICONTROL Audience Marketplace] dati a cui non sei iscritto. Per informazioni su come navigare nel Marketplace e trovare segmenti simili, consulta [Audience Marketplace per gli acquirenti di dati](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) .

![informazioni di base sui segmenti](assets/basic-segment-information.png)

## Informazioni sui segmenti {#basics}

Di seguito gli strumenti di gestione dei segmenti è possibile trovare le seguenti informazioni sui segmenti:

1. **[!UICONTROL Basic Information]:** mostra i dettagli richiesti e facoltativi specificati al momento della creazione del segmento. Per una panoramica dettagliata del significato di questi campi, consulta [Generatore di segmenti](segment-builder.md) .
2. **[!UICONTROL Segment Graph]:** visualizza graficamente i dati sulle prestazioni e per intervalli fissi di 1, 7, 14, 30, 60 e 90 giorni. Spieghiamo i numeri della popolazione del segmento in un [articolo separato](../../features/segments/segment-builder-data.md).

   ![grafico a segmenti](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** Il rapporto mostra il numero di persone o famiglie idonee per un segmento contando il numero di ID multi-dispositivo e/o di ID grafici dei dispositivi esterni collegati ai dispositivi qualificati per il segmento (mostrato dal  [!UICONTROL Total Segment Population]). Gli ID multi-dispositivo e gli ID grafici dei dispositivi esterni visualizzati in questo rapporto vengono utilizzati per unire i profili con la regola di unione dei profili utilizzata dal segmento. Questo rapporto viene visualizzato solo se hai selezionato un’origine dati multi-dispositivo o un grafico dei dispositivi esterno nella regola di unione profili in uso nel segmento.

   ![grafico a segmenti](assets/segment-type.png)

   >[!NOTE]
   >
   >Il rapporto [!UICONTROL Identity Type Breakdown] viene visualizzato solo in Audience Manager se disponi di ID multi-dispositivo qualificati per il segmento.

   Guarda il video seguente per una panoramica di [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:** elenca le caratteristiche del segmento insieme alle regole di qualificazione.
5. **[!UICONTROL Destination Mappings]:** elenca le mappature di destinazione per il segmento.
6. **[!UICONTROL Management Tools]:** consente di creare, modificare, clonare ed eliminare segmenti.
