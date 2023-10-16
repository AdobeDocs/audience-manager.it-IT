---
description: Scopri come abilitare la condivisione dei dati e come i tipi di pubblico vengono condivisi tra Audienci Manager e Adobe Experience Platform
solution: Audience Manager
title: Condivisione dei segmenti Experienci Platform con Audienci Manager e altre soluzioni Experience Cloud
keywords: Condivisione del pubblico AEP, segmenti AEP, segmenti Platform, condivisione dei segmenti, condivisione dei tipi di pubblico, condivisione dei segmenti AAM AEP
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1953'
ht-degree: 1%

---

# Condivisione dei segmenti Experienci Platform con Audienci Manager e altre soluzioni Experience Cloud

## Panoramica {#overview}

La funzionalità di condivisione del pubblico tra Audienci Manager e Adobe Experience Platform consente di condividere caratteristiche e segmenti di Audienci Manager in Adobe Experience Platform e segmenti di Experienci Platform in Audienci Manager.

Hai bisogno di [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) e [Tipi di pubblico di Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) destinazione in Experienci Platform per abilitare la condivisione del pubblico tra Audienci Manager e Adobe Experience Platform.

Puoi utilizzare le caratteristiche e i segmenti Audienci Manager in Experienci Platform per aggiungere dati Audienci Manager ai profili dei clienti e beneficiare dell’Experience Platform [servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en).

Ad Audience Manager, puoi utilizzare i segmenti Experienci Platform per i casi di utilizzo di Data Management Platform, ad esempio:
* Aggiungi [dati di terze parti](/help/using/overview/data-types-collected.md#third-party-data) ai tuoi segmenti;
* [Modellazione algoritmica](/help/using/features/algorithmic-models/understanding-models.md);
* Attiva i segmenti in destinazioni non ancora supportate nell’Experience Platform [catalogo delle destinazioni](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Inoltre, i segmenti di Experience Platform sono condivisi con altre soluzioni di Experience Cloud tramite [Servizi core](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * È necessaria una licenza di Audience Manager per abilitare i casi d’uso di Data Management Platform menzionati in precedenza.
> * Tu *non è necessario* una licenza Audienci Manager per condividere segmenti Experienci Platform con Adobe Advertising Cloud, Adobe Target, Marketo e altre soluzioni Experience Cloud tramite l’integrazione dei servizi core.

Consulta la tabella seguente per una panoramica dei casi di utilizzo della condivisione del pubblico:

| **Caso d&#39;uso** | **Adobe Experience Platform** | **Audience Manager** | **Servizi di base** |
|---------|----------|---------|---------|
| **Condivisione del pubblico** | <ul><li>Arricchire i profili dei clienti con dati Audienci Manager</li><li>Utilizzare i dati Audienci Manager nella segmentazione Experienci Platform</li></ul> | <ul><li>Aggiungere dati di terze parti ai segmenti</li><li>Modellazione algoritmica</li><li>Attivazione per altre destinazioni</li></ul> | Utilizza i segmenti di Experienci Platform in altre soluzioni di Experience Cloud, come Adobe Target, Advertising Cloud o Marketo. |

{style="table-layout:auto"}

## Segmenti e caratteristiche di Audience Manager in Adobe Experience Platform {#aam-segments-traits-in-aep}

Le sezioni seguenti descrivono come abilitare la condivisione dei dati da Audience Manager a Experience Platform e come utilizzare le caratteristiche e i segmenti Audienci Manager in Experienci Platform.

### Attiva la condivisione dei dati da Audience Manager a Experience Platform {#enable-aam-to-aep-data}

Per inviare segmenti e caratteristiche da un Audienci Manager Experience Platform all’altro, è necessario impostare il connettore di origine dell’Audience Manager nel catalogo delle origini dell’Experience Platform. Si tratta di un flusso di lavoro self-service che non richiede il coinvolgimento dell’Assistenza clienti o dei team di progettazione Adobi. Per impostare il connettore della sorgente di Audience Manager, leggere:

* [Sorgente Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [Creare una connessione sorgente Adobe Audience Manager nell’interfaccia utente](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe incoraggia i clienti a configurare la connessione senza selezionare **[!UICONTROL Select all segments]** e **[!UICONTROL Select all traits]** come mostrato di seguito. L’acquisizione di popolazioni di segmenti Audienci Manager di dimensioni considerevoli ha un impatto diretto sul conteggio totale dei profili quando invii un segmento di Audience Manager a Platform per la prima volta utilizzando l’origine di Audience Manager. Ciò significa che la selezione di tutti i segmenti può potenzialmente causare un conteggio dei profili superiore al limite di utilizzo della licenza consentito.
>
>![Screenshot che mostra le opzioni Select all segments (Seleziona tutti i segmenti) e Select all traits (Seleziona tutte le caratteristiche) non selezionate nel flusso di lavoro per la connessione al connettore di origine dell&#39;Audience Manager.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Utilizzare caratteristiche e segmenti Audienci Manager in Experienci Platform {#use-aam-data-in-aep}

Dopo aver impostato il connettore di origine dell’Audience Manager per importare caratteristiche e segmenti da Audienci Manager, i dati dell’Audience Manager vengono visualizzati in Experienci Platform come **Tipi di pubblico** nel flusso di lavoro del segmento. Per ulteriori informazioni sui segmenti e sulle caratteristiche dell’Audience Manager in Experienci Platform, leggi:

* [Panoramica del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Guida utente di Experienci Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Segmenti Adobe Experience Platform in Audienci Manager {#aep-segments-in-aam}

Le sezioni seguenti descrivono come abilitare la condivisione dei dati da Experienci Platform a Audienci Manager e come utilizzare i segmenti Experienci Platform in Audienci Manager.

### Attiva la condivisione dei dati da Experience Platform a Audience Manager {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> Questa sezione descrive l’integrazione legacy di condivisione dei segmenti da Experienci Platform a Audienci Manager. Ora puoi configurare questa integrazione senza il supporto dei rappresentanti del cliente Adobe. Per ulteriori informazioni, leggere [Tipi di pubblico di Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) documentazione di destinazione.

>[!NOTE]
>
> Contatta il tuo Adobe Customer Success Manager o l’Assistenza clienti per sbloccare l’accesso a questa funzionalità.

Per inviare segmenti da Experienci Platform a Audienci Manager, contatta l’Assistenza clienti o il tuo Customer Success Manager. I team di gestione dell’Assistenza clienti e del Supporto clienti devono inviare un ticket (vedi il ticket modello AAM-52354) per abilitare la connessione da Platform all’Audience Manager.

Assicurati di condividere i piani per i dati che vanno da Platform a Audienci Manager, per garantire che la connessione sia configurata correttamente. Ad esempio, se hai bisogno di condividere dati regionali per segmenti inviati ad Adobe Target, queste informazioni devono essere comunicate nel ticket. La connessione di condivisione dei dati da Experienci Platform a Audienci Manager viene impostata entro sei giorni lavorativi dall’invio della richiesta.

### Utilizzare i segmenti Experienci Platform in Audienci Manager {#use-aep-data-in-aam}

I segmenti creati in Experienci Platform vengono visualizzati nell’interfaccia di Audienci Manager come segnali, caratteristiche e segmenti, con le seguenti regole di composizione:

* Segnale: per ogni segmento di Experience Platform, dovresti visualizzare i segnali nel modulo `segID = segment ID`.
* Caratteristica: la regola della caratteristica è l’ID del segmento di Experience Platform.
* Segmento: il segmento è costituito dalla caratteristica descritta sopra.

### Segnali {#aep-segments-as-aam-signals}

Seleziona **[!UICONTROL Audience Data > Signals > General Online Data]** e cerca per `SegId` per trovare i segnali provenienti da Experienci Platform. Puoi utilizzare questa schermata a scopo di debug, per verificare se l’integrazione tra Experienci Platform e Audienci Manager è stata impostata correttamente.

![Visualizza i segnali di Experience Platform in Audience Manager nel dashboard Segnali](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Caratteristiche  {#aep-segments-as-aam-traits}

Audienci Manager crea automaticamente una cartella di caratteristiche denominata **Caratteristiche Experienci Platform** nella memorizzazione delle caratteristiche.

![Caratteristiche dal dashboard Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Puoi utilizzare le caratteristiche create automaticamente nei segmenti insieme ad altre caratteristiche. Ad esempio, puoi combinare le caratteristiche create da segmenti Experienci Platform con le caratteristiche di terze parti acquisite tramite [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Per un esempio di una caratteristica creata automaticamente da un segmento di Experience Platform, vedi la schermata seguente:

![Caratteristica da Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Numero articolo | Nome | Descrizione |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Le caratteristiche create dai segmenti Experienci Platform vengono create come caratteristiche onboarded in Audienci Manager. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti Experienci Platform vengono memorizzati nell’origine dati **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento in Experienci Platform. |
| 4 | [!UICONTROL Trait Expression] | L’espressione della caratteristica è `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Segmento creato automaticamente che utilizza questa caratteristica come composizione. |

{style="table-layout:auto"}

### Segmenti  {#aep-segments-as-aam-segments}

Audienci Manager crea automaticamente una cartella di segmenti denominata **Segmenti Experienci Platform** nell’archiviazione dei segmenti.

![Schermata del dashboard](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Per un esempio di segmento creato automaticamente da un segmento di Experience Platform, vedi la schermata seguente:

![Schermata del segmento](/help/using/integration/integration-aep/assets/aep-segment.png)

| Numero articolo | Nome | Descrizione |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Il codice di integrazione corrisponde all’ID del segmento in Experienci Platform. |
| 2 | [!UICONTROL Data Source] | Creazione automatica. Tutte le caratteristiche e i segmenti creati automaticamente dai segmenti Experienci Platform vengono memorizzati nell’origine dati **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** indica che i segmenti creati automaticamente seguono il criterio di unione impostato in Experienci Platform. |
| 4 | [!UICONTROL Segment Rule] | Il segmento è costituito dalla caratteristica descritta nella [Sezione delle caratteristiche](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Audience Manager di supporto per il controllo dell&#39;esportazione dei dati in Experienci Platform {#aam-data-export-control-in-aep}

Al fine di applicare la conformità dell’utilizzo dei dati in Experienci Platform, tutti i set di dati e i campi applicabili devono essere forniti appropriati [etichette di utilizzo dei dati](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html). Inoltre, [criteri di utilizzo dati](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=it) devono essere abilitate per specifiche azioni di marketing su tali etichette, come indicato da [Framework DULE (Data Usage Labeling and Enforcement, etichettatura e applicazione dell’uso dei dati)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework).

Nel processo di condivisione del pubblico tra Audienci Manager e Experienci Platform, tutti i Controlli sull’esportazione dei dati applicati ai segmenti Audienci Manager vengono tradotti in etichette equivalenti e in azioni di marketing riconosciute dalla Governance dei dati Experienci Platform, e viceversa.

>[!NOTE]
>
>Per informazioni generali sui controlli sull&#39;esportazione dei dati, consulta [Documentazione sui controlli sull’esportazione dei dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
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
| Questa destinazione può essere utilizzata per il targeting di annunci nel sito | Pubblicità on-site |
| Questa destinazione può essere utilizzata per la personalizzazione degli annunci nel sito | Personalizzazione nel sito |

{style="table-layout:auto"}

## Comprendere le differenze di popolazione tra Audience Manager e Experience Platform {#aep-aam-segment-population-differences}

I numeri della popolazione del segmento possono variare tra i segmenti di Audience Manager e di Experience Platform. Anche se i numeri dei segmenti per tipi di pubblico simili o identici devono essere prossimi, le differenze nelle popolazioni possono essere dovute ai fattori elencati di seguito.

### Valutazione del segmento in Experienci Platform

Audienci Manager aggiorna i numeri di reporting nell’interfaccia una volta al giorno. La tempistica di questo aggiornamento raramente è allineata con quella della valutazione del segmento in Experienci Platform.

### Differenze tra le regole di unione profili e i criteri di unione

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) AUDIENCE MANAGER e [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) in Experienci Platform funziona in modo diverso e il grafico di identità utilizzato per ogni varia. Per questo motivo, sono attese alcune differenze tra le popolazioni dei segmenti.

>[!NOTE]
>
> Quando condividi segmenti da un Experience Platform a un Audience Manager, l’organizzazione Platform [criterio di unione predefinito](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) ha la precedenza sul [criterio di unione utilizzato dal segmento](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) condiviso con Audienci Manager. Ad esempio, se il criterio di unione del segmento condiviso consente [Unione ID](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure), ma il criterio di unione predefinito dell’organizzazione no, potrebbe causare differenze di popolazione tra Platform e Audienci Manager.

### Composizione del segmento in Experienci Platform

L’integrazione tra Adobe Experience Platform e Audienci Manager condivide una serie di [spazi dei nomi di identità](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) per tutti i clienti: ECID, IDFA, GAID, indirizzi e-mail con hash (EMAIL_LC_SHA256), AdCloud ID. Se i segmenti Experienci Platform utilizzano uno di questi come identità primaria per i profili qualificati, i profili vengono conteggiati in caratteristiche e segmenti Audienci Manager.

>[!NOTE]
>
> I tipi di pubblico in Experience Platform con identità ricavate da e-mail non elaborate non vengono mai visualizzati in Audienci Manager.

Ad esempio, se disponessi di un segmento di Experience Platform &quot;All my customers&quot; (Tutti i miei clienti) e i profili idonei fossero ID del sistema di gestione delle relazioni con i clienti, ECID, IDFA, indirizzi e-mail non elaborati e con hash, il segmento corrispondente in Audienci Manager includerebbe solo i profili ricavati da ECID, IDFA e indirizzi e-mail con hash. La popolazione del segmento in Audienci Manager sarebbe inferiore a quella in Experienci Platform.

![Experienci Platform Audience Manager di condivisione del segmento - composizione del segmento](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Panoramica del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Guida utente di Experienci Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Connettore Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
