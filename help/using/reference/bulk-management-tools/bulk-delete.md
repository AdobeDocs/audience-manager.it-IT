---
description: L'eliminazione di massa consente di rimuovere più segmenti, caratteristiche, cartelle, segnali derivati e destinazioni con una singola operazione. Per effettuare una richiesta di eliminazione collettiva, effettuate le seguenti operazioni.
seo-description: L'eliminazione di massa consente di rimuovere più segmenti, caratteristiche, cartelle, segnali derivati e destinazioni con una singola operazione. Per effettuare una richiesta di eliminazione collettiva, effettuate le seguenti operazioni.
seo-title: Elimina massa
solution: Audience Manager
title: Elimina massa
uuid: 679 cde 46-09 fb -45 c 6-b 84 d -47 e 00 e 0 e 7 c 0 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Delete{#bulk-delete}

L'eliminazione di massa consente di rimuovere più segmenti, caratteristiche, cartelle, segnali derivati e destinazioni con una singola operazione. Per effettuare una richiesta di eliminazione collettiva, effettuate le seguenti operazioni.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell' [!DNL Audience Manager] interfaccia utente vengono rispettate nell' [!UICONTROL Bulk Management Tools]interfaccia.

>[!NOTE]
>
>Un eliminazione in massa per le mappature di destinazione non riesce se vi sono segmenti mappati alla destinazione. Rimuovi i segmenti da quella destinazione nell'interfaccia utente prima di tentare di indirizzare le destinazioni di eliminazione in massa. Inoltre, le cartelle di segmenti e segmenti devono essere vuote prima di poterle eliminare.

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
2. Click the **[!UICONTROL Delete]** tab.
3. Incolla le intestazioni di eliminazione nella prima riga del foglio di lavoro di aggiornamento.
4. Incolla o immetti gli ID per gli oggetti da eliminare nella colonna sotto l'intestazione.
5. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] La colonna restituisce un messaggio che indica se l'elemento è stato eliminato o un messaggio di errore.
Prima di inserire i dati, il foglio di lavoro di aggiornamento in blocco deve essere simile a quello seguente:

![](assets/delete.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
