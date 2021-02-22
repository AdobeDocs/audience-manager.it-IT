---
description: 'Questa pagina include istruzioni dettagliate su come combinare i dati CRM offline con i dati comportamentali già disponibili in  Audience Manager per creare nuovi segmenti di pubblico, quindi inviare questi segmenti di pubblico a Destinazioni basate su Persone.  '
seo-description: 'Questa pagina include istruzioni dettagliate su come combinare i dati CRM offline con i dati comportamentali già disponibili in  Audience Manager per creare nuovi segmenti di pubblico, quindi inviare questi segmenti di pubblico a Destinazioni basate su Persone.   '
seo-title: 'Flusso di lavoro A: personalizzazione basata su tutte le attività online combinate con dati offline'
solution: Audience Manager
title: 'Flusso di lavoro A: personalizzazione basata su tutte le attività online combinate con dati offline'
feature: Destinazioni basate su persone
translation-type: tm+mt
source-git-commit: 6e3a06da8149c91a9192b5b3ee582e46fbb1790c
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 7%

---


# Flusso di lavoro A: personalizzazione basata su tutte le attività online combinate con dati offline {#workflow-a}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

Questa pagina include istruzioni dettagliate su come combinare i dati offline [!DNL CRM] con i dati comportamentali già disponibili in  Audience Manager per creare nuovi segmenti di pubblico, quindi inviare tali segmenti a [!DNL People-Based Destinations].

## Passaggio 1 - Configura impostazioni origine dati {#configure-data-source-settings}

A seconda che gli [DPUUID](../../reference/ids-in-aam.md) siano minuscoli, indirizzi e-mail con hash, potrebbe essere necessario configurare l&#39;origine dati che memorizzerà gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail  [](../../reference/ids-in-aam.md) DPUUID sono già minuscoli e con hash.**

In questo caso, è necessario etichettare l&#39;origine dati corrispondente come tale:

1. Vai a [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Individuare l&#39;origine dati che contiene i [DPUUID](../../reference/ids-in-aam.md) e fare clic su di essa.
1. Nel menu a discesa **[!UICONTROL ID Type]**, selezionare **[!UICONTROL Cross Device]**.
1. Assicurarsi che l&#39;opzione [!UICONTROL Cannot be tied to personally identifiable information] sia deselezionata.
1. Nella sezione **[!UICONTROL Data Source Settings]**, selezionare le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e attivare l&#39;opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilizzare il menu a discesa per selezionare l&#39;etichetta **[!UICONTROL Emails(SHA256, lowercased)]** per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l&#39;origine dati come contenente i dati con hash con tale algoritmo specifico.  Audience Manager non esegue l&#39;hash dei dati in questo passaggio. Assicurati che gli indirizzi e-mail che intendi memorizzare in questa origine dati siano già crittografati con l&#39;algoritmo [!DNL SHA256]. In caso contrario, non sarà possibile utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salvare le impostazioni dell&#39;origine dati.

 

**Scenario 2: gli indirizzi e-mail  [](../../reference/ids-in-aam.md) DPUUID non sono minuscoli e con hash.**

In questo caso, è necessario creare una nuova origine dati cross-device in cui memorizzare gli indirizzi e-mail con hash. Come procedere:

1. Accedete al vostro account  Audience Manager e andate a **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**, quindi fate clic su **[!UICONTROL Add New]**.
1. Immettere un [!UICONTROL Name] e [!UICONTROL Description] per la nuova origine dati.
1. Nel menu a discesa **[!UICONTROL ID Type]**, selezionare **[!UICONTROL Cross Device]**.
1. Nella sezione **[!UICONTROL Data Source Settings]**, selezionare le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e attivare l&#39;opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilizzare il menu a discesa per selezionare l&#39;etichetta **[!UICONTROL Emails(SHA256, lowercased)]** per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l&#39;origine dati come contenente i dati con hash con tale algoritmo specifico.  Audience Manager non esegue l&#39;hash dei dati in questo passaggio. Assicurati che gli indirizzi e-mail che intendi memorizzare in questa origine dati siano già crittografati con l&#39;algoritmo [!DNL SHA256]. In caso contrario, non sarà possibile utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salvare le impostazioni dell&#39;origine dati.

Guardate il video seguente per un&#39;esercitazione video su come creare un&#39;origine dati per [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Consulta [Data Onboarding](people-based-destinations-prerequisites.md#data-onboarding) per le domande frequenti su come portare i dati offline in  Audience Manager per le destinazioni basate sulle persone.

## Passaggio 2 - Corrispondenza DPUUID con indirizzi e-mail con hash tramite sincronizzazione ID basata su file {#match-ids-emails}

>[!IMPORTANT]
>
> Questo passaggio si applica solo a [Scenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descritto sopra. Se gli [DPUUID ](../../reference/ids-in-aam.md) esistenti sono già indirizzi e-mail con hashing, passate a [Passaggio 3 - Create a Profile Merge Rule for Segmentation](people-based-destinations-workflow-combined.md#create-merge-rule) (Crea una regola di unione dei profili per la segmentazione).

Supponiamo che si desideri far corrispondere gli [DPUUID ](../../reference/ids-in-aam.md) esistenti agli indirizzi e-mail con hash dalla tabella seguente (colonna a destra), e memorizzare gli indirizzi e-mail con hash nella nuova origine dati creata in [Passaggio 1 - Configura impostazioni origine dati](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 8915902479676034373311707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

È possibile collegare fino a 10 indirizzi e-mail con hash a un singolo [DPUUID](../../reference/ids-in-aam.md). A tal fine, separate gli indirizzi e-mail con hash con un `<TAB>` all&#39;interno del file di sincronizzazione.

Nel nostro esempio, ora ci sono due origini dati.

| ID origine dati | Contenuto origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

 

Il file di sincronizzazione [ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) avrebbe i seguenti contenuti:

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

## Passaggio 3 - Crea una regola di unione dei profili per la segmentazione {#create-merge-rule}

Il passo successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare alle tue destinazioni basate sulle persone.

>[!IMPORTANT]
>
> Se hai già una regola definita con le opzioni [!UICONTROL Current Authenticated Profiles] o [!UICONTROL Last Authenticated Profiles], puoi passare a [Passaggio 4 - Crea segmenti di pubblico](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Accedete al vostro account  Audience Manager e andate a **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Clic **[!UICONTROL Add New Rule]**.
1. Immettere una regola di unione dei profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. Nella sezione **[!UICONTROL Profile Merge Rule Setup]**, selezionare le opzioni **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**.
1. Nell&#39;elenco **[!UICONTROL Cross-Device Profile Options]**, selezionare le origini dati sulle quali si desidera eseguire la segmentazione. Devono essere le origini dati che contengono gli [DPUUID ](../../reference/ids-in-aam.md) esistenti.

## Passaggio 4 - Creazione di segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti di pubblico, utilizzate il Generatore di segmenti [](../segments/segment-builder.md). Se si dispone di segmenti di pubblico esistenti da inviare a [!DNL People-Based Destinations], passare a [Passaggio 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone](people-based-destinations-workflow-combined.md#configure-authentication).

## Passaggio 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone {#configure-authentication}

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
>Un Audience Manager gestisce l&#39;integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Consulta Rinnovo token di autenticazione per informazioni dettagliate su come rinnovare i token scaduti.

## Passaggio 6 - Creare una destinazione basata sulle persone {#create-destination}

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
1. Nella sezione **[!UICONTROL Segment Mappings]**, selezionare i segmenti che si desidera inviare a questa destinazione. Si tratta dei segmenti creati al [Passaggio 4 - Create Audience Segments](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Salva la destinazione.
