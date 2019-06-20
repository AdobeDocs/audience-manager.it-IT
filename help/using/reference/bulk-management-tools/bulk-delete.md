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


# Elimina massa{#bulk-delete}

L&#39;eliminazione di massa consente di rimuovere più segmenti, caratteristiche, cartelle, segnali derivati e destinazioni con una singola operazione. Per effettuare una richiesta di eliminazione collettiva, effettuate le seguenti operazioni.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>Non [!UICONTROL Bulk Management Tools]*sono* supportati da [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. Per modifiche in massa, consigliamo di lavorare con [le API](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell&#39; [!DNL Audience Manager] interfaccia utente vengono rispettate nell&#39; [!UICONTROL Bulk Management Tools]interfaccia.

>[!NOTE]
>
>Un eliminazione in massa per le mappature di destinazione non riesce se vi sono segmenti mappati alla destinazione. Rimuovi i segmenti da quella destinazione nell&#39;interfaccia utente prima di tentare di indirizzare le destinazioni di eliminazione in massa. Inoltre, le cartelle di segmenti e segmenti devono essere vuote prima di poterle eliminare.

Per eliminare più elementi, aprite il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fare clic sulla **[!UICONTROL Headers]** scheda e copiare le intestazioni create per l&#39;elemento da aggiungere.
2. Fare clic sulla **[!UICONTROL Delete]** scheda.
3. Incolla le intestazioni di eliminazione nella prima riga del foglio di lavoro di aggiornamento.
4. Incolla o immetti gli ID per gli oggetti da eliminare nella colonna sotto l&#39;intestazione.
5. Fornite le informazioni [richieste](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fate clic **[!UICONTROL Submit]** su.

   Il foglio di lavoro crea una [!UICONTROL Results] colonna. [!UICONTROL Results] La colonna restituisce un messaggio che indica se l&#39;elemento è stato eliminato o un messaggio di errore.
Prima di inserire i dati, il foglio di lavoro di aggiornamento in blocco deve essere simile a quello seguente:

![](assets/delete.png)

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consultate [Risoluzione dei problemi per strumenti di gestione collettiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
