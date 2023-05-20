---
description: La pagina dei dettagli di una singola caratteristica fornisce una panoramica di informazioni quali il nome della caratteristica, l’ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di audit delle caratteristiche. Per visualizzare questi dettagli, passa a Dati pubblico > Caratteristiche e fai clic sul nome della caratteristica che desideri utilizzare.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Pagina dei dettagli delle caratteristiche
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: raggruppamento per tipo di identità, raggruppamento identità, reporting identità pubblico, multi-dispositivo, ID dispositivo
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# [!UICONTROL Trait] Pagina dettagli {#trait-details-page}

Pagina dei dettagli di un singolo utente [!UICONTROL trait] offre una panoramica della [!UICONTROL trait] dettagli quali [!UICONTROL trait] nome, ID, metriche delle prestazioni, espressioni che definiscono [!UICONTROL trait], i segmenti a cui appartiene e [!UICONTROL trait] registro di controllo. Per visualizzare questi dettagli, vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** e fai clic sul nome del [!UICONTROL trait] vuoi lavorare con.

## [!UICONTROL Trait] Strumenti di gestione {#trait-management-tools}

La parte superiore della [!UICONTROL trait] nella pagina dei dettagli sono inclusi gli strumenti che è possibile utilizzare per gestire [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: utilizza questa opzione per creare nuovi [!UICONTROL rule-based], [!UICONTROL algorithmic], o [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: utilizza questa opzione per modificare la configurazione della [!UICONTROL trait].
3. **[!UICONTROL Delete]**: utilizza questa opzione per rimuovere il [!UICONTROL trait] dal tuo account Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: utilizza questa opzione per trovare simili [!UICONTROL traits] a quello visualizzato, da [!UICONTROL Audience Marketplace] addebiti per dati a cui non sei abbonato. Consulta [Audience Marketplace per gli acquirenti di dati](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) per scoprire come navigare nel [!UICONTROL Marketplace] e trovare caratteristiche simili.

![informazioni di base sulle caratteristiche](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informazioni {#basics}

Il [!UICONTROL Trait Information] Questa sezione mostra i dettagli sui campi obbligatori e facoltativi completati durante la creazione di [!UICONTROL trait]. Ciò include elementi come [!UICONTROL trait] tipo, [!UICONTROL trait] ID, descrizione, [!UICONTROL data source]e altri metadati. Questi dettagli variano a seconda di [!UICONTROL trait] tipo ([!UICONTROL folder], [!UICONTROL onboarded], o [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Il [!UICONTROL Trait Graph] fornisce una panoramica delle metriche delle prestazioni per il [!UICONTROL trait]. Posizionare il cursore su una linea di tendenza per visualizzare i dati aggiuntivi per la linea selezionata [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] rappresenta un numero di utenti univoci che hanno aggiunto questo elemento [!UICONTROL trait] al loro profilo nell’intervallo di tempo specificato. Il [!UICONTROL Total Trait Population] indica il numero di utenti univoci attualmente qualificati per questo [!UICONTROL trait].

Per [!UICONTROL rule-based traits], [!UICONTROL trait] la qualificazione avviene in tempo reale, in quanto gli utenti si qualificano per un [!UICONTROL trait] nel browser.

Per [!UICONTROL onboarded traits], [!UICONTROL trait] la qualifica si verifica dopo l’elaborazione di un file in entrata, ovvero quando il file in entrata viene [alimentato in Audience Manager](../../faq/faq-inbound-data-ingestion.md) ed è quando [!UICONTROL trait] si verifica una qualifica.

Il [!UICONTROL Trait Graph] mostra le seguenti informazioni:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: seleziona questa opzione per visualizzare i risultati per [!UICONTROL traits] che raccolgono dati per i profili autenticati. Quando selezioni questa opzione, vengono visualizzati solo i dati [!UICONTROL Cross-Device ID] e non saranno presenti dati sotto il [!UICONTROL Device ID] rapporto.
   * **[!UICONTROL Device ID]**: seleziona questa opzione per visualizzare i risultati per [!UICONTROL traits] che raccolgono dati per i profili dispositivo. Quando selezioni questa opzione, vengono visualizzati solo i dati [!UICONTROL Device ID] e non saranno presenti dati sotto il [!UICONTROL Cross-Device ID] rapporto.

      ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: numero di utenti univoci che hanno aggiunto questo elemento [!UICONTROL trait] al loro profilo nell’intervallo di tempo specificato.
* **[!UICONTROL Total Trait Population]**: numero di utenti univoci attualmente qualificati per questo [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: le prime tre voci mostrano le prime tre [!UICONTROL cross-device data sources] con il più alto numero di abitanti che si sono qualificati per [!UICONTROL trait], in ordine decrescente. La quarta voce mostra la somma di tutti gli altri [!DNL DPUUIDs] ([!DNL CRM IDs]) che si sono qualificati per [!UICONTROL trait], dalla [!UICONTROL cross-device data sources] che non sono tra i primi tre. Questo report viene visualizzato solo se si seleziona [!UICONTROL Cross-device ID] nel [!UICONTROL Show Results By] menu a discesa in alto a destra nella pagina. L’opzione predefinita dell’elenco a discesa è [!UICONTROL Device ID], in cui il report non viene visualizzato.

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >L&#39;Audience Manager visualizza solo [!UICONTROL Identity Type Breakdown] segnala se hai [!UICONTROL cross-device] ID qualificati per [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Espressione {#trait-expression}

Il [!UICONTROL Trait Expression] mostra i criteri che gli utenti devono soddisfare per qualificarsi per [!UICONTROL trait]. Queste regole vengono impostate quando [creare o modificare una caratteristica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmenti  {#trait-segments}

Il [!UICONTROL Segments with this Trait] sezione elenca tutti i segmenti selezionati [!UICONTROL trait] appartiene a. Puoi fare clic sul nome di un segmento per visualizzarne i dettagli.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Registro di controllo/cronologia {#trait-audit-history}

Per [!UICONTROL rule-based] e [!UICONTROL onboarded traits], il [!UICONTROL Trait Expression Change History] mostra le ultime 10 modifiche apportate a [!UICONTROL trait] regole di espressione e chi le ha create. Se il [!UICONTROL trait] ha più di 10 modifiche, fai clic su **[!UICONTROL Export to CSV]** per scaricare l&#39;intero registro di controllo. Il registro di controllo non è disponibile per [!UICONTROL folder] o [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] nel [!UICONTROL By User] per colonna si intende che l’account dell’utente è stato eliminato.

![](assets/traitHistory.png)
