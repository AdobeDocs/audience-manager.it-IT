---
description: Questo articolo spiega come configurare Twitter Custom Audiences per le integrazioni nuove ed esistenti.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configurare tipi di pubblico personalizzati di Twitter come destinazione self-service basata su dispositivi
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 8023bfe1e4ea415867e1233f143627ff179cce42
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 1%

---

# Configurare [!DNL Twitter Custom Audiences] come destinazione self-service basata su dispositivi {#configure-twitter}

Questo articolo spiega come configurare un&#39;integrazione con [Twitter Custom Audiences](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Prerequisiti {#prerequisites}

Prima di configurare la destinazione [!DNL Twitter Custom Audiences], verifica i seguenti prerequisiti Twitter che devi soddisfare.

1. Il tuo account [!DNL Twitter Ads] deve essere idoneo per la pubblicità. I nuovi account [!DNL Twitter Ads] non sono idonei per la pubblicità nelle prime 2 settimane dopo la loro creazione.
2. L&#39;autorizzazione [!DNL Twitter] per l&#39;account utente a cui hai autorizzato l&#39;accesso in Audience Manager deve essere abilitata per [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) .
3. Quando crei la prima [!DNL Twitter Custom Audiences] destinazione nell&#39;istanza di Audience Manager, contatta Adobe Consulting o l&#39;Assistenza clienti per abilitare la sincronizzazione ID [!DNL Twitter] (ID origine dati = 1123) per il tuo account. Questa operazione è necessaria per la sincronizzazione corretta tra Audience Manager e [!DNL Twitter].

## Aggiungi una nuova destinazione [!DNL Twitter Custom Audiences] {#add-new-twitter-destination}

Questa sezione descrive i passaggi da seguire per configurare una nuova destinazione basata su dispositivi per [!DNL Twitter Custom Audiences]. Questo scenario presuppone che non disponi di una destinazione [!DNL Twitter Custom Audiences] esistente configurata tramite il tuo consulente di Adobe o l’Assistenza clienti.

### Passaggio 1: Autentica con [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Prima di poter aggiungere la destinazione basata su dispositivo, devi collegare l’Audience Manager e il tuo account [!DNL Twitter Custom Audiences]. Ecco come eseguire questa operazione:

1. Accedi al tuo account di Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma di destinazione, visualizzala in questa pagina. In caso contrario, la pagina è vuota.
1. Clic **[!DNL Add Account]**.
1. Seleziona [!DNL Twitter Custom Audiences] e fai clic su **[!DNL Confirm]** per essere reindirizzato alla pagina di autenticazione.

   ![piattaforme integrate](assets/dbd-integrated-platforms.png)

1. Dopo l’autenticazione, vieni reindirizzato ad Audience Manager dove dovresti visualizzare i tuoi account pubblicitari associati. Seleziona l’account dell’inserzionista da utilizzare e fai clic su **[!DNL Confirm]**.

### Passaggio 2: Creare una nuova destinazione basata su dispositivi {#step2-create-new-destination}

Dopo aver collegato l&#39;Audience Manager e il [!DNL Twitter Custom Audiences], puoi creare la nuova destinazione. Ecco come eseguire questa operazione:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione esistente basata su dispositivo. Assicurati di fornire un nome che ti aiuterà a identificare correttamente la destinazione.

1. Accedi al tuo account di Audience Manager, vai a **[!DNL Audience Data > Destinations]** e fai clic su **[!DNL Create Destination]**.
1. Nella sezione **[!DNL Basic Information]** , immetti un **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizza le impostazioni seguenti: ![setup](assets/dbd-new-basic.png)
1. Clic **[!DNL Next]**.
1. Scegli le [Etichette esportazione dati](/help/using/features/data-export-controls.md#controls-labels) che desideri impostare per questa destinazione.
1. Clic **[!DNL Save]**.
1. Nella sezione **[!DNL Segment Mappings]** , seleziona i segmenti di pubblico che desideri inviare a questa destinazione.
1. Salva la destinazione.

## Considerazioni sulla mappatura dei segmenti {#segment-mapping-considerations}

Quando mappi segmenti di pubblico a [!UICONTROL Twitter], assicurati di soddisfare i seguenti requisiti di denominazione dei segmenti:

* Fornisci nomi di mappatura dei segmenti leggibili dall’utente. È consigliabile utilizzare lo stesso nome utilizzato per i segmenti di Audience Manager.
* Non utilizzare caratteri speciali (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) nei nomi di mappatura di segmenti e segmenti. Se il nome del segmento di Audience Manager contiene questi caratteri, rimuovili prima di mappare il segmento a una destinazione [!UICONTROL Twitter].

### Esempio

* Nome corretto del segmento o della mappatura: &quot;Acquirenti americani ed europei&quot;;
* Nome di segmento o di mappatura non corretto: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Non è possibile modificare i nomi dei segmenti già mappati. Audience Manager utilizza i nomi dei segmenti per identificare correttamente i segmenti nell’integrazione.

## Considerazioni sulle percentuali di corrispondenza {#match-rates-considerations}

* L’integrazione tra Audience Manager e [!UICONTROL Twitter Custom Audiences] supporta le versioni precedenti del pubblico. Tutte le qualifiche dei segmenti vengono inviate a [!UICONTROL Twitter] al momento della creazione della destinazione.
