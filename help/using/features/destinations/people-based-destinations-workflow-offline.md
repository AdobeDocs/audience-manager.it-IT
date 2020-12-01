---
description: 'Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico dai dati dei clienti esclusivamente offline e inviarli alle destinazioni basate sulle persone.  '
seo-description: 'Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico dai dati dei clienti esclusivamente offline e inviarli alle destinazioni basate sulle persone.  '
seo-title: 'Flusso di lavoro B: personalizzazione basata su dati solo offline'
solution: Audience Manager
title: 'Flusso di lavoro B: personalizzazione basata su dati solo offline'
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 6%

---


# Flusso di lavoro B: personalizzazione basata su dati solo offline {#workflow-b}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico dai dati dei clienti esclusivamente offline e inviarli alle destinazioni basate sulle persone.

## Passaggio 1 - Caratteristiche offline di bordo {#step-1-onboard-traits}

Il primo passo per la creazione di segmenti di pubblico in questo scenario è portare i dati dei clienti offline in  Audience Manager.

>[!IMPORTANT]
>
> Prima di continuare, accertatevi che l&#39;attività del cliente che state per imbarcare sia già definita in  Audience Manager con le corrispondenti [caratteristiche registrate](../traits/trait-and-segment-qualification-reference.md).

Indipendentemente dal fatto che gli ID cliente  Audience Manager esistenti ([DPUUIDs](../../reference/ids-in-aam.md)) siano o meno crittografati, è necessario eseguire l&#39;onboarding della caratteristica rispetto all&#39;origine dati che contiene i [DPUUID](../../reference/ids-in-aam.md).

### Esempio

Desiderate qualificare gli ID cliente dalla tabella seguente per gli ID caratteristica caricati corrispondenti. Consideriamo che i [DPUUID](../../reference/ids-in-aam.md) sono memorizzati in un&#39;origine dati con l&#39;ID 999999 e l&#39;ID  partner del Audience Manager è 123.

| ID cliente (DPUUID) | ID caratteristica integrato |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 8915902479676034373311707646026765593 | 11223, 93342, 27341 |

<br />

Per qualificare gli ID cliente nell&#39;esempio precedente per le caratteristiche registrate corrispondenti, è necessario caricare un file di dati in entrata [](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) con i seguenti contenuti:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

Il nome del file sarà simile al seguente: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Per informazioni dettagliate sulla struttura del nome del file, vedere [ requisiti di nome e dimensione del file Amazon S3 per i file di dati in ingresso](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

## Passaggio 2 - Configura impostazioni origine dati {#configure-data-source-settings}

A seconda che gli [DPUUID](../../reference/ids-in-aam.md) siano minuscoli, indirizzi e-mail con hash, potrebbe essere necessario configurare l&#39;origine dati che memorizzerà gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail  [](../../reference/ids-in-aam.md) DPUUID sono già minuscoli e con hash.**

In questo caso, è necessario etichettare l&#39;origine dati corrispondente come tale:

1. Vai a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. Individuare l&#39;origine dati che contiene i [DPUUID](../../reference/ids-in-aam.md) e fare clic su di essa.
1. Assicurarsi che l&#39;opzione **[!UICONTROL Cannot be tied to personally identifiable information]** sia deselezionata.
1. Salvare le impostazioni dell&#39;origine dati.

 

**Scenario 2: gli indirizzi e-mail  [](../../reference/ids-in-aam.md) DPUUID non sono minuscoli e con hash.**

In questo caso, è necessario creare una nuova origine dati cross-device in cui memorizzare gli indirizzi e-mail con hash. Come procedere:

1. Accedete al vostro account  Audience Manager e andate a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, quindi fate clic su **[!UICONTROL Add New]**.
1. Immettere un **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati.
1. Nel menu a discesa **[!UICONTROL ID Type]**, selezionare **[!UICONTROL Cross Device]**.
1. Nella sezione **[!UICONTROL Data Source Settings]**, selezionare le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e attivare l&#39;opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilizzare il menu a discesa per selezionare l&#39;etichetta **[!UICONTROL Emails(SHA256, lowercased)]** per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l&#39;origine dati come contenente i dati con hash con tale algoritmo specifico.  Audience Manager non esegue l&#39;hash dei dati in questo passaggio. Assicurati che gli indirizzi e-mail che intendi memorizzare in questa origine dati siano già crittografati con l&#39;algoritmo [!DNL SHA256]. In caso contrario, non sarà possibile utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulta [Data Onboarding](people-based-destinations-prerequisites.md#data-onboarding) per le domande frequenti su come portare i dati offline in  Audience Manager per le destinazioni basate sulle persone.

Guardate il video seguente per un&#39;esercitazione video su come creare un&#39;origine dati per [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Passaggio 3 - Corrispondenza DPUUID con indirizzi e-mail con hash tramite sincronizzazione ID basata su file {#match-ids-emails}

>[!IMPORTANT]
>
> Questo passaggio si applica solo a [Scenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descritto sopra. Se gli [DPUUID ](../../reference/ids-in-aam.md) esistenti sono già indirizzi e-mail con hashing, passate a [Passaggio 4 - Create a Profile Merge Rule for Segmentation](#create-profile-merge-rule) (Crea una regola di unione dei profili per la segmentazione).

Supponiamo di voler far corrispondere gli [DPUUID](../../reference/ids-in-aam.md) esistenti dall&#39;esempio al Passaggio 1 agli indirizzi e-mail con hash dalla tabella seguente (colonna a destra), e memorizzare gli indirizzi e-mail con hash nella nuova origine dati creata al [Passaggio 2 - Configura impostazioni origine dati](#configure-data-source-settings).

Come promemoria, ora hai due origini dati:

| ID origine dati | Contenuto origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 8915902479676034373311707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Nel nostro esempio, il file di sincronizzazione [ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) avrebbe i seguenti contenuti:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Il file di sincronizzazione [ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) deve seguire la seguente struttura di denominazione:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Nell&#39;esempio precedente, il nome del file sarà simile al seguente:
`c2c_id_999999_987654_1560431657.sync`

[Scarica il file di esempio qui](assets/c2c_id_999999_987654_1560431657.sync).

Dopo aver creato il file di sincronizzazione ID, devi caricarlo in un [!DNL Amazon S3] bucket. Per informazioni su come caricare i file di sincronizzazione ID, vedi [Invia dati batch a  Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Passaggio 4 - Crea una regola di unione dei profili per la segmentazione {#create-profile-merge-rule}

Il passo successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare al tuo [!DNL People-Based Destinations].

1. Accedete al vostro account  Audience Manager e andate a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Clic [!UICONTROL Add New Rule].
3. Immettere una regola di unione dei profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Nella sezione **[!UICONTROL Profile Merge Rule Setup]**, selezionare la regola **[!UICONTROL All Cross-Device Profiles]** dall&#39;elenco **[!UICONTROL Cross-Device Options]**.
5. Nell&#39;elenco **[!UICONTROL Cross-Device Profile Options]**, selezionare l&#39;origine dati rispetto alla quale sono registrate le caratteristiche.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Passaggio 5 - Creazione di segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti da dati esclusivamente offline, utilizzate il [Generatore di segmenti](../segments/segment-builder.md) e accertatevi di utilizzare la nuova regola di unione dei profili creata nel passaggio precedente al momento della creazione del segmento.

## Passaggio 6 - Configurare l&#39;autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedete al vostro account  Audience Manager e andate a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se avete già configurato un&#39;integrazione con una piattaforma social, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
1. Clic **[!UICONTROL Add Account]**.
1. Utilizzate il menu a discesa **[!UICONTROL People-Based Platform]** per selezionare la piattaforma con cui desiderate configurare l&#39;integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
1. Fare clic su **[!UICONTROL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
1. Dopo aver eseguito l&#39;autenticazione sull&#39;account della tua piattaforma sociale, verrai reindirizzato  Audience Manager in cui dovresti vedere gli account dell&#39;inserzionista associato. Selezionate l&#39;account dell&#39;inserzionista che desiderate utilizzare e fate clic su **[!UICONTROL Confirm]**.
1.  Audience Manager visualizza una notifica nella parte superiore della pagina per informarvi se l’account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere le notifiche quando l&#39;autenticazione della piattaforma social sta per scadere.

>[!IMPORTANT]
>
> Audience Manager gestisce l&#39;integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Consulta Rinnovo token di autenticazione per informazioni dettagliate su come rinnovare i token scaduti.

## Passaggio 7 - Creare una destinazione basata sulle persone {#create-destination}

1. Accedete al vostro account  Audience Manager, andate a **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** e fate clic su **[!UICONTROL Create Destination]**.
1. Nella sezione **[!UICONTROL Basic Information]**, immettere **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati e utilizzare le seguenti impostazioni:
   * **[!UICONTROL Category]**: Piattaforme integrate;
   * **[!UICONTROL Type]**: Persone;
   * **[!UICONTROL Platform]**: selezionate la piattaforma basata sulle persone a cui desiderate inviare i segmenti di pubblico;
   * **[!UICONTROL Account]**: selezionate l&#39;account dell&#39;inserzionista desiderato associato alla piattaforma selezionata.
      ![create-Destination](assets/pbd-create-destination.png)
1. Clic **[!UICONTROL Next]**.
1. Scegliere la **[!UICONTROL Data Export Labels]** che si desidera impostare per questa destinazione.
1. Nella sezione **[!UICONTROL Configuration]**, selezionare l&#39;origine dati che contiene le origini dati con hash.
1. Nella sezione **[!UICONTROL Segment Mappings]**, selezionare i segmenti che si desidera inviare a questa destinazione. Si tratta dei segmenti creati al [Passo 5 - Create Audience Segments](people-based-destinations-workflow-offline.md#create-audience-segments).
1. Salva la destinazione.
