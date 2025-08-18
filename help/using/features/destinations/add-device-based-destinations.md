---
description: Questo articolo spiega come configurare nuove destinazioni basate su dispositivi dall’interfaccia utente di Audience Manager.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Aggiungere nuove destinazioni basate su dispositivi
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 1%

---

# Aggiungere nuove destinazioni basate su dispositivi {#add-new-device-based-destinations}

Questo articolo spiega come configurare nuove destinazioni basate su dispositivi dall’interfaccia utente di Audience Manager.

>[!IMPORTANT]
>
>Attualmente, la maggior parte delle destinazioni basate su dispositivi non è idonea per il flusso di lavoro di configurazione self-service. Se la destinazione basata su dispositivo che devi aggiungere non viene visualizzata nell’elenco delle destinazioni, contatta il tuo consulente Adobe o l’Assistenza clienti.

## Panoramica {#overview}

Il processo di aggiunta di una nuova destinazione basata su dispositivo consiste in due passaggi principali. Innanzitutto, devi configurare l’integrazione tra Audience Manager e il partner di destinazione. Dopo aver eseguito questa operazione, puoi creare una nuova destinazione basata su dispositivo.

## Prerequisiti {#prerequisites}

Quando crei la prima destinazione basata su dispositivo con una piattaforma integrata, contatta Adobe Consulting o l’Assistenza clienti per abilitare la sincronizzazione ID tra Audience Manager e la piattaforma integrata per il tuo account. Questo è necessario per la corretta sincronizzazione tra Audience Manager e la piattaforma di destinazione.

## Passaggio 1: Autenticazione con una piattaforma di destinazione {#step1}

Prima di poter creare una nuova destinazione basata su dispositivo, devi configurare l’integrazione tra Audience Manager e la piattaforma di destinazione. Ecco come eseguire questa operazione:

1. Accedi al tuo account Audience Manager e passa a **[!DNL Administration > Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma di destinazione, dovresti visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
1. Fare clic su **[!DNL Add Account]**.
1. Selezionare la piattaforma di destinazione con cui si desidera eseguire l&#39;autenticazione e fare clic su **[!DNL Confirm]** per essere reindirizzati alla pagina di autenticazione della piattaforma selezionata.

   ![piattaforme integrate](assets/dbd-integrated-platforms.png)

1. Dopo aver eseguito l’autenticazione nell’account della piattaforma di destinazione, vieni reindirizzato ad Audience Manager dove dovresti visualizzare gli account pubblicitari associati. Selezionare l&#39;account pubblicitario che si desidera utilizzare e fare clic su **[!DNL Confirm]**.

## Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2}

Dopo aver configurato l’integrazione della piattaforma di destinazione, puoi creare la nuova destinazione. Ecco come eseguire questa operazione:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione basata su dispositivo esistente. Assicurati di fornire un nome che ti aiuti a identificare correttamente la destinazione.

1. Accedi al tuo account Audience Manager, passa a **[!DNL Audience Data > Destinations]** e fai clic su **[!DNL Create Destination]**.
1. Nella sezione **[!DNL Basic Information]** immettere **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizzare le impostazioni nell&#39;elenco seguente:

   ![installazione](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: seleziona la piattaforma di destinazione a cui desideri inviare i segmenti di pubblico.
   * **[!DNL Account]**: selezionare l&#39;account dell&#39;inserzionista desiderato associato alla piattaforma selezionata.
1. Fare clic su **[!DNL Next]**.
1. Scegliere le [etichette di esportazione dati](/help/using/features/data-export-controls.md#controls-labels) che si desidera impostare per questa destinazione.
1. Fare clic su **[!DNL Save]**.
1. Nella sezione **[!DNL Segment Mappings]**, seleziona i segmenti di pubblico che desideri inviare a questa destinazione.
1. Salva la destinazione.
