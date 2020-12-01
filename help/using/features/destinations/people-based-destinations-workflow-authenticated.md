---
description: 'Questa pagina include istruzioni dettagliate su come combinare dati CRM offline con dati comportamentali in tempo reale per gli utenti autenticati per creare segmenti di pubblico, quindi inviare questi segmenti di pubblico a Destinazioni basate su persone. '
seo-description: 'Questa pagina include istruzioni dettagliate su come combinare dati CRM offline con dati comportamentali in tempo reale per gli utenti autenticati per creare segmenti di pubblico, quindi inviare questi segmenti di pubblico a Destinazioni basate su persone.  '
seo-title: 'Flusso di lavoro C: personalizzazione basata su attività autenticate combinate con dati offline'
solution: Audience Manager
title: 'Flusso di lavoro C: personalizzazione basata su attività autenticate combinate con dati offline'
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 5%

---


# Flusso di lavoro C: personalizzazione basata su attività autenticate combinate con dati offline {#workflow-c}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

Questa pagina include istruzioni dettagliate su come combinare i dati offline [!DNL CRM] con i dati comportamentali in tempo reale per gli utenti autenticati, al fine di creare segmenti di pubblico e quindi inviare tali segmenti a [!DNL People-Based Destinations].

## Passaggio 1 - Configura impostazioni origine dati {#configure-data-source-settings}

A seconda che gli [DPUUID](../../reference/ids-in-aam.md) siano minuscoli, indirizzi e-mail con hash, potrebbe essere necessario configurare l&#39;origine dati che memorizzerà gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail  [](../../reference/ids-in-aam.md) DPUUID sono già minuscoli e con hash.**

In questo caso, passate a [Passo 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone](#configure-authentication).

 

**Scenario 2: gli indirizzi e-mail  [](../../reference/ids-in-aam.md) DPUUID non sono minuscoli e con hash.**

In questo caso, è necessario creare una nuova origine dati cross-device in cui memorizzare gli indirizzi e-mail con hash. Come procedere:

1. Accedete al vostro account  Audience Manager e andate a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, quindi fate clic su **[!UICONTROL Add New]**.
1. Immettere un **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati.
1. Nel menu a discesa **[!UICONTROL ID Type]**, selezionare **[!UICONTROL Cross Device]**.
1. Nella sezione **[!UICONTROL Data Source Settings]**, selezionare le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e attivare l&#39;opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilizzare il menu a discesa per selezionare l&#39;etichetta **[!UICONTROL Emails(SHA256, lowercased)]** per questa origine dati.
   >[!IMPORTANT]
   >
   >Questa opzione etichetta solo l&#39;origine dati come contenente i dati con hash con tale algoritmo specifico.  Audience Manager non esegue l&#39;hash dei dati in questo passaggio. Assicurati che gli indirizzi e-mail che intendi memorizzare in questa origine dati siano già crittografati con l&#39;algoritmo [!DNL SHA256]. In caso contrario, non sarà possibile utilizzarlo per [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consulta [Data Onboarding](people-based-destinations-prerequisites.md#data-onboarding) per le domande frequenti su come portare i dati offline in  Audience Manager per le destinazioni basate sulle persone.

Guardate il video seguente per un&#39;esercitazione video su come creare un&#39;origine dati per [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Passaggio 2 - Utilizzare gli ID dichiarati per far corrispondere DPUUID agli indirizzi e-mail con hash tramite chiamate HTTP in tempo reale {#match-email-addresses}

Per qualificare gli utenti autenticati per le caratteristiche basate su regola, è necessario inviare la qualifica tramite [ID dichiarati](../declared-ids.md).

### Esempio

Supponiamo che siano state create le due seguenti origini dati.

| ID origine dati | Contenuto origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

 

Quindi, vuoi qualificare gli ID CRM di seguito per la caratteristica nella tabella.

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash | Caratteristica |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 | location = US |

 

Il tuo ID dichiarato deve seguire la sintassi seguente:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

Nell’esempio precedente, la chiamata ID dichiarata dovrebbe essere simile alla seguente:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Passaggio 3 - Crea una regola di unione dei profili per la segmentazione {#create-profile-merge-rule-segmentation}

Il passo successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare al tuo [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Se hai già una regola definita con le opzioni **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**, puoi passare a [Passaggio 4 - Crea segmenti di pubblico](#create-audience-segments).

1. Accedete al vostro account  Audience Manager e andate a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Clic **[!UICONTROL Add New Rule]**.
3. Immettere una regola di unione dei profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Nella sezione **[!UICONTROL Profile Merge Rule Setup]**, selezionare la regola **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** dall&#39;elenco **[!UICONTROL Cross-Device Options]**.
5. Nell&#39;elenco **[!UICONTROL Cross-Device Profile Options]**, selezionare le origini dati sulle quali si desidera eseguire la segmentazione. Devono essere le origini dati che contengono i DPUUID esistenti.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Passaggio 4 - Creazione di segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti, utilizzare il [Generatore di segmenti](../segments/segment-builder.md). Se si dispone di segmenti di pubblico esistenti da inviare a [!DNL People-Based Destinations], passare a [Passaggio 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone](#configure-authentication).

## Passaggio 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedete al vostro account  Audience Manager e andate a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se avete già configurato un&#39;integrazione con una piattaforma social, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
2. Clic **[!UICONTROL Add Account]**.
3. Utilizzate il menu a discesa **[!UICONTROL People-Based Platform]** per selezionare la piattaforma con cui desiderate configurare l&#39;integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
4. Fare clic su **[!UICONTROL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
5. Dopo aver eseguito l&#39;autenticazione sull&#39;account della tua piattaforma sociale, verrai reindirizzato  Audience Manager in cui dovresti vedere gli account dell&#39;inserzionista associato. Selezionate l&#39;account dell&#39;inserzionista che desiderate utilizzare e fate clic su **[!UICONTROL Confirm]**.
6.  Audience Manager visualizza una notifica nella parte superiore della pagina per informarvi se l’account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere le notifiche quando l&#39;autenticazione della piattaforma social sta per scadere.

>[!IMPORTANT]
>
> Audience Manager gestisce l&#39;integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Consulta Rinnovo token di autenticazione per informazioni dettagliate su come rinnovare i token scaduti.

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
1. Nella sezione **[!UICONTROL Segment Mappings]**, selezionare i segmenti che si desidera inviare a questa destinazione. Si tratta dei segmenti creati al [Passaggio 4 - Create Audience Segments](#create-audience-segments).
1. Salva la destinazione.
