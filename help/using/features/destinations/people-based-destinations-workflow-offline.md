---
description: 'This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.  '
seo-description: 'This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.  '
seo-title: Flusso di lavoro B - Personalizzazione basata su dati solo offline
solution: Audience Manager
title: Workflow B - Personalization Based on Offline-Only Data
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Flusso di lavoro B - Personalizzazione basata su dati solo offline {#workflow-b}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell'utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per assistenza legale.

Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico dai dati dei clienti esclusivamente offline e inviarli alle destinazioni basate sulle persone.

## Passaggio 1 - Caratteristiche offline di bordo {#step-1-onboard-traits}

Il primo passo per la creazione di segmenti di pubblico in questo scenario è portare i dati dei clienti offline in Audience Manager.

>[!IMPORTANT]
>
> Prima di continuare, accertatevi che l’attività del cliente che state per imbarcare sia già definita in Audience Manager con le caratteristiche [registrate corrispondenti](../traits/trait-qualification-reference.md).

Indipendentemente dal fatto che gli ID cliente esistenti di Audience Manager ([DPUUID](../../reference/ids-in-aam.md)) siano o meno indirizzi e-mail con hash, devi eseguire l’onboarding delle caratteristiche rispetto all’origine dati che contiene i tuoi [DPUUID](../../reference/ids-in-aam.md).

### Esempio 

Desiderate qualificare gli ID cliente dalla tabella seguente per gli ID caratteristica caricati corrispondenti. Consideriamo che i tuoi [DPUUID](../../reference/ids-in-aam.md) sono memorizzati in un'origine dati con l'ID 999999 e l'ID partner Audience Manager è 123.

| ID cliente (DPUUID) | ID caratteristica integrato |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />
Per qualificare gli ID cliente nell'esempio precedente per le caratteristiche registrate corrispondenti, dovete caricare un [file di dati in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) con i seguenti contenuti:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

Il nome del file sarà simile al seguente: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Per informazioni dettagliate sulla struttura del nome del file, consultate Requisiti di nome e dimensione del file [Amazon S3 per i file](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) in entrata.

## Passaggio 2 - Configura impostazioni origine dati {#configure-data-source-settings}

A seconda che i vostri [DPUUID](../../reference/ids-in-aam.md) siano minuscoli, indirizzi e-mail con hash, potrebbe essere necessario configurare l'origine dati che memorizzerà gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail[DPUUID](../../reference/ids-in-aam.md)sono già minuscoli e con hash.**

In questo caso, è necessario etichettare l'origine dati corrispondente come tale:

1. Vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**.
1. Individua l’origine dati che contiene i tuoi [DPUUID](../../reference/ids-in-aam.md)e fai clic su di essa.
1. Accertatevi che l’opzione **[!UICONTROL Cannot be tied to personally identifiable information]** sia deselezionata.
1. Salvare le impostazioni dell'origine dati.

 

**Scenario 2: gli indirizzi e-mail[DPUUID](../../reference/ids-in-aam.md)non sono minuscoli e con hash.**

In questo caso, è necessario creare una nuova origine dati cross-device in cui memorizzare gli indirizzi e-mail con hash. Come procedere:

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**, quindi fai clic su **[!UICONTROL Add New]**.
1. Enter a  and  for your new data source.**[!UICONTROL Name]****[!UICONTROL Description]**
1. Nel **[!UICONTROL ID Type]** menu a discesa, selezionate **[!UICONTROL Cross Device]**.
1. In the  section, select both the  and  options, and enable the  option.**[!UICONTROL Data Source Settings]****[!UICONTROL Inbound]****[!UICONTROL Outbound]****[!UICONTROL Share associated cross-device IDs in people-based destinations]**
1. Use the drop-down menu to select the  label for this data source.**[!UICONTROL Emails(SHA256, lowercased)]**
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Make sure the email addresses that you plan on storing in this data source are already hashed with the  algorithm. [!DNL SHA256] Otherwise, you won't be able to use it for .[!DNL People-Based Destinations]

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > See Data Onboarding for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.[](people-based-destinations-prerequisites.md#data-onboarding)

## Step 3 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> This step only applies to Scenario 2 described above. [](people-based-destinations-workflow-offline.md#configure-data-source-settings) Se i [DPUUID](../../reference/ids-in-aam.md) esistenti sono già indirizzi e-mail con hash, passa al [Passaggio 4 - Crea una regola di unione dei profili per la segmentazione](#create-profile-merge-rule).

Let's say you want to match your existing DPUUIDs from the example at Step 1 to the hashed email addresses from the table below (right column), and store the hashed email addresses in the new data source that you created at Step 2 - Configure Data Source Settings.[](../../reference/ids-in-aam.md)[](#configure-data-source-settings)

As a reminder, you would now have two data sources:

| Data source ID | Data source contents |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Il file [di sincronizzazione](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ID avrebbe i seguenti contenuti:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Il file [di sincronizzazione](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ID deve seguire la seguente struttura di denominazione:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Nell'esempio precedente, il nome del file sarà simile al seguente:
`c2c_id_999999_987654_1560431657.sync`

[Scarica il file di esempio qui](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

## Passaggio 4 - Crea una regola di unione dei profili per la segmentazione {#create-profile-merge-rule}

Il passo successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare al tuo [!DNL People-Based Destinations].

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Clic [!UICONTROL Add New Rule].
3. Immettete una regola di unione dei profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Nella **[!UICONTROL Profile Merge Rule Setup]** sezione, selezionare la **[!UICONTROL All Cross-Device Profiles]** regola dall' **[!UICONTROL Cross-Device Options]** elenco.
5. Nell' **[!UICONTROL Cross-Device Profile Options]** elenco, selezionare l'origine dati rispetto alla quale sono registrate le caratteristiche.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Passaggio 5 - Creazione di segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti da dati esclusivamente offline, utilizza il Generatore [di](../segments/segment-builder.md) segmenti e accertati di utilizzare la nuova regola di unione di profilo creata nel passaggio precedente al momento della creazione del segmento.

## Passaggio 6 - Configurare l'autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Se avete già configurato un'integrazione con una piattaforma social, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
1. Fai clic su **[!UICONTROL Add Account]**.
1. Utilizzate il menu a **[!UICONTROL People-Based Platform]** discesa per selezionare la piattaforma con cui desiderate configurare l'integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
1. Fare clic per **[!UICONTROL Confirm]** essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
1. Dopo aver eseguito l'autenticazione sull'account della piattaforma social, verrete reindirizzati ad Audience Manager, dove dovrebbero essere visualizzati gli account degli inserzionisti associati. Selezionate l’account dell’inserzionista da usare e fate clic su **[!UICONTROL Confirm]**.
1. Audience Manager visualizza una notifica nella parte superiore della pagina per informarvi se l'account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere le notifiche quando l'autenticazione della piattaforma social sta per scadere.

>[!IMPORTANT]
>
>Un Audience Manager gestisce l'integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Consulta Rinnovo token di autenticazione per informazioni dettagliate su come rinnovare i token scaduti.

## Passaggio 7 - Creare una destinazione basata sulle persone {#create-destination}

1. Accedi al tuo account Audience Manager, vai a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** e fai clic su **[!UICONTROL Create Destination]**.
1. Nella **[!UICONTROL Basic Information]** sezione immettere una **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati e utilizzare le seguenti impostazioni:
   * **[!UICONTROL Category]**: Piattaforme integrate;
   * **[!UICONTROL Type]**: Persone;
   * **[!UICONTROL Platform]**: selezionate la piattaforma basata sulle persone a cui desiderate inviare i segmenti di pubblico;
   * **[!UICONTROL Account]**: selezionate l'account dell'inserzionista desiderato associato alla piattaforma selezionata.
      ![create-Destination](assets/pbd-create-destination.png)
1. Fai clic su **[!UICONTROL Next]**.
1. Scegliere l' **[!UICONTROL Data Export Labels]** impostazione da impostare per la destinazione.
1. Nella **[!UICONTROL Configuration]** sezione, selezionare l'origine dati che contiene le origini dati con hash.
1. Nella **[!UICONTROL Segment Mappings]** sezione, selezionate i segmenti che desiderate inviare a questa destinazione. Si tratta dei segmenti creati al [Passaggio 5 - Creazione di segmenti](people-based-destinations-workflow-offline.md#create-audience-segments)di pubblico.
1. Salva la destinazione.
