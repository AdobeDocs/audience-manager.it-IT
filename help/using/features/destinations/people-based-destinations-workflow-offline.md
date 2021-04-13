---
description: 'Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico dai dati di clienti solo offline e inviarli alle destinazioni basate sulle persone.  '
seo-description: 'Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico dai dati di clienti solo offline e inviarli alle destinazioni basate sulle persone.  '
seo-title: 'Flusso di lavoro B: personalizzazione basata su dati solo offline'
solution: Audience Manager
title: 'Flusso di lavoro B: personalizzazione basata su dati solo offline'
feature: Destinazioni basate su persone
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 6%

---

# Flusso di lavoro B: personalizzazione basata su dati solo offline {#workflow-b}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico dai dati di clienti solo offline e inviarli alle destinazioni basate sulle persone.

## Passaggio 1 - Caratteristiche offline integrate {#step-1-onboard-traits}

Il primo passo per la creazione di segmenti di pubblico in questo scenario è quello di portare in Audience Manager i dati dei clienti offline.

>[!IMPORTANT]
>
> Prima di continuare, assicurati che l&#39;attività del cliente che stai per imbarcare sia già definita in Audience Manager con le corrispondenti [caratteristiche onboarded](../traits/trait-and-segment-qualification-reference.md).

Indipendentemente dal fatto che gli ID cliente Audienci Manager esistenti ([DPUUID](../../reference/ids-in-aam.md)) siano o meno con hash o meno, è necessario eseguire l&#39;onboarding delle caratteristiche rispetto all&#39;origine dati che contiene i [DPUUID](../../reference/ids-in-aam.md).

### Esempio

Desideri qualificare gli ID cliente dalla tabella seguente per i corrispondenti ID di caratteristiche onboarded. Consideriamo che i [DPUUID](../../reference/ids-in-aam.md) sono memorizzati in un’origine dati con l’ID 99999 e l’ID partner Audience Manager è 123.

| ID cliente (DPUUID) | ID caratteristica onboarded |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 8915902479676034373311707646026765593 | 11223, 93342, 27341 |

<br />

Per qualificare gli ID cliente nell’esempio precedente per le caratteristiche onboarded corrispondenti, devi caricare un [file di dati in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) con i seguenti contenuti:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

Il nome del file sarà simile al seguente: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Per informazioni dettagliate sulla struttura del nome file, consulta [Requisiti di nome e dimensione file Amazon S3 per i file in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) .

## Passaggio 2: configurare le impostazioni delle origini dati {#configure-data-source-settings}

A seconda che i [DPUUID](../../reference/ids-in-aam.md) siano minuscole o meno, gli indirizzi e-mail con hash potrebbero essere necessari per configurare l&#39;origine dati in cui verranno memorizzati gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail con hash  [](../../reference/ids-in-aam.md) DPUUID sono già minuscoli.**

In questo caso, è necessario etichettare l’origine dati corrispondente come tale:

1. Vai a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. Trova l&#39;origine dati contenente i [DPUUID](../../reference/ids-in-aam.md) e fai clic su di essa.
1. Assicurati che l’opzione **[!UICONTROL Cannot be tied to personally identifiable information]** sia deselezionata.
1. Salva le impostazioni dell’origine dati.

 

**Scenario 2: gli indirizzi e-mail con hash  [](../../reference/ids-in-aam.md) DPUUID non sono minuscoli.**

In questo caso, devi creare una nuova origine dati multi-dispositivo che memorizzerà gli indirizzi e-mail con hash. Ecco come eseguire questa operazione:

1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, quindi fai clic su **[!UICONTROL Add New]**.
1. Immetti una **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati.
1. Nel menu a discesa **[!UICONTROL ID Type]**, seleziona **[!UICONTROL Cross Device]**.
1. Nella sezione **[!UICONTROL Data Source Settings]** , seleziona entrambe le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e abilita l’opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilizza il menu a discesa per selezionare l’etichetta **[!UICONTROL Emails(SHA256, lowercased)]** per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l’origine dati come contenente dati con hash con quell’algoritmo specifico. In questo passaggio Audience Manager non esegue l’hash dei dati. Assicurati che gli indirizzi e-mail che intendi memorizzare in questa origine dati siano già contraddistinti dall’algoritmo [!DNL SHA256]. In caso contrario, non potrai utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulta [Onboarding dei dati](people-based-destinations-prerequisites.md#data-onboarding) per le domande frequenti su come inserire i dati offline in Audience Manager per le destinazioni basate su persone.

Guarda il video seguente per un&#39;esercitazione video su come creare un&#39;origine dati per [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Passaggio 3: associare DPUUID a indirizzi e-mail con hash tramite sincronizzazione ID basata su file {#match-ids-emails}

>[!IMPORTANT]
>
> Questo passaggio si applica solo allo [Scenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descritto sopra. Se gli [DPUUID](../../reference/ids-in-aam.md) esistenti sono già indirizzi e-mail con hash, passa a [Passaggio 4 - Creare una regola di unione profili per la segmentazione](#create-profile-merge-rule).

Supponiamo che desideri far corrispondere gli [DPUUID](../../reference/ids-in-aam.md) esistenti dall&#39;esempio al passaggio 1 agli indirizzi e-mail con hash dalla tabella seguente (colonna a destra) e archiviare gli indirizzi e-mail con hash nella nuova origine dati creata in [Passaggio 2 - Configura impostazioni origine dati](#configure-data-source-settings).

Come promemoria, ora disponi di due origini dati:

| ID origine dati | Contenuto dell&#39;origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 8915902479676034373311707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Nel nostro esempio, il tuo [file di sincronizzazione ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) avrebbe i seguenti contenuti:

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

## Passaggio 4: creare una regola di unione profili per la segmentazione {#create-profile-merge-rule}

Il passaggio successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare al tuo [!DNL People-Based Destinations].

1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Clic [!UICONTROL Add New Rule].
3. Immetti una regola di unione profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Nella sezione **[!UICONTROL Profile Merge Rule Setup]** , seleziona la regola **[!UICONTROL All Cross-Device Profiles]** dall&#39;elenco **[!UICONTROL Cross-Device Options]**.
5. Nell’elenco **[!UICONTROL Cross-Device Profile Options]** , seleziona l’origine dati rispetto alla quale sono state caricate le caratteristiche.
   ![configurazione delle regole di unione](assets/pbd-pmr.png)

## Passaggio 5 - Creare segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti dai dati solo offline, utilizza il [Generatore di segmenti](../segments/segment-builder.md) e assicurati di utilizzare la nuova regola di unione profili creata nel passaggio precedente durante la creazione del segmento.

## Passaggio 6: configurare l’autenticazione della piattaforma basata sulle persone {#configure-authentication}

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
>Audience Manager gestisce l’integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Per informazioni dettagliate su come rinnovare i token scaduti, consulta Rinnovo token di autenticazione .

## Passaggio 7 - Creare una destinazione basata sulle persone {#create-destination}

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
1. Nella sezione **[!UICONTROL Segment Mappings]** , seleziona i segmenti che desideri inviare a questa destinazione. Si tratta dei segmenti creati al [Passaggio 5: creare segmenti di pubblico](people-based-destinations-workflow-offline.md#create-audience-segments).
1. Salva la destinazione.
