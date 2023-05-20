---
description: Questa pagina include istruzioni dettagliate su come combinare i dati CRM offline con i dati comportamentali già disponibili in Audience Manager per creare nuovi segmenti di pubblico e inviarli a destinazioni basate su persone.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: 'Flusso di lavoro A: personalizzazione basata su tutte le attività online combinate con dati offline'
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 6%

---

# Flusso di lavoro A: personalizzazione basata su tutte le attività online combinate con dati offline {#workflow-a}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

Questa pagina include istruzioni dettagliate su come combinare in modalità offline [!DNL CRM] con dati comportamentali già disponibili in Audience Manager per creare nuovi segmenti di pubblico, quindi invia questi segmenti di pubblico a [!DNL People-Based Destinations].

## Passaggio 1: configurare le impostazioni dell’origine dati {#configure-data-source-settings}

A seconda che [DPUUID](../../reference/ids-in-aam.md) sono indirizzi e-mail con hash in minuscolo; potrebbe essere necessario configurare l’origine dati in cui verranno memorizzati gli indirizzi e-mail con hash.

 

**Scenario 1: il tuo [DPUUID](../../reference/ids-in-aam.md) sono già indirizzi e-mail con hash in minuscolo.**

In questo caso, è necessario etichettare l’origine dati corrispondente come tale:

1. Vai a [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Trova l&#39;origine dati che contiene [DPUUID](../../reference/ids-in-aam.md)e fare clic su di esso.
1. In **[!UICONTROL ID Type]** menu a discesa, seleziona **[!UICONTROL Cross Device]**.
1. Assicurati che l’opzione [!UICONTROL Cannot be tied to personally identifiable information] non è selezionato.
1. In **[!UICONTROL Data Source Settings]** , selezionare entrambe le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e abilitare **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opzione.
1. Utilizza il menu a discesa per selezionare **[!UICONTROL Emails(SHA256, lowercased)]** etichetta per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta l’origine dati solo come contenente dati con hash con quell’algoritmo specifico. L’Audience Manager non esegue l’hashing dei dati in questo passaggio. Assicurati che gli indirizzi e-mail che intendi archiviare in questa origine dati abbiano già un hash con [!DNL SHA256] algoritmo. In caso contrario, non potrai utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salvare le impostazioni dell&#39;origine dati.

 

**Scenario 2: [DPUUID](../../reference/ids-in-aam.md) non sono indirizzi e-mail con hash in minuscolo.**

In questo caso, devi creare una nuova origine dati multi-dispositivo che memorizzerà gli indirizzi e-mail con hash. Ecco come eseguire questa operazione:

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** e fai clic su **[!UICONTROL Add New]**.
1. Immetti un [!UICONTROL Name] e [!UICONTROL Description] per la nuova origine dati.
1. In **[!UICONTROL ID Type]** menu a discesa, seleziona **[!UICONTROL Cross Device]**.
1. In **[!UICONTROL Data Source Settings]** , selezionare entrambe le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e abilitare **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opzione.
1. Utilizza il menu a discesa per selezionare **[!UICONTROL Emails(SHA256, lowercased)]** etichetta per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta l’origine dati solo come contenente dati con hash con quell’algoritmo specifico. L’Audience Manager non esegue l’hashing dei dati in questo passaggio. Assicurati che gli indirizzi e-mail che intendi archiviare in questa origine dati abbiano già un hash con [!DNL SHA256] algoritmo. In caso contrario, non potrai utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Salvare le impostazioni dell&#39;origine dati.

Guarda il video seguente per un tutorial video su come creare un’origine dati per [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Consulta [Onboarding dei dati](people-based-destinations-prerequisites.md#data-onboarding) per le domande frequenti su come inserire i dati offline in Audience Manager per Destinazioni basate su persone.

## Passaggio 2: abbinare gli DPUUID agli indirizzi e-mail con hash tramite la sincronizzazione ID basata su file {#match-ids-emails}

>[!IMPORTANT]
>
> Questo passaggio si applica solo a [Scenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descritto in precedenza. Se il tuo [DPUUID](../../reference/ids-in-aam.md) sono già indirizzi e-mail con hash, vai a [Passaggio 3: creare una regola di unione profili per la segmentazione](people-based-destinations-workflow-combined.md#create-merge-rule).

Supponiamo che tu voglia far corrispondere il tuo esistente [DPUUID](../../reference/ids-in-aam.md) agli indirizzi e-mail con hash dalla tabella seguente (colonna di destra) e memorizza tali indirizzi nella nuova origine dati creata in [Passaggio 1: configurare le impostazioni dell’origine dati](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Puoi collegare fino a 10 indirizzi e-mail con hash a un singolo [DPUUID](../../reference/ids-in-aam.md). A questo scopo, separa gli indirizzi e-mail con hash con un `<TAB>`, nel file di sincronizzazione.

Nel nostro esempio, ora avresti due origini di dati.

| ID origine dati | Contenuti dell’origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

 

Il tuo [File di sincronizzazione ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) avrebbe il seguente contenuto:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Il [File di sincronizzazione ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) deve seguire questa struttura di denominazione:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Nell’esempio precedente, il nome del file sarà simile al seguente:
`c2c_id_999999_987654_1560431657.sync`

[Scarica il file di esempio qui](assets/c2c_id_999999_987654_1560431657.sync).

Dopo aver creato il file di sincronizzazione ID, devi caricarlo in un [!DNL Amazon S3] secchio. Per informazioni su come caricare i file di sincronizzazione ID, consulta [Invia dati batch all&#39;Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Passaggio 3: creare una regola di unione profili per la segmentazione {#create-merge-rule}

Il passaggio successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare alle destinazioni basate su persone.

>[!IMPORTANT]
>
> Se hai già definito una regola con [!UICONTROL Current Authenticated Profiles] o [!UICONTROL Last Authenticated Profiles] opzioni, è possibile passare a [Passaggio 4: creare segmenti di pubblico](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Clic **[!UICONTROL Add New Rule]**.
1. Inserisci una regola di unione profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. In **[!UICONTROL Profile Merge Rule Setup]** , seleziona la sezione **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** opzioni.
1. In **[!UICONTROL Cross-Device Profile Options]** , seleziona le origini dati sulle quali desideri eseguire la segmentazione. Queste dovrebbero essere le origini dati che contengono [DPUUID](../../reference/ids-in-aam.md).

## Passaggio 4: creare segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti di pubblico, utilizza [Generatore di segmenti](../segments/segment-builder.md). Se sono presenti segmenti di pubblico che desideri inviare a [!DNL People-Based Destinations], vai a [Passaggio 5: configurare l’autenticazione della piattaforma basata sulle persone](people-based-destinations-workflow-combined.md#configure-authentication).

## Passaggio 5: configurare l’autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma social, dovresti visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
1. Clic **[!UICONTROL Add Account]**.
1. Utilizza il **[!UICONTROL People-Based Platform]** menu a discesa per selezionare la piattaforma con cui configurare l’integrazione.
   ![people-based-platform](assets/pbd-add.png)
1. Clic **[!UICONTROL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
1. Dopo aver eseguito l’autenticazione all’account della piattaforma social, vieni reindirizzato all’Audience Manager in cui dovresti visualizzare gli account pubblicitari associati. Seleziona l’account dell’inserzionista che desideri utilizzare e fai clic su **[!UICONTROL Confirm]**.
1. In Audience Manager, nella parte superiore della pagina viene visualizzata una notifica per comunicare se l’account è stato aggiunto correttamente. La notifica ti consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere notifiche quando l’autenticazione della piattaforma social network sta per scadere.

>[!IMPORTANT]
>
>Un Audience Manager gestisce l’integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Consulta Rinnovo del token di autenticazione per informazioni su come rinnovare i token scaduti.

## Passaggio 6: creare una destinazione basata su persone {#create-destination}

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** e fai clic su **[!UICONTROL Create Destination]**.
1. In **[!UICONTROL Basic Information]** , immetti un **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati e utilizzare le impostazioni seguenti:
   * **[!UICONTROL Category]**: Piattaforme Integrate;
   * **[!UICONTROL Type]**: Basato Sulle Persone;
   * **[!UICONTROL Platform]**: seleziona la piattaforma basata sulle persone a cui desideri inviare i segmenti di pubblico;
   * **[!UICONTROL Account]**: seleziona l’account dell’inserzionista desiderato associato alla piattaforma selezionata.
      ![create-destination](assets/pbd-create-destination.png)
1. Clic **[!UICONTROL Next]**.
1. Scegli la **[!UICONTROL Data Export Labels]** che desideri impostare per questa destinazione.
1. In **[!UICONTROL Configuration]** , selezionare l&#39;origine dati che contiene le origini dati con hash.
1. In **[!UICONTROL Segment Mappings]** , seleziona i segmenti che desideri inviare a questa destinazione. Si tratta dei segmenti creati in [Passaggio 4: creare segmenti di pubblico](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Salva la destinazione.
