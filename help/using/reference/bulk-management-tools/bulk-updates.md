---
description: Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi della cartella dei segmenti o delle caratteristiche in un'unica operazione. Seguite queste istruzioni per effettuare aggiornamenti in blocco.
keywords: baaam
seo-description: Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi della cartella dei segmenti o delle caratteristiche in un'unica operazione. Seguite queste istruzioni per effettuare aggiornamenti in blocco.
seo-title: Aggiornamenti di massa
solution: Audience Manager
title: Aggiornamenti di massa
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Aggiornamenti di massa{#bulk-updates}

Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi della cartella dei segmenti o delle caratteristiche in un&#39;unica operazione. Seguite queste istruzioni per effettuare aggiornamenti in blocco.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, aprire il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fate clic sulla **[!UICONTROL Headers]** scheda e copiate le intestazioni di aggiornamento per l’elemento da modificare.
2. Fate clic sulla **[!UICONTROL Update]** scheda.
3. Incollare le intestazioni di aggiornamento nella prima riga del foglio di lavoro di aggiornamento. Tenete presente quanto segue:

   * Quando si aggiorna una cartella, tutte le intestazioni sono obbligatorie.
   * Quando si aggiornano segmenti o caratteristiche, è necessario solo l’ID segmento (SID) e l’elemento intestazione che deve essere modificato. Elimina intestazioni inutilizzate.

4. Incollate o digitate i dati da modificare in una colonna corrispondente in base all&#39;etichetta dell&#39;intestazione.
5. Nella barra degli strumenti del foglio di lavoro, fare clic su un pulsante di aggiornamento corrispondente all&#39;elemento che si sta aggiornando.
Questa azione consente di aprire la [!UICONTROL Account Information] finestra di dialogo.

6. Fornite le informazioni [di](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) accesso richieste e fate clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea una [!UICONTROL Results] colonna. La [!UICONTROL Results] colonna restituisce la risposta JSON per un&#39;operazione riuscita. Per gli esempi, consultate [REST API](../../api/rest-api-main/rest-api-main.md) . Prima di immettere i dati, il foglio di lavoro di aggiornamento in blocco deve essere simile al seguente:

![](assets/update.png)

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consulta Risoluzione dei [problemi relativi agli strumenti](../../reference/bulk-management-tools/bulk-troubleshooting.md)di gestione in blocco.
