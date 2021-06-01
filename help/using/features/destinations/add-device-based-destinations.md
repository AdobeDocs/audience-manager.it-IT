---
description: Questo articolo spiega come configurare nuove destinazioni basate su dispositivi dall’interfaccia utente di Audience Manager.
seo-description: Questo articolo spiega come configurare nuove destinazioni basate su dispositivi dall’interfaccia utente di Audience Manager.
seo-title: Aggiungere nuove destinazioni basate su dispositivi
solution: Audience Manager
title: Aggiungere nuove destinazioni basate su dispositivi
feature: Nozioni di base sulle destinazioni
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 4%

---

# Aggiungere nuove destinazioni basate su dispositivi {#add-new-device-based-destinations}

Questo articolo spiega come configurare nuove destinazioni basate su dispositivi dall’interfaccia utente di Audience Manager.

>[!IMPORTANT]
>
>Attualmente, la maggior parte delle destinazioni basate su dispositivi non sono idonee per il flusso di lavoro di configurazione self-service. Se la destinazione basata su dispositivi che devi aggiungere non viene visualizzata nell’elenco delle destinazioni , contatta il tuo consulente di Adobe o l’Assistenza clienti .

## Panoramica {#overview}

Il processo di aggiunta di una nuova destinazione basata su dispositivi consiste in due passaggi principali. Innanzitutto, devi configurare l’integrazione tra Audience Manager e il partner di destinazione. Una volta fatto questo, puoi creare una nuova destinazione basata su dispositivi.

## Prerequisiti {#prerequisites}

Quando crei la prima destinazione basata su dispositivi con una piattaforma integrata, contatta Adobe Consulting o l’Assistenza clienti per abilitare la sincronizzazione ID tra Audience Manager e la piattaforma integrata per il tuo account. Questa operazione è necessaria per la sincronizzazione corretta tra Audience Manager e la piattaforma di destinazione.

## Passaggio 1: Autenticazione con una piattaforma di destinazione {#step1}

Prima di poter creare una nuova destinazione basata su dispositivi, devi configurare l’integrazione tra Audience Manager e la piattaforma di destinazione. Ecco come eseguire questa operazione:

1. Accedi al tuo account di Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma di destinazione, visualizzala in questa pagina. In caso contrario, la pagina è vuota.
1. Clic **[!DNL Add Account]**.
1. Seleziona la piattaforma di destinazione con cui desideri eseguire l’autenticazione e fai clic su **[!DNL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.

   ![piattaforme integrate](assets/dbd-integrated-platforms.png)

1. Dopo aver eseguito l’autenticazione all’account della piattaforma di destinazione, vieni reindirizzato all’Audience Manager in cui dovresti visualizzare gli account dell’inserzionista associati. Seleziona l’account dell’inserzionista da utilizzare e fai clic su **[!DNL Confirm]**.

## Passaggio 2: Creare una nuova destinazione basata su dispositivi {#step2}

Dopo aver configurato l’integrazione della piattaforma di destinazione, puoi creare la nuova destinazione. Ecco come eseguire questa operazione:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione esistente basata su dispositivo. Assicurati di fornire un nome che ti aiuterà a identificare correttamente la destinazione.

1. Accedi al tuo account di Audience Manager, vai a **[!DNL Audience Data > Destinations]** e fai clic su **[!DNL Create Destination]**.
1. Nella sezione **[!DNL Basic Information]** , immetti un **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizza le impostazioni nell’elenco seguente:

   ![setup](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**:  [!DNL Device-Based];
   * **[!DNL Platform]**: seleziona la piattaforma di destinazione a cui desideri inviare i segmenti di pubblico.
   * **[!DNL Account]**: seleziona l’account inserzionista desiderato associato alla piattaforma selezionata.
1. Clic **[!DNL Next]**.
1. Scegli le [Etichette esportazione dati](/help/using/features/data-export-controls.md#controls-labels) che desideri impostare per questa destinazione.
1. Clic **[!DNL Save]**.
1. Nella sezione **[!DNL Segment Mappings]** , seleziona i segmenti di pubblico che desideri inviare a questa destinazione.
1. Salva la destinazione.
