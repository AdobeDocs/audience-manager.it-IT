---
description: 'Questa pagina include istruzioni dettagliate su come combinare dati CRM offline con dati comportamentali in tempo reale per gli utenti autenticati per creare segmenti di pubblico, quindi inviare questi segmenti di pubblico a Destinazioni basate su persone. '
seo-description: 'Questa pagina include istruzioni dettagliate su come combinare dati CRM offline con dati comportamentali in tempo reale per gli utenti autenticati per creare segmenti di pubblico, quindi inviare questi segmenti di pubblico a Destinazioni basate su persone.  '
seo-title: Flusso di lavoro C - Personalizzazione basata su attività autenticata combinata con dati offline
solution: Audience Manager
title: Flusso di lavoro C - Personalizzazione basata su attività autenticata combinata con dati offline
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Flusso di lavoro C - Personalizzazione basata su attività autenticata combinata con dati offline {#workflow-c}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell'utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per assistenza legale.

Questa pagina include istruzioni dettagliate su come combinare [!DNL CRM] i dati offline con i dati comportamentali in tempo reale per gli utenti autenticati, al fine di creare segmenti di pubblico e quindi inviare tali segmenti a [!DNL People-Based Destinations].

## Passaggio 1 - Configura impostazioni origine dati {#configure-data-source-settings}

A seconda che i vostri [DPUUID](../../reference/ids-in-aam.md) siano minuscoli, indirizzi e-mail con hash, potrebbe essere necessario configurare l'origine dati che memorizzerà gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail[DPUUID](../../reference/ids-in-aam.md)sono già minuscoli e con hash.**

In questo caso, passate al [Passaggio 5 - Configurare l'autenticazione](#configure-authentication)della piattaforma basata sulle persone.

 

**Scenario 2: gli indirizzi e-mail[DPUUID](../../reference/ids-in-aam.md)non sono minuscoli e con hash.**

In questo caso, è necessario creare una nuova origine dati cross-device in cui memorizzare gli indirizzi e-mail con hash. Come procedere:

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**, quindi fai clic su **[!UICONTROL Add New]**.
1. Immettere un **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati.
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

## Passaggio 2 - Utilizzare gli ID dichiarati per far corrispondere DPUUID agli indirizzi e-mail con hash tramite chiamate HTTP in tempo reale {#match-email-addresses}

Per qualificare gli utenti autenticati per caratteristiche basate su regola, devi inviare la qualifica alla caratteristica tramite ID [](../declared-ids.md)dichiarati.

### Esempio 

Supponiamo che siano state create le due seguenti origini dati.

| ID origine dati | Contenuto origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

 

Quindi, vuoi qualificare gli ID CRM di seguito per la caratteristica nella tabella.

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash | Caratteristiche |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

Il tuo ID dichiarato deve seguire la sintassi seguente:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

Nell’esempio precedente, la chiamata ID dichiarata dovrebbe essere simile alla seguente:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Passaggio 3: crea una regola di unione dei profili per la segmentazione {#create-profile-merge-rule-segmentation}

Il passo successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare al tuo [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Se hai già una regola definita con le **[!UICONTROL Current Authenticated Profiles]** opzioni o **[!UICONTROL Last Authenticated Profiles]** , puoi passare al [Passaggio 4 - Crea segmenti](#create-audience-segments)di pubblico.

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Fai clic su **[!UICONTROL Add New Rule]**.
3. Immettete una regola di unione dei profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Nella **[!UICONTROL Profile Merge Rule Setup]** sezione, selezionare la **[!UICONTROL Current Authenticated Profiles]** regola o **[!UICONTROL Last Authenticated Profiles]** dall' **[!UICONTROL Cross-Device Options]** elenco.
5. Nell' **[!UICONTROL Cross-Device Profile Options]** elenco, selezionare le origini dati sulle quali eseguire la segmentazione. Devono essere le origini dati che contengono i DPUUID esistenti.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Passaggio 4 - Creazione di segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti, usa il Generatore di [segmenti](../segments/segment-builder.md). Se hai segmenti di pubblico esistenti a cui vuoi inviare [!DNL People-Based Destinations], passa al [Passaggio 5 - Configura autenticazione](#configure-authentication)della piattaforma basata sulle persone.

## Passaggio 5 - Configurare l'autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Se avete già configurato un'integrazione con una piattaforma social, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
2. Fai clic su **[!UICONTROL Add Account]**.
3. Utilizzate il menu a **[!UICONTROL People-Based Platform]** discesa per selezionare la piattaforma con cui desiderate configurare l'integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
4. Fare clic per **[!UICONTROL Confirm]** essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
5. Dopo aver eseguito l'autenticazione sull'account della piattaforma social, verrete reindirizzati ad Audience Manager, dove dovrebbero essere visualizzati gli account degli inserzionisti associati. Selezionate l’account dell’inserzionista da usare e fate clic su **[!UICONTROL Confirm]**.
6. Audience Manager visualizza una notifica nella parte superiore della pagina per informarvi se l'account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere le notifiche quando l'autenticazione della piattaforma social sta per scadere.

>[!IMPORTANT]
>
>Audience Manager gestisce l'integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Consulta Rinnovo token di autenticazione per informazioni dettagliate su come rinnovare i token scaduti.

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
1. Nella **[!UICONTROL Segment Mappings]** sezione, selezionate i segmenti che desiderate inviare a questa destinazione. Si tratta dei segmenti creati al [Passaggio 4 - Creazione di segmenti](#create-audience-segments)di pubblico.
1. Salva la destinazione.
