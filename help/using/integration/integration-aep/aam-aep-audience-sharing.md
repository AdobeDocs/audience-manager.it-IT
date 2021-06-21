---
description: Questo articolo descrive come i tipi di pubblico vengono condivisi tra Audience Manager e Adobe Experience Platform.
seo-description: Questo articolo descrive come i tipi di pubblico vengono condivisi tra Audience Manager e Adobe Experience Platform.
seo-title: Condivisione del pubblico tra Audience Manager e Adobe Experience Platform
solution: Audience Manager
title: Condivisione del pubblico tra Audience Manager e Adobe Experience Platform
keywords: Condivisione di audience AEP, segmenti AEP, segmenti Platform, condivisione di segmenti, condivisione di audience, condivisione di segmenti
feature: Integrazione di Platform
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1480'
ht-degree: 2%

---

# Experience Platform di condivisione di segmenti con Audience Manager e altre soluzioni di Experience Cloud {#aam-aep-audience-sharing}

>[!NOTE]
>
> Contatta il tuo rappresentante commerciale Adobe per sbloccare l&#39;accesso a questa funzionalità.

## Panoramica {#overview}

La funzionalità di condivisione del pubblico tra Audience Manager e Adobe Experience Platform ti consente di condividere le caratteristiche e i segmenti di Audience Manager in Adobe Experience Platform e viceversa. È necessario [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) per abilitare la condivisione del pubblico tra Audience Manager e Adobe Experience Platform.

Puoi utilizzare caratteristiche e segmenti di Audience Manager in Experience Platform per aggiungere dati di Audience Manager ai profili dei clienti e per sfruttare l’Experience Platform [servizio di segmentazione](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md).

Ad Audience Manager, puoi utilizzare segmenti di Experience Platform per casi d’uso di Data Management Platform, ad esempio:
* Aggiungi [dati di terze parti](/help/using/overview/data-types-collected.md#third-party-data) ai tuoi segmenti;
* [Modellazione](/help/using/features/algorithmic-models/understanding-models.md) algoritmica;
* Attiva i segmenti in destinazioni non ancora supportate nell&#39;Experience Platform [catalogo delle destinazioni](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Inoltre, i segmenti di Experience Platform sono condivisi con altre soluzioni Experience Cloud tramite [Servizi di base](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * È necessaria una licenza di Audience Manager per abilitare i casi d’uso di Data Management Platform sopra menzionati.
> * Per condividere segmenti di Experience Platform con Adobe Advertising Cloud, Adobe Target, Marketo e altre soluzioni di Experience Cloud tramite l’integrazione dei servizi core, non è necessaria una licenza di Audience Manager *tramite .*


Vedi la tabella seguente per una panoramica dei casi d’uso di condivisione del pubblico:

| **Caso d&#39;uso** | **Adobe Experience Platform** | **Audience Manager** | **Servizi di base** |
|---------|----------|---------|---------|
| **Condivisione del pubblico** | <ul><li>Arricchire i profili dei clienti con i dati di Audience Manager</li><li>Utilizzare i dati di Audience Manager nella segmentazione degli Experienci Platform</li></ul> | <ul><li>Aggiungere dati di terze parti ai segmenti</li><li>Modellazione algoritmica</li><li>Attivazione a destinazioni aggiuntive</li></ul> | Utilizza i segmenti di Experience Platform in altre soluzioni di Experience Cloud, come Adobe Target, Advertising Cloud o Marketo. |

{style=&quot;table-layout:auto&quot;}

## Audience Manager di segmenti e caratteristiche in Adobe Experience Platform {#aam-segments-traits-in-aep}

Le caratteristiche e i segmenti del tuo Audience Manager vengono visualizzati in Experience Platform come **Tipi di pubblico** nel flusso di lavoro dei segmenti. Per ulteriori informazioni sui segmenti e sulle caratteristiche di Audience Manager in Experience Platform, consulta:

* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Guida utente di Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Connettore Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

## Segmenti Adobe Experience Platform nell&#39;Audience Manager {#aep-segments-in-aam}

I segmenti creati in Experience Platform vengono visualizzati nell’interfaccia di Audience Manager come segnali, caratteristiche e segmenti, con le seguenti regole di composizione:

* Segnale: Per ogni segmento di Experience Platform, è necessario visualizzare i segnali nel modulo `segID = segment ID`.
* Caratteristica: La regola delle caratteristiche è l’ID del segmento di Experience Platform.
* Segmento: Il segmento è costituito dalla caratteristica descritta sopra.

### Segnali {#aep-segments-as-aam-signals}

Seleziona **[!UICONTROL Audience Data > Signals > General Online Data]** e cerca `SegId` per trovare i segnali provenienti dall&#39;Experience Platform. Puoi utilizzare questa schermata a scopo di debug, per verificare se l’integrazione tra Experience Platform e Audience Manager è stata configurata correttamente.

![Vedi segnali di Experience Platform in Audience Manager nel dashboard Segnali](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Caratteristiche {#aep-segments-as-aam-traits}

Audience Manager crea automaticamente una cartella di caratteristiche denominata **Caratteristiche Experienci Platform** nell’archiviazione delle caratteristiche.

![Caratteristiche dal dashboard di Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puoi utilizzare le caratteristiche create automaticamente nei segmenti accanto ad altre caratteristiche. Ad esempio, puoi combinare le caratteristiche create dai segmenti di Experience Platform con le caratteristiche di terze parti acquisite tramite l’ [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Per un esempio di una caratteristica creata automaticamente da un segmento di Experience Platform, vedi la schermata seguente:

![Caratteristiche da Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numero articolo | Nome | Descrizione |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Le caratteristiche create dai segmenti di Experience Platform vengono create come caratteristiche onboarded in Audience Manager. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti di Experience Platform vengono memorizzati nell’origine dati **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento in Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | L&#39;espressione della caratteristica è `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Un segmento creato automaticamente che utilizza questa caratteristica come sua composizione. |

{style=&quot;table-layout:auto&quot;}

### Segmenti {#aep-segments-as-aam-segments}

Audience Manager crea automaticamente una cartella di segmenti denominata **Segmenti di Experience Platform** nell&#39;archiviazione dei segmenti.

![Schermata del dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Per un esempio di segmento creato automaticamente da un segmento di Experience Platform, vedi la schermata seguente:

![Schermata del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numero articolo | Nome | Descrizione |
|---------|----------|---------|
| 3 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti di Experience Platform vengono memorizzati nell’origine dati **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica che i segmenti creati automaticamente seguono il criterio di unione impostato in Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Il segmento è costituito dalla caratteristica descritta nella sezione [Caratteristiche](#aep-segments-as-aam-traits). |

{style=&quot;table-layout:auto&quot;}

## Supporto di Audience Manager Data Export Control nell&#39;Experience Platform {#aam-data-export-control-in-aep}

Per applicare la conformità in materia di utilizzo dei dati in Experience Platform, a tutti i set di dati e i campi applicabili devono essere assegnate [etichette di utilizzo dei dati](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html) appropriate. Inoltre, [i criteri di utilizzo dei dati](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) devono essere abilitati per azioni di marketing specifiche rispetto a tali etichette, come descritto dal framework [Etichettatura e applicazione dell&#39;uso dei dati (DULE)](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework).

Nel processo di condivisione del pubblico tra Audience Manager e Experience Platform, tutti i controlli sull’esportazione dei dati applicati ai segmenti di Audience Manager vengono tradotti in etichette e azioni di marketing equivalenti riconosciute dalla governance dei dati di Experience Platform e viceversa.

>[!NOTE]
>
>Per informazioni più generali sui controlli sull&#39;esportazione dei dati, consulta la [documentazione sui controlli sull&#39;esportazione dei dati](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html).
>
>Questo documento fornisce un riferimento per vedere come specifici controlli dell’esportazione dei dati di Audience Manager vengono mappati sulle etichette di utilizzo dei dati e sulle azioni di marketing in Platform.

### Controlli sull’esportazione dei dati per le etichette di utilizzo dei dati

La tabella seguente illustra il modo in cui specifiche etichette di utilizzo dei dati vengono associate a controlli di esportazione dei dati riconosciuti:

| Controllo dell&#39;esportazione dei dati | Etichetta di utilizzo dei dati |
| --- | --- |
| Non può essere utilizzato con informazioni personali identificabili | C3: I dati non possono essere combinati o altrimenti utilizzati con informazioni direttamente identificabili |
| Non può essere utilizzato per il targeting di annunci offsite | C5: I dati non possono essere utilizzati per il targeting intersito basato su interessi di contenuti o annunci |
| Non può essere utilizzato per il targeting di annunci on-site | C6: I dati non possono essere utilizzati per il targeting di annunci sul sito |
| Non può essere utilizzato per la personalizzazione sul sito | C7: I dati non possono essere utilizzati per il targeting sul sito del contenuto |

{style=&quot;table-layout:auto&quot;}

### Controlli sull’esportazione dei dati per le azioni di marketing

La tabella seguente illustra il modo in cui le etichette di esportazione dei dati specifiche vengono mappate su azioni di marketing riconosciute:

| Etichetta esportazione dati | Azione di marketing |
| --- | --- |
| Questa destinazione può consentire una combinazione con informazioni personali identificabili (PII) | Combinare con PII |
| Questa destinazione può essere utilizzata per il targeting di annunci fuori sito | Targeting tra siti |
| Questa destinazione può essere utilizzata per il targeting degli annunci sul sito | Pubblicità on-site |
| Questa destinazione può essere utilizzata per la personalizzazione degli annunci sul sito | Personalizzazione on-site |

{style=&quot;table-layout:auto&quot;}

## Comprendere le differenze di popolazione del segmento tra Audience Manager e Experience Platform {#aep-aam-segment-population-differences}

I numeri della popolazione del segmento possono variare tra i segmenti di Audience Manager e Experience Platform. Anche se i numeri dei segmenti per tipi di pubblico simili o identici devono essere vicini, le differenze di popolazione possono essere dovute ai fattori elencati di seguito.

### Valutazione del segmento in Experience Platform

Ad Audience Manager, i numeri dei rapporti nell’interfaccia vengono aggiornati una volta al giorno.   La tempistica di questo aggiornamento raramente si allinea con il tempo di valutazione del segmento nell’Experience Platform.

### Differenze tra regole di unione profili e criteri di unione

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager e  [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) in Experience Platform funzionano in modo diverso, e il grafico di identità utilizzato per ogni variabile. Per questo motivo, sono previste alcune differenze tra le popolazioni dei segmenti.

### Composizione del segmento in Experience Platform

L&#39;integrazione tra Adobe Experience Platform e Audience Manager condivide una serie di [spazi dei nomi di identità ](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) standard per tutti i clienti: ECID, IDFA, GAID, indirizzi e-mail con hash (EMAIL_LC_SHA256), AdCloud ID. Se i segmenti di Experience Platform utilizzano uno di questi come identità principale per i profili qualificati, i profili vengono conteggiati nelle caratteristiche e nei segmenti di Audience Manager.

>[!NOTE]
>
> I tipi di pubblico in Experience Platform con identità ricavate da e-mail non vengono mai visualizzati in Audience Manager.

Ad esempio, se avevi un segmento di Experience Platform &quot;Tutti i miei clienti&quot; e i profili qualificati erano ID CRM, ECID, IDFA, indirizzi e-mail non elaborati e con hash, il segmento corrispondente nell’Audience Manager includerebbe solo profili con chiave di ECID, IDFA e indirizzi e-mail con hash. La popolazione del segmento in Audience Manager sarebbe inferiore a quella in Experience Platform.

![Experience Platform ad Audience Manager della condivisione dei segmenti - composizione dei segmenti](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Guida utente di Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Connettore Audience Manager](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

