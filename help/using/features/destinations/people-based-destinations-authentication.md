---
description: 'Questa pagina contiene indicazioni su come configurare e gestire l’integrazione tra le piattaforme basate su persone e su Audience Manager. '
seo-description: 'Questa pagina contiene indicazioni su come configurare e gestire l’integrazione tra le piattaforme basate su persone e su Audience Manager. '
seo-title: Autenticazione con piattaforme basate su persone
solution: Audience Manager
title: Autenticazione con piattaforme basate su persone
feature: Destinazioni basate su persone
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# Autenticazione con piattaforme basate su persone {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

Questa pagina contiene indicazioni su come configurare e gestire l’integrazione
tra piattaforme basate su persone e Audience Manager.

>[!NOTE]
>Questo è un passaggio obbligatorio per le destinazioni basate su persone, indipendentemente dallo scenario di implementazione.

## Configurare l’autenticazione della piattaforma basata sulle persone {#configure-authentication}

1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Se disponi di un’integrazione configurata in precedenza con una piattaforma social, visualizzala in questa pagina. In caso contrario, la pagina è vuota.
   ![integrazione basata sulle persone](assets/pbd-config.png)
2. Clic **[!UICONTROL Add Account]**.
3. Utilizza il menu a discesa **[!UICONTROL People-Based Platform]** per selezionare la piattaforma con cui desideri configurare l’integrazione.
   ![piattaforma basata sulle persone](assets/pbd-add.png)
4. Fai clic su **[!UICONTROL Confirm]** per essere reindirizzato alla pagina di autenticazione della piattaforma selezionata.
5. Dopo aver eseguito l’autenticazione all’account della piattaforma social, vieni reindirizzato all’Audience Manager in cui dovresti visualizzare gli account dell’inserzionista associati. Seleziona l’account dell’inserzionista da utilizzare e fai clic su **[!UICONTROL Confirm]**.
6. In Audience Manager viene visualizzata una notifica nella parte superiore della pagina per sapere se l’account è stato aggiunto correttamente. La notifica ti consente anche di aggiungere un indirizzo e-mail di contatto per ricevere notifiche da Adobe quando l’autenticazione della piattaforma social sta per scadere.

## Scadenza e gestione delle notifiche dei token di autenticazione {#token-expiration-notification}

Audience Manager gestisce l’integrazione con le piattaforme social tramite token di autenticazione che scadono dopo un certo periodo di tempo. La durata di validità dei token è soggetta alle regole di integrazione di ogni piattaforma social. Una volta scaduto il token di autenticazione, Audience Manager non è in grado di inviare i segmenti di pubblico alla destinazione. Per evitare questo scenario, ti consigliamo di aggiungere almeno un indirizzo e-mail di contatto alla tua integrazione, in modo da ricevere notifiche non appena il token di autenticazione sta per scadere. In questo caso, puoi effettuare nuovamente l’autenticazione per garantire che la destinazione continui a ricevere i segmenti di pubblico.

Ecco come aggiungere indirizzi e-mail alle integrazioni esistenti:

1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifica l’integrazione per la quale desideri ricevere le notifiche di scadenza del token e fai clic sull’icona **[!UICONTROL Edit]** .
1. Inserisci gli indirizzi e-mail che desideri ricevere le notifiche di scadenza del token, separati da virgole.
1. Clic **[!UICONTROL Save]**.

## Rinnovo token di autenticazione {#token-renewal}

Quando un token di autenticazione scade, l’integrazione tra Audience Manager e la piattaforma social corrispondente viene interrotta, pertanto l’Audience Manager non può più inviare segmenti di pubblico alla destinazione. La pagina [!UICONTROL Integrated Accounts] mostra lo stato di scadenza di ogni integrazione nella colonna [!UICONTROL Expiration] e ti consente di rinnovare l’autenticazione in qualsiasi momento.

Ecco come rinnovare un’autenticazione scaduta o in procinto di scadere:
1. Accedi al tuo account di Audience Manager e vai a **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifica l’integrazione necessaria per rinnovare l’autenticazione. Le autenticazioni scadute sono contrassegnate come [!UICONTROL Expired], mentre le autenticazioni che stanno per scadere mostrano a breve il numero rimanente di giorni autenticati.
1. Fai clic sull&#39;icona corrispondente **[!UICONTROL Renew]** nella colonna [!UICONTROL Expiration] . Questo attiva il flusso di lavoro **[!UICONTROL Renew Account]** , che ti riporta alla pagina di autenticazione della piattaforma social. Dopo l’autenticazione, il token viene rinnovato con la nuova data di scadenza.
   ![pbd-rinnovo](assets/pbd-renew.png)
