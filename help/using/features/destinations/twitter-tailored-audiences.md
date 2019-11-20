---
description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-title: Configurare l'audience personalizzata di Twitter come destinazione autonoma basata su dispositivo
solution: Audience Manager
title: Configurare l'audience personalizzata di Twitter come destinazione autonoma basata su dispositivo
translation-type: tm+mt
source-git-commit: 4af2d7a4e2162f8d69273cf76aecb5f1ff00e7b6

---


# Configurare [!DNL Twitter Tailored Audiences] come destinazione autonoma basata su dispositivo {#configure-twitter}

Questo articolo spiega come configurare un'integrazione con audience [personalizzate per](https://business.twitter.com/en/targeting/tailored-audiences.html)Twitter.

## Prerequisiti {#prerequisites}

Prima di configurare la [!DNL Twitter Tailored Audiences] destinazione, accertatevi di verificare i seguenti prerequisiti Twitter da soddisfare.

1. Il tuo [!DNL Twitter Ads] account deve essere idoneo per la pubblicità. I nuovi [!DNL Twitter Ads] account non sono ammessi alla pubblicità nelle prime due settimane dopo la loro creazione.
2. Il tuo account [!DNL Twitter] utente per il quale hai autorizzato l'accesso in Audience Manager deve avere l'autorizzazione [Partner Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) abilitata.
3. Quando crei la prima [!DNL Twitter Tailored Audiences] destinazione nell’istanza di Audience Manager, contatta il servizio di consulenza Adobe o l’assistenza clienti per abilitare la sincronizzazione [!DNL Twitter] ID (ID origine dati = 1123) per il tuo account. Questo è necessario per la corretta sincronizzazione tra Audience Manager e [!DNL Twitter].

## Aggiungi una nuova [!DNL Twitter Tailored Audiences] destinazione {#add-new-twitter-destination}

Questa sezione descrive i passaggi da seguire per configurare una nuova destinazione basata su dispositivo per [!DNL Twitter Tailored Audiences]. Questo scenario presuppone che non sia configurata alcuna [!DNL Twitter Tailored Audiences] destinazione tramite il consulente Adobe o l'Assistenza clienti.

### Passaggio 1: Autenticazione con [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Prima di poter aggiungere la destinazione basata sui dispositivi, è necessario collegare Audience Manager al proprio [!DNL Twitter Tailored Audiences] account. Come procedere:

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**. Se disponete di un'integrazione configurata in precedenza con una piattaforma di destinazione, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
1. Fai clic su **[!DNL Add Account]**.
1. Selezionate [!DNL Twitter Tailored Audiences] e fate clic **[!DNL Confirm]** per reindirizzare la pagina di autenticazione.                     ![piattaforme integrate](assets/dbd-integrated-platforms.png)
1. Dopo l'autenticazione, verrete reindirizzati ad Audience Manager dove dovrebbero essere visualizzati gli account dell'inserzionista associato. Selezionate l’account dell’inserzionista da usare e fate clic su **[!DNL Confirm]**.

### Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2-create-new-destination}

Dopo aver collegato Audience Manager e il vostro account [!DNL Twitter Tailored Audiences], potete creare la nuova destinazione. Come procedere:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione esistente basata su dispositivo. Assicuratevi di fornire un nome che vi consenta di identificare correttamente la destinazione.

1. Accedi al tuo account Audience Manager, vai a **[!DNL Audience Data > Destinations]** e fai clic su **[!DNL Create Destination]**.
1. Nella **[!DNL Basic Information]** sezione immettere un **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizzare le impostazioni seguenti: ![setup](assets/dbd-new-basic.png)
1. Fai clic su **[!DNL Next]**.
1. Scegliere le etichette [di esportazione](/help/using/features/data-export-controls.md#controls-labels) dati da impostare per questa destinazione.
1. Fai clic su **[!DNL Save]**.
1. Nella **[!DNL Segment Mappings]** sezione, selezionate i segmenti di pubblico che desiderate inviare a questa destinazione.
1. Salva la destinazione.

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## Considerazioni sulla mappatura dei segmenti {#segment-mapping-considerations}

Quando mappate i segmenti di pubblico su [!UICONTROL Twitter], accertatevi di soddisfare i seguenti requisiti di denominazione dei segmenti:

* Fornisci nomi di mappatura dei segmenti leggibili dall’utente. È consigliabile utilizzare lo stesso nome utilizzato per i segmenti Audience Manager.
* Non utilizzare caratteri speciali (`,``%` `:``;` `@``/``=` `?` `$`) nei nomi di mappatura segmenti e segmenti. Se il nome del segmento di Audience Manager contiene questi caratteri, rimuoverli prima di mappare il segmento a una [!UICONTROL Twitter] destinazione.

### Esempio 

* Correggi il nome del segmento o della mappatura: "Acquirenti statunitensi ed europei";
* Nome segmento o mappatura errato: "US, European 5h0pP3rs".

>[!IMPORTANT]
>
>Non è possibile modificare i nomi dei segmenti già mappati. Audience Manager utilizza i nomi dei segmenti per identificare correttamente i segmenti nell'integrazione.

## Considerazioni sui tassi di corrispondenza {#match-rates-considerations}

* Quando si utilizza [!UICONTROL Twitter Tailored Audiences], le [!UICONTROL Segment Addressable Audience] metriche e quelle [!UICONTROL Segment Match Rate] della pagina di destinazione non visualizzeranno alcun valore. Si tratta di un comportamento normale, in quanto l'audience che corrisponde con le percentuali di corrispondenza per questa destinazione viene gestita e ospitata da [!UICONTROL Twitter], non da Adobe.
* Al momento, l'integrazione tra Audience Manager e [!UICONTROL Twitter Tailored Audiences] non supporta i backfill storici dell'audience. Ciò significa che solo le qualifiche del segmento che si verificano *dopo* che il segmento è mappato su una destinazione Twitter vengono inviate [!UICONTROL Twitter] in tempo reale.
