---
description: Questa pagina include istruzioni dettagliate su come combinare i dati CRM offline con i dati comportamentali in tempo reale affinché gli utenti autenticati possano creare segmenti di pubblico e inviarli a destinazioni basate su persone.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: 'Flusso di lavoro C: Personalization basato su attività autenticate combinate con dati offline'
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 0%

---

# Flusso di lavoro C: Personalization basato su attività autenticate combinate con dati offline {#workflow-c}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

Questa pagina include istruzioni dettagliate su come combinare dati [!DNL CRM] offline con dati comportamentali in tempo reale per consentire agli utenti autenticati di creare segmenti di pubblico e inviarli a [!DNL People-Based Destinations].

## Passaggio 1: configurare le impostazioni di Data Source {#configure-data-source-settings}

A seconda che i [DPUUID](../../reference/ids-in-aam.md) siano indirizzi e-mail con hash in minuscolo, potrebbe essere necessario configurare l&#39;origine dati che memorizzerà gli indirizzi e-mail con hash.

 

**Scenario 1: gli indirizzi e-mail con hash [DPUUID](../../reference/ids-in-aam.md) sono già minuscoli.**

In questo caso, vai al [Passaggio 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone](#configure-authentication).

 

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

## Passaggio 2: utilizzare gli ID dichiarati per associare i DPUUID agli indirizzi e-mail con hash tramite chiamate HTTP in tempo reale {#match-email-addresses}

Per qualificare gli utenti autenticati per le caratteristiche basate su regole, devi inviare la qualifica delle caratteristiche tramite [ID dichiarati](../declared-ids.md).

### Esempio

Supponiamo che tu abbia creato le due seguenti origini dati.

| ID origine dati | Contenuti dell’origine dati |
| -------------- | -------------------------- |
| 999999 | DPUUID esistenti (ID CRM) |
| 987654 | Indirizzi e-mail con hash |

 

Quindi, desideri qualificare gli ID del sistema di gestione delle relazioni con i clienti sottostanti per la caratteristica nella tabella.

| DPUUID (ID CRM) | Indirizzo e-mail | Indirizzo e-mail con hash | Caratteristica |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

L’ID dichiarato deve seguire questa sintassi:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

Nell’esempio precedente, la chiamata dell’ID dichiarato dovrebbe essere simile alla seguente:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Passaggio 3: creare una regola di unione profili per la segmentazione {#create-profile-merge-rule-segmentation}

Il passaggio successivo consiste nella creazione di una nuova regola di unione che ti aiuterà a creare i segmenti di pubblico da inviare a [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Se hai già definito una regola con le opzioni **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]**, puoi passare al [Passaggio 4 - Crea segmenti di pubblico](#create-audience-segments).

1. Accedi al tuo account Audience Manager e passa a **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Fare clic su **[!UICONTROL Add New Rule]**.
3. Immettere una regola di unione profili **[!UICONTROL Name]** e **[!UICONTROL Description]**.
4. Nella sezione **[!UICONTROL Profile Merge Rule Setup]** selezionare la regola **[!UICONTROL Current Authenticated Profiles]** o **[!UICONTROL Last Authenticated Profiles]** dall&#39;elenco **[!UICONTROL Cross-Device Options]**.
5. Nell&#39;elenco **[!UICONTROL Cross-Device Profile Options]** selezionare le origini dati sulle quali si desidera eseguire la segmentazione. Queste dovrebbero essere le origini dati contenenti gli attuali DPUUID.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Passaggio 4: creare segmenti di pubblico {#create-audience-segments}

Per creare nuovi segmenti, utilizza [Segment Builder](../segments/segment-builder.md). Se hai segmenti di pubblico esistenti che desideri inviare a [!DNL People-Based Destinations], passa a [Passaggio 5 - Configurare l&#39;autenticazione della piattaforma basata sulle persone](#configure-authentication).

## Passaggio 5: configurare l’autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account Audience Manager e passa a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma social, dovresti visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata su persone](assets/pbd-config.png)
2. Fare clic su **[!UICONTROL Add Account]**.
3. Utilizza il menu a discesa **[!UICONTROL People-Based Platform]** per selezionare la piattaforma con cui configurare l&#39;integrazione.
   ![people-based-platform](assets/pbd-add.png)
4. Fare clic su **[!UICONTROL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
5. Dopo aver eseguito l’autenticazione all’account della piattaforma social, vieni reindirizzato all’Audience Manager in cui dovresti visualizzare gli account pubblicitari associati. Selezionare l&#39;account pubblicitario che si desidera utilizzare e fare clic su **[!UICONTROL Confirm]**.
6. In Audience Manager, nella parte superiore della pagina viene visualizzata una notifica per comunicare se l’account è stato aggiunto correttamente. La notifica ti consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere notifiche quando l’autenticazione della piattaforma social network sta per scadere.

>[!IMPORTANT]
>
>Audience Manager gestisce l’integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. Consulta Rinnovo del token di autenticazione per informazioni su come rinnovare i token scaduti.

## Passaggio 6: creare una destinazione basata su persone {#create-destination}

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
1. Nella sezione **[!UICONTROL Segment Mappings]**, seleziona i segmenti che desideri inviare a questa destinazione. Si tratta dei segmenti creati nel [Passaggio 4 - Creazione di segmenti di pubblico](#create-audience-segments).
1. Salva la destinazione.
