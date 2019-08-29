---
description: 'Questa pagina include indicazioni dettagliate su come combinare dati CRM offline con dati comportamentali in tempo reale per gli utenti autenticati per la creazione di segmenti di pubblico, quindi inviare questi segmenti di pubblico alle destinazioni basate su persone. '
seo-description: 'Questa pagina include indicazioni dettagliate su come combinare dati CRM offline con dati comportamentali in tempo reale per gli utenti autenticati per la creazione di segmenti di pubblico, quindi inviare questi segmenti di pubblico alle destinazioni basate su persone.  '
seo-title: Flusso di lavoro C - Personalizzazione basata sull'attività autenticata combinata con dati offline
solution: Audience Manager
title: Flusso di lavoro C - Personalizzazione basata sull'attività autenticata combinata con dati offline
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# Flusso di lavoro C - Personalizzazione basata sull'attività autenticata combinata con dati offline {#workflow-c}

Questa pagina include indicazioni dettagliate su come combinare dati offline [!DNL CRM] con dati comportamentali in tempo reale per consentire agli utenti autenticati di creare segmenti di pubblico, e quindi inviare questi segmenti di pubblico.[!DNL People-Based Destinations]

## Passaggio 1 - Configurazione delle impostazioni Origini dati {#configure-data-source-settings}

A seconda che [i dpuuid](../../reference/ids-in-aam.md) siano minuscoli, indirizzi e-mail con hash, potrebbe essere necessario configurare l'origine dati che archivia gli indirizzi e-mail con hash.

**Scenario 1:[i dpuuid](../../reference/ids-in-aam.md)sono già lettere minuscole, indirizzi e-mail con hash.**

In questo caso, passate al [passaggio 5 - Configura autenticazione piattaforma basata su utenti](#configure-authentication).

**Scenario 2:[i dpuuid non](../../reference/ids-in-aam.md)sono lettere minuscole, indirizzi e-mail con hash.**

In questo caso, è necessario creare una nuova origine dati cross-device che memorizzi gli indirizzi e-mail con hash. Ecco come effettuare questa operazione:

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**, quindi fai clic **[!UICONTROL Add New]** su.
1. Immettete un **[!UICONTROL Name]** 'origine dati e **[!UICONTROL Description]** per la nuova origine dati.
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

## Passaggio 2 - Utilizzare ID dichiarati per far corrispondere dpuuid agli indirizzi e-mail con hash tramite chiamate in tempo reale {#match-email-addresses}

Per qualificare gli utenti autenticati per caratteristiche basate su regole, è necessario inviare la qualifica di caratteristica tramite [ID dichiarati](../declared-ids.md).

### Esempio 

Supponiamo che siano state create le due seguenti origini dati.

| ID origine dati | Contenuto origine dati |
|---|---|
| 999999 | Dpuuids esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

Quindi, puoi qualificare gli ID CRM di seguito per la caratteristica nella tabella.

| DPUUID (CRM ID) | Indirizzo e-mail | Indirizzo e-mail con hash | Caratteristica |
|---|---|---|---|
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | posizione = US |

L'ID dichiarato deve seguire questa sintassi:

`https://yourDomain.demdex.net/event?d_cid_ic=myHashedEmailDataSourceID%01myHashedEmail&d_cid_ic=myCrmDataSourceID%01myCRMID&key=value`

Nell'esempio precedente, la chiamata ID dichiarata dovrebbe avere l'aspetto seguente:

`https://yourDomain.demdex.net/event?d_cid_ic=987654%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=999999%0168079982765673198504052656074456196039&location=US`

## Passaggio 3 - Crea una regola di unione profilo per segmentazione {#create-profile-merge-rule-segmentation}

Il passaggio successivo crea una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare al [!DNL People-Based Destinations]tuo.

>[!IMPORTANT]
>
>Se hai già una regola definita con le **[!UICONTROL Current Authenticated Profiles]** opzioni, **[!UICONTROL Last Authenticated Profiles]** puoi passare al [passaggio 4 - Crea segmenti di pubblico](#create-audience-segments).

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Fai clic su **[!UICONTROL Add New Rule]**.
3. Immettete una regola di unione dei profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Nella **[!UICONTROL Profile Merge Rule Setup]** sezione, selezionate **[!UICONTROL All Cross-Device Profiles]** la regola dall' **[!UICONTROL Cross-Device Options]** elenco.
5. Nell **[!UICONTROL Cross-Device Profile Options]** 'elenco, seleziona le origini dati su cui vuoi eseguire la segmentazione. Queste devono essere le origini dati contenenti i dpuuid esistenti.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Passaggio 4 - Crea segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti, usa il Generatore [di segmenti](../segments/segment-builder.md). Se hai segmenti di pubblico esistenti a cui [!DNL People-Based Destinations]vuoi inviare, passa al [passaggio 5 - Configura autenticazione piattaforma basata su utenti](#configure-authentication).

## Passaggio 5 - Configurazione dell'autenticazione piattaforma basata su utenti {#configure-authentication}

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Se disponete di un'integrazione configurata in precedenza con una piattaforma social, dovreste visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
2. Fai clic su **[!UICONTROL Add Account]**.
3. Utilizzate il **[!UICONTROL People-Based Platform]** menu a discesa per selezionare la piattaforma con la quale desiderate configurare l'integrazione.
   ![persone basate su persone](assets/pbd-add.png)
4. Fate clic per **[!UICONTROL Confirm]** essere reindirizzati alla pagina di autenticazione della piattaforma selezionata.
5. Dopo aver eseguito l'autenticazione al tuo account della piattaforma social, verrai reindirizzato ad Audience Manager dove dovresti vedere i tuoi account pubblicitari associati. Selezionate l'account pubblicitario che desiderate utilizzare e fate clic **[!UICONTROL Confirm]** su.
6. Audience Manager visualizza una notifica nella parte superiore della pagina per segnalare se l'account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere notifiche quando l'autenticazione della piattaforma social sta per scadere.

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
1. Nella **[!UICONTROL Segment Mappings]** sezione, seleziona i segmenti che vuoi inviare a questa destinazione. Si tratta dei segmenti creati al [passaggio 4 - Crea segmenti di pubblico](#create-audience-segments).
1. Salvate la destinazione.
