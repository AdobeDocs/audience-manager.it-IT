---
description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-title: Configurare l'audience personalizzata di Twitter come destinazione autonoma basata su dispositivo
solution: Audience Manager
title: Configurare l'audience personalizzata di Twitter come destinazione autonoma basata su dispositivo
translation-type: tm+mt
source-git-commit: c6318921b49603015b4670a361ec85ffa29abb30

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
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page.                     ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.

### Passaggio 2: Create a New Device-Based Destination {#step2-create-new-destination}

After you have linked Audience Manager and your , you can create the new destination. [!DNL Twitter Tailored Audiences] Here's how to do this:

>[!NOTE]
>
>You cannot change the name of an existing device-based destination. Make sure to provide a name that will help you identify the destination correctly.

1. Log in to your Audience Manager account, go to , and click .**[!DNL Audience Data > Destinations]****[!DNL Create Destination]**
2. In the  section, enter a  and  for your new destination, and use the settings below: setup **[!DNL Basic Information]****[!DNL Name]****[!DNL Description]**![](assets/dbd-new-basic.png)
3. Fai clic su **[!DNL Next]**.
4. Choose the Data Export Labels that you want to set for this destination.[](/help/using/features/data-export-controls.md#controls-labels)
5. Fai clic su **[!DNL Save]**.
6. In the  section, select the audience segments that you want to send to this destination.**[!DNL Segment Mappings]**
7. Save the destination.

## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

Per migliorare l'esperienza dell'utente e semplificare il processo di configurazione, stiamo aggiornando l' [!DNL Twitter Tailored Audiences] integrazione a un modello self-service, dove puoi eseguire la configurazione autonomamente dall'interfaccia utente di Audience Manager. Questa sezione descrive i passaggi necessari per aggiornare l'integrazione esistente di Twitter.

>[!IMPORTANT]
>
>I passaggi descritti di seguito si applicano solo se disponete di un'integrazione esistente con [!DNL Twitter Tailored Audiences], configurata da un consulente Audience Manager o dall'Assistenza clienti. Il processo di aggiornamento completo della destinazione al modello self-service potrebbe richiedere fino a 5 giorni lavorativi. Nel frattempo, la destinazione è ancora attiva e Audience Manager continua a inviarvi audience.
> Vedere l'articolo numero 3 in [Prerequisiti](#prerequisites) prima di migrare [!DNL Twitter Tailored Audiences] al modello self-service.

Seguite i passaggi riportati di seguito per migrare la [!DNL Twitter Tailored Audiences] destinazione esistente al modello self-service.

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**.
1. Fai clic su **[!DNL Add Account]**.
1. Selezionate [!DNL Twitter Tailored Audiences] e fate clic **[!DNL Confirm]** per reindirizzare la pagina di autenticazione. ![piattaforme integrate](assets/dbd-integrated-platforms.png)
1. Dopo aver eseguito l'autenticazione con il tuo [!DNL Twitter] account, verrai reindirizzato ad Audience Manager, dove potrai vedere gli account degli inserzionisti associati. Selezionate l’account dell’inserzionista da usare e fate clic su **[!DNL Confirm]**.
1. Vai a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** e fai clic sulla destinazione Twitter da configurare.
1. Fai clic su **[!UICONTROL Edit]**. Nella **[!UICONTROL Basic Information]** sezione fare clic sul menu a **[!UICONTROL Integrated Account]** discesa e selezionare l' [!DNL Twitter] account con cui si è autenticato al punto 4.
1. **[!UICONTROL Save]** la destinazione.

## Convalida della migrazione a Self-Service Administration {#migration-validation}

La migrazione completa delle [!DNL Twitter] integrazioni esistenti all'amministrazione self-service può richiedere fino a 7 giorni. Al termine della migrazione, Audience Manager visualizza una notifica nell'interfaccia utente.

Vedrete anche un nuovo set di audience nel vostro [!DNL Twitter] account, con i loro nomi con il prefisso [[!DNL Adobe DMP Audience]]. Consentite fino a 7 giorni per consentire al pubblico di essere completamente riempito. Una volta completata la migrazione, dovrete utilizzare questi nuovi tipi di pubblico invece dei vecchi.

## Considerazioni sulla mappatura dei segmenti {#segment-mapping-considerations}

Quando mappate i segmenti di pubblico su Twitter, accertatevi di soddisfare i seguenti requisiti di denominazione dei segmenti:

* Fornisci nomi di mappatura dei segmenti leggibili dall’utente. È consigliabile utilizzare lo stesso nome utilizzato per i segmenti Audience Manager.
* Non utilizzare virgole nei nomi di mappatura segmenti e segmenti.

### Esempio 

* Correggi il nome del segmento o della mappatura: "Acquirenti statunitensi ed europei";
* Nome segmento o mappatura errato: "US, European 5h0pP3rs".

>[!IMPORTANT]
>
>You cannot change the names of already mapped segments. Audience Manager utilizza i nomi dei segmenti per identificare correttamente i segmenti nell'integrazione.

## Considerazioni sui tassi di corrispondenza {#match-rates-considerations}

When using , the  and  metrics from the destination page will not display any values. [!UICONTROL Twitter Tailored Audiences][!UICONTROL Segment Addressable Audience][!UICONTROL Segment Match Rate] This is normal behavior, since audience matching along with the match rates for this destination are handled and hosted by , not Adobe.[!UICONTROL Twitter]
