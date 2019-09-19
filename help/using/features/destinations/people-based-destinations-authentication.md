---
description: 'Questa pagina contiene istruzioni su come configurare e gestire l''integrazione tra Audience Manager e le piattaforme basate sulle persone. '
seo-description: 'Questa pagina contiene istruzioni su come configurare e gestire l''integrazione tra Audience Manager e le piattaforme basate sulle persone. '
seo-title: Autenticazione con piattaforme basate su persone
solution: Audience Manager
title: Autenticazione con piattaforme basate su persone
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# Autenticazione con piattaforme basate su persone {#authentication-with-people-based-platforms}

Questa pagina contiene istruzioni su come configurare e gestire l'integrazione tra Audience Manager e le piattaforme basate sulle persone.

>[!NOTE]
>Si tratta di un passaggio obbligatorio per le destinazioni basate su persone, indipendentemente dallo scenario di implementazione.

## Configurare l'autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Se avete già configurato un'integrazione con una piattaforma social, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
1. Fai clic su **[!UICONTROL Add Account]**.
1. Utilizzate il menu a **[!UICONTROL People-Based Platform]** discesa per selezionare la piattaforma con cui desiderate configurare l'integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
1. Fare clic per **[!UICONTROL Confirm]** essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
1. Dopo aver eseguito l'autenticazione sull'account della piattaforma social, verrete reindirizzati ad Audience Manager, dove dovrebbero essere visualizzati gli account degli inserzionisti associati. Selezionate l’account dell’inserzionista da usare e fate clic su **[!UICONTROL Confirm]**.
1. Audience Manager visualizza una notifica nella parte superiore della pagina per informarvi se l'account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere le notifiche quando l'autenticazione della piattaforma social sta per scadere.

## Scadenza token di autenticazione e gestione delle notifiche {#token-expiration-notification}

Audience Manager gestisce l'integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. La durata della validità del token è soggetta alle regole di integrazione di ciascuna piattaforma social. Una volta scaduto il token di autenticazione, Audience Manager non è in grado di inviare i segmenti di pubblico alla destinazione. Per evitare questo scenario, si consiglia di aggiungere almeno un indirizzo e-mail di contatto all'integrazione, in modo da ricevere una notifica non appena il token di autenticazione sta per scadere. In questo caso, puoi autenticarti nuovamente per assicurarti che la destinazione continui a ricevere i tuoi segmenti di pubblico.

Come aggiungere indirizzi e-mail alle integrazioni esistenti:

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identificate l'integrazione per la quale desiderate ricevere le notifiche di scadenza del token e fate clic sull' **[!UICONTROL Edit]** icona.
1. Inserite gli indirizzi e-mail che desiderate ricevere notifiche di scadenza token, separati da virgole.
1. Fai clic su **[!UICONTROL Save]**.

## Rinnovo token di autenticazione {#token-renewal}

Quando un token di autenticazione scade, l'integrazione tra Audience Manager e la piattaforma social corrispondente viene interrotta, pertanto Audience Manager non può più inviare segmenti di pubblico alla destinazione. La [!UICONTROL Integrated Accounts] pagina mostra lo stato di scadenza di ciascuna integrazione nella [!UICONTROL Expiration] colonna e consente di rinnovare l’autenticazione in qualsiasi momento.

Come rinnovare un'autenticazione scaduta o in procinto di scadere:
1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identificate l'integrazione per la quale desiderate rinnovare l'autenticazione. Le autenticazioni scadute sono contrassegnate come [!UICONTROL Expired], mentre quelle che stanno per scadere indicano a breve il numero rimanente di giorni autenticati.
1. Fate clic sull' **[!UICONTROL Renew]** icona corrispondente nella [!UICONTROL Expiration] colonna. Questo attiva il **[!UICONTROL Renew Account]** flusso di lavoro, che vi riporta alla pagina di autenticazione della piattaforma social. Dopo l’autenticazione, il token viene rinnovato con la nuova data di scadenza.
   ![pbd-rinnovo](assets/pbd-renew.png)
