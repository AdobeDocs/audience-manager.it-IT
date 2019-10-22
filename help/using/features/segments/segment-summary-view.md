---
description: Nella pagina di riepilogo del segmento sono visualizzati dettagli quali nome, caratteristiche del segmento, regole, dati sulle prestazioni e informazioni sulla mappatura della destinazione.
seo-description: Nella pagina di riepilogo del segmento sono visualizzati dettagli quali nome, caratteristiche del segmento, regole, dati sulle prestazioni e informazioni sulla mappatura della destinazione.
seo-title: Visualizzazione riepilogo segmenti
solution: Audience Manager
title: Visualizzazione riepilogo segmenti
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: suddivisione del tipo di identità, analisi dell'identità, segnalazione dell'identità dell'audience
translation-type: tm+mt
source-git-commit: 345042673a9ee7abdac994d774e5c4c893a78749

---


# Visualizzazione riepilogo segmenti {#segment-summary-view}

Nella [!UICONTROL Segment Summary] pagina sono visualizzati dettagli quali nome, caratteristiche del segmento, dati sulle prestazioni delle regole e informazioni sulla mappatura della destinazione.

Fai clic sul nome di un segmento dal dashboard principale per accedere alla relativa pagina di riepilogo. Le sezioni di riepilogo includono:

1. **[!UICONTROL Basic Information]** : Mostra i dettagli obbligatori e facoltativi specificati al momento della creazione del segmento.
2. **[!UICONTROL Segment Graph]** : Visualizza i dati sulle prestazioni graficamente e per intervalli fissi di 1, 7, 14, 30, 60 e 90 giorni. Spieghiamo i numeri della popolazione in un articolo [](../../features/segments/segment-builder-data.md)separato.

   ![segmenti-grafo](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]** : Il rapporto mostra il numero di persone o famiglie idonee per un segmento contando il numero di ID cross-device e/o di ID di Device Graph esterni collegati ai dispositivi idonei per il segmento (mostrato dal [!UICONTROL Total Segment Population]). Gli ID cross-device e gli ID di Device Graph esterni mostrati in questo rapporto vengono utilizzati per unire i profili con la regola di unione dei profili utilizzata dal segmento. Questo rapporto viene visualizzato solo se hai selezionato un'origine dati multi-dispositivo o un Device Graph esterno nella regola di unione del profilo utilizzata dal segmento.

   ![segmenti-grafo](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager visualizza il [!UICONTROL Identity Type Breakdown] rapporto solo se hai degli ID cross-device qualificati per il segmento.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=ita)

4. **[!UICONTROL Segment Rules]** : Elenca le caratteristiche nel segmento insieme alle regole di qualifica.
5. **[!UICONTROL Destination Mappings]** : Elenca le mappature di destinazione per il segmento.
6. **[!UICONTROL Management Tools]** : Controlli che consentono di creare, modificare, duplicare ed eliminare segmenti.