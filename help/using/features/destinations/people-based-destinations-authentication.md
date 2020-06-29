---
description: 'Questa pagina contiene istruzioni su come configurare e gestire l''integrazione tra  Audience Manager e le piattaforme basate sulle persone. '
seo-description: 'Questa pagina contiene istruzioni su come configurare e gestire l''integrazione tra  Audience Manager e le piattaforme basate sulle persone. '
seo-title: Autenticazione con piattaforme basate su persone
solution: Audience Manager
title: Autenticazione con piattaforme basate su persone
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 0%

---


# Autenticazione con piattaforme basate su persone {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

Questa pagina contiene istruzioni su come configurare e gestire l’integrazione tra  Audience Manager e piattaforme basate sulle persone.

>[!NOTE]
>Si tratta di un passaggio obbligatorio per le destinazioni basate su persone, indipendentemente dallo scenario di implementazione.

## Configurare l’autenticazione Platform basata sulle persone {#configure-authentication}

1. Accedete al vostro account Audience Manager  e andate a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se avete già configurato un&#39;integrazione con una piattaforma social, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
2. Clic **[!UICONTROL Add Account]**.
3. Utilizzate il menu a **[!UICONTROL People-Based Platform]** discesa per selezionare la piattaforma con cui desiderate configurare l&#39;integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
4. Fare clic per **[!UICONTROL Confirm]** essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
5. Dopo aver eseguito l&#39;autenticazione sull&#39;account della tua piattaforma social, verrai reindirizzato a  Audience Manager, dove potrai vedere gli account dell&#39;inserzionista associato. Selezionate l’account dell’inserzionista da usare e fate clic su **[!UICONTROL Confirm]**.
6.  Audience Manager visualizza una notifica nella parte superiore della pagina per informarvi se l’account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere notifiche da Adobe quando l&#39;autenticazione della piattaforma social sta per scadere.

## Scadenza token di autenticazione e gestione delle notifiche {#token-expiration-notification}

 Audience Manager gestisce l&#39;integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. La durata della validità del token è soggetta alle regole di integrazione di ciascuna piattaforma social. Una volta scaduto il token di autenticazione,  Audience Manager non è in grado di inviare i segmenti di pubblico alla destinazione. Per evitare questo scenario, si consiglia di aggiungere almeno un indirizzo e-mail di contatto all&#39;integrazione, in modo da ricevere una notifica non appena il token di autenticazione sta per scadere. In questo caso, puoi autenticarti nuovamente per assicurarti che la destinazione continui a ricevere i tuoi segmenti di pubblico.

Come aggiungere indirizzi e-mail alle integrazioni esistenti:

1. Accedete al vostro account Audience Manager  e andate a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identificate l&#39;integrazione per la quale desiderate ricevere le notifiche di scadenza del token e fate clic sull&#39; **[!UICONTROL Edit]** icona.
1. Inserite gli indirizzi e-mail che desiderate ricevere notifiche di scadenza del token, separati da virgole.
1. Clic **[!UICONTROL Save]**.

## Rinnovo token di autenticazione {#token-renewal}

Quando scade un token di autenticazione, l&#39;integrazione tra  Audience Manager e la piattaforma social corrispondente viene interrotta,  Audience Manager non può più inviare segmenti di pubblico alla destinazione. La [!UICONTROL Integrated Accounts] pagina mostra lo stato di scadenza di ciascuna integrazione nella [!UICONTROL Expiration] colonna e consente di rinnovare l’autenticazione in qualsiasi momento.

Come rinnovare un&#39;autenticazione scaduta o in procinto di scadere:
1. Accedete al vostro account Audience Manager  e andate a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identificate l&#39;integrazione per la quale desiderate rinnovare l&#39;autenticazione. Le autenticazioni scadute sono contrassegnate come [!UICONTROL Expired], mentre quelle che stanno per scadere indicano a breve il numero rimanente di giorni autenticati.
1. Fate clic sull&#39; **[!UICONTROL Renew]** icona corrispondente nella [!UICONTROL Expiration] colonna. Questo attiva il **[!UICONTROL Renew Account]** flusso di lavoro, che vi riporta alla pagina di autenticazione della piattaforma social. Dopo l’autenticazione, il token viene rinnovato con la nuova data di scadenza.
   ![pbd-rinnovo](assets/pbd-renew.png)
