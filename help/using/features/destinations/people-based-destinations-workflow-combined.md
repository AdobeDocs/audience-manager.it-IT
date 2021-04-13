---
description: 'Questa pagina include indicazioni dettagliate su come combinare dati CRM offline con dati comportamentali già in uso in Audience Manager per creare nuovi segmenti di pubblico e quindi inviare questi segmenti di pubblico a Destinazioni basate su persone.  '
seo-description: 'Questa pagina include indicazioni dettagliate su come combinare dati CRM offline con dati comportamentali già in uso in Audience Manager per creare nuovi segmenti di pubblico e quindi inviare questi segmenti di pubblico a Destinazioni basate su persone.   '
seo-title: 'Flusso di lavoro A: personalizzazione basata su tutte le attività online combinate con dati offline'
solution: Audience Manager
title: 'Flusso di lavoro A: personalizzazione basata su tutte le attività online combinate con dati offline'
feature: Destinazioni basate su persone
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 7%

---

# Flusso di lavoro A: personalizzazione basata su tutte le attività online combinate con dati offline {#workflow-a}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

Questa pagina include indicazioni dettagliate su come combinare dati [!DNL CRM] offline con dati comportamentali già disponibili in Audience Manager per creare nuovi segmenti di pubblico, quindi inviare questi segmenti di pubblico a [!DNL People-Based Destinations].

## Passaggio 1: configurare le impostazioni delle origini dati {#configure-data-source-settings}

A seconda che i [DPUUID](../../reference/ids-in-aam.md) siano minuscole o meno, gli indirizzi e-mail con hash potrebbero essere necessari per configurare l&#39;origine dati in cui verranno memorizzati gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail con hash  [](../../reference/ids-in-aam.md) DPUUID sono già minuscoli.**

In questo caso, è necessario etichettare l’origine dati corrispondente come tale:

1. Vai a [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Trova l&#39;origine dati contenente i [DPUUID](../../reference/ids-in-aam.md) e fai clic su di essa.
1. Nel menu a discesa **[!UICONTROL ID Type]**, seleziona **[!UICONTROL Cross Device]**.
1. Assicurati che l’opzione [!UICONTROL Cannot be tied to personally identifiable information] sia deselezionata.
1. Nella sezione **[!UICONTROL Data Source Settings]** , seleziona entrambe le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e abilita l’opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilizza il menu a discesa per selezionare l’etichetta **[!UICONTROL Emails(SHA256, lowercased)]** per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l’origine dati come contenente dati con hash con quell’algoritmo specifico. In questo passaggio Audience Manager non esegue l’hash dei dati. Assicurati che gli indirizzi e-mail che intendi memorizzare in questa origine dati siano già contraddistinti dall’algoritmo [!DNL SHA256]. In caso contrario, non potrai utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salva le impostazioni dell’origine dati.

 

**Scenario 2: gli indirizzi e-mail con hash  [](../../reference/ids-in-aam.md) DPUUID non sono minuscoli.**

In questo caso, devi creare una nuova origine dati multi-dispositivo che memorizzerà gli indirizzi e-mail con hash. Ecco come eseguire questa operazione:

1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**, quindi fai clic su **[!UICONTROL Add New]**.
1. Immetti una [!UICONTROL Name] e [!UICONTROL Description] per la nuova origine dati.
1. Nel menu a discesa **[!UICONTROL ID Type]**, seleziona **[!UICONTROL Cross Device]**.
1. Nella sezione **[!UICONTROL Data Source Settings]** , seleziona entrambe le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e abilita l’opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilizza il menu a discesa per selezionare l’etichetta **[!UICONTROL Emails(SHA256, lowercased)]** per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l’origine dati come contenente dati con hash con quell’algoritmo specifico. In questo passaggio Audience Manager non esegue l’hash dei dati. Assicurati che gli indirizzi e-mail che intendi memorizzare in questa origine dati siano già contraddistinti dall’algoritmo [!DNL SHA256]. In caso contrario, non potrai utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salva le impostazioni dell’origine dati.

Guarda il video seguente per un&#39;esercitazione video su come creare un&#39;origine dati per [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Consulta [Onboarding dei dati](people-based-destinations-prerequisites.md#data-onboarding) per le domande frequenti su come inserire i dati offline in Audience Manager per le destinazioni basate su persone.

## Passaggio 2: associare DPUUID agli indirizzi e-mail con hash tramite sincronizzazione ID basata su file {#match-ids-emails}

>[!IMPORTANT]
>
> Questo passaggio si applica solo allo [Scenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descritto sopra. Se gli [DPUUID](../../reference/ids-in-aam.md) esistenti sono già indirizzi e-mail con hash, passa a [Passaggio 3 - Creare una regola di unione profili per la segmentazione](people-based-destinations-workflow-combined.md#create-merge-rule).

Supponiamo che desideri far corrispondere gli [DPUUID](../../reference/ids-in-aam.md) esistenti agli indirizzi e-mail con hash dalla tabella seguente (colonna a destra) e archiviare gli indirizzi e-mail con hash nella nuova origine dati creata in [Passaggio 1 - Configurare le impostazioni delle origini dati](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 8915902479676034373311707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Puoi collegare fino a 10 indirizzi e-mail con hash a un singolo [DPUUID](../../reference/ids-in-aam.md). A questo scopo, separa gli indirizzi e-mail con hash con un `<TAB>` all’interno del file di sincronizzazione.

Nel nostro esempio, ora si dispone di due origini dati.

| ID origine dati | Contenuto dell&#39;origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

 

Il tuo [file di sincronizzazione ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) avrebbe i seguenti contenuti:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Il [file di sincronizzazione ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) deve seguire questa struttura di denominazione:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Nell’esempio precedente, il nome del file sarà simile al seguente:
`c2c_id_999999_987654_1560431657.sync`

[Scarica il file di esempio qui](assets/c2c_id_999999_987654_1560431657.sync).

Dopo aver creato il file di sincronizzazione ID, devi caricarlo in un [!DNL Amazon S3] bucket. Per informazioni su come caricare i file di sincronizzazione ID, consulta [Invia dati in batch ad Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Passaggio 3: creare una regola di unione profili per la segmentazione {#create-merge-rule}

Il passaggio successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare alle destinazioni basate su persone.

>[!IMPORTANT]
>
> Se disponi già di una regola definita con le opzioni [!UICONTROL Current Authenticated Profiles] o [!UICONTROL Last Authenticated Profiles], puoi passare a [Passaggio 4 - Crea segmenti di pubblico](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Clic **[!UICONTROL Add New Rule]**.
1. Immetti una regola di unione profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. Nella sezione **[!UICONTROL Profile Merge Rule Setup]** , seleziona le opzioni **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** .
1. Nell’elenco **[!UICONTROL Cross-Device Profile Options]**, seleziona le origini dati sulle quali desideri eseguire la segmentazione. Devono essere le origini dati che contengono i [DPUUIDs](../../reference/ids-in-aam.md) esistenti.

## Passaggio 4 - Creare segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti di pubblico, utilizza il [Generatore di segmenti](../segments/segment-builder.md). Se hai segmenti di pubblico esistenti da inviare a [!DNL People-Based Destinations], passa a [Passaggio 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone](people-based-destinations-workflow-combined.md#configure-authentication).

## Passaggio 5: configurare l’autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma social, visualizzala in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
1. Clic **[!UICONTROL Add Account]**.
1. Utilizza il menu a discesa **[!UICONTROL People-Based Platform]** per selezionare la piattaforma con cui desideri configurare l’integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
1. Fai clic su **[!UICONTROL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
1. Dopo aver eseguito l’autenticazione all’account della piattaforma social, vieni reindirizzato all’Audience Manager in cui dovresti visualizzare gli account dell’inserzionista associati. Seleziona l’account dell’inserzionista da utilizzare e fai clic su **[!UICONTROL Confirm]**.
1. In Audience Manager viene visualizzata una notifica nella parte superiore della pagina per sapere se l’account è stato aggiunto correttamente. La notifica ti consente anche di aggiungere un indirizzo e-mail di contatto per ricevere notifiche quando l’autenticazione della piattaforma social sta per scadere.

>[!IMPORTANT]
>
>Un Audience Manager gestisce l’integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Per informazioni dettagliate su come rinnovare i token scaduti, consulta Rinnovo token di autenticazione .

## Passaggio 6: creare una destinazione basata sulle persone {#create-destination}

1. Accedi al tuo account di Audience Manager, vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** e fai clic su **[!UICONTROL Create Destination]**.
1. Nella sezione **[!UICONTROL Basic Information]**, immetti un **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati e utilizza le seguenti impostazioni:
   * **[!UICONTROL Category]**: Piattaforme integrate;
   * **[!UICONTROL Type]**: Persone;
   * **[!UICONTROL Platform]**: seleziona la piattaforma basata sulle persone a cui desideri inviare i segmenti di pubblico;
   * **[!UICONTROL Account]**: seleziona l’account inserzionista desiderato associato alla piattaforma selezionata.
      ![create-destination](assets/pbd-create-destination.png)
1. Clic **[!UICONTROL Next]**.
1. Scegli il **[!UICONTROL Data Export Labels]** da impostare per questa destinazione.
1. Nella sezione **[!UICONTROL Configuration]** , seleziona l’origine dati contenente le origini dati con hash.
1. Nella sezione **[!UICONTROL Segment Mappings]** , seleziona i segmenti che desideri inviare a questa destinazione. Si tratta dei segmenti creati al [Passaggio 4 - Creare segmenti di pubblico](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Salva la destinazione.
