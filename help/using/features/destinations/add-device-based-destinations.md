---
description: Questo articolo spiega come configurare nuove destinazioni basate su dispositivi dall'interfaccia utente di Audience Manager.
seo-description: Questo articolo spiega come configurare nuove destinazioni basate su dispositivi dall'interfaccia utente di Audience Manager.
seo-title: Aggiungere nuove destinazioni basate su dispositivo
solution: Audience Manager
title: Aggiungere nuove destinazioni basate su dispositivo
translation-type: tm+mt
source-git-commit: d185a1d418e99abb99c36b28dfb419a1fb3b60f5

---


# Aggiungere nuove destinazioni basate su dispositivo {#add-new-device-based-destinations}

Questo articolo spiega come configurare nuove destinazioni basate su dispositivi dall'interfaccia utente di Audience Manager.

## Panoramica {#overview}

Il processo di aggiunta di una nuova destinazione basata su dispositivo consiste in due passaggi principali. Innanzitutto, devi configurare l'integrazione tra Audience Manager e il partner di destinazione. In tal caso, potete creare una nuova destinazione basata su dispositivo.

>[!IMPORTANT]
>
>Non tutte le destinazioni basate su dispositivo sono idonee al flusso di lavoro di configurazione self-service. Se la destinazione basata su dispositivo che devi aggiungere non viene visualizzata nell'elenco delle destinazioni, contatta il tuo consulente Adobe o l'Assistenza clienti per assistenza.

## Passaggio 1: Autenticazione con una piattaforma di destinazione {#step1}

Prima di creare una nuova destinazione basata su dispositivo, devi configurare l'integrazione tra Audience Manager e la piattaforma di destinazione. Ecco come effettuare questa operazione:

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**. Se disponete di un'integrazione configurata in precedenza con una piattaforma di destinazione, dovreste visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
2. Fai clic su **[!DNL Add Account]**.
3. Selezionate la piattaforma di destinazione con cui desiderate autenticare e fate clic per **[!DNL Confirm]** essere reindirizzati alla pagina di autenticazione della piattaforma selezionata. ![piattaforme integrate](assets/dbd-integrated-platforms.png)
4. Dopo aver eseguito l'autenticazione nell'account della piattaforma di destinazione, verrete reindirizzati ad Audience Manager dove dovrebbero essere presentati gli account pubblicitari associati. Selezionate l'account pubblicitario che desiderate utilizzare e fate clic **[!DNL Confirm]** su.

## Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2}

Dopo aver configurato l'integrazione della piattaforma di destinazione, potete creare la nuova destinazione. Ecco come effettuare questa operazione:

>[!NOTE]
>
>Non potete modificare il nome di una destinazione esistente basata su dispositivo. Assicuratevi di fornire un nome che consenta di identificare correttamente la destinazione.

1. Accedi al tuo account Audience Manager, vai a **[!DNL Audience Data > Destinations]** e fai clic **[!DNL Create Destination]** su.
2. Nella **[!DNL Basic Information]** sezione, immettete una **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizzate le impostazioni nell'elenco seguente: ![setup](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: Selezionate la piattaforma di destinazione a cui desiderate inviare i segmenti di pubblico.
   * **[!DNL Account]**: selezionate l'account pubblicitario desiderato associato alla piattaforma selezionata.
3. Fai clic su **[!DNL Next]**.
4. Scegliete [le etichette](/help/using/features/data-export-controls.md#controls-labels) esportazione dati che desiderate impostare per questa destinazione.
5. Fai clic su **[!DNL Save]**.
6. Nella **[!DNL Segment Mappings]** sezione, seleziona i segmenti di pubblico che vuoi inviare a questa destinazione.
7. Salvate la destinazione.

