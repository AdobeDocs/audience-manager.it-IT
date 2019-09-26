---
description: 'Questa pagina contiene istruzioni su come configurare e gestire l''integrazione tra Audience Manager e le piattaforme basate sulle persone. '
seo-description: 'Questa pagina contiene istruzioni su come configurare e gestire l''integrazione tra Audience Manager e le piattaforme basate sulle persone. '
seo-title: Autenticazione con piattaforme basate su persone
solution: Audience Manager
title: Autenticazione con piattaforme basate su persone
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

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
1. Audience Manager visualizza una notifica nella parte superiore della pagina per informarvi se l'account è stato aggiunto correttamente. La notifica consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere notifiche da Adobe quando l'autenticazione della piattaforma social sta per scadere.

## Scadenza token di autenticazione e gestione delle notifiche {#token-expiration-notification}

Audience Manager gestisce l'integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. La durata della validità del token è soggetta alle regole di integrazione di ciascuna piattaforma social. Una volta scaduto il token di autenticazione, Audience Manager non è in grado di inviare i segmenti di pubblico alla destinazione. Per evitare questo scenario, si consiglia di aggiungere almeno un indirizzo e-mail di contatto all'integrazione, in modo da ricevere una notifica non appena il token di autenticazione sta per scadere. In questo caso, puoi autenticarti nuovamente per assicurarti che la destinazione continui a ricevere i tuoi segmenti di pubblico.

Come aggiungere indirizzi e-mail alle integrazioni esistenti:

1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identificate l'integrazione per la quale desiderate ricevere le notifiche di scadenza del token e fate clic sull' **[!UICONTROL Edit]** icona.
1. Inserite gli indirizzi e-mail che desiderate ricevere notifiche di scadenza token, separati da virgole.
1. Fai clic su **[!UICONTROL Save]**.

## Rinnovo token di autenticazione {#token-renewal}

When an authentication token expires, the integration between Audience Manager and the corresponding social platform is interrupted, so Audience Manager cannot send audience segments to the destination anymore. The  page shows you the expiration status of each integration in the  column, and allows you to renew the authentication at any time.[!UICONTROL Integrated Accounts][!UICONTROL Expiration]

Here's how to renew an expired or about-to-expire authentication:
1. Accedi al tuo account Audience Manager e vai a **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identify the integration that you need to renew authentication for. Expired authentications are marked as [!UICONTROL Expired], while authentications that are about to expire soon show the remaining number of authenticated days.
1. Click the corresponding  icon in the  column. **[!UICONTROL Renew]**[!UICONTROL Expiration] This triggers the  workflow, which takes you back through the social platform's authentication page. **[!UICONTROL Renew Account]** Once you authenticate, the token is renewed with the new expiration date.
   ![pbd-renew](assets/pbd-renew.png)
