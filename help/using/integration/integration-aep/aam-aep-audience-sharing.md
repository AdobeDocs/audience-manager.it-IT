---
description: Questo articolo descrive come i tipi di pubblico vengono condivisi tra Audience Manager e Adobe Experience Platform.
seo-description: Questo articolo descrive come i tipi di pubblico vengono condivisi tra Audience Manager e Adobe Experience Platform.
seo-title: Condivisione dell'audience tra Audience Manager e Adobe Experience Platform
solution: Audience Manager
title: Condivisione dell'audience tra Audience Manager e Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: f191035a1ad4b83bb3d391de80e1f925d6295df7

---


# Condivisione dell&#39;audience tra Audience Manager e Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Per accedere a questa funzionalità, contattate il vostro rappresentante commerciale Adobe.

## Panoramica {#overview}

La funzionalità di condivisione dell&#39;audience tra Audience Manager e Adobe Experience Platform consente di condividere le caratteristiche e i segmenti di Audience Manager con Adobe Experience Platform e viceversa. È necessario disporre del connettore [](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) Audience Manager per abilitare la condivisione dell&#39;audience tra Audience Manager e Adobe Experience Platform.

Puoi utilizzare le caratteristiche e i segmenti di Audience Manager in Experience Platform per aggiungere dati di Audience Manager ai tuoi profili cliente e per trarre vantaggio dal servizio [di](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)segmentazione della piattaforma Experience.

In Audience Manager puoi utilizzare i segmenti della piattaforma Experience per i casi di utilizzo della piattaforma di gestione dati, come:
* Aggiungi dati [di](/help/using/overview/data-types-collected.md#third-party-data) terze parti ai tuoi segmenti;
* [modellazione](/help/using/features/algorithmic-models/understanding-models.md)algoritmica;
* Attiva i tuoi segmenti in destinazioni non ancora supportate nel catalogo [delle](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)destinazioni della piattaforma Experience.

Inoltre, i segmenti della tua piattaforma Experience sono condivisi con altre soluzioni Experience Cloud, tramite i servizi [](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)di base.

<br> 

Consulta la tabella seguente per una panoramica dei casi di utilizzo della condivisione di audience:

| **Caso d&#39;uso** | **Adobe Experience Platform** | **Audience Manager** | **Servizi di base** |
---------|----------|---------|---------
| **Condivisione dell&#39;audience** | <ul><li>Arricchisci i profili dei clienti con i dati di Audience Manager</li><li>Utilizzo dei dati di Audience Manager nella segmentazione della piattaforma Experience</li></ul> | <ul><li>Aggiunta di dati di terze parti ai segmenti</li><li>Modellazione algoritmica</li><li>Attivazione a destinazioni aggiuntive</li></ul> | Utilizza i segmenti della piattaforma Experience Cloud in altre soluzioni Experience Cloud, come Adobe Target o Analytics. |

<br> 

## Segmenti e caratteristiche di Audience Manager in Adobe Experience Platform {#aam-segments-traits-in-aep}

Le caratteristiche e i segmenti di Audience Manager vengono visualizzati in Experience Platform come **Audiences** nel flusso di lavoro dei segmenti. Per ulteriori informazioni sui segmenti e sulle caratteristiche di Audience Manager in Experience Platform, vedi:

* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guida utente di Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Connettore Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segmenti della piattaforma Adobe Experience in Audience Manager {#aep-segments-in-aam}

I segmenti creati in Experience Platform vengono visualizzati nell’interfaccia di Audience Manager come caratteristiche e segmenti, con le seguenti regole di composizione:
* Caratteristiche: La regola caratteristica è l&#39;ID del segmento della piattaforma esperienza.
* Segmento: Il segmento è costituito dalla caratteristica descritta sopra.

### Caratteristiche {#aep-segments-as-aam-traits}

Audience Manager crea automaticamente una cartella di caratteristiche denominata **Experience Platform Traits** (Caratteristiche della piattaformaesperienza) nell&#39;archivio delle caratteristiche.

![Caratteristiche del dashboard di Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puoi utilizzare caratteristiche create automaticamente nei segmenti accanto ad altre caratteristiche. Ad esempio, puoi combinare le caratteristiche create dai segmenti di Experience Platform con caratteristiche di terze parti acquisite tramite [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Per un esempio di caratteristica creata automaticamente da un segmento della piattaforma Experience, vedi la schermata seguente:

![Caratteristiche della piattaforma Experience](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numero articolo | Nome | Descrizione |
---------|----------|---------
| 1 | Tipo di caratteristica | Le caratteristiche create dai segmenti della piattaforma Experience vengono create come caratteristiche registrate in Audience Manager. |
| 2 | Origine dati | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti della piattaforma Experience vengono memorizzati nell’origine dati Condivisione **pubblico** Adobe Experience Platform. |
| 3 | Codice integrazione | Il codice di integrazione corrisponde all’ID del segmento in Experience Platform. |
| 4 | Espressione caratteristica | L&#39;espressione trait è `segID = segment ID in Experience Platform`. |
| 5 | Segmenti con questa caratteristica | Segmento creato automaticamente che utilizza questa caratteristica come composizione. |

<br> 

### Segmenti {#aep-segments-as-aam-segments}

Audience Manager crea automaticamente una cartella di segmenti denominata Segmenti **della piattaforma** Experience nel sistema di memorizzazione dei segmenti.

![Screenshot del dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Per un esempio di segmento creato automaticamente da un segmento di Experience Platform, vedi la schermata seguente:

![Screenshot del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numero articolo | Nome | Descrizione |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti della piattaforma Experience vengono memorizzati nell’origine dati **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica che i segmenti creati automaticamente seguono il criterio di unione impostato in Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Il segmento è costituito dalla caratteristica descritta nella sezione [Caratteristiche](#aep-segments-as-aam-traits). |

## Comprendere le differenze di popolazione dei segmenti tra Audience Manager e la piattaforma Experience

I numeri di popolazione dei segmenti possono variare tra i segmenti di Audience Manager e della piattaforma Experience. Anche se i numeri dei segmenti per tipi di pubblico simili o identici devono essere vicini, le differenze nelle popolazioni possono essere dovute a:

* I processi di segmentazione sono tempi di esecuzione. Audience Manager esegue un processo di segmentazione che aggiorna i numeri nell&#39;interfaccia una volta al giorno. Questo processo si allinea raramente ai processi di segmentazione in Experience Platform.
* [Le regole](/help/using/features/profile-merge-rules/merge-rules-overview.md) di unione dei profili in Audience Manager e i criteri [di](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) unione in Experience Platform funzionano in modo diverso, e il grafico di identità utilizzato per ciascun gruppo varia. Per questo motivo, ci si aspetta che ci siano delle differenze tra le popolazioni dei segmenti.


>[!MORELIKETHIS]
>
>* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guida utente di Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Connettore Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)


