---
description: L’eliminazione in blocco consente di rimuovere segmenti, caratteristiche, cartelle, segnali derivati e destinazioni multipli con un’unica operazione. Seguite queste istruzioni per effettuare una richiesta di eliminazione in blocco.
seo-description: L’eliminazione in blocco consente di rimuovere segmenti, caratteristiche, cartelle, segnali derivati e destinazioni multipli con un’unica operazione. Seguite queste istruzioni per effettuare una richiesta di eliminazione in blocco.
seo-title: Elimina in blocco
solution: Audience Manager
title: Elimina in blocco
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Elimina in blocco{#bulk-delete}

L’eliminazione in blocco consente di rimuovere segmenti, caratteristiche, cartelle, segnali derivati e destinazioni multipli con un’unica operazione. Seguite queste istruzioni per effettuare una richiesta di eliminazione in blocco.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>Le [!UICONTROL Bulk Management Tools] opzioni non *sono supportate da* [!DNL Audience Manager]. Questo strumento è fornito per comodità e solo come cortesia. Per modifiche di massa, consigliamo di lavorare con le API [](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Un'eliminazione in blocco per le mappature di destinazione non riesce se i segmenti sono mappati sulla destinazione. Rimuovere i segmenti da tale destinazione nell'interfaccia utente prima di tentare di eliminare in massa le destinazioni. Inoltre, le cartelle relative alle caratteristiche e ai segmenti devono essere vuote prima di poter essere eliminate.

Per eliminare più elementi, aprire il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fate clic sulla **[!UICONTROL Headers]** scheda e copiate le intestazioni create per l’elemento da aggiungere.
2. Click the **[!UICONTROL Delete]** tab.
3. Incolla le intestazioni di eliminazione nella prima riga del foglio di lavoro di aggiornamento.
4. Incollate o digitate gli ID per gli oggetti da eliminare nella colonna sotto l’intestazione.
5. Fornite le informazioni [di](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) accesso richieste e fate clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea una [!UICONTROL Results] colonna. La [!UICONTROL Results] colonna restituisce un messaggio che indica se l’elemento è stato eliminato o se è stato visualizzato un messaggio di errore.
Prima di immettere i dati, il foglio di lavoro di aggiornamento in blocco deve essere simile al seguente:

![](assets/delete.png)

Se l'aggiornamento in blocco restituisce un errore o non riesce, consultate Risoluzione dei [problemi relativi agli strumenti](../../reference/bulk-management-tools/bulk-troubleshooting.md)di gestione in blocco.
