---
description: 'Questa pagina include istruzioni dettagliate su come combinare dati CRM offline con dati comportamentali già presenti in Audience Manager per creare nuovi segmenti di pubblico, quindi inviare questi segmenti di pubblico a Destinazioni basate su Persone.  '
seo-description: 'Questa pagina include istruzioni dettagliate su come combinare dati CRM offline con dati comportamentali già presenti in Audience Manager per creare nuovi segmenti di pubblico, quindi inviare questi segmenti di pubblico a Destinazioni basate su Persone.   '
seo-title: Flusso di lavoro A - Personalizzazione basata su tutte le attività online combinate con dati offline
solution: Audience Manager
title: Flusso di lavoro A - Personalizzazione basata su tutte le attività online combinate con dati offline
translation-type: tm+mt
source-git-commit: fb5d9eff3573048d3e8a570b342a97bce3cd8da0

---


# Flusso di lavoro A - Personalizzazione basata su tutte le attività online combinate con dati offline {#workflow-a}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell'utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per assistenza legale.

Questa pagina include istruzioni dettagliate su come combinare [!DNL CRM] dati offline con dati comportamentali già presenti in Audience Manager per creare nuovi segmenti di pubblico e quindi inviare tali segmenti a [!DNL People-Based Destinations].

## Passaggio 1 - Configura impostazioni origine dati {#configure-data-source-settings}

A seconda che i vostri [DPUUID](../../reference/ids-in-aam.md) siano minuscoli, indirizzi e-mail con hash, potrebbe essere necessario configurare l'origine dati che memorizzerà gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail[DPUUID](../../reference/ids-in-aam.md)sono già minuscoli e con hash.**

In questo caso, è necessario etichettare l'origine dati corrispondente come tale:

1. Vai a [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. Individua l’origine dati che contiene i tuoi [DPUUID](../../reference/ids-in-aam.md)e fai clic su di essa.
1. Nel **[!UICONTROL ID Type]** menu a discesa, selezionate **[!UICONTROL Cross Device]**.
1. Accertatevi che l’opzione [!UICONTROL Cannot be tied to personally identifiable information] sia deselezionata.
1. Nella **[!UICONTROL Data Source Settings]** sezione, selezionate sia le **[!UICONTROL Inbound]** opzioni che le **[!UICONTROL Outbound]** opzioni e abilitate l' **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opzione.
1. Utilizzare il menu a discesa per selezionare l' **[!UICONTROL Emails(SHA256, lowercased)]** etichetta per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l'origine dati come contenente i dati con hash con tale algoritmo specifico. Audience Manager non esegue l'hash dei dati in questo passaggio. Assicurati che gli indirizzi e-mail che intendi memorizzare in questa origine dati siano già crittografati con l' [!DNL SHA256] algoritmo. In caso contrario, non potrai utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salvare le impostazioni dell'origine dati.

 

**Scenario 2: gli indirizzi e-mail[DPUUID](../../reference/ids-in-aam.md)non sono minuscoli e con hash.**

In questo caso, è necessario creare una nuova origine dati cross-device in cui memorizzare gli indirizzi e-mail con hash. Come procedere:

1. Log in to your Audience Manager account and go to  &gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]****[!UICONTROL Add New]**
1. Enter a  and  for your new data source.[!UICONTROL Name][!UICONTROL Description]
1. In the  drop-down menu, select .**[!UICONTROL ID Type]****[!UICONTROL Cross Device]**
1. In the  section, select both the  and  options, and enable the  option.**[!UICONTROL Data Source Settings]****[!UICONTROL Inbound]****[!UICONTROL Outbound]****[!UICONTROL Share associated cross-device IDs in people-based destinations]**
1. Use the drop-down menu to select the  label for this data source.**[!UICONTROL Emails(SHA256, lowercased)]**
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Make sure the email addresses that you plan on storing in this data source are already hashed with the  algorithm. [!DNL SHA256] Otherwise, you won't be able to use it for .[!DNL People-Based Destinations]

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Save the data source settings.

>[!NOTE]
>
> Consulta [Data onboarding](people-based-destinations-prerequisites.md#data-onboarding) per domande frequenti su come portare i dati offline in Audience Manager per le destinazioni basate su persone.

## Passaggio 2 - Corrispondenza DPUUID con indirizzi e-mail con hash tramite sincronizzazione ID basata su file {#match-ids-emails}

>[!IMPORTANT]
>
> This step only applies to Scenario 2 described above. [](people-based-destinations-workflow-combined.md#configure-data-source-settings) Se i [DPUUID](../../reference/ids-in-aam.md) esistenti sono già indirizzi e-mail con hash, passa al [Passaggio 3 - Crea una regola di unione dei profili per la segmentazione](people-based-destinations-workflow-combined.md#create-merge-rule).

Supponiamo che tu voglia far corrispondere i tuoi [DPUUID](../../reference/ids-in-aam.md) esistenti agli indirizzi e-mail con hash della tabella seguente (colonna a destra), e memorizzare gli indirizzi e-mail con hash nella nuova origine dati creata al [Passaggio 1 - Configura impostazioni](people-based-destinations-workflow-combined.md#configure-data-source-settings)origine dati.

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Potete collegare fino a 10 indirizzi e-mail con hash a un singolo [DPUUID](../../reference/ids-in-aam.md). A questo scopo, separate gli indirizzi e-mail con hash con una virgola all'interno del file di sincronizzazione.

Nel nostro esempio, ora ci sono due origini dati.

| ID origine dati | Contenuto origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

 

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

Dopo aver creato il file di sincronizzazione ID, devi caricarlo in un [!DNL Amazon S3] bucket. Per informazioni su come caricare i file di sincronizzazione ID, consulta [Inviare dati batch ad Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Passaggio 3: crea una regola di unione dei profili per la segmentazione {#create-merge-rule}

Il passo successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare alle tue destinazioni basate sulle persone.

>[!IMPORTANT]
>
> Se hai già una regola definita con le [!UICONTROL Current Authenticated Profiles] opzioni o [!UICONTROL Last Authenticated Profiles] , puoi passare al [Passaggio 4 - Crea segmenti](people-based-destinations-workflow-combined.md#create-audience-segments)di pubblico.

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**.
1. Fai clic su **[!UICONTROL Add New Rule]**.
1. Immettete una regola di unione dei profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. Nella **[!UICONTROL Profile Merge Rule Setup]** sezione selezionare le **[!UICONTROL Current Authenticated Profiles]** opzioni o **[!UICONTROL Last Authenticated Profiles]** .
1. Nell' **[!UICONTROL Cross-Device Profile Options]** elenco, selezionare le origini dati sulle quali eseguire la segmentazione. Devono essere le origini dati che contengono i [DPUUID](../../reference/ids-in-aam.md)esistenti.

## Passaggio 4 - Creazione di segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti di pubblico, utilizza il Generatore di [segmenti](../segments/segment-builder.md). Se hai segmenti di pubblico esistenti a cui vuoi inviare [!DNL People-Based Destinations], passa al [Passaggio 5 - Configura autenticazione](people-based-destinations-workflow-combined.md#configure-authentication)della piattaforma basata sulle persone.

## Step 5 - Configure People-Based Platform Authentication {#configure-authentication}

1. Log in to your Audience Manager account and go to  &gt; . **[!UICONTROL Administration]****[!UICONTROL Integrated Accounts]** If you have a previously configured integration with a social platform, you should see it listed in this page. Otherwise, the page is empty.
   ![people-based-integration](assets/pbd-config.png)
1. Fai clic su **[!UICONTROL Add Account]**.
1. Use the  drop-down menu to select the platform that you want to configure the integration with.**[!UICONTROL People-Based Platform]**
   ![people-based-platform](assets/pbd-add.png)
1. Click  to be redirected to the authentication page of the selected platform.**[!UICONTROL Confirm]**
1. Once you've authenticated to your social platform account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Selezionate l’account dell’inserzionista da usare e fate clic su **[!UICONTROL Confirm]**.
1. Audience Manager visualizza una notifica nella parte superiore della pagina per informarvi se l'account è stato aggiunto correttamente. The notification also allows you to add a contact email address to receive notifications when the social platform authentication is about to expire.

>[!IMPORTANT]
>
>A udience Manager handles the integration with social platforms through authentication tokens that expire after a certain amount of time. Consulta Rinnovo token di autenticazione per informazioni dettagliate su come rinnovare i token scaduti.

## Passaggio 6 - Creare una destinazione basata sulle persone {#create-destination}

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
1. Nella **[!UICONTROL Segment Mappings]** sezione, selezionate i segmenti che desiderate inviare a questa destinazione. Si tratta dei segmenti creati al [Passaggio 4 - Creazione di segmenti](people-based-destinations-workflow-combined.md#create-audience-segments)di pubblico.
1. Salva la destinazione.
