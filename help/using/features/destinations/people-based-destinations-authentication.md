---
description: 'Questa pagina contiene indicazioni su come configurare e gestire l''integrazione tra Audience Manager e le piattaforme basate su persone. '
seo-description: 'Questa pagina contiene indicazioni su come configurare e gestire l''integrazione tra Audience Manager e le piattaforme basate su persone. '
seo-title: Autenticazione con piattaforme basate su persone
solution: Audience Manager
title: Autenticazione con piattaforme basate su persone
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# Autenticazione con piattaforme basate su persone {#authentication-with-people-based-platforms}

Questa pagina contiene indicazioni su come configurare e gestire l'integrazione tra Audience Manager e le piattaforme basate su persone.

>[!NOTE]
>Questo è un passaggio obbligatorio per Destinazioni basate su persone, a prescindere dallo scenario di implementazione.

## Configurare l'autenticazione piattaforma basata su utenti {#configure-authentication}

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Se disponete di un'integrazione configurata in precedenza con una piattaforma social, dovreste visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
1. Fai clic su **[!UICONTROL Add Account]**.
1. Utilizzate il **[!UICONTROL People-Based Platform]** menu a discesa per selezionare la piattaforma con la quale desiderate configurare l'integrazione.
   ![persone basate su persone](assets/pbd-add.png)
1. Fate clic per **[!UICONTROL Confirm]** essere reindirizzati alla pagina di autenticazione della piattaforma selezionata.
1. Dopo aver eseguito l'autenticazione al tuo account della piattaforma social, verrai reindirizzato ad Audience Manager dove dovresti vedere i tuoi account pubblicitari associati. Selezionate l'account pubblicitario che desiderate utilizzare e fate clic **[!UICONTROL Confirm]** su.
1. Audience Manager visualizza una notifica nella parte superiore della pagina per segnalare se l'account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere notifiche quando l'autenticazione della piattaforma social sta per scadere.

## Scadenza token di autenticazione e gestione delle notifiche {#token-expiration-notification}

Audience Manager gestisce l'integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. La durata della validità del token è soggetta alle regole di integrazione della piattaforma social network. Una volta scaduto il token di autenticazione, Audience Manager non è in grado di inviare i segmenti di pubblico alla destinazione. Per evitare questo scenario, consigliamo di aggiungere almeno un indirizzo e-mail di contatto all'integrazione, per ricevere una notifica non appena il token di autenticazione sta per scadere. In tal caso, potete eseguire nuovamente l'autenticazione per assicurarvi che la destinazione continui a ricevere i segmenti di pubblico.

Ecco come aggiungere indirizzi e-mail a integrazioni esistenti:

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifica l'integrazione per la quale desideri ricevere le notifiche di scadenza dei token, quindi fai clic sull' **[!UICONTROL Edit]** icona.
1. Inserite gli indirizzi e-mail per i quali desiderate ricevere le notifiche di scadenza dei token, separati da virgole.
1. Fai clic su **[!UICONTROL Save]**.

## Rinnovo token di autenticazione {#token-renewal}

Quando scade un token di autenticazione, l'integrazione tra Audience Manager e la corrispondente piattaforma social viene interrotta, pertanto Audience Manager non può più inviare segmenti di pubblico alla destinazione. [!UICONTROL Integrated Accounts] La pagina indica lo stato di scadenza di ogni integrazione nella [!UICONTROL Expiration] colonna e consente di rinnovare l'autenticazione in qualsiasi momento.

Ecco come rinnovare un'autenticazione scaduta o su scadenza:
1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identificare l'integrazione per cui rinnovare l'autenticazione. Le autenticazioni scadute sono contrassegnate come [!UICONTROL Expired], mentre le autenticazioni che stanno per scadere mostrano presto il numero rimanente di giorni autenticati.
1. Fare clic sulla corrispondente **[!UICONTROL Renew]** icona nella [!UICONTROL Expiration] colonna. Questo attiva il **[!UICONTROL Renew Account]** flusso di lavoro, che riporterà la pagina di autenticazione della piattaforma social. Dopo l'autenticazione, il token viene rinnovato con la nuova data di scadenza.
   ![pbd-renew](assets/pbd-renew.png)
