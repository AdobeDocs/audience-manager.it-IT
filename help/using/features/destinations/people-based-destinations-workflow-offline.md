---
description: Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico a partire da dati dei clienti solo offline e inviarli a destinazioni basate su persone.
seo-description: This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.
seo-title: Workflow B - Personalization Based on Offline-Only Data
solution: Audience Manager
title: 'Flusso di lavoro B: Personalization basato su dati solo offline'
feature: People-based Destinations
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---

# Flusso di lavoro B: Personalization basato su dati solo offline {#workflow-b}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

Questa pagina include istruzioni dettagliate su come creare segmenti di pubblico a partire da dati dei clienti solo offline e inviarli a destinazioni basate su persone.

## Passaggio 1 - Caratteristiche offline integrate {#step-1-onboard-traits}

In questo scenario, il primo passaggio della creazione di segmenti di pubblico consiste nell’Audience Manager dei dati dei clienti offline.

>[!IMPORTANT]
>
> Prima di continuare, assicurati che l&#39;attività cliente che stai per eseguire sia già definita in Audience Manager con le corrispondenti [caratteristiche onboarded](../traits/trait-and-segment-qualification-reference.md).

Indipendentemente dal fatto che gli ID cliente Audience Manager esistenti ([DPUUID](../../reference/ids-in-aam.md)) siano o meno e-mail con hash, è necessario eseguire l&#39;onboarding delle caratteristiche nell&#39;origine dati che contiene i [DPUUID](../../reference/ids-in-aam.md).

### Esempio

Desideri qualificare gli ID cliente dalla tabella seguente per gli ID caratteristica onboarded corrispondenti. Supponiamo che i tuoi [DPUUID](../../reference/ids-in-aam.md) siano memorizzati in un&#39;origine dati con ID 999999 e che l&#39;ID dell&#39;origine dati Audience Manager sia 123.

| ID cliente (DPUUID) | ID caratteristica onboarded |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

Per qualificare gli ID cliente nell&#39;esempio precedente per le caratteristiche onboarded corrispondenti, devi caricare un [file di dati in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) con il seguente contenuto:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

Il nome del file sarà simile al seguente: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Per informazioni dettagliate sulla struttura del nome file, vedere [Requisiti di nome Amazon S3 e dimensione file per i file di dati in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

## Passaggio 2: configurare le impostazioni di Data Source {#configure-data-source-settings}

A seconda che i [DPUUID](../../reference/ids-in-aam.md) siano indirizzi e-mail con hash in minuscolo, potrebbe essere necessario configurare l&#39;origine dati che memorizzerà gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail con hash [DPUUID](../../reference/ids-in-aam.md) sono già minuscoli.**

In questo caso, è necessario etichettare l’origine dati corrispondente come tale:

1. Vai a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. Trovare l&#39;origine dati che contiene i [DPUUID](../../reference/ids-in-aam.md) e fare clic su di essa.
1. Verificare che l&#39;opzione **[!UICONTROL Cannot be tied to personally identifiable information]** sia deselezionata.
1. Salvare le impostazioni dell&#39;origine dati.

 

**Scenario 2: gli indirizzi e-mail con hash [DPUUID](../../reference/ids-in-aam.md) non sono minuscoli.**

In questo caso, devi creare una nuova origine dati multi-dispositivo che memorizzerà gli indirizzi e-mail con hash. Ecco come eseguire questa operazione:

1. Accedi al tuo account Audience Manager e passa a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, quindi fai clic su **[!UICONTROL Add New]**.
1. Immettere **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati.
1. Nel menu a discesa **[!UICONTROL ID Type]**, selezionare **[!UICONTROL Cross Device]**.
1. Nella sezione **[!UICONTROL Data Source Settings]** selezionare entrambe le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e abilitare l&#39;opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilizzare il menu a discesa per selezionare l&#39;etichetta **[!UICONTROL Emails(SHA256, lowercased)]** per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta l’origine dati solo come contenente dati con hash con quell’algoritmo specifico. L’Audience Manager non esegue l’hashing dei dati in questo passaggio. Verificare che gli indirizzi di posta elettronica che si prevede di memorizzare in questa origine dati siano già sottoposti a hashing con l&#39;algoritmo [!DNL SHA256]. In caso contrario, non potrai utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulta [Onboarding dei dati](people-based-destinations-prerequisites.md#data-onboarding) per le domande frequenti su come inserire i dati offline in Audience Manager per le destinazioni basate sulle persone.

Guarda il video seguente per un&#39;esercitazione video su come creare un&#39;origine dati per [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/34899?captions=ita)

## Passaggio 3: abbinare gli DPUUID agli indirizzi e-mail con hash tramite la sincronizzazione ID basata su file {#match-ids-emails}

>[!IMPORTANT]
>
> Questo passaggio si applica solo allo [scenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) descritto sopra. Se i tuoi [DPUUID](../../reference/ids-in-aam.md) esistenti sono già indirizzi e-mail con hash, vai al [Passaggio 4 - Creare una regola di unione profili per la segmentazione](#create-profile-merge-rule).

Supponiamo che tu voglia far corrispondere i tuoi [DPUUID](../../reference/ids-in-aam.md) esistenti dall&#39;esempio al passaggio 1 agli indirizzi e-mail con hash della tabella seguente (colonna di destra) e archiviare gli indirizzi e-mail con hash nella nuova origine dati creata al [passaggio 2 - Configurare le impostazioni di Data Source](#configure-data-source-settings).

Come promemoria, ora sono disponibili due origini dati:

| ID origine dati | Contenuti dell’origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Nel nostro esempio, il file di sincronizzazione [ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) avrebbe il seguente contenuto:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Il file di sincronizzazione [ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) deve seguire questa struttura dei nomi:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Nell’esempio precedente, il nome del file sarà simile al seguente:
`c2c_id_999999_987654_1560431657.sync`

[Scarica qui il file di esempio](assets/c2c_id_999999_987654_1560431657.sync).

Dopo aver creato il file di sincronizzazione ID, devi caricarlo in un bucket [!DNL Amazon S3]. Per informazioni su come caricare i file di sincronizzazione ID, vedere [Send Batch Data to Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Passaggio 4: creare una regola di unione profili per la segmentazione {#create-profile-merge-rule}

Il passaggio successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare a [!DNL People-Based Destinations].

1. Accedi al tuo account Audience Manager e passa a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Fare clic su [!UICONTROL Add New Rule].
3. Immettere una regola di unione profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Nella sezione **[!UICONTROL Profile Merge Rule Setup]** selezionare la regola **[!UICONTROL All Cross-Device Profiles]** dall&#39;elenco **[!UICONTROL Cross-Device Options]**.
5. Nell&#39;elenco **[!UICONTROL Cross-Device Profile Options]**, seleziona l&#39;origine dati su cui sono state effettuate le caratteristiche.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Passaggio 5: creare segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti da dati solo offline, utilizza il [Generatore di segmenti](../segments/segment-builder.md) e assicurati di utilizzare la nuova regola di unione profili creata nel passaggio precedente durante la creazione del segmento.

## Passaggio 6: configurare l’autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account Audience Manager e passa a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma social, dovresti visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata su persone](assets/pbd-config.png)
1. Fare clic su **[!UICONTROL Add Account]**.
1. Utilizza il menu a discesa **[!UICONTROL People-Based Platform]** per selezionare la piattaforma con cui configurare l&#39;integrazione.
   ![people-based-platform](assets/pbd-add.png)
1. Fare clic su **[!UICONTROL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
1. Dopo aver eseguito l’autenticazione all’account della piattaforma social, vieni reindirizzato all’Audience Manager in cui dovresti visualizzare gli account pubblicitari associati. Selezionare l&#39;account pubblicitario che si desidera utilizzare e fare clic su **[!UICONTROL Confirm]**.
1. In Audience Manager, nella parte superiore della pagina viene visualizzata una notifica per comunicare se l’account è stato aggiunto correttamente. La notifica ti consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere notifiche quando l’autenticazione della piattaforma social network sta per scadere.

>[!IMPORTANT]
>
>Audience Manager gestisce l’integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Consulta Rinnovo del token di autenticazione per informazioni su come rinnovare i token scaduti.

## Passaggio 7: creare una destinazione basata su persone {#create-destination}

1. Accedi al tuo account Audience Manager, passa a **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** e fai clic su **[!UICONTROL Create Destination]**.
1. Nella sezione **[!UICONTROL Basic Information]** immettere **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati e utilizzare le impostazioni seguenti:
   * **[!UICONTROL Category]**: Piattaforme integrate;
   * **[!UICONTROL Type]**: Basato Su Persone;
   * **[!UICONTROL Platform]**: selezionare la piattaforma basata sulle persone a cui si desidera inviare i segmenti di pubblico;
   * **[!UICONTROL Account]**: selezionare l&#39;account dell&#39;inserzionista desiderato associato alla piattaforma selezionata.

     ![create-destination](assets/pbd-create-destination.png)
1. Fare clic su **[!UICONTROL Next]**.
1. Scegliere **[!UICONTROL Data Export Labels]** che si desidera impostare per questa destinazione.
1. Nella sezione **[!UICONTROL Configuration]** selezionare l&#39;origine dati che contiene le origini dati con hash.
1. Nella sezione **[!UICONTROL Segment Mappings]**, seleziona i segmenti che desideri inviare a questa destinazione. Si tratta dei segmenti creati nel [Passaggio 5 - Creazione di segmenti di pubblico](people-based-destinations-workflow-offline.md#create-audience-segments).
1. Salva la destinazione.
