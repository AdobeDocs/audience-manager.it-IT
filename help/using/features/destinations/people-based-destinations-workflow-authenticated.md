---
description: 'Questa pagina include indicazioni dettagliate su come combinare dati CRM offline con dati comportamentali in tempo reale per gli utenti autenticati al fine di creare segmenti di pubblico e quindi inviare tali segmenti di pubblico a Destinazioni basate su persone. '
seo-description: 'Questa pagina include indicazioni dettagliate su come combinare dati CRM offline con dati comportamentali in tempo reale per gli utenti autenticati al fine di creare segmenti di pubblico e quindi inviare tali segmenti di pubblico a Destinazioni basate su persone.  '
seo-title: 'Flusso di lavoro C: personalizzazione basata su attività autenticate combinate con dati offline'
solution: Audience Manager
title: 'Flusso di lavoro C: personalizzazione basata su attività autenticate combinate con dati offline'
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 5%

---

# Flusso di lavoro C: personalizzazione basata su attività autenticate combinate con dati offline {#workflow-c}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

Questa pagina include indicazioni dettagliate su come combinare dati offline [!DNL CRM] con dati comportamentali in tempo reale per gli utenti autenticati al fine di creare segmenti di pubblico e quindi inviare tali segmenti a [!DNL People-Based Destinations].

## Passaggio 1: configurare le impostazioni delle origini dati {#configure-data-source-settings}

A seconda che i [DPUUID](../../reference/ids-in-aam.md) siano minuscole o meno, gli indirizzi e-mail con hash potrebbero essere necessari per configurare l&#39;origine dati in cui verranno memorizzati gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail con hash  [](../../reference/ids-in-aam.md) DPUUID sono già minuscoli.**

In questo caso, passa a [Passaggio 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone](#configure-authentication).

 

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

## Passaggio 2: utilizzare ID dichiarati per associare DPUUID agli indirizzi e-mail con hash tramite chiamate HTTP in tempo reale {#match-email-addresses}

Per qualificare gli utenti autenticati per le caratteristiche basate su regole, devi inviare la qualifica della caratteristica tramite [ID dichiarati](../declared-ids.md).

### Esempio

Supponiamo che tu abbia creato le due seguenti origini dati.

| ID origine dati | Contenuto dell&#39;origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

 

Quindi, vuoi qualificare gli ID CRM riportati di seguito per la caratteristica nella tabella.

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash | Caratteristica |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 | posizione = US |

 

L&#39;ID dichiarato deve seguire questa sintassi:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

Nell’esempio precedente, la chiamata ID dichiarata deve essere simile alla seguente:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Passaggio 3: creare una regola di unione profili per la segmentazione {#create-profile-merge-rule-segmentation}

Il passaggio successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare al tuo [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Se disponi già di una regola definita con le opzioni **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**, puoi passare a [Passaggio 4 - Crea segmenti di pubblico](#create-audience-segments).

1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Clic **[!UICONTROL Add New Rule]**.
3. Immetti una regola di unione profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Nella sezione **[!UICONTROL Profile Merge Rule Setup]** , seleziona la regola **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** dall’elenco **[!UICONTROL Cross-Device Options]**.
5. Nell’elenco **[!UICONTROL Cross-Device Profile Options]**, seleziona le origini dati sulle quali desideri eseguire la segmentazione. Devono essere le origini dati che contengono i DPUUID esistenti.
   ![configurazione delle regole di unione](assets/pbd-pmr-combined.png)

## Passaggio 4 - Creare segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti, utilizza il [Generatore di segmenti](../segments/segment-builder.md). Se hai segmenti di pubblico esistenti da inviare a [!DNL People-Based Destinations], passa a [Passaggio 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone](#configure-authentication).

## Passaggio 5: configurare l’autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma social, visualizzala in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
2. Clic **[!UICONTROL Add Account]**.
3. Utilizza il menu a discesa **[!UICONTROL People-Based Platform]** per selezionare la piattaforma con cui desideri configurare l’integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
4. Fai clic su **[!UICONTROL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
5. Dopo aver eseguito l’autenticazione all’account della piattaforma social, vieni reindirizzato all’Audience Manager in cui dovresti visualizzare gli account dell’inserzionista associati. Seleziona l’account dell’inserzionista da utilizzare e fai clic su **[!UICONTROL Confirm]**.
6. In Audience Manager viene visualizzata una notifica nella parte superiore della pagina per sapere se l’account è stato aggiunto correttamente. La notifica ti consente anche di aggiungere un indirizzo e-mail di contatto per ricevere notifiche quando l’autenticazione della piattaforma social sta per scadere.

>[!IMPORTANT]
>
>Audience Manager gestisce l’integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Per informazioni dettagliate su come rinnovare i token scaduti, consulta Rinnovo token di autenticazione .

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
1. Nella sezione **[!UICONTROL Segment Mappings]** , seleziona i segmenti che desideri inviare a questa destinazione. Si tratta dei segmenti creati al [Passaggio 4 - Creare segmenti di pubblico](#create-audience-segments).
1. Salva la destinazione.
