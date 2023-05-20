---
description: Questo articolo spiega come configurare i tipi di pubblico personalizzati di Twitter per le integrazioni nuove ed esistenti.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configurare i tipi di pubblico personalizzati di Twitter come destinazione self-service basata su dispositivi
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# Configura [!DNL Twitter Custom Audiences] come destinazione self-service basata su dispositivo {#configure-twitter}

Questo articolo spiega come configurare un’integrazione con [Tipi di pubblico personalizzati twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Prerequisiti {#prerequisites}

Prima di configurare [!DNL Twitter Custom Audiences] destinazione, assicurati di soddisfare i seguenti prerequisiti.

* Il tuo [!DNL Twitter Ads] l&#39;account deve essere idoneo per la pubblicità. Nuovo [!DNL Twitter Ads] gli account non sono idonei per la pubblicità nelle prime 2 settimane dopo la loro creazione.
* Il tuo [!DNL Twitter] l&#39;account utente per il quale hai autorizzato l&#39;accesso in Audience Manager deve avere [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) autorizzazione abilitata.
* Durante la creazione del primo [!DNL Twitter Custom Audiences] nell’istanza Audience Manager, contatta la consulenza o l’assistenza clienti Adobe per abilitare [!DNL Twitter] Sincronizzazione ID (ID origine dati = 1123) per l’account. Questa operazione è necessaria per la corretta sincronizzazione tra Audience Manager e [!DNL Twitter].

## Aggiungi un nuovo [!DNL Twitter Custom Audiences] Destinazione {#add-new-twitter-destination}

Questa sezione descrive i passaggi da seguire per configurare una nuova destinazione basata su dispositivo per [!DNL Twitter Custom Audiences]. Questo scenario presuppone che non siano presenti [!DNL Twitter Custom Audiences] configurata tramite il consulente Adobe o l’Assistenza clienti.

### Passaggio 1: Autentica con [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Prima di poter aggiungere la destinazione basata su dispositivo, devi collegare l’Audience Manager e il [!DNL Twitter Custom Audiences] account. Ecco come eseguire questa operazione:

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma di destinazione, dovresti visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
1. Clic **[!DNL Add Account]**.
1. Seleziona [!DNL Twitter Custom Audiences] e fai clic su **[!DNL Confirm]** per essere reindirizzato alla pagina di autenticazione.

   ![piattaforme integrate](assets/dbd-integrated-platforms.png)

1. Dopo l&#39;autenticazione, si viene reindirizzati all&#39;Audience Manager in cui dovrebbero essere visualizzati gli account pubblicitari associati. Seleziona l’account dell’inserzionista che desideri utilizzare e fai clic su **[!DNL Confirm]**.

### Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2-create-new-destination}

Dopo aver collegato l’Audience Manager e il [!DNL Twitter Custom Audiences], puoi creare la nuova destinazione. Ecco come eseguire questa operazione:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione basata su dispositivo esistente. Assicurati di fornire un nome che ti aiuti a identificare correttamente la destinazione.

1. Accedi al tuo account Audience Manager e vai a **[!DNL Audience Data > Destinations]** e fai clic su **[!DNL Create Destination]**.
1. In **[!DNL Basic Information]** , immetti un **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizza le impostazioni seguenti: ![configurazione](assets/dbd-new-basic.png)
1. Clic **[!DNL Next]**.
1. Scegli la [Etichette esportazione dati](/help/using/features/data-export-controls.md#controls-labels) che desideri impostare per questa destinazione.
1. Clic **[!DNL Save]**.
1. In **[!DNL Segment Mappings]** , seleziona i segmenti di pubblico che desideri inviare a questa destinazione.
1. Salva la destinazione.

## Considerazioni sulla mappatura dei segmenti {#segment-mapping-considerations}

Quando si mappano segmenti di pubblico a [!UICONTROL Twitter], assicurati di soddisfare i seguenti requisiti di denominazione dei segmenti:

* Fornisci nomi di mappatura dei segmenti leggibili dall’utente. È consigliabile utilizzare lo stesso nome utilizzato per i segmenti di Audience Manager.
* Non utilizzare caratteri speciali (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) nei nomi di mappatura di segmenti e segmenti. Se il nome del segmento di Audience Manager contiene questi caratteri, rimuovili prima di mappare il segmento a [!UICONTROL Twitter] destinazione.

### Esempio

* Nome corretto del segmento o della mappatura: &quot;Acquirenti statunitensi ed europei&quot;;
* Nome di segmento o mappatura non corretto: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Non è possibile modificare i nomi dei segmenti già mappati. Audience Manager utilizza i nomi dei segmenti per identificare correttamente i segmenti nell’integrazione.

## Considerazioni sulle percentuali di corrispondenza {#match-rates-considerations}

* L&#39;integrazione tra Audience Manager e [!UICONTROL Twitter Custom Audiences] supporta retrocompilazioni storiche del pubblico. Tutte le qualifiche dei segmenti vengono inviate a [!UICONTROL Twitter] quando crei la destinazione.

## Risoluzione dei problemi {#troubleshooting}

Quando configuri o invii dati alla destinazione Tipi di pubblico personalizzati di Twitter, potresti riscontrare gli errori descritti di seguito. Questa sezione spiega cosa può causare gli errori e come correggerli.

| Messaggio di errore | Occorrenza/Motivo | Risoluzione |
|---|---|---|
| `Internal server error` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audience Manager quando si tenta di aggiungere una nuova [!DNL Twitter] che utilizza una versione obsoleta dell’API di Twitter. | Contatta l’Assistenza clienti di Adobe. |
| `Twitter Error: This request is not properly authenticated` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audience Manager quando si tenta di mappare segmenti con nomi di segmenti non supportati sulla destinazione. | Controlla i nomi dei segmenti mappati e assicurati che non contengano caratteri non supportati. Consulta [considerazioni sulla mappatura dei segmenti](#segment-mapping-considerations) per l’elenco dei caratteri non supportati. |
| `Twitter Error: Account XXXXXXXXX was not found` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audience Manager quando le credenziali configurate per la destinazione non sono autorizzate ad accedere all’account Twitter Ads corrispondente. | <ul><li>Assicurati che le credenziali dell’account utilizzate soddisfino le [prerequisiti](#prerequisites).</li><li>Passa all’interfaccia utente di Twitter Ads utilizzando le stesse credenziali e verifica se i tipi di pubblico corretti sono visualizzati nella corrispondente `XXXXXXXXX` account. </li></ul> |