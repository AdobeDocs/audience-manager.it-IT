---
description: Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, elementi di segmenti o cartelle di caratteristiche in una singola operazione. Seguite queste istruzioni per effettuare aggiornamenti in blocco.
keywords: baaam
seo-description: Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, elementi di segmenti o cartelle di caratteristiche in una singola operazione. Seguite queste istruzioni per effettuare aggiornamenti in blocco.
seo-title: Aggiornamenti di massa
solution: Audience Manager
title: Aggiornamenti di massa
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Aggiornamenti di massa{#bulk-updates}

Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, elementi di segmenti o cartelle di caratteristiche in una singola operazione. Seguite queste istruzioni per effettuare aggiornamenti in blocco.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>Le [!UICONTROL Bulk Management Tools] opzioni non *sono supportate da* [!DNL Audience Manager]. Questo strumento è fornito per comodità e solo come cortesia. Per modifiche di massa, consigliamo di lavorare con le API [](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, aprire il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fate clic sulla **[!UICONTROL Headers]** scheda e copiate le intestazioni di aggiornamento per l’elemento da modificare.
1. Click the **[!UICONTROL Update]** tab.
1. Incollare le intestazioni di aggiornamento nella prima riga del foglio di lavoro di aggiornamento. Tenete presente quanto segue:

   * Quando si aggiorna una cartella, tutte le intestazioni sono obbligatorie.
   * Quando si aggiornano segmenti o caratteristiche, è necessario solo l’ID segmento (SID) e l’elemento intestazione che deve essere modificato. Elimina intestazioni inutilizzate.

1. Incollate o digitate i dati da modificare in una colonna corrispondente in base all'etichetta dell'intestazione.
1. Nella barra degli strumenti del foglio di lavoro, fare clic su un pulsante di aggiornamento corrispondente all'elemento che si sta aggiornando.
Questa azione consente di aprire la [!UICONTROL Account Information] finestra di dialogo.

1. Fornite le informazioni [di](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) accesso richieste e fate clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea una [!UICONTROL Results] colonna. La [!UICONTROL Results] colonna restituisce la risposta JSON per un'operazione riuscita. Per gli esempi, consultate [REST API](../../api/rest-api-main/rest-api-main.md) . Prima di immettere i dati, il foglio di lavoro di aggiornamento in blocco deve essere simile al seguente:

![](assets/update.png)

Se l'aggiornamento in blocco restituisce un errore o non riesce, consultate Risoluzione dei [problemi relativi agli strumenti](../../reference/bulk-management-tools/bulk-troubleshooting.md)di gestione in blocco.
