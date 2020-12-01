---
description: L'eliminazione in blocco consente di rimuovere segmenti, caratteristiche, cartelle, segnali derivati, origini dati, modelli e destinazioni multipli con un'unica operazione. Seguite queste istruzioni per effettuare una richiesta di eliminazione in blocco.
seo-description: L'eliminazione in blocco consente di rimuovere segmenti, caratteristiche, cartelle, segnali derivati, origini dati, modelli e destinazioni multipli con un'unica operazione. Seguite queste istruzioni per effettuare una richiesta di eliminazione in blocco.
seo-title: Eliminazione in blocco
solution: Audience Manager
title: Eliminazione in blocco
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---


# Eliminazione in blocco{#bulk-delete}

L&#39;eliminazione in blocco consente di rimuovere segmenti, caratteristiche, cartelle, segnali derivati, origini dati, modelli e destinazioni multipli con un&#39;unica operazione. Seguite queste istruzioni per effettuare una richiesta di eliminazione in blocco.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella  [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Un&#39;eliminazione in blocco per le mappature di destinazione non riuscirà se i segmenti sono mappati sulla destinazione. Rimuovere i segmenti da tale destinazione nell&#39;interfaccia utente prima di tentare di eliminare in massa le destinazioni. Inoltre, le cartelle relative alle caratteristiche e ai segmenti devono essere vuote prima di poter essere eliminate.

Per eliminare più elementi, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Headers]** e copiare le intestazioni di creazione per l&#39;elemento da aggiungere.
2. Fare clic sulla scheda **[!UICONTROL Delete]**.
3. Incollare le intestazioni di eliminazione nella prima riga del foglio di lavoro di aggiornamento.
4. Incollate o digitate gli ID per gli oggetti da eliminare nella colonna sotto l’intestazione.
5. Specificare le informazioni di accesso [necessarie](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fare clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea una colonna [!UICONTROL Results]. La colonna [!UICONTROL Results] restituisce un messaggio che indica se l&#39;elemento è stato eliminato o un messaggio di errore.
Prima di immettere i dati, il foglio di lavoro di aggiornamento in blocco deve essere simile al seguente:

![](assets/delete.png)

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, vedere [Risoluzione dei problemi per gli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
