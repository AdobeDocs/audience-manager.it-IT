---
description: 'Questa pagina include indicazioni dettagliate su come combinare dati CRM offline con dati comportamentali già presenti in Audience Manager per creare nuovi segmenti di pubblico, quindi inviare questi segmenti di pubblico alle destinazioni basate su persone.  '
seo-description: 'Questa pagina include indicazioni dettagliate su come combinare dati CRM offline con dati comportamentali già presenti in Audience Manager per creare nuovi segmenti di pubblico, quindi inviare questi segmenti di pubblico alle destinazioni basate su persone.   '
seo-title: Flusso di lavoro A - Personalizzazione basata su tutta l'attività online combinata con dati offline
solution: Audience Manager
title: Flusso di lavoro A - Personalizzazione basata su tutta l'attività online combinata con dati offline
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# Flusso di lavoro A - Personalizzazione basata su tutta l'attività online combinata con dati offline {#workflow-a}

Questa pagina include indicazioni dettagliate su come combinare dati offline [!DNL CRM] con dati comportamentali già presenti in Audience Manager per creare nuovi segmenti di pubblico, e [!DNL People-Based Destinations]quindi inviare questi segmenti di pubblico.

## Passaggio 1 - Configurazione delle impostazioni Origini dati {#configure-data-source-settings}

A seconda che [i dpuuid](../../reference/ids-in-aam.md) siano minuscoli, indirizzi e-mail con hash, potrebbe essere necessario configurare l'origine dati che archivia gli indirizzi e-mail con hash.

**Scenario 1:[i dpuuid](../../reference/ids-in-aam.md)sono già lettere minuscole, indirizzi e-mail con hash.**

In tal caso, è necessario etichettare l'origine dati corrispondente come tale:

1. Vai a [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. Trova l'origine dati che contiene i tuoi [dpuuid](../../reference/ids-in-aam.md)e fai clic su di esso.
1. Verificate che l'opzione [!UICONTROL Cannot be tied to personally identifiable information] non sia selezionata.
1. Salvare le impostazioni dell'origine dati.

**Scenario 2:[i dpuuid non](../../reference/ids-in-aam.md)sono lettere minuscole, indirizzi e-mail con hash.**

In questo caso, è necessario creare una nuova origine dati cross-device che memorizzi gli indirizzi e-mail con hash. Ecco come effettuare questa operazione:

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**, quindi fai clic **[!UICONTROL Add New]** su.
1. Immettete un [!UICONTROL Name] 'origine dati e [!UICONTROL Description] per la nuova origine dati.
1. Nel menu **[!UICONTROL ID Type]** a discesa, selezionate **[!UICONTROL Cross Device]**.
1. Nella **[!UICONTROL Data Source Settings]** sezione, selezionare entrambe **[!UICONTROL Inbound]****[!UICONTROL Outbound]** le opzioni e abilitare l' **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opzione.
1. Utilizzate il menu a discesa per selezionare **[!UICONTROL Emails(SHA256, lowercased)]** l'etichetta per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l'origine dati come dati contenenti dati hash con quell'algoritmo specifico. Audience Manager non hash i dati in questo passaggio. Accertatevi che gli indirizzi e-mail che pianificate di memorizzare in questa origine dati siano già hash con l' [!DNL SHA256] algoritmo. In caso contrario, non sarà possibile utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

>[!NOTE]
>
> Consulta [Onboarding (Onboarding)](people-based-destinations-prerequisites.md#data-onboarding) per le domande frequenti su come portare i dati offline in Audience Manager per Destinazioni basate su persone.

## Passaggio 2 - Corrispondenza di dpuuid con indirizzi e-mail con hash tramite sincronizzazione ID basata su file {#match-ids-emails}

>[!IMPORTANT]
>
> Questo passaggio si applica solo alla [situazione 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) descritta sopra. Se i [dpuuid esistenti](../../reference/ids-in-aam.md) sono già indirizzi e-mail con hash, passa al [passaggio 3 - Crea una regola unione profilo per segmentazione](people-based-destinations-workflow-combined.md#create-merge-rule).

Supponiamo che desideri associare [i dpuuid](../../reference/ids-in-aam.md) esistenti agli indirizzi e-mail con hash dalla tabella seguente (colonna a destra) e memorizzare gli indirizzi e-mail con hash nella nuova origine dati creata al [Passaggio 1 - Configura impostazioni sorgente dati](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (CRM ID) | Indirizzo e-mail | Indirizzo e-mail con hash |
| --- | --- | --- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

Potete collegare fino a 10 indirizzi e-mail con hash a un singolo [DPUUID](../../reference/ids-in-aam.md). A tal fine, separate gli indirizzi e-mail con hash con una virgola, all'interno del file di sincronizzazione.

Nel nostro esempio, ora hai due origini dati.

| ID origine dati | Contenuto origine dati |
| --- | --- |
| 999999 | Dpuuids esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

Il [file](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) di sincronizzazione ID avrà i seguenti contenuti:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

Il [file](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) di sincronizzazione ID deve seguire questa struttura di denominazione:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

Nell'esempio precedente, il nome file sarà simile al seguente:`c2c_id_999999_987654_1560431657.sync`


[Scarica qui il file di esempio](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

## Passaggio 3 - Crea una regola di unione profilo per segmentazione {#create-merge-rule}

Il passaggio successivo crea una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare alle destinazioni basate sulle persone.

>[!IMPORTANT]
>
> Se hai già una regola definita con le [!UICONTROL Current Authenticated Profiles] opzioni, [!UICONTROL Last Authenticated Profiles] puoi passare al [passaggio 4 - Crea segmenti di pubblico](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**.
1. Fai clic su **[!UICONTROL Add New Rule]**.
1. Immettete una regola di unione dei profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
1. Nella **[!UICONTROL Profile Merge Rule Setup]** sezione, selezionare le **[!UICONTROL Current Authenticated Profiles]****[!UICONTROL Last Authenticated Profiles]** opzioni desiderate.
1. Nell **[!UICONTROL Cross-Device Profile Options]** 'elenco, seleziona le origini dati su cui vuoi eseguire la segmentazione. Queste devono essere le origini dati contenenti i [dpuuid esistenti](../../reference/ids-in-aam.md).

## Passaggio 4 - Crea segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti di pubblico, usa il Generatore [di segmenti](../segments/segment-builder.md). Se hai segmenti di pubblico esistenti a cui [!DNL People-Based Destinations]vuoi inviare, passa al [passaggio 5 - Configura autenticazione piattaforma basata su utenti](people-based-destinations-workflow-combined.md#configure-authentication).

## Passaggio 5 - Configurazione dell'autenticazione piattaforma basata su utenti {#configure-authentication}

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Se disponete di un'integrazione configurata in precedenza con una piattaforma social, dovreste visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
1. Fai clic su **[!UICONTROL Add Account]**.
1. Utilizzate il **[!UICONTROL People-Based Platform]** menu a discesa per selezionare la piattaforma con la quale desiderate configurare l'integrazione.
   ![persone basate su persone](assets/pbd-add.png)
1. Fate clic per **[!UICONTROL Confirm]** essere reindirizzati alla pagina di autenticazione della piattaforma selezionata.
1. Dopo aver eseguito l'autenticazione al tuo account della piattaforma social, verrai reindirizzato ad Audience Manager dove dovresti vedere i tuoi account pubblicitari associati. Selezionate l'account pubblicitario che desiderate utilizzare e fate clic **[!UICONTROL Confirm]** su.
1. Audience Manager visualizza una notifica nella parte superiore della pagina per segnalare se l'account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere notifiche quando l'autenticazione della piattaforma social sta per scadere.

>[!IMPORTANT]
>
>Un manager uditivo gestisce l'integrazione con le piattaforme social tramite token di autenticazione che scade dopo un certo periodo di tempo. Per informazioni su come rinnovare i token scaduti, consultate Rinnovo token di autenticazione.

## Passaggio 6: creare una destinazione basata su persone {#create-destination}

1. Accedi al tuo account Audience Manager, vai a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** e fai clic **[!UICONTROL Create Destination]** su.
1. Nella **[!UICONTROL Basic Information]** sezione, immetti a **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati e usa le impostazioni seguenti:
   * **[!UICONTROL Category]**: Piattaforme integrate;
   * **[!UICONTROL Type]**: Persone;
   * **[!UICONTROL Platform]**: selezionate la piattaforma basata sulle persone a cui desiderate inviare i segmenti di pubblico;
   * **[!UICONTROL Account]**: selezionate l'account pubblicitario desiderato associato alla piattaforma selezionata.
      ![create-destination](assets/pbd-create-destination.png)
1. Fai clic su **[!UICONTROL Next]**.
1. Scegliete l' **[!UICONTROL Data Export Labels]** impostazione che desiderate impostare per la destinazione.
1. Nella **[!UICONTROL Configuration]** sezione, seleziona l'origine dati che contiene le origini dati hash.
1. Nella **[!UICONTROL Segment Mappings]** sezione, seleziona i segmenti che vuoi inviare a questa destinazione. Si tratta dei segmenti creati al [passaggio 4 - Crea segmenti di pubblico](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Salvate la destinazione.
