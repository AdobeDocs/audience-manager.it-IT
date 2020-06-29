---
description: La pagina dei dettagli di una caratteristica specifica fornisce una panoramica delle informazioni come il nome della caratteristica, l’ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di controllo delle caratteristiche. Per visualizzare questi dettagli, vai Dati pubblico > Caratteristiche e fai clic sul nome della caratteristica con cui vuoi lavorare.
seo-description: La pagina dei dettagli di una caratteristica specifica fornisce una panoramica delle informazioni come il nome della caratteristica, l’ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di controllo delle caratteristiche. Per visualizzare questi dettagli, vai Dati pubblico > Caratteristiche e fai clic sul nome della caratteristica con cui vuoi lavorare.
seo-title: Pagina Dettagli caratteristica
solution: Audience Manager
title: Pagina Dettagli caratteristica
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 0%

---


# [!UICONTROL Trait] Pagina Dettagli {#trait-details-page}

La pagina dei dettagli di un singolo [!UICONTROL trait] fornisce una panoramica dei [!UICONTROL trait] dettagli, come il [!UICONTROL trait] nome, l’ID, le metriche delle prestazioni, le espressioni che definiscono i [!UICONTROL trait], i segmenti a cui appartiene e il registro di [!UICONTROL trait] controllo. Per visualizzare questi dettagli, passate a **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** e fate clic sul nome dell’ [!UICONTROL trait] utente con cui desiderate lavorare.

## [!UICONTROL Trait] Strumenti di gestione {#trait-management-tools}

Nella parte superiore della pagina dei [!UICONTROL trait] dettagli sono disponibili gli strumenti che consentono di gestire [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Utilizzate questa opzione per creare nuovo [!UICONTROL rule-based], [!UICONTROL algorithmic]o [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Utilizzare questa opzione per modificare la configurazione della corrente [!UICONTROL trait].
3. **[!UICONTROL Delete]**: Utilizzate questa opzione per rimuovere la corrente [!UICONTROL trait] dal vostro account Audience Manager .
4. **[!UICONTROL Marketplace Recommendations]**: Utilizzate questa opzione per trovare un risultato simile [!UICONTROL traits] a quello visualizzato, dalle [!UICONTROL Audience Marketplace] tariffe dati alle quali non siete iscritti. Consulta [Audience Marketplace per gli acquirenti](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) di dati per apprendere come navigare [!UICONTROL Marketplace] e trovare caratteristiche simili.

![informazioni sulle caratteristiche di base](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informazioni {#basics}

La [!UICONTROL Trait Information] sezione mostra i dettagli relativi ai campi obbligatori e facoltativi completati al momento della creazione della [!UICONTROL trait]. Questo include informazioni quali [!UICONTROL trait] tipo, [!UICONTROL trait] ID, descrizione [!UICONTROL data source]e altri metadati. Questi dettagli variano a seconda del [!UICONTROL trait] tipo ([!UICONTROL folder], [!UICONTROL onboarded]o [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Fornisce [!UICONTROL Trait Graph] metriche delle prestazioni a colpo d&#39;occhio per la selezione [!UICONTROL trait]. Posizionare il cursore su una linea di tendenza per visualizzare i dati aggiuntivi per la linea selezionata [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] rappresentano un numero di utenti univoci che lo hanno aggiunto [!UICONTROL trait] al proprio profilo nell’intervallo di tempo specificato. Indica [!UICONTROL Total Trait Population] il numero di utenti univoci attualmente qualificati per questo [!UICONTROL trait].

Ad [!UICONTROL rule-based traits]esempio, [!UICONTROL trait] la qualifica viene eseguita in tempo reale, in quanto gli utenti possono accedere a un [!UICONTROL trait] browser.

Ad [!UICONTROL onboarded traits]esempio, [!UICONTROL trait] la qualifica ha luogo dopo l&#39;elaborazione di un file in entrata, ovvero il file in ingresso viene [inserito in  Audience Manager](../../faq/faq-inbound-data-ingestion.md) , ovvero quando avviene la [!UICONTROL trait] qualifica.

Vengono [!UICONTROL Trait Graph] visualizzate le informazioni seguenti:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: selezionate questa opzione per visualizzare i risultati per [!UICONTROL traits] la raccolta di dati per i profili autenticati. Quando selezionate questa opzione, vengono visualizzati solo i dati nel [!UICONTROL Cross-Device ID] rapporto e nessun dato sarà presente nel [!UICONTROL Device ID] rapporto.
   * **[!UICONTROL Device ID]**: selezionate questa opzione per visualizzare i risultati per [!UICONTROL traits] la raccolta di dati per i profili dispositivo. Quando selezionate questa opzione, vengono visualizzati solo i dati nel [!UICONTROL Device ID] rapporto e nessun dato sarà presente nel [!UICONTROL Cross-Device ID] rapporto.

      ![grafico a tratti](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Numero di utenti univoci che lo hanno aggiunto [!UICONTROL trait] al proprio profilo nell&#39;intervallo di tempo specificato.
* **[!UICONTROL Total Trait Population]**: Il numero di utenti univoci attualmente qualificati per questo [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: Le prime tre voci mostrano i primi tre [!UICONTROL cross-device data sources] con il numero di popolazione più elevato che hanno qualificato per il [!UICONTROL trait], in ordine decrescente. La quarta voce mostra la somma di tutte le altre [!DNL DPUUIDs] ([!DNL CRM IDs]) qualificate per il [!UICONTROL trait], da quelle [!UICONTROL cross-device data sources] che non si trovano nelle prime tre. Questo rapporto viene visualizzato solo se selezionate [!UICONTROL Cross-device ID] nel menu a [!UICONTROL Show Results By] discesa in alto a destra della pagina. L&#39;opzione predefinita è [!UICONTROL Device ID], dove il rapporto non viene visualizzato.

   ![grafico a tratti](assets/trait-identity.png)

   >[!NOTE]
   >
   > Audience Manager visualizza il [!UICONTROL Identity Type Breakdown] rapporto solo se disponete [!UICONTROL cross-device] di ID qualificati per il [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Espressione {#trait-expression}

La [!UICONTROL Trait Expression] sezione mostra i criteri che gli utenti devono soddisfare per qualificarsi per l&#39; [!UICONTROL trait]. Queste regole vengono impostate al momento della [creazione o della modifica di una caratteristica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] Segmenti {#trait-segments}

Nella [!UICONTROL Segments with this Trait] sezione sono elencati tutti i segmenti a cui [!UICONTROL trait] appartiene la selezione. Potete fare clic sul nome di un segmento per visualizzare i dettagli su di esso.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Registro di controllo/cronologia {#trait-audit-history}

Per [!UICONTROL rule-based] e [!UICONTROL onboarded traits], [!UICONTROL Trait Expression Change History] mostra le ultime 10 modifiche apportate alle regole di [!UICONTROL trait] espressione e chi le ha apportate. Se [!UICONTROL trait] sono presenti più di 10 modifiche, fare clic **[!UICONTROL Export to CSV]** per scaricare l&#39;intero registro di controllo. Il registro di controllo non è disponibile per [!UICONTROL folder] o [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] nella [!UICONTROL By User] colonna indica che l’account dell’utente è stato eliminato.

![](assets/traitHistory.png)