---
description: Questo articolo spiega come configurare Twitter Custom Audiences per le integrazioni nuove ed esistenti.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Configurare tipi di pubblico personalizzati di Twitter come destinazione self-service basata su dispositivi
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# Configura [!DNL Twitter Custom Audiences] come destinazione self-service basata su dispositivi {#configure-twitter}

Questo articolo spiega come configurare un’integrazione con [Tipi di pubblico personalizzati twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Prerequisiti {#prerequisites}

Prima di configurare il [!DNL Twitter Custom Audiences] assicurati di soddisfare i seguenti prerequisiti.

* Le [!DNL Twitter Ads] l&#39;account deve essere idoneo per la pubblicità. Nuovo [!DNL Twitter Ads] gli account non sono ammessi alla pubblicità nelle prime due settimane dopo la loro creazione.
* Le [!DNL Twitter] l&#39;account utente per il quale hai autorizzato l&#39;accesso in Audience Manager deve avere [Audience Manager partner](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) autorizzazione abilitata.
* Durante la creazione del primo [!DNL Twitter Custom Audiences] nella tua istanza di Audience Manager, contatta il Consulente Adobe o l’Assistenza clienti per abilitare il [!DNL Twitter] Sincronizzazione ID (Data Source ID = 1123) per il tuo account. Questo è necessario per la sincronizzazione corretta tra Audience Manager e [!DNL Twitter].

## Aggiungi un nuovo [!DNL Twitter Custom Audiences] Destinazione {#add-new-twitter-destination}

Questa sezione descrive i passaggi da seguire per configurare una nuova destinazione basata su dispositivi per [!DNL Twitter Custom Audiences]. Questo scenario presuppone che non sia esistente [!DNL Twitter Custom Audiences] destinazione configurata tramite il tuo consulente di Adobe o l’Assistenza clienti.

### Passaggio 1: Autentica con [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Prima di poter aggiungere la destinazione basata su dispositivo, devi collegare l’Audience Manager e la [!DNL Twitter Custom Audiences] conto. Ecco come eseguire questa operazione:

1. Accedi al tuo account Audience Manager e vai a **[!DNL Administration > Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma di destinazione, visualizzala in questa pagina. In caso contrario, la pagina è vuota.
1. Clic **[!DNL Add Account]**.
1. Seleziona [!DNL Twitter Custom Audiences] e fai clic su **[!DNL Confirm]** da reindirizzare alla pagina di autenticazione.

   ![piattaforme integrate](assets/dbd-integrated-platforms.png)

1. Dopo l’autenticazione, vieni reindirizzato ad Audience Manager dove dovresti visualizzare i tuoi account pubblicitari associati. Seleziona l’account dell’inserzionista da utilizzare e fai clic su **[!DNL Confirm]**.

### Passaggio 2: Creare una nuova destinazione basata su dispositivi {#step2-create-new-destination}

Dopo aver collegato l’Audience Manager e la [!DNL Twitter Custom Audiences], puoi creare la nuova destinazione. Ecco come eseguire questa operazione:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione esistente basata su dispositivo. Assicurati di fornire un nome che ti aiuterà a identificare correttamente la destinazione.

1. Accedi al tuo account di Audience Manager e vai a **[!DNL Audience Data > Destinations]** e fai clic su **[!DNL Create Destination]**.
1. In **[!DNL Basic Information]** sezione , immetti un **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizzare le impostazioni seguenti: ![setup](assets/dbd-new-basic.png)
1. Clic **[!DNL Next]**.
1. Scegli la [Etichette di esportazione dei dati](/help/using/features/data-export-controls.md#controls-labels) che si desidera impostare per questa destinazione.
1. Clic **[!DNL Save]**.
1. In **[!DNL Segment Mappings]** seleziona i segmenti di pubblico che desideri inviare a questa destinazione.
1. Salva la destinazione.

## Considerazioni sulla mappatura dei segmenti {#segment-mapping-considerations}

Quando si mappano segmenti di pubblico a [!UICONTROL Twitter], assicurati di soddisfare i seguenti requisiti di denominazione dei segmenti:

* Fornisci nomi di mappatura dei segmenti leggibili dall’utente. È consigliabile utilizzare lo stesso nome utilizzato per i segmenti di Audience Manager.
* Non utilizzare caratteri speciali (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) nei nomi di mappatura dei segmenti e dei segmenti. Se il nome del segmento di Audience Manager contiene questi caratteri, rimuovili prima di mappare il segmento a un [!UICONTROL Twitter] destinazione.

### Esempio

* Nome corretto del segmento o della mappatura: &quot;Acquirenti americani ed europei&quot;;
* Nome di segmento o di mappatura non corretto: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Non è possibile modificare i nomi dei segmenti già mappati. Audience Manager utilizza i nomi dei segmenti per identificare correttamente i segmenti nell’integrazione.

## Considerazioni sulle percentuali di corrispondenza {#match-rates-considerations}

* L&#39;integrazione tra Audience Manager e [!UICONTROL Twitter Custom Audiences] supporta i backfills dello storico del pubblico. Tutte le qualifiche dei segmenti vengono inviate a [!UICONTROL Twitter] quando crei la destinazione.

## Risoluzione dei problemi    {#troubleshooting}

Durante la configurazione o l’invio di dati alla destinazione Tipi di pubblico personalizzati di Twitter, potresti riscontrare gli errori descritti di seguito. Questa sezione spiega cosa può causare gli errori e come correggerli.

| Messaggio di errore | Occorrenza/Motivo | Risoluzione |
|---|---|---|
| `Internal server error` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audience Manager quando si tenta di aggiungere un nuovo [!DNL Twitter] utilizzando una versione obsoleta dell’API Twitter. | Contatta l’Assistenza clienti di Adobe. |
| `Twitter Error: This request is not properly authenticated` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audience Manager quando si tenta di mappare i segmenti con nomi di segmento non supportati sulla destinazione. | Esamina i nomi dei segmenti mappati e accertati che non contengano caratteri non supportati. Vedi [considerazioni sulla mappatura dei segmenti](#segment-mapping-considerations) per l’elenco dei caratteri non supportati. |
| `Twitter Error: Account XXXXXXXXX was not found` | Questo messaggio di errore viene visualizzato nell’interfaccia utente di Audience Manager quando le credenziali configurate per la destinazione non sono autorizzate ad accedere all’account Twitter Ads corrispondente. | <ul><li>Assicurati che le credenziali dell&#39;account che stai utilizzando soddisfino le [prerequisiti](#prerequisites).</li><li>Passa all’interfaccia utente di Twitter Ads utilizzando le stesse credenziali e verifica se i tipi di pubblico corretti sono visualizzati sotto il corrispondente `XXXXXXXXX` conto. </li></ul> |