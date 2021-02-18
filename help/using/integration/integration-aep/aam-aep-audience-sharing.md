---
description: Questo articolo descrive come le audience vengono condivise tra  Audience Manager e Adobe Experience Platform.
seo-description: Questo articolo descrive come le audience vengono condivise tra  Audience Manager e Adobe Experience Platform.
seo-title: Condivisione del pubblico tra Audience Manager e Adobe Experience Platform
solution: Audience Manager
title: Condivisione del pubblico tra Audience Manager e Adobe Experience Platform
keywords: Condivisione di audience AEP, segmenti AEP, segmenti piattaforma, condivisione di segmenti, condivisione di audience, condivisione di segmenti
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: 62938e95fa9eed3e747fa4dabf8695c5dbefde17
workflow-type: tm+mt
source-wordcount: '1504'
ht-degree: 2%

---


#  condivisione del segmento di Experience Platform con  Audience Manager e altre soluzioni Experience Cloud di di  {#aam-aep-audience-sharing}

>[!NOTE]
>
> Contattate il rappresentante commerciale  Adobe per accedere a questa funzionalità.

## Panoramica {#overview}

La funzionalità di condivisione del pubblico tra  Audience Manager e Adobe Experience Platform consente di condividere le caratteristiche e i segmenti  Audience Manager su Adobe Experience Platform e viceversa. È necessario disporre di [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) per abilitare la condivisione dell&#39;audience tra  Audience Manager e Adobe Experience Platform.

Puoi utilizzare  caratteristiche e segmenti di Audience Manager in  Experience Platform per aggiungere  dati Audience Manager ai profili dei clienti e per beneficiare del servizio di segmentazione del Experience Platform  [](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md).

In  Audience Manager puoi utilizzare  segmenti di Experience Platform per i casi di utilizzo della piattaforma di gestione dati, come:
* Aggiungi [dati di terze parti](/help/using/overview/data-types-collected.md#third-party-data) ai tuoi segmenti;
* [modellazione](/help/using/features/algorithmic-models/understanding-models.md) algoritmica;
* Attiva i tuoi segmenti in destinazioni non ancora supportate nel catalogo delle destinazioni [del Experience Platform di ](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Inoltre, i segmenti di Experience Platform  vengono condivisi con altre soluzioni  Experience Cloud tramite [Servizi di base](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * È necessaria una licenza di Audience Manager  per abilitare i casi d’uso della piattaforma di gestione dati di cui sopra.
> * *non è necessario* una licenza di Audience Manager  per condividere segmenti  Experience Platform con Adobe Advertising Cloud,  Adobe Target, Marketo e altre soluzioni di Experience Cloud , tramite l&#39;integrazione dei servizi di base.


<br> 

Consulta la tabella seguente per una panoramica dei casi di utilizzo della condivisione di audience:

| **Caso d&#39;uso** | **Adobe Experience Platform** | **Audience Manager** | **Servizi di base** |
---------|----------|---------|---------
| **Condivisione dell&#39;audience** | <ul><li>Arricchisci i profili dei clienti con i dati dei Audienci Manager </li><li>Utilizzare  dati Audience Manager nella segmentazione  Experience Platform</li></ul> | <ul><li>Aggiunta di dati di terze parti ai segmenti</li><li>Modellazione algoritmica</li><li>Attivazione a destinazioni aggiuntive</li></ul> | Utilizzare  segmenti di Experience Platform in altre soluzioni di Experience Cloud , come  Adobe Target,  Advertising Cloud o Marketo. |

<br> 

##  segmenti e caratteristiche di Audience Manager in Adobe Experience Platform {#aam-segments-traits-in-aep}

Le caratteristiche e i segmenti  Audience Manager vengono visualizzati  Experience Platform come **Audiences** nel flusso di lavoro dei segmenti. Per ulteriori informazioni sui segmenti e sulle caratteristiche  Audience Manager in  Experience Platform, vedi:

* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guida utente del Generatore di segmenti di  Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Connettore Audience Manager ](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segmenti Adobe Experience Platform nel Audience Manager  {#aep-segments-in-aam}

I segmenti creati in  Experience Platform vengono visualizzati nell’interfaccia del Audience Manager  come segnali, caratteristiche e segmenti, con le seguenti regole di composizione:

* Segnale: Per ciascun segmento di Experience Platform , è necessario visualizzare i segnali nel modulo `segID = segment ID`.
* Caratteristiche: La regola caratteristica è l&#39;ID del segmento del Experience Platform .
* Segmento: Il segmento è costituito dalla caratteristica descritta sopra.

### Segnali {#aep-segments-as-aam-signals}

Selezionare **[!UICONTROL Audience Data > Signals > General Online Data]** e cercare per `SegId` per trovare i segnali provenienti  Experience Platform. È possibile utilizzare questa schermata a scopo di debug, per verificare se l&#39;integrazione tra  Experience Platform e  Audience Manager è stata configurata correttamente.

![Visualizzare  segnali di Experience Platform in  Audience Manager nel pannello Segnali](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Caratteristiche {#aep-segments-as-aam-traits}

 Audience Manager crea automaticamente una cartella di caratteristiche denominata **Caratteristiche del Experience Platform** nell&#39;archivio delle caratteristiche.

![Caratteristiche dal dashboard  Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puoi utilizzare caratteristiche create automaticamente nei segmenti accanto ad altre caratteristiche. Ad esempio, potete combinare le caratteristiche create dai segmenti  Experience Platform con caratteristiche di terze parti acquisite tramite il Audience Marketplace [](/help/using/features/audience-marketplace/audience-marketplace.md).

Per un esempio di caratteristica creata automaticamente da un segmento di Experience Platform , consultate la schermata seguente:

![Caratteristiche dal Experience Platform ](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numero articolo | Nome | Descrizione |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Le caratteristiche create da  segmenti di Experience Platform vengono create come caratteristiche registrate  Audience Manager. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti  Experience Platform vengono memorizzati nell&#39;origine dati **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento nel  Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | L&#39;espressione trait è `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Segmento creato automaticamente che utilizza questa caratteristica come composizione. |

<br> 

### Segmenti {#aep-segments-as-aam-segments}

 Audience Manager crea automaticamente una cartella del segmento denominata **Segmenti di Experience Platform** nell&#39;archivio del segmento.

![Screenshot del dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Per un esempio di segmento creato automaticamente da un segmento di Experience Platform , consultate la schermata seguente:

![Screenshot del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numero articolo | Nome | Descrizione |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento nel  Experience Platform. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti  Experience Platform vengono memorizzati nell&#39;origine dati **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica che i segmenti creati automaticamente seguono il criterio di unione impostato  Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Il segmento è costituito dalla caratteristica descritta nella sezione [Caratteristiche](#aep-segments-as-aam-traits). |

##  Audience Manager Controllo dell&#39;esportazione dei dati in  Experience Platform {#aam-data-export-control-in-aep}

Per applicare la conformità all&#39;uso dei dati in  Experience Platform, a tutti i set di dati e i campi applicabili devono essere assegnate [etichette di utilizzo dei dati](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html) appropriate. Inoltre, è necessario abilitare i [criteri di utilizzo dei dati](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) per azioni di marketing specifiche rispetto a tali etichette, come indicato dal framework [Etichettatura ed applicazione dell&#39;uso dei dati (DULE)](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework).

Nel processo di condivisione dell&#39;audience tra  Audience Manager e  Experience Platform, tutti i Controlli sull&#39;esportazione dei dati applicati  segmenti di Audience Manager vengono convertiti in etichette e azioni di marketing equivalenti riconosciute da  Governance dei dati del Experience Platform e viceversa.

>[!NOTE]
>
>Per ulteriori informazioni generali sui controlli di esportazione dei dati, consultare la [documentazione sui controlli di esportazione dei dati](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html).
>
>Questo documento fornisce un riferimento per il modo in cui specifici controlli di esportazione dei dati  Audience Manager vengono mappati sulle etichette di utilizzo dei dati e sulle azioni di marketing in Piattaforma.

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

## Comprendere le differenze di popolazione del segmento tra  Audience Manager e  Experience Platform {#aep-aam-segment-population-differences}

Il numero di popolazione del segmento può variare tra i segmenti del Audience Manager  e  Experience Platform. Anche se i numeri dei segmenti per tipi di pubblico simili o identici devono essere vicini, le differenze di popolazione possono essere dovute ai fattori elencati di seguito.

### Valutazione del segmento in  Experience Platform

 Audience Manager aggiorna i numeri di report nell&#39;interfaccia una volta al giorno.   Il tempo di questo aggiornamento è raramente in linea con il tempo di valutazione del segmento nel  Experience Platform.

### Differenze tra le regole di unione dei profili e i criteri di unione

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md)  Audience Manager e  [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) in  Experience Platform funzionano in modo diverso, e il grafico dell&#39;identità utilizzato per ciascun  varia. Per questo motivo, ci si aspetta che ci siano delle differenze tra le popolazioni dei segmenti.

### Composizione del segmento nel Experience Platform 

L&#39;integrazione tra Adobe Experience Platform e  Audience Manager condivide una serie di [spazi dei nomi di identità ](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) standard per tutti i clienti: ECID, IDFA, GAID, indirizzi e-mail con hash (EMAIL_LC_SHA256), ID AdCloud. Se i segmenti di Experience Platform  utilizzano uno di questi come identità principale per i profili qualificati, i profili vengono conteggiati in  caratteristiche e segmenti di Audience Manager.

Inoltre,  Audience Manager può registrare le realizzazioni in entrata per qualsiasi namespace identità personalizzata utilizzata nei segmenti  Experience Platform se:
* l&#39;identità è contrassegnata come principale *e*
* nel Audience Manager è già presente un&#39;origine dati cross-device corrispondente.

>[!NOTE]
>
> Il pubblico in  Experience Platform con identità cancellate le e-mail non viene mai visualizzato  Audience Manager.

Ad esempio, se aveste un segmento di Experience Platform  &quot;Tutti i miei clienti&quot; e i profili qualificati sarebbero ID CRM, ECID, IDFA, indirizzi e-mail non elaborati e con hash, il segmento corrispondente nel Audience Manager  includerebbe solo i profili con chiave degli ID CRM, ECID, IDFA e indirizzi e-mail con hash. La popolazione del segmento nel Audience Manager  sarebbe inferiore a quella del Experience Platform .

![ Experience Platform a  la condivisione del segmento del Audience Manager - Composizione del segmento](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guida utente del Generatore di segmenti di  Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Connettore Audience Manager ](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)