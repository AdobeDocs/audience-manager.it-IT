---
description: La pagina dei dettagli di una singola caratteristica fornisce una panoramica di informazioni quali il nome della caratteristica, l’ID, le metriche delle prestazioni, le espressioni che definiscono la caratteristica, i segmenti a cui appartiene e il registro di audit delle caratteristiche. Per visualizzare questi dettagli, passa a Dati pubblico > Caratteristiche e fai clic sul nome della caratteristica che desideri utilizzare.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Pagina dettagli caratteristica
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: raggruppamento per tipo di identità, raggruppamento identità, reporting identità pubblico, multi-dispositivo, ID dispositivo
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# Pagina dettagli [!UICONTROL Trait] {#trait-details-page}

La pagina dei dettagli per un singolo [!UICONTROL trait] fornisce una panoramica dei dettagli di [!UICONTROL trait], ad esempio il nome, l&#39;ID, le metriche delle prestazioni, le espressioni che definiscono [!UICONTROL trait], i segmenti a cui appartiene e il registro di controllo [!UICONTROL trait] di [!UICONTROL trait]. Per visualizzare questi dettagli, passare a **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** e fare clic sul nome di [!UICONTROL trait] che si desidera utilizzare.

## Strumenti di gestione [!UICONTROL Trait] {#trait-management-tools}

La parte superiore della pagina dei dettagli di [!UICONTROL trait] contiene gli strumenti che è possibile utilizzare per gestire [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: utilizzare questa opzione per creare nuovi [!UICONTROL rule-based], [!UICONTROL algorithmic] o [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: utilizzare questa opzione per modificare la configurazione dell&#39;elemento [!UICONTROL trait] corrente.
3. **[!UICONTROL Delete]**: utilizza questa opzione per rimuovere [!UICONTROL trait] corrente dal tuo account Audience Manager.
4. **[!UICONTROL Marketplace Recommendations]**: Utilizzare questa opzione per trovare [!UICONTROL traits] simile a quello visualizzato, da [!UICONTROL Audience Marketplace] tariffe dati a cui non si è abbonati. Consulta [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) per scoprire come navigare in [!UICONTROL Marketplace] e trovare caratteristiche simili.

![informazioni sulle caratteristiche di base](assets/basic-trait-information.png)

## Informazioni su [!UICONTROL Trait] {#basics}

La sezione [!UICONTROL Trait Information] mostra i dettagli sui campi obbligatori e facoltativi completati durante la creazione di [!UICONTROL trait]. Sono inclusi elementi come il tipo [!UICONTROL trait], l&#39;ID [!UICONTROL trait], la descrizione, [!UICONTROL data source] e altri metadati. Questi dettagli variano a seconda del tipo [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] o [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph] fornisce una panoramica delle metriche delle prestazioni per [!UICONTROL trait] selezionato. Posizionare il cursore su una linea di tendenza per visualizzare i dati aggiuntivi per [!UICONTROL trait] selezionato.

[!UICONTROL Unique Trait Realizations] rappresenta un conteggio di utenti univoci che hanno aggiunto [!UICONTROL trait] al loro profilo nell&#39;intervallo di tempo specificato. [!UICONTROL Total Trait Population] indica il numero di utenti univoci attualmente qualificati per [!UICONTROL trait].

Per [!UICONTROL rule-based traits], la qualifica per [!UICONTROL trait] avviene in tempo reale, in quanto gli utenti si qualificano per [!UICONTROL trait] nel browser.

Per [!UICONTROL onboarded traits], la qualifica di [!UICONTROL trait] si verifica dopo l&#39;elaborazione di un file in entrata, ovvero il file in entrata è [inviato in Audience Manager](../../faq/faq-inbound-data-ingestion.md) e si verifica quando si verifica la qualifica di [!UICONTROL trait].

[!UICONTROL Trait Graph] mostra le seguenti informazioni:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: selezionare questa opzione per visualizzare i risultati per [!UICONTROL traits] che stanno raccogliendo dati per i profili autenticati. Quando si seleziona questa opzione, vengono visualizzati solo i dati nel report [!UICONTROL Cross-Device ID] e non saranno presenti dati nel report [!UICONTROL Device ID].
   * **[!UICONTROL Device ID]**: selezionare questa opzione per visualizzare i risultati per [!UICONTROL traits] che stanno raccogliendo dati per i profili dispositivo. Quando si seleziona questa opzione, vengono visualizzati solo i dati nel report [!UICONTROL Device ID] e non saranno presenti dati nel report [!UICONTROL Cross-Device ID].

     ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: un conteggio di utenti univoci che hanno aggiunto [!UICONTROL trait] al loro profilo nell&#39;intervallo di tempo specificato.
* **[!UICONTROL Total Trait Population]**: numero di utenti univoci attualmente qualificati per [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: le prime tre voci mostrano i primi tre [!UICONTROL cross-device data sources] con il conteggio di popolazione più alto qualificati per [!UICONTROL trait], in ordine decrescente. La quarta voce mostra la somma di tutti gli altri [!DNL DPUUIDs] ([!DNL CRM IDs]) qualificati per [!UICONTROL trait], dai [!UICONTROL cross-device data sources] che non sono tra i primi tre. Questo report viene visualizzato solo se si seleziona [!UICONTROL Cross-device ID] nel menu a discesa [!UICONTROL Show Results By] nella parte superiore destra della pagina. L&#39;opzione predefinita dell&#39;elenco a discesa è [!UICONTROL Device ID], dove il report non viene visualizzato.

  ![trait-graph](assets/trait-identity.png)

  >[!NOTE]
  >
  >Audience Manager visualizza il report [!UICONTROL Identity Type Breakdown] solo se si dispone di [!UICONTROL cross-device] ID qualificati per [!UICONTROL trait].

  >[!VIDEO](https://video.tv.adobe.com/v/36989?captions=ita)

## Espressione [!UICONTROL Trait] {#trait-expression}

La sezione [!UICONTROL Trait Expression] mostra i criteri che gli utenti devono soddisfare per qualificarsi per [!UICONTROL trait]. Queste regole vengono impostate quando [crei o modifichi una caratteristica](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] segmenti {#trait-segments}

Nella sezione [!UICONTROL Segments with this Trait] sono elencati tutti i segmenti a cui appartiene il [!UICONTROL trait] selezionato. Puoi fare clic sul nome di un segmento per visualizzarne i dettagli.

![](assets/traitSegments.png)

## Registro cronologia/controllo [!UICONTROL Trait] {#trait-audit-history}

Per [!UICONTROL rule-based] e [!UICONTROL onboarded traits], [!UICONTROL Trait Expression Change History] mostra le ultime 10 modifiche apportate alle regole di espressione [!UICONTROL trait] e chi le ha apportate. Se [!UICONTROL trait] contiene più di 10 modifiche, fare clic su **[!UICONTROL Export to CSV]** per scaricare l&#39;intero registro di controllo. Il registro di controllo non è disponibile per [!UICONTROL folder] o [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] nella colonna [!UICONTROL By User] indica che l&#39;account per l&#39;utente è stato eliminato.

![](assets/traitHistory.png)
