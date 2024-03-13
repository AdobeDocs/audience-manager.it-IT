---
description: Questa pagina contiene istruzioni su come configurare e gestire l’integrazione tra piattaforme Audienci Manager e piattaforme basate sulle persone.
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: Autenticazione con piattaforme basate su persone
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: 1809e9ee0b19a8ffb4bec38162f728d543d13701
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# Autenticazione con piattaforme basate su persone {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

Questa pagina contiene istruzioni su come configurare e gestire l’integrazione tra piattaforme Audienci Manager e piattaforme basate sulle persone.

>[!NOTE]
>Questo è un passaggio obbligatorio per le destinazioni basate su persone, indipendentemente dallo scenario di implementazione.

## Configurare l’autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account Audienci Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma social, dovresti visualizzarla in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
2. Clic **[!UICONTROL Add Account]**.
3. Utilizza il **[!UICONTROL People-Based Platform]** menu a discesa per selezionare la piattaforma con cui configurare l’integrazione.
   ![people-based-platform](assets/pbd-add.png)
4. Clic **[!UICONTROL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
5. Dopo aver eseguito l’autenticazione all’account della piattaforma social, vieni reindirizzato all’Audience Manager in cui dovresti visualizzare gli account pubblicitari associati. Seleziona l’account dell’inserzionista che desideri utilizzare e fai clic su **[!UICONTROL Confirm]**.
6. In Audience Manager, nella parte superiore della pagina viene visualizzata una notifica per comunicare se l’account è stato aggiunto correttamente. La notifica ti consente inoltre di aggiungere un indirizzo e-mail di contatto per ricevere notifiche da Adobe quando l’autenticazione della piattaforma social sta per scadere.

## Gestione della scadenza e delle notifiche del token di autenticazione {#token-expiration-notification}

Audienci Manager gestisce l’integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. La durata della validità del token è soggetta alle regole di integrazione di ogni piattaforma social. Una volta scaduto il token di autenticazione, Audienci Manager non è in grado di inviare i segmenti di pubblico alla destinazione. Per evitare questo scenario, ti consigliamo di aggiungere almeno un indirizzo e-mail di contatto all’integrazione, in modo da ricevere una notifica non appena il token di autenticazione sta per scadere. In questo caso, puoi ripetere l’autenticazione per garantire che la destinazione continui a ricevere i segmenti di pubblico.

Ecco come aggiungere indirizzi e-mail alle integrazioni esistenti:

1. Accedi al tuo account Audienci Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifica l’integrazione per la quale desideri ricevere notifiche di scadenza del token e fai clic sul pulsante **[!UICONTROL Edit]** icona.
1. Inserisci gli indirizzi e-mail a cui desideri ricevere le notifiche di scadenza del token, separati da virgole.
1. Clic **[!UICONTROL Save]**.

## Rinnovo del token di autenticazione {#token-renewal}

Quando un token di autenticazione scade, l’integrazione tra Audienci Manager e la piattaforma social corrispondente viene interrotta, pertanto Audienci Manager non può più inviare segmenti di pubblico alla destinazione. Il [!UICONTROL Integrated Accounts] mostra lo stato di scadenza di ogni integrazione nella sezione [!UICONTROL Expiration] e ti consente di rinnovare l’autenticazione in qualsiasi momento.

Di seguito viene illustrato come rinnovare un’autenticazione scaduta o in scadenza:
1. Accedi al tuo account Audienci Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifica l’integrazione per la quale è necessario rinnovare l’autenticazione. Le autenticazioni scadute sono contrassegnate come [!UICONTROL Expired], mentre le autenticazioni che stanno per scadere mostrano il numero rimanente di giorni autenticati.
1. Fai clic sul pulsante corrispondente **[!UICONTROL Renew]** icona in [!UICONTROL Expiration] colonna. Questo attiva il **[!UICONTROL Renew Account]** flusso di lavoro, che ti riporta alla pagina di autenticazione della piattaforma social. Dopo l’autenticazione, il token viene rinnovato con la nuova data di scadenza.
   ![pbd-renew](assets/pbd-renew.png)
