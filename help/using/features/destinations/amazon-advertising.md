---
description: Questo articolo spiega come configurare Amazon Advertising per le integrazioni nuove ed esistenti.
solution: Audience Manager
title: Configurare Amazon Advertising come destinazione self-service basata su dispositivo
source-git-commit: 01f3c2d813a91b8541bd8ba8a8b030f67a4f979e
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 1%

---


# Configura [!DNL Amazon Advertising] come destinazione self-service basata su dispositivo {#configure-amazon}

Questo articolo spiega come configurare un’integrazione con [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us).

## Prerequisiti {#prerequisites}

Prima di configurare [!DNL Amazon Advertising] destinazione, assicurati di soddisfare i seguenti prerequisiti.

* Il tuo [!DNL Amazon] l&#39;account deve essere idoneo per la pubblicità.
* Durante la creazione del primo [!DNL Amazon Advertising] nell’istanza Audienci Manager, contatta la consulenza o l’assistenza clienti Adobe per abilitare [!DNL Amazon] Sincronizzazione ID (ID origine dati = 139200) per l’account. Questa operazione è necessaria per la corretta sincronizzazione tra Audienci Manager e [!DNL Amazon].
* Dopo la creazione del nuovo pubblico del provider di dati, è necessario [aggiornare i metadati](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) e aggiungi **[!DNL audience fees]**. Per questa operazione è possibile utilizzare [API di Amazon Ads](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) o [Interfaccia utente di Amazon Advertising](https://advertising.amazon.com/).

## Aggiungi un nuovo [!DNL Amazon Advertising] Destinazione {#add-new-amazon-destination}

Questa sezione descrive i passaggi da seguire per configurare una nuova destinazione basata su dispositivo per [!DNL Amazon Advertising]. Questo scenario presuppone che non siano presenti [!DNL Amazon Advertising] configurata tramite il consulente Adobe o l’Assistenza clienti.

### Passaggio 1: Autentica con [!DNL Amazon Advertising] {#step1-authenticate-with-amazon}

Prima di poter aggiungere la destinazione basata su dispositivo, devi collegare l’Audience Manager e il [!DNL Amazon Advertising] account. Ecco come eseguire questa operazione:

1. Accedi al tuo account Audienci Manager e vai a **[!UICONTROL Administration > Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma di destinazione, dovresti visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
1. Seleziona **[!UICONTROL Add Account]**.
1. Seleziona [!UICONTROL Amazon Data Provider].

   ![piattaforme integrate](assets/dbd-amazon-without-options.png)

1. Seleziona una delle opzioni **[!UICONTROL Amazon Data Provider]** opzioni a seconda dell&#39;area geografica in cui [!DNL Amazon Ads] viene creato l’account (Nord America, Europa o Estremo Oriente) e fai clic su **[!DNL Confirm]** per essere reindirizzato alla pagina di autenticazione.

   ![piattaforme integrate](assets/dbd-amazon-with-options.png)

1. Dopo l&#39;autenticazione, si viene reindirizzati all&#39;Audience Manager in cui dovrebbero essere visualizzati gli account pubblicitari associati. Seleziona l’account dell’inserzionista che desideri utilizzare e fai clic su **[!UICONTROL Confirm]**. In questo modo hai autorizzato l’accesso ad Audience Manager per inviare aggiornamenti per i tuoi tipi di pubblico.

### Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2-create-new-destination}

Dopo aver collegato l’Audience Manager e il [!DNL Amazon Advertising] account, puoi creare la nuova destinazione. Ecco come eseguire questa operazione:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione basata su dispositivo esistente. Assicurati di fornire un nome che ti aiuti a identificare correttamente la destinazione.

1. Accedi al tuo account Audienci Manager e vai a **[!UICONTROL Audience Data > Destinations]**, e seleziona **[!UICONTROL Create Destination]**.
1. In **[!UICONTROL Basic Information]** , immetti un **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova destinazione e utilizza le impostazioni seguenti:

   ![configurazione](assets/dbd-new-account-amazon.png)

1. Seleziona **[!UICONTROL Next]**.
1. Scegli la [Etichette esportazione dati](/help/using/features/data-export-controls.md#controls-labels) che desideri impostare per questa destinazione.
1. Seleziona **[!UICONTROL Save]**.
1. In **[!UICONTROL Segment Mappings]** , seleziona i segmenti di pubblico che desideri inviare a questa destinazione.
1. Salva la destinazione.

## Considerazioni sulle percentuali di corrispondenza {#match-rates-considerations}

L&#39;integrazione tra Audienci Manager e [!DNL Amazon Advertising] supporta retrocompilazioni storiche del pubblico. Tutte le qualifiche dei segmenti vengono inviate a [!DNL Amazon] quando crei la destinazione.

## Risoluzione dei problemi {#troubleshooting}

Durante la configurazione o l’invio di dati a [!DNL Amazon Advertising] destinazione, potrebbero verificarsi gli errori descritti di seguito. Questa sezione spiega cosa può causare gli errori e come correggerli.

| Messaggio di errore | Occorrenza/Motivo | Risoluzione |
|---|---|---|
| `Internal server error` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audienci Manager quando si tenta di aggiungere una nuova [!DNL Amazon] che utilizza una versione obsoleta dell’API di Amazon. | Contatta l’Assistenza clienti di Adobe. |
| `Amazon Error: Account XXXXXXXXX was not found` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audienci Manager quando le credenziali configurate per la destinazione non sono autorizzate ad accedere all’account Amazon Ads corrispondente. | <ul><li>Assicurati che le credenziali dell’account utilizzate soddisfino le [prerequisiti](#prerequisites).</li><li>Passa all’interfaccia utente di Amazon Ads utilizzando le stesse credenziali e verifica se i tipi di pubblico corretti sono visualizzati nell’account corrispondente. </li></ul> |
