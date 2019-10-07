---
description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-title: Configurare l'audience personalizzata di Twitter come destinazione autonoma basata su dispositivo
solution: Audience Manager
title: Configurare l'audience personalizzata di Twitter come destinazione autonoma basata su dispositivo
translation-type: tm+mt
source-git-commit: a267dab29a8d0e47a27a7db2a4288ae677a1180d

---


# Configurare [!DNL Twitter Tailored Audiences] come destinazione autonoma basata su dispositivo {#configure-twitter}

In questo articolo viene illustrato come configurare l'audience [personalizzata per](https://business.twitter.com/en/targeting/tailored-audiences.html) Twitter per le integrazioni nuove ed esistenti.

## Prerequisiti {#prerequisites}

Prima di configurare la [!DNL Twitter Tailored Audiences] destinazione, accertatevi di verificare i seguenti prerequisiti Twitter da soddisfare.

1. Il tuo [!DNL Twitter Ads] account deve essere idoneo per la pubblicità. I nuovi [!DNL Twitter Ads] account non sono ammessi alla pubblicità nelle prime due settimane dopo la loro creazione.
1. L'account utente Twitter per il quale avete autorizzato l'accesso in Audience Manager deve avere l'autorizzazione [Partner Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) abilitata.
1. Se state [aggiornando l'integrazione Twitter esistente a un'amministrazione](#update-existing-twitter-integrations)self-service, l'account utente Twitter deve avere l'autorizzazione [Ad Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) abilitata.
1. Quando crei la prima [!DNL Twitter Tailored Audiences] destinazione nell’istanza di Audience Manager, contatta il servizio di consulenza Adobe o l’assistenza clienti per abilitare la sincronizzazione [!DNL Twitter] ID (ID origine dati = 1123) per il tuo account. Questo è necessario per la corretta sincronizzazione tra Audience Manager e [!DNL Twitter].

## Aggiungi una nuova [!DNL Twitter Tailored Audiences] destinazione {#add-new-twitter-destination}

Questa sezione descrive i passaggi da seguire per configurare una nuova destinazione basata su dispositivo per [!DNL Twitter Tailored Audiences]. Questo scenario presuppone che non sia configurata alcuna [!DNL Twitter Tailored Audiences] destinazione tramite il consulente Adobe o l'Assistenza clienti.

### Passaggio 1: Autenticazione con [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Prima di poter aggiungere la destinazione basata sui dispositivi, è necessario collegare Audience Manager al proprio [!DNL Twitter Tailored Audiences] account. Come procedere:

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**. Se disponete di un'integrazione configurata in precedenza con una piattaforma di destinazione, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
2. Fai clic su **[!DNL Add Account]**.
3. Selezionate [!DNL Twitter Tailored Audiences] e fate clic **[!DNL Confirm]** per reindirizzare la pagina di autenticazione.                     ![piattaforme integrate](assets/dbd-integrated-platforms.png)
4. Dopo l'autenticazione, verrete reindirizzati ad Audience Manager dove dovrebbero essere visualizzati gli account dell'inserzionista associato. Selezionate l’account dell’inserzionista da usare e fate clic su **[!DNL Confirm]**.

### Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2-create-new-destination}

Dopo aver collegato Audience Manager e il vostro account [!DNL Twitter Tailored Audiences], potete creare la nuova destinazione. Come procedere:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione esistente basata su dispositivo. Assicuratevi di fornire un nome che vi aiuterà a identificare correttamente la destinazione.

1. Accedi al tuo account Audience Manager, vai a **[!DNL Audience Data > Destinations]** e fai clic su **[!DNL Create Destination]**.
2. Nella **[!DNL Basic Information]** sezione immettere un **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizzare le impostazioni seguenti: ![setup](assets/dbd-new-basic.png)
3. Fai clic su **[!DNL Next]**.
4. Scegliere le etichette [di esportazione](/help/using/features/data-export-controls.md#controls-labels) dati da impostare per questa destinazione.
5. Fai clic su **[!DNL Save]**.
6. Nella **[!DNL Segment Mappings]** sezione, selezionate i segmenti di pubblico che desiderate inviare a questa destinazione.
7. Salva la destinazione.

## Aggiornamento Delle Integrazioni Twitter Esistenti All'Amministrazione Self-Service {#update-existing-twitter-integrations}

Per migliorare l'esperienza dell'utente e semplificare il processo di configurazione, stiamo aggiornando l' [!DNL Twitter Tailored Audiences] integrazione a un modello self-service, dove puoi eseguire la configurazione autonomamente dall'interfaccia utente di Audience Manager. Questa sezione descrive i passaggi necessari per aggiornare l'integrazione esistente di Twitter.

>[!IMPORTANT]
>
>I passaggi descritti di seguito si applicano solo se disponete di un'integrazione esistente con [!DNL Twitter Tailored Audiences], configurata da un consulente Audience Manager o dall'Assistenza clienti.
> Vedere l'articolo numero 3 in [Prerequisiti](#prerequisites) prima di migrare [!DNL Twitter Tailored Audiences] al modello self-service.

Seguite i passaggi riportati di seguito per migrare la [!DNL Twitter Tailored Audiences] destinazione esistente al modello self-service.

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**.
2. Fai clic su **[!DNL Add Account]**.
3. Selezionate [!DNL Twitter Tailored Audiences] e fate clic **[!DNL Confirm]** per reindirizzare la pagina di autenticazione. ![piattaforme integrate](assets/dbd-integrated-platforms.png)
4. Dopo aver eseguito l'autenticazione con il tuo [!DNL Twitter] account, verrai reindirizzato ad Audience Manager, dove potrai vedere gli account degli inserzionisti associati. Selezionate l’account dell’inserzionista da usare e fate clic su **[!DNL Confirm]**.
5. Vai a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** e fai clic sulla destinazione Twitter da configurare.
6. Fai clic su **[!UICONTROL Edit]**. Nella **[!UICONTROL Basic Information]** sezione fare clic sul menu a **[!UICONTROL Integrated Account]** discesa e selezionare l' [!DNL Twitter] account con cui si è autenticato al punto 4.
7. **[!UICONTROL Save]** la destinazione.

<!-- ## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## Considerazioni sulla mappatura dei segmenti {#segment-mapping-considerations}

Quando mappate i segmenti di pubblico su Twitter, accertatevi di soddisfare i seguenti requisiti di denominazione dei segmenti:

* Fornisci nomi di mappatura dei segmenti leggibili dall’utente. È consigliabile utilizzare lo stesso nome utilizzato per i segmenti Audience Manager.
* Non utilizzare virgole nei nomi di mappatura segmenti e segmenti.

### Esempio 

* Correggi il nome del segmento o della mappatura: "Acquirenti statunitensi ed europei";
* Nome segmento o mappatura errato: "US, European 5h0pP3rs".

>[!IMPORTANT]
>
>Non è possibile modificare i nomi dei segmenti già mappati. Audience Manager utilizza i nomi dei segmenti per identificare correttamente i segmenti nell'integrazione.

## Considerazioni sui tassi di corrispondenza {#match-rates-considerations}

Quando si utilizza [!UICONTROL Twitter Tailored Audiences], le [!UICONTROL Segment Addressable Audience] metriche e quelle [!UICONTROL Segment Match Rate] della pagina di destinazione non visualizzeranno alcun valore. Si tratta di un comportamento normale, in quanto l'audience che corrisponde con le percentuali di corrispondenza per questa destinazione viene gestita e ospitata da [!UICONTROL Twitter], non da Adobe.
