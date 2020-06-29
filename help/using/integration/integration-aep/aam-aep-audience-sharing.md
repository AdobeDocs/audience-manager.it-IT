---
description: Questo articolo descrive come le audience vengono condivise tra  Audience Manager e  Adobe Experience Platform.
seo-description: Questo articolo descrive come le audience vengono condivise tra  Audience Manager e  Adobe Experience Platform.
seo-title: Condivisione dell'audience tra  Audience Manager e  Adobe Experience Platform
solution: Audience Manager
title: Condivisione dell'audience tra  Audience Manager e  Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 1%

---


# Condivisione dell&#39;audience tra  Audience Manager e  Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Per accedere a questa funzionalità, contattate il vostro rappresentante commerciale Adobe.

## Panoramica {#overview}

La funzionalità di condivisione dell&#39;audience tra  Audience Manager e  Adobe Experience Platform consente di condividere le caratteristiche e i segmenti  Audience Manager  Adobe Experience Platform e viceversa. È necessario disporre del [Connettore](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) Audience Manager per abilitare la condivisione dell&#39;audience tra  Audience Manager e  Adobe Experience Platform.

Puoi usare  caratteristiche e segmenti Audience Manager in  Experience Platform per aggiungere  dati Audience Manager ai profili dei clienti e per beneficiare del  servizio [di](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)segmentazione di Experience Platform.

In  Audience Manager puoi utilizzare  segmenti Experience Platform per i casi di utilizzo Platform di Gestione dati, ad esempio:
* Aggiungi dati [di](/help/using/overview/data-types-collected.md#third-party-data) terze parti ai tuoi segmenti;
* [modellazione](/help/using/features/algorithmic-models/understanding-models.md)algoritmica;
* Attiva i tuoi segmenti in destinazioni non ancora supportate nel catalogo [](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)delle destinazioni Experience Platform.

Inoltre, i tuoi segmenti Experience Platform  sono condivisi con altre soluzioni Experience Cloud , tramite i servizi [](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)di base.

<br> 

Consulta la tabella seguente per una panoramica dei casi di utilizzo della condivisione di audience:

| **Caso d&#39;uso** | **Adobe Experience Platform** | **Audience Manager** | **Servizi di base** |
---------|----------|---------|---------
| **Condivisione dell&#39;audience** | <ul><li>Arricchisci i profili dei clienti con  dati Audience Manager</li><li>Utilizzare  dati Audience Manager nella segmentazione  Experience Platform</li></ul> | <ul><li>Aggiunta di dati di terze parti ai segmenti</li><li>Modellazione algoritmica</li><li>Attivazione a destinazioni aggiuntive</li></ul> | Utilizza  segmenti Experience Platform in altre soluzioni  Experience Cloud, ad esempio  Adobe Target o  Analytics. |

<br> 

##  segmenti e caratteristiche Audience Manager nel Adobe Experience Platform  {#aam-segments-traits-in-aep}

Le  caratteristiche e i segmenti Audience Manager vengono visualizzati  Experience Platform come **pubblico** nel flusso di lavoro dei segmenti. Per ulteriori informazioni sui segmenti e sulle caratteristiche  Audience Manager in  Experience Platform, vedi:

* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [guida utente di Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

##  segmenti di Adobe Experience Platform in  Audience Manager {#aep-segments-in-aam}

I segmenti creati in  Experience Platform vengono visualizzati nell’interfaccia  Audience Manager come caratteristiche e segmenti, con le seguenti regole di composizione:
* Caratteristiche: La regola caratteristica è l&#39;ID del segmento Experience Platform .
* Segmento: Il segmento è costituito dalla caratteristica descritta sopra.

### Caratteristiche {#aep-segments-as-aam-traits}

 Audience Manager crea automaticamente una cartella di caratteristiche denominata **Experience Platform Traits** nell&#39;archivio delle caratteristiche.

![Caratteristiche  dashboard Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puoi utilizzare caratteristiche create automaticamente nei segmenti accanto ad altre caratteristiche. Ad esempio, puoi combinare le caratteristiche create da  segmenti Experience Platform con caratteristiche di terze parti acquisite tramite l&#39; [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Per un esempio di caratteristica creata automaticamente da un segmento Experience Platform , vedete la schermata seguente:

![Caratteristiche di  Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numero articolo | Nome | Descrizione |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Le caratteristiche create  segmenti Experience Platform vengono create come caratteristiche integrate in  Audience Manager. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente  segmenti Experience Platform vengono memorizzati nell&#39;origine dati **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento in  Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | L&#39;espressione trait è `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Segmento creato automaticamente che utilizza questa caratteristica come composizione. |

<br> 

### Segmenti {#aep-segments-as-aam-segments}

 Audience Manager crea automaticamente una cartella di segmenti denominata **Segmenti** Experience Platform nell’archiviazione dei segmenti.

![Screenshot del dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Per un esempio di segmento creato automaticamente da un segmento Experience Platform , vedi la schermata seguente:

![Screenshot del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numero articolo | Nome | Descrizione |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento in  Experience Platform. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente  segmenti Experience Platform vengono memorizzati nell&#39;origine dati **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica che i segmenti creati automaticamente seguono il criterio di unione impostato in  Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Il segmento è costituito dalla caratteristica descritta nella sezione [Caratteristiche](#aep-segments-as-aam-traits). |

##  il supporto di Audience Manager Data Export Control in  Experience Platform {#aam-data-export-control-in-aep}

Per applicare la conformità all&#39;uso dei dati in  Experience Platform, a tutti i set di dati e i campi applicabili devono essere assegnate etichette [di utilizzo](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)dei dati appropriate. Inoltre, i criteri [di utilizzo dei](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) dati devono essere attivati per azioni di marketing specifiche rispetto a tali etichette, come indicato dal framework [DULE (](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)Data Usage Labeling and Enforcement).

Nel processo di condivisione dell&#39;audience tra  Audience Manager e  Experience Platform, tutti i Controlli sull&#39;esportazione dei dati applicati  segmenti Audience Manager vengono convertiti in etichette e azioni di marketing equivalenti riconosciute  Experience Platform Data Governance e viceversa.

>[!NOTE] Per ulteriori informazioni generali sui controlli per l&#39;esportazione dei dati, consulta la documentazione [sui controlli per l&#39;esportazione dei](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)dati.
Questo documento fornisce un riferimento per il modo in cui  controlli di esportazione dati Audience Manager specifici vengono mappati sulle etichette di utilizzo dei dati e sulle azioni di marketing in Platform.

### Controlli sull&#39;esportazione dei dati per le etichette di utilizzo dei dati

Nella tabella seguente è illustrato il modo in cui specifici Controlli sull’esportazione dei dati vengono mappati sulle etichette di utilizzo dei dati riconosciute:

| Controllo esportazione dati | Etichetta utilizzo dati |
| --- | --- |
| Non può essere utilizzato con informazioni personali | C3: I dati non possono essere combinati o altrimenti utilizzati con informazioni direttamente identificabili |
| Non può essere utilizzato per il targeting di annunci offsite | C5: I dati non possono essere utilizzati per il targeting intersito dei contenuti o degli annunci in base agli interessi |
| Non può essere utilizzato per il targeting di annunci on-site | C6: I dati non possono essere utilizzati per il targeting di annunci on-site |
| Non può essere utilizzato per la personalizzazione in sito | C7: I dati non possono essere utilizzati per il targeting on-site del contenuto |

### Controlli sull&#39;esportazione dei dati per le azioni di marketing

La tabella seguente mostra il modo in cui specifiche Etichette esportazione dati vengono mappate su azioni di marketing riconosciute:

| Etichetta esportazione dati | Azione marketing |
| --- | --- |
| Questa destinazione può consentire una combinazione con informazioni personali (PII) | Combinazione con PII |
| Questa destinazione può essere utilizzata per targeting di annunci fuori sito | Targeting tra siti |
| Questa destinazione può essere utilizzata per il targeting on-site degli annunci | Pubblicità on-site |
| Questa destinazione può essere utilizzata per la personalizzazione degli annunci sul sito | Personalizzazione on-site |

## Comprendere le differenze di popolazione dei segmenti tra  Audience Manager e  Experience Platform

I numeri di popolazione dei segmenti possono variare tra i segmenti  Audience Manager e  Experience Platform. Anche se i numeri dei segmenti per tipi di pubblico simili o identici devono essere vicini, le differenze nelle popolazioni possono essere dovute a:

* I processi di segmentazione sono tempi di esecuzione.  Audience Manager esegue un processo di segmentazione che aggiorna i numeri nell’interfaccia una volta al giorno. Questo processo si allinea raramente ai processi di segmentazione in  Experience Platform.
* [Le regole](/help/using/features/profile-merge-rules/merge-rules-overview.md) di unione dei profili in  Audience Manager e [Unisci criteri](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) in  Experience Platform funzionano in modo diverso e il grafico dell&#39;identità utilizzato per ciascun profilo varia. Per questo motivo, ci si aspetta che ci siano delle differenze tra le popolazioni dei segmenti.

>[!MORELIKETHIS]
>
>* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [guida utente di Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)