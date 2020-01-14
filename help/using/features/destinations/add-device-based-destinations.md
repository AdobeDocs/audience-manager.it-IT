---
description: Questo articolo spiega come configurare nuove destinazioni basate sui dispositivi dall’interfaccia utente di Audience Manager.
seo-description: Questo articolo spiega come configurare nuove destinazioni basate sui dispositivi dall’interfaccia utente di Audience Manager.
seo-title: Aggiungi nuove destinazioni basate su dispositivo
solution: Audience Manager
title: Aggiungi nuove destinazioni basate su dispositivo
translation-type: tm+mt
source-git-commit: 4cc7077cd5911bc603db254d9b55f129ce8f6cd5

---


# Aggiungi nuove destinazioni basate su dispositivo {#add-new-device-based-destinations}

Questo articolo spiega come configurare nuove destinazioni basate sui dispositivi dall’interfaccia utente di Audience Manager.

>[!IMPORTANT]
>
>Attualmente, la maggior parte delle destinazioni basate su dispositivi non sono idonee per il flusso di lavoro di configurazione self-service. Se la destinazione basata sui dispositivi che devi aggiungere non viene visualizzata nell’elenco delle destinazioni, contatta il tuo consulente Adobe o l’Assistenza clienti per assistenza.

## Panoramica {#overview}

Il processo di aggiunta di una nuova destinazione basata sui dispositivi consiste di due passaggi principali. Innanzitutto, devi configurare l’integrazione tra Audience Manager e il partner di destinazione. Una volta raggiunto tale obiettivo, puoi creare una nuova destinazione basata sui dispositivi.

## Prerequisiti {#prerequisites}

Quando crei la prima destinazione basata su dispositivo con una piattaforma integrata, contatta il Consulente Adobe o l&#39;Assistenza clienti per abilitare la sincronizzazione ID tra Audience Manager e la piattaforma integrata per il tuo account. Questo è necessario per la corretta sincronizzazione tra Audience Manager e la piattaforma di destinazione.



## Passaggio 1: Autenticazione con una piattaforma di destinazione {#step1}

Prima di poter creare una nuova destinazione basata su dispositivo, è necessario configurare l&#39;integrazione tra Audience Manager e la piattaforma di destinazione. Come procedere:

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**. Se disponete di un&#39;integrazione configurata in precedenza con una piattaforma di destinazione, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
1. Clic **[!DNL Add Account]**.
1. Selezionate la piattaforma di destinazione con cui desiderate eseguire l&#39;autenticazione e fate clic per **[!DNL Confirm]**essere reindirizzati alla pagina di autenticazione della piattaforma selezionata.![piattaforme integrate](assets/dbd-integrated-platforms.png)
1. Dopo aver eseguito l&#39;autenticazione sull&#39;account della piattaforma di destinazione, verrete reindirizzati ad Audience Manager, dove dovrebbero essere visualizzati gli account dell&#39;inserzionista associato. Selezionate l’account dell’inserzionista da usare e fate clic su **[!DNL Confirm]**.

## Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2}

Dopo aver configurato l&#39;integrazione della piattaforma di destinazione, potete creare la nuova destinazione. Come procedere:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione esistente basata su dispositivo. Assicuratevi di fornire un nome che vi aiuterà a identificare correttamente la destinazione.

1. Accedi al tuo account Audience Manager, vai a **[!DNL Audience Data > Destinations]**e fai clic su**[!DNL Create Destination]**.
1. Nella **[!DNL Basic Information]**sezione immettere un**[!DNL Name]** e **[!DNL Description]**per la nuova destinazione e utilizzare le impostazioni nell&#39;elenco seguente:![setup](assets/dbd-new-basic.png)
   * **[!DNL Category]**:[!DNL Integrated Platforms];
   * **[!DNL Type]**:[!DNL Device-Based];
   * **[!DNL Platform]**: selezionate la piattaforma di destinazione alla quale desiderate inviare i segmenti di pubblico.
   * **[!DNL Account]**: selezionate l&#39;account dell&#39;inserzionista desiderato associato alla piattaforma selezionata.
1. Clic **[!DNL Next]**.
1. Scegliere le etichette [di esportazione](/help/using/features/data-export-controls.md#controls-labels) dati da impostare per questa destinazione.
1. Clic **[!DNL Save]**.
1. Nella **[!DNL Segment Mappings]**sezione, selezionate i segmenti di pubblico che desiderate inviare a questa destinazione.
1. Salva la destinazione.
