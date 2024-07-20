---
description: Questo articolo spiega come configurare i tipi di pubblico personalizzati di Twitter per le integrazioni nuove ed esistenti.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configurare i tipi di pubblico personalizzati del Twitter come destinazione self-service basata su dispositivi
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Configura [!DNL Twitter Custom Audiences] come destinazione self-service basata su dispositivo {#configure-twitter}

Questo articolo spiega come configurare un&#39;integrazione con [Tipi di pubblico personalizzati di Twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Prerequisiti {#prerequisites}

Prima di configurare la destinazione [!DNL Twitter Custom Audiences], verificare di soddisfare i seguenti prerequisiti.

* L&#39;account [!DNL Twitter Ads] deve essere idoneo per la pubblicità. I nuovi account di [!DNL Twitter Ads] non sono idonei per la pubblicità nelle prime 2 settimane dopo la loro creazione.
* L&#39;account utente [!DNL Twitter] per il quale hai autorizzato l&#39;accesso in Audience Manager deve avere l&#39;autorizzazione [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) abilitata.
* Durante la creazione della prima destinazione [!DNL Twitter Custom Audiences] nell&#39;istanza Audience Manager, contatta Adobe Consulting o l&#39;Assistenza clienti per abilitare la sincronizzazione ID [!DNL Twitter] (ID Data Source = 1123) per il tuo account. Necessario per la sincronizzazione corretta tra Audience Manager e [!DNL Twitter].

## Aggiungi una nuova destinazione [!DNL Twitter Custom Audiences] {#add-new-twitter-destination}

Questa sezione descrive i passaggi da seguire per configurare una nuova destinazione basata su dispositivo per [!DNL Twitter Custom Audiences]. Questo scenario presuppone che non sia già stata configurata alcuna destinazione [!DNL Twitter Custom Audiences] tramite il tuo consulente Adobe o l&#39;Assistenza clienti.

### Passaggio 1: Autentica con [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Prima di poter aggiungere la destinazione basata su dispositivo, devi collegare l&#39;Audience Manager e il tuo account [!DNL Twitter Custom Audiences]. Ecco come eseguire questa operazione:

1. Accedi al tuo account Audience Manager e passa a **[!DNL Administration > Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma di destinazione, dovresti visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
1. Fare clic su **[!DNL Add Account]**.
1. Selezionare [!DNL Twitter Custom Audiences] e fare clic su **[!DNL Confirm]** per reindirizzare alla pagina di autenticazione.

   ![piattaforme integrate](assets/dbd-integrated-platforms.png)

1. Dopo l&#39;autenticazione, si viene reindirizzati all&#39;Audience Manager in cui dovrebbero essere visualizzati gli account pubblicitari associati. Selezionare l&#39;account pubblicitario che si desidera utilizzare e fare clic su **[!DNL Confirm]**.

### Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2-create-new-destination}

Dopo aver collegato l&#39;Audience Manager e [!DNL Twitter Custom Audiences], puoi creare la nuova destinazione. Ecco come eseguire questa operazione:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione basata su dispositivo esistente. Assicurati di fornire un nome che ti aiuti a identificare correttamente la destinazione.

1. Accedi al tuo account Audience Manager, passa a **[!DNL Audience Data > Destinations]** e fai clic su **[!DNL Create Destination]**.
1. Nella sezione **[!DNL Basic Information]** immettere **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizzare le impostazioni seguenti: ![configurazione](assets/dbd-new-basic.png)
1. Fare clic su **[!DNL Next]**.
1. Scegliere le [etichette di esportazione dati](/help/using/features/data-export-controls.md#controls-labels) che si desidera impostare per questa destinazione.
1. Fare clic su **[!DNL Save]**.
1. Nella sezione **[!DNL Segment Mappings]**, seleziona i segmenti di pubblico che desideri inviare a questa destinazione.
1. Salva la destinazione.

## Considerazioni sulla mappatura dei segmenti {#segment-mapping-considerations}

Quando mappi i segmenti di pubblico a [!UICONTROL Twitter], assicurati di soddisfare i seguenti requisiti di denominazione dei segmenti:

* Fornisci nomi di mappatura dei segmenti leggibili dall’utente. È consigliabile utilizzare lo stesso nome utilizzato per i segmenti di Audience Manager.
* Non utilizzare caratteri speciali (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) nei nomi di mapping di segmenti e segmenti. Se il nome del segmento di Audience Manager contiene questi caratteri, rimuoverli prima di mappare il segmento a una destinazione [!UICONTROL Twitter].

### Esempio

* Nome corretto del segmento o della mappatura: &quot;Acquirenti statunitensi ed europei&quot;;
* Nome di segmento o mappatura non corretto: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Non è possibile modificare i nomi dei segmenti già mappati. Audience Manager utilizza i nomi dei segmenti per identificare correttamente i segmenti nell’integrazione.

## Considerazioni sulle percentuali di corrispondenza {#match-rates-considerations}

* L&#39;integrazione tra Audience Manager e [!UICONTROL Twitter Custom Audiences] supporta i backfill cronologici del pubblico. Tutte le qualifiche dei segmenti vengono inviate a [!UICONTROL Twitter] quando si crea la destinazione.

## Risoluzione dei problemi {#troubleshooting}

Quando configuri o invii dati alla destinazione Tipi di pubblico personalizzati del Twitter, potresti riscontrare gli errori descritti di seguito. Questa sezione spiega cosa può causare gli errori e come correggerli.

| Messaggio di errore | Occorrenza/Motivo | Risoluzione |
|---|---|---|
| `Internal server error` | Questo messaggio di errore viene visualizzato nell&#39;interfaccia utente di Audience Manager quando si tenta di aggiungere un nuovo account [!DNL Twitter] utilizzando una versione obsoleta dell&#39;API di Twitter. | Contatta l’Assistenza clienti di Adobe. |
| `Twitter Error: This request is not properly authenticated` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audience Manager quando si tenta di mappare segmenti con nomi di segmenti non supportati sulla destinazione. | Controlla i nomi dei segmenti mappati e assicurati che non contengano caratteri non supportati. Per l&#39;elenco dei caratteri non supportati, vedere [considerazioni sulla mappatura dei segmenti](#segment-mapping-considerations). |
| `Twitter Error: Account XXXXXXXXX was not found` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audience Manager quando le credenziali configurate per la destinazione non sono autorizzate ad accedere all’account Twitter Ads corrispondente. | <ul><li>Assicurati che le credenziali dell&#39;account utilizzate soddisfino i [prerequisiti](#prerequisites).</li><li>Passa all&#39;interfaccia utente di Twitter Ads utilizzando le stesse credenziali e verifica se i tipi di pubblico corretti sono visualizzati nell&#39;account `XXXXXXXXX` corrispondente. </li></ul> |