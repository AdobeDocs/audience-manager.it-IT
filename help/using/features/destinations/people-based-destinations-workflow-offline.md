---
description: 'Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico dai dati dei clienti esclusivamente offline e inviarli alle destinazioni basate sulle persone.  '
seo-description: 'Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico dai dati dei clienti esclusivamente offline e inviarli alle destinazioni basate sulle persone.  '
seo-title: Flusso di lavoro B - Personalizzazione basata su dati solo offline
solution: Audience Manager
title: Flusso di lavoro B - Personalizzazione basata su dati solo offline
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

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

| Customer ID (DPUUID) | Onboarded Trait ID |
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
See Amazon S3 Name and File Size Requirements for Inbound Data Files for detailed information on the file name structure.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

## Passaggio 2 - Configura impostazioni origine dati {#configure-data-source-settings}

A seconda che i vostri [DPUUID](../../reference/ids-in-aam.md) siano minuscoli, indirizzi e-mail con hash, potrebbe essere necessario configurare l'origine dati che memorizzerà gli indirizzi e-mail con hash.

 

**Scenario 1: your DPUUIDs are already lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In questo caso, è necessario etichettare l'origine dati corrispondente come tale:

1. Vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**.
1. Individua l’origine dati che contiene i tuoi [DPUUID](../../reference/ids-in-aam.md)e fai clic su di essa.
1. Accertatevi che l’opzione **[!UICONTROL Cannot be tied to personally identifiable information]** sia deselezionata.
1. Salvare le impostazioni dell'origine dati.

 

**Scenario 2: your DPUUIDs are not lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to create a new cross-device data source that will store your hashed email addresses. Here's how to do this:

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**, quindi fai clic su **[!UICONTROL Add New]**.
1. Enter a  and  for your new data source.**[!UICONTROL Name]****[!UICONTROL Description]**
1. Nel **[!UICONTROL ID Type]** menu a discesa, selezionate **[!UICONTROL Cross Device]**.
1. Nella **[!UICONTROL Data Source Settings]** sezione, selezionate sia le **[!UICONTROL Inbound]** opzioni che le **[!UICONTROL Outbound]** opzioni e abilitate l' **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opzione.
1. Utilizzare il menu a discesa per selezionare l' **[!UICONTROL Emails(SHA256, lowercased)]** etichetta per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l'origine dati come contenente i dati con hash con tale algoritmo specifico. Audience Manager non esegue l'hash dei dati in questo passaggio. Assicurati che gli indirizzi e-mail che intendi memorizzare in questa origine dati siano già crittografati con l' [!DNL SHA256] algoritmo. In caso contrario, non potrai utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulta [Data onboarding](people-based-destinations-prerequisites.md#data-onboarding) per domande frequenti su come portare i dati offline in Audience Manager per le destinazioni basate su persone.

## Passaggio 3 - Corrispondenza DPUUID con indirizzi e-mail con hash tramite sincronizzazione ID basata su file {#match-ids-emails}

>[!IMPORTANT]
>
> Questo passaggio si applica solo allo [scenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) sopra descritto. Se i [DPUUID](../../reference/ids-in-aam.md) esistenti sono già indirizzi e-mail con hash, passa al [Passaggio 4 - Crea una regola di unione dei profili per la segmentazione](#create-profile-merge-rule).

Supponiamo che desideri far corrispondere i tuoi [DPUUID](../../reference/ids-in-aam.md) esistenti dall'esempio al Passaggio 1 agli indirizzi e-mail con hash dalla tabella seguente (colonna a destra), e memorizzare gli indirizzi e-mail con hash nella nuova origine dati creata al [Passaggio 2 - Configura impostazioni](#configure-data-source-settings)origine dati.

Come promemoria, ora hai due origini dati:

| ID origine dati | Contenuto origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Nel nostro esempio, il file [di sincronizzazione](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) ID avrebbe i seguenti contenuti:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

The ID synchronization file must follow this naming structure:[](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Nell'esempio precedente, il nome del file sarà simile al seguente:
`c2c_id_999999_987654_1560431657.sync`

[Download example file here.](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)

Once you've created your ID synchronization file, you need to upload it to an  bucket. [!DNL Amazon S3] To learn how to upload ID synchronization files, see Send Batch Data to Audience Manager.[](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)

## Passaggio 4 - Crea una regola di unione dei profili per la segmentazione {#create-profile-merge-rule}

Il passo successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare al tuo [!DNL People-Based Destinations].

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Clic [!UICONTROL Add New Rule].
3. Enter a profile merge rule  and .**[!UICONTROL Name]****[!UICONTROL Description]**
4. Nella **[!UICONTROL Profile Merge Rule Setup]** sezione, selezionare la **[!UICONTROL All Cross-Device Profiles]** regola dall' **[!UICONTROL Cross-Device Options]** elenco.
5. Nell' **[!UICONTROL Cross-Device Profile Options]** elenco, selezionare l'origine dati rispetto alla quale sono registrate le caratteristiche.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Passaggio 5 - Creazione di segmenti di pubblico {#create-audience-segments}

To create new segments from offline-only data, use the Segment Builder and make sure you use the new profile merge rule that you created in the previous step when creating the segment.[](../segments/segment-builder.md)

## Step 6 - Configure People-Based Platform Authentication {#configure-authentication}

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Se avete già configurato un'integrazione con una piattaforma social, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
   ![people-based-integration](assets/pbd-config.png)
1. Fai clic su **[!UICONTROL Add Account]**.
1. Utilizzate il menu a **[!UICONTROL People-Based Platform]** discesa per selezionare la piattaforma con cui desiderate configurare l'integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
1. Click  to be redirected to the authentication page of the selected platform.**[!UICONTROL Confirm]**
1. Dopo aver eseguito l'autenticazione sull'account della piattaforma social, verrete reindirizzati ad Audience Manager, dove dovrebbero essere visualizzati gli account degli inserzionisti associati. Selezionate l’account dell’inserzionista da usare e fate clic su **[!UICONTROL Confirm]**.
1. Audience Manager visualizza una notifica nella parte superiore della pagina per informarvi se l'account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere le notifiche quando l'autenticazione della piattaforma social sta per scadere.

>[!IMPORTANT]
>
>Audience Manager gestisce l'integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Consulta Rinnovo token di autenticazione per informazioni dettagliate su come rinnovare i token scaduti.

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
1. In the  section, select the segments that you want to send to this destination. **[!UICONTROL Segment Mappings]** Si tratta dei segmenti creati al [Passaggio 5 - Creazione di segmenti](people-based-destinations-workflow-offline.md#create-audience-segments)di pubblico.
1. Save the destination.
