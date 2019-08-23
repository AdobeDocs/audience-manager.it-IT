---
description: Questo articolo spiega come configurare i tipi di pubblico Twitter personalizzati per le integrazioni nuove ed esistenti.
seo-description: Questo articolo spiega come configurare i tipi di pubblico Twitter personalizzati per le integrazioni nuove ed esistenti.
seo-title: Configurare i tipi di pubblico personalizzati su Twitter come destinazione basata su dispositivo self-service
solution: Audience Manager
title: Configurare i tipi di pubblico personalizzati su Twitter come destinazione basata su dispositivo self-service
translation-type: tm+mt
source-git-commit: bdc626ef11aacbf1fcbf138748b56acc24ec7b13

---


# Configurare [!DNL Twitter Tailored Audiences] come destinazione basata su dispositivo self-service {#configure-twitter}

Questo articolo spiega come configurare [i tipi di pubblico Twitter personalizzati](https://business.twitter.com/en/targeting/tailored-audiences.html) per le integrazioni nuove ed esistenti.

## Prerequisiti {#prerequisites}

Prima di configurare [!DNL Twitter Tailored Audiences] la destinazione, verificate di aver preso visione dei seguenti prerequisiti Twitter che dovete soddisfare.

1. Il tuo [!DNL Twitter Ads] account deve essere idoneo per la pubblicità. I nuovi [!DNL Twitter Ads] account non sono idonei per la pubblicità nelle prime 2 settimane dopo averli creati.
2. L'account utente Twitter a cui hai autorizzato accesso in Audience Manager deve disporre dell'autorizzazione [di manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) audience manager abilitata.
3. Se [state aggiornando l'integrazione Twitter esistente con l'amministrazione self-service](#update-existing-twitter-integrations), l'account utente di Twitter deve avere abilitato l'autorizzazione [Ad Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) .

## Aggiungere una nuova [!DNL Twitter Tailored Audiences] destinazione {#add-new-twitter-destination}

In questa sezione sono descritti i passaggi da seguire per la configurazione di una nuova destinazione basata su dispositivo. [!DNL Twitter Tailored Audiences] In questo scenario si presuppone che non esista [!DNL Twitter Tailored Audiences] una destinazione esistente configurata tramite il consulente Adobe o l'Assistenza clienti.

### Passaggio 1: Autenticazione con [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Prima di poter aggiungere la destinazione basata su dispositivo, devi collegare Audience Manager e il tuo [!DNL Twitter Tailored Audiences] account. Ecco come effettuare questa operazione:

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**. Se disponete di un'integrazione configurata in precedenza con una piattaforma di destinazione, dovreste visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
2. Fai clic su **[!DNL Add Account]**.
3. Seleziona [!DNL Twitter Tailored Audiences] e fai clic per **[!DNL Confirm]** essere reindirizzati alla pagina di autenticazione. ![piattaforme integrate](assets/dbd-integrated-platforms.png)
4. Una volta autenticato, verrete reindirizzati ad Audience Manager dove dovreste vedere gli account pubblicitari associati. Selezionate l'account pubblicitario che desiderate utilizzare e fate clic **[!DNL Confirm]** su.

### Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2-create-new-destination}

Dopo aver collegato Audience Manager e la tua [!DNL Twitter Tailored Audiences], puoi creare la nuova destinazione. Ecco come effettuare questa operazione:

>[!NOTE]
>
>Non potete modificare il nome di una destinazione esistente basata su dispositivo. Assicuratevi di fornire un nome che consenta di identificare correttamente la destinazione.

1. Accedi al tuo account Audience Manager, vai a **[!DNL Audience Data > Destinations]** e fai clic **[!DNL Create Destination]** su.
2. Nella **[!DNL Basic Information]** sezione, immettete una **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizzate le impostazioni seguenti: ![setup](assets/dbd-new-basic.png)
3. Fai clic su **[!DNL Next]**.
4. Scegliete [le etichette](/help/using/features/data-export-controls.md#controls-labels) esportazione dati che desiderate impostare per questa destinazione.
5. Fai clic su **[!DNL Save]**.
6. Nella **[!DNL Segment Mappings]** sezione, seleziona i segmenti di pubblico che vuoi inviare a questa destinazione.
7. Salvate la destinazione.

## Aggiorna integrazioni Twitter esistenti a amministrazione self-service {#update-existing-twitter-integrations}

Per migliorare l'esperienza utente e semplificare il processo di configurazione, stiamo aggiornando l' [!DNL Twitter Tailored Audiences] integrazione a un modello self-service, in cui puoi eseguire la configurazione autonomamente, dall'interfaccia utente di Audience Manager. Questa sezione descrive i passaggi necessari per aggiornare l'integrazione con Twitter esistente.

>[!IMPORTANT]
>
>I passaggi descritti di seguito sono applicabili solo se hai un'integrazione esistente con [!DNL Twitter Tailored Audiences]un consulente Audience Manager o l'Assistenza clienti. Il processo di aggiornamento completo della destinazione al modello autonomo può richiedere fino a 5 giorni lavorativi. Nel frattempo, la destinazione è ancora attiva e Audience Manager continua a inviare audience.
> Prima di effettuare la migrazione [al](#prerequisites) [!DNL Twitter Tailored Audiences] modello self-service, consultate l'articolo 3 nei Prerequisiti.

Effettuate le seguenti operazioni per migrare [!DNL Twitter Tailored Audiences] la destinazione esistente nel modello autonomo.

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**.
1. Fai clic su **[!DNL Add Account]**.
1. Seleziona [!DNL Twitter Tailored Audiences] e fai clic per **[!DNL Confirm]** essere reindirizzati alla pagina di autenticazione. ![piattaforme integrate](assets/dbd-integrated-platforms.png)
1. Dopo aver autenticato il tuo [!DNL Twitter] account, verrai reindirizzato ad Audience Manager dove dovresti vedere i tuoi account pubblicitari associati. Selezionate l'account pubblicitario che desiderate utilizzare e fate clic **[!DNL Confirm]** su.
1. Vai a **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** e fai clic sulla destinazione Twitter che devi configurare.
1. Fai clic su **[!UICONTROL Edit]**. Nella **[!UICONTROL Basic Information]** sezione, fai clic sul **[!UICONTROL Integrated Account]** menu a discesa e seleziona l' [!DNL Twitter] account con cui hai autenticato il passaggio 4.
1. **[!UICONTROL Save]** la destinazione.

## Convalida della migrazione a Amministrazione self-service {#migration-validation}

La migrazione completa delle integrazioni esistenti [!DNL Twitter] all'amministrazione self-service può richiedere fino a 7 giorni. Una volta completata la migrazione, Audience Manager visualizza una notifica nell'interfaccia utente.

Vedrai anche un nuovo set di audience nel [!DNL Twitter] tuo account, con i relativi nomi prefissi da [! DNL [Adobe DMP Audience]]. La popolazione dell'audience deve essere completamente retrocompilata fino a 7 giorni. Una volta completata la migrazione, usa queste nuove audience invece dei vecchi.

## Considerazioni sulla mappatura segmenti {#segment-mapping-considerations}

Quando mappatura di segmenti di pubblico su Twitter, assicurati di soddisfare i seguenti requisiti di denominazione segmenti:

* Fornire nomi di mappatura segmenti leggibili. Consigliamo di utilizzare lo stesso nome utilizzato per i segmenti Audience Manager.
* Non utilizzare virgole nel segmento e nomi di mappatura segmenti.

### Esempio 

* Nome corretto del segmento o della mappatura: " US and European Shoppers ",
* Nome di segmento o mappatura errato: " US, Europa 5 h 0 PP 3 rs ".

>[!IMPORTANT]
>
>Non puoi modificare i nomi dei segmenti già mappati. Audience Manager usa i nomi dei segmenti per identificare correttamente i segmenti nell'integrazione.
