---
description: Scopri come abilitare la condivisione dei dati e come i tipi di pubblico vengono condivisi tra Audience Manager e Adobe Experience Platform
solution: Audience Manager
title: Condivisione dei segmenti Experience Platform con Audience Manager e altre soluzioni Experience Cloud
keywords: Condivisione del pubblico AEP, segmenti AEP, segmenti Platform, condivisione dei segmenti, condivisione dei tipi di pubblico, condivisione dei segmenti AAM AEP
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Condivisione dei segmenti Experience Platform con Audience Manager e altre soluzioni Experience Cloud

## Panoramica {#overview}

La funzionalità di condivisione del pubblico tra Audience Manager e Adobe Experience Platform consente di condividere caratteristiche e segmenti di Audience Manager in Adobe Experience Platform e segmenti di Experience Platform in Audience Manager.

Per abilitare la condivisione del pubblico tra Experience Cloud e Adobe Experience Platform, è necessaria la destinazione [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=it) e [Tipi di pubblico di Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=it) in Experience Platform.

Puoi utilizzare le caratteristiche e i segmenti Audience Manager in Experience Platform per aggiungere dati Audience Manager ai profili dei clienti e beneficiare del servizio di segmentazione Experience Platform [1&rbrace;.](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=it)

Ad Audience Manager, puoi utilizzare i segmenti Experience Platform per i casi di utilizzo di Data Management Platform, ad esempio:
* Aggiungi [dati di terze parti](/help/using/overview/data-types-collected.md#third-party-data) ai tuoi segmenti;
* [Modellazione algoritmica](/help/using/features/algorithmic-models/understanding-models.md);
* Attiva i segmenti in destinazioni non ancora supportate nel [catalogo delle destinazioni di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html?lang=it).

Inoltre, i tuoi segmenti di Experience Platform sono condivisi con altre soluzioni di Experience Cloud tramite [Servizi di base](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=it).

>[!IMPORTANT]
>
> * È necessaria una licenza di Audience Manager per abilitare i casi d’uso di Data Management Platform menzionati in precedenza.
> * *non hai bisogno* di una licenza Audience Manager per condividere segmenti Experience Platform con Adobe Advertising Cloud, Adobe Target, Marketo e altre soluzioni Experience Cloud tramite l&#39;integrazione dei servizi core.

Consulta la tabella seguente per una panoramica dei casi di utilizzo della condivisione del pubblico:

| **Caso d&#39;uso** | **Adobe Experience Platform** | **Audience Manager** | **Servizi di base** |
|---------|----------|---------|---------|
| **Condivisione del pubblico** | <ul><li>Arricchire i profili dei clienti con dati Audienci Manager</li><li>Utilizzare i dati Audience Manager nella segmentazione Experience Platform</li></ul> | <ul><li>Aggiungere dati di terze parti ai segmenti</li><li>Modellazione algoritmica</li><li>Attivazione per altre destinazioni</li></ul> | Utilizza i segmenti di Experience Platform in altre soluzioni di Experience Cloud, come Adobe Target, Advertising Cloud o Marketo. |

{style="table-layout:auto"}

## Segmenti e caratteristiche di Audience Manager in Adobe Experience Platform {#aam-segments-traits-in-aep}

Le sezioni seguenti descrivono come abilitare la condivisione dei dati da Audience Manager a Experience Platform e come utilizzare le caratteristiche e i segmenti Audience Manager in Experience Platform.

### Attiva la condivisione dei dati da Audience Manager a Experience Platform {#enable-aam-to-aep-data}

Per inviare segmenti e caratteristiche da un Audienci Manager Experience Platform all’altro, è necessario impostare il connettore di origine dell’Audience Manager nel catalogo delle origini dell’Experience Platform. Si tratta di un flusso di lavoro self-service che non richiede il coinvolgimento dell’Assistenza clienti o dei team di progettazione Adobi. Per impostare il connettore della sorgente di Audience Manager, leggere:

* [Origine Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=it)
* [Creare una connessione di origine Adobe Audience Manager nell&#39;interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=it)

>[!IMPORTANT]
>
>L&#39;Adobe incoraggia i clienti a configurare la connessione senza selezionare le opzioni **[!UICONTROL Select all segments]** e **[!UICONTROL Select all traits]**, come illustrato di seguito. L’acquisizione di popolazioni di segmenti Audience Manager di dimensioni considerevoli ha un impatto diretto sul conteggio totale dei profili quando invii un segmento di Audience Manager a Platform per la prima volta utilizzando l’origine di Audience Manager. Ciò significa che la selezione di tutti i segmenti può potenzialmente causare un conteggio dei profili superiore al limite di utilizzo della licenza consentito.
>
>![Schermata che mostra le opzioni Seleziona tutti i segmenti e Seleziona tutte le caratteristiche deselezionate nel flusso di lavoro per la connessione al connettore di origine dell&#39;Audience Manager.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Utilizzare caratteristiche e segmenti Audience Manager in Experience Platform {#use-aam-data-in-aep}

Dopo aver impostato il connettore di origine di Audience Manager per importare caratteristiche e segmenti da Audience Manager, i dati di Audience Manager vengono visualizzati in Experience Platform come **Tipi di pubblico** nel flusso di lavoro dei segmenti. Per ulteriori informazioni sui segmenti e sulle caratteristiche dell’Audience Manager in Experience Platform, leggi:

* [Panoramica del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=it#audiences)
* [Guida utente di Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=it#audiences)

## Segmenti Adobe Experience Platform in Audience Manager {#aep-segments-in-aam}

Le sezioni seguenti descrivono come abilitare la condivisione dei dati da Experience Platform a Audience Manager e come utilizzare i segmenti Experience Platform in Audience Manager.

### Attiva la condivisione dei dati da Experience Platform a Audience Manager {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> Questa sezione descrive l’integrazione legacy di condivisione dei segmenti da Experience Platform a Audience Manager. Ora puoi configurare questa integrazione senza il supporto dei rappresentanti del cliente Adobe. Per ulteriori informazioni, consulta la documentazione di destinazione di [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=it).

>[!NOTE]
>
> Contatta il tuo Adobe Customer Success Manager o l’Assistenza clienti per sbloccare l’accesso a questa funzionalità.

Per inviare segmenti da Experience Platform a Audience Manager, contatta l’Assistenza clienti o il tuo Customer Success Manager. I team di gestione dell’Assistenza clienti e del Supporto clienti devono inviare un ticket (vedi il ticket modello AAM-52354) per abilitare la connessione da Platform all’Audience Manager.

Assicurati di condividere i piani per i dati che vanno da Platform a Audience Manager, per garantire che la connessione sia configurata correttamente. Ad esempio, se hai bisogno di condividere dati regionali per segmenti inviati ad Adobe Target, queste informazioni devono essere comunicate nel ticket. La connessione di condivisione dei dati da Experience Platform a Audience Manager viene impostata entro sei giorni lavorativi dall’invio della richiesta.

### Utilizzare i segmenti Experience Platform in Audience Manager {#use-aep-data-in-aam}

I segmenti creati in Experience Platform vengono visualizzati nell’interfaccia di Audience Manager come segnali, caratteristiche e segmenti, con le seguenti regole di composizione:

* Segnale: per ogni segmento di Experience Platform, dovresti visualizzare i segnali nel formato `segID = segment ID`.
* Caratteristica: la regola della caratteristica è l’ID del segmento di Experience Platform.
* Segmento: il segmento è costituito dalla caratteristica descritta sopra.

### Segnali {#aep-segments-as-aam-signals}

Selezionare **[!UICONTROL Audience Data > Signals > General Online Data]** ed eseguire una ricerca per `SegId` per trovare i segnali provenienti dall&#39;Experience Platform. Puoi utilizzare questa schermata a scopo di debug, per verificare se l’integrazione tra Experience Platform e Audience Manager è stata impostata correttamente.

![Visualizza segnali di Experience Platform in Audience Manager nel dashboard Segnali](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Caratteristiche {#aep-segments-as-aam-traits}

Audience Manager crea automaticamente una cartella di caratteristiche denominata **Caratteristiche Experienci Platform** nell&#39;archivio delle caratteristiche.

![Caratteristiche dal dashboard Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puoi utilizzare le caratteristiche create automaticamente nei segmenti insieme ad altre caratteristiche. È ad esempio possibile combinare le caratteristiche create da segmenti Experience Platform con le caratteristiche di terze parti acquisite tramite l&#39;[Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Per un esempio di una caratteristica creata automaticamente da un segmento di Experience Platform, vedi la schermata seguente:

![Caratteristica da Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numero articolo | Nome | Descrizione |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Le caratteristiche create dai segmenti Experience Platform vengono create come caratteristiche onboarded in Audience Manager. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti Experience Platform vengono memorizzati nell&#39;origine dati **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento in Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | Espressione caratteristica: `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Segmento creato automaticamente che utilizza questa caratteristica come composizione. |

{style="table-layout:auto"}

### Segmenti {#aep-segments-as-aam-segments}

Audience Manager crea automaticamente una cartella di segmenti denominata **Segmenti di Experience Platform** nell&#39;archivio dei segmenti.

![Schermata del dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Per un esempio di segmento creato automaticamente da un segmento di Experience Platform, vedi la schermata seguente:

![Schermata del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numero articolo | Nome | Descrizione |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti Experience Platform vengono memorizzati nell&#39;origine dati **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica che i segmenti creati automaticamente seguono i criteri di unione impostati nell&#39;Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Il segmento è costituito dalla caratteristica descritta nella sezione [Caratteristiche](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Audience Manager di supporto per il controllo dell&#39;esportazione dei dati in Experience Platform {#aam-data-export-control-in-aep}

Per applicare la conformità all&#39;utilizzo dei dati in Experience Platform, tutti i set di dati e i campi applicabili devono ricevere [etichette di utilizzo dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=it) appropriate. Inoltre, è necessario abilitare [i criteri di utilizzo dati](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=it) per specifiche azioni di marketing su tali etichette, come descritto dal [framework DULE (Data Usage Labeling and Enforcement, etichettatura e applicazione dell&#39;utilizzo dei dati)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=it#dule-framework).

Nel processo di condivisione del pubblico tra Audience Manager e Experience Platform, tutti i Controlli sull’esportazione dei dati applicati ai segmenti Audience Manager vengono tradotti in etichette equivalenti e in azioni di marketing riconosciute dalla Governance dei dati Experience Platform, e viceversa.

>[!NOTE]
>
>Per ulteriori informazioni generali sui controlli sull&#39;esportazione dei dati, fare riferimento alla [documentazione sui controlli sull&#39;esportazione dei dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=it).
>
>Questo documento fornisce un riferimento su come specifici controlli sull’esportazione dei dati di Audience Manager vengono mappati sulle etichette di utilizzo dei dati e sulle azioni di marketing in Platform.

### Controlli sull’esportazione dei dati nelle etichette di utilizzo dei dati

La tabella seguente illustra la mappatura di specifici controlli sull’esportazione dei dati alle etichette di utilizzo dei dati riconosciute:

| Controllo esportazione dati | Etichetta di utilizzo dati |
| --- | --- |
| Non può essere utilizzato con informazioni personali | C3: I dati non possono essere combinati o altrimenti utilizzati con informazioni direttamente identificabili |
| Non può essere utilizzato per il targeting di annunci offsite | C5: i dati non possono essere utilizzati per il targeting tra siti di contenuti o annunci basato sugli interessi |
| Non può essere utilizzato per il targeting di annunci nel sito | C6: I dati non possono essere utilizzati per il targeting di annunci nel sito |
| Non può essere utilizzato per la personalizzazione nel sito | C7: i dati non possono essere utilizzati per il targeting dei contenuti sul sito |

{style="table-layout:auto"}

### Controlli sull’esportazione dei dati nelle azioni di marketing

La tabella seguente illustra il modo in cui le etichette di esportazione dei dati specifiche si associano alle azioni di marketing riconosciute:

| Etichetta esportazione dati | Azione di marketing |
| --- | --- |
| Questa destinazione può consentire la combinazione con informazioni personali (PII) | Combina con PII |
| Questa destinazione può essere utilizzata per il targeting di annunci fuori sito | Targeting tra siti |
| Questa destinazione può essere utilizzata per il targeting di annunci nel sito | Advertising on-site |
| Questa destinazione può essere utilizzata per la personalizzazione degli annunci nel sito | Personalization on-site |

{style="table-layout:auto"}

## Comprendere le differenze di popolazione tra Audience Manager e Experience Platform {#aep-aam-segment-population-differences}

I numeri della popolazione del segmento possono variare tra i segmenti di Audience Manager e di Experience Platform. Anche se i numeri dei segmenti per tipi di pubblico simili o identici devono essere prossimi, le differenze nelle popolazioni possono essere dovute ai fattori elencati di seguito.

### Valutazione del segmento in Experience Platform

Audience Manager aggiorna i numeri di reporting nell’interfaccia una volta al giorno. La tempistica di questo aggiornamento raramente è allineata con quella della valutazione del segmento in Experience Platform.

### Differenze tra le regole di unione profili e i criteri di unione

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager e [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html?lang=it) in Experience Platform funzionano in modo diverso e il grafico delle identità utilizzato per ciascuno varia. Per questo motivo, sono attese alcune differenze tra le popolazioni dei segmenti.

>[!NOTE]
>
> Quando condividi segmenti da un Experienci Platform Audience Manager all&#39;altro, il [criterio di unione predefinito](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=it#default-merge-policy) dell&#39;organizzazione Platform ha la precedenza sul [criterio di unione utilizzato dal segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=it#merge-policies) condiviso con Audience Manager. Se, ad esempio, il criterio di unione del segmento condiviso consente l&#39;unione di [ID](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=it#configure), ma il criterio di unione predefinito dell&#39;organizzazione non lo consente, è possibile che si verifichino differenze di popolazione tra Platform e Audience Manager.

### Composizione del segmento in Experience Platform

L&#39;integrazione tra Adobe Experience Platform e Audience Manager condivide una serie di [spazi dei nomi di identità](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=it#identity-types) standard per tutti i clienti: ECID, IDFA, GAID, indirizzi e-mail con hash (EMAIL_LC_SHA256), ID AdCloud. Se i segmenti Experience Platform utilizzano uno di questi come identità primaria per i profili qualificati, i profili vengono conteggiati in caratteristiche e segmenti Audienci Manager.

>[!NOTE]
>
> I tipi di pubblico in Experience Platform con identità ricavate da e-mail non elaborate non vengono mai visualizzati in Audience Manager.

Ad esempio, se disponessi di un segmento di Experience Platform &quot;All my customers&quot; (Tutti i miei clienti) e i profili idonei fossero ID del sistema di gestione delle relazioni con i clienti, ECID, IDFA, indirizzi e-mail non elaborati e con hash, il segmento corrispondente in Audience Manager includerebbe solo i profili ricavati da ECID, IDFA e indirizzi e-mail con hash. La popolazione del segmento in Audience Manager sarebbe inferiore a quella in Experience Platform.

![Experience Platform di Audience Manager della condivisione del segmento - composizione del segmento](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Panoramica del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=it#audiences)
>* [Guida utente di Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=it#audiences)
>* [Connettore Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=it)
