---
description: La pagina di riepilogo dei segmenti visualizza dettagli quali nome, caratteristiche nel segmento, regole, dati sulle prestazioni e informazioni sul mapping delle destinazioni.
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: Pagina Dettagli segmento
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: raggruppamento per tipo di identità, raggruppamento identità, reporting identità pubblico, multi-dispositivo, ID dispositivo
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Pagina Dettagli segmento {#segment-summary-view}

La pagina dei dettagli di un singolo segmento fornisce una panoramica dei dettagli del segmento, ad esempio il nome del segmento, l’ID, le metriche delle prestazioni, le regole che definiscono il segmento e le mappature di destinazione. Per visualizzare questi dettagli, vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** e fai clic sul nome del segmento che desideri usare.

## Strumenti di gestione dei segmenti {#segment-management-tools}

La parte superiore della pagina dei dettagli dei segmenti contiene gli strumenti che puoi utilizzare per gestire i segmenti:

1. **[!UICONTROL Add New]**: utilizzare questa opzione per attivare [!UICONTROL Segment Builder] e creare nuovi segmenti.
2. **[!UICONTROL Edit]**: utilizzare questa opzione per modificare la configurazione del segmento corrente.
3. **[!UICONTROL Duplicate]**: utilizzare questa opzione per creare una copia del segmento corrente.
4. **[!UICONTROL Delete]**: utilizzare questa opzione per rimuovere il segmento corrente dall&#39;account di Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**: utilizzare questa opzione per trovare segmenti simili a quelli che si stanno visualizzando, da [!UICONTROL Audience Marketplace] feed di dati a cui non si è iscritti. Consulta l&#39;[Audience Marketplace per gli acquirenti di dati](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) per scoprire come navigare nel Marketplace e trovare segmenti simili.

![informazioni-segmento-base](assets/basic-segment-information.png)

## Informazioni segmento {#basics}

Sotto gli strumenti di gestione dei segmenti puoi trovare le seguenti informazioni sui segmenti:

1. **[!UICONTROL Basic Information]:** mostra i dettagli obbligatori e facoltativi specificati al momento della creazione del segmento. Consulta [Generatore di segmenti](segment-builder.md) per una panoramica dettagliata del significato di questi campi.
2. **[!UICONTROL Segment Graph]:** visualizza graficamente i dati sulle prestazioni e per intervalli di 1, 7, 14, 30, 60 e 90 giorni fissi. I numeri di popolazione dei segmenti vengono spiegati in un [articolo separato](../../features/segments/segment-builder-data.md).

   ![segment-graph](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown]:** Il report mostra il numero di persone o famiglie che si qualificano per un segmento contando il numero di ID multi-dispositivo e/o ID del grafico dei dispositivi esterni che sono collegati ai dispositivi qualificati per il segmento (mostrato da [!UICONTROL Total Segment Population]). Gli ID multi-dispositivo e gli ID del grafico del dispositivo esterno mostrati in questo rapporto vengono utilizzati per unire i profili con la regola di unione profili utilizzata dal segmento. Questo report viene visualizzato solo se hai selezionato un’origine dati multi-dispositivo o un grafico dei dispositivi esterno nella regola di unione profili utilizzata dal segmento.

   ![segment-graph](assets/segment-type.png)

   >[!NOTE]
   >
   >In Audience Manager viene visualizzato il report [!UICONTROL Identity Type Breakdown] solo se si dispone di ID multi-dispositivo qualificati per il segmento.

   Guarda il video seguente per una panoramica di [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/36989?captions=ita)

4. **[!UICONTROL Segment Rules]:** elenca le caratteristiche nel segmento insieme alle regole di qualificazione.
5. **[!UICONTROL Destination Mappings]:** Elenca i mapping di destinazione per il segmento.
6. **[!UICONTROL Management Tools]:** controlli che consentono di creare, modificare, clonare ed eliminare segmenti.
