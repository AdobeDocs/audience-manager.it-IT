---
description: Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi della cartella dei segmenti o delle caratteristiche in un'unica operazione. Seguite queste istruzioni per effettuare aggiornamenti in blocco.
keywords: baaam
seo-description: Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi della cartella dei segmenti o delle caratteristiche in un'unica operazione. Seguite queste istruzioni per effettuare aggiornamenti in blocco.
seo-title: Aggiornamenti in blocco
solution: Audience Manager
title: Aggiornamenti in blocco
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---


# Aggiornamenti in blocco{#bulk-updates}

Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi della cartella dei segmenti o delle caratteristiche in un&#39;unica operazione. Seguite queste istruzioni per effettuare aggiornamenti in blocco.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella  [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Headers]** e copiare le intestazioni di aggiornamento per l&#39;elemento da modificare.
2. Fare clic sulla scheda **[!UICONTROL Update]**.
3. Incollare le intestazioni di aggiornamento nella prima riga del foglio di lavoro di aggiornamento. Tenete presente quanto segue:

   * Quando si aggiorna una cartella, tutte le intestazioni sono obbligatorie.
   * Quando si aggiornano segmenti o caratteristiche, è necessario solo l’ID segmento (SID) e l’elemento intestazione che deve essere modificato. Elimina intestazioni inutilizzate.

4. Incollate o digitate i dati da modificare in una colonna corrispondente in base all&#39;etichetta dell&#39;intestazione.
5. Nella barra degli strumenti del foglio di lavoro, fare clic su un pulsante di aggiornamento corrispondente al pulsante        elemento che si sta aggiornando.
Questa azione apre la finestra di dialogo [!UICONTROL Account Information].

6. Specificare le informazioni di accesso [necessarie](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fare clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea una colonna [!UICONTROL Results]. La colonna [!UICONTROL Results] restituisce la risposta JSON per un&#39;operazione riuscita. Per gli esempi, vedere [REST APIs](../../api/rest-api-main/rest-api-main.md). Prima di immettere i dati, il foglio di lavoro di aggiornamento in blocco deve essere simile al seguente:

![](assets/update.png)

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, vedere [Risoluzione dei problemi per gli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
