---
description: L’eliminazione in blocco consente di rimuovere più segmenti, caratteristiche, cartelle, segnali derivati, origini dati, modelli e destinazioni con una singola operazione. Segui queste istruzioni per effettuare una richiesta di eliminazione in blocco.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Eliminazione in blocco
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Eliminazione in blocco{#bulk-delete}

L’eliminazione in blocco consente di rimuovere più segmenti, caratteristiche, cartelle, segnali derivati, origini dati, modelli e destinazioni con una singola operazione. Segui queste istruzioni per effettuare una richiesta di eliminazione in blocco.

>[!IMPORTANT]
>
>Gli strumenti di gestione in blocco non sono un’offerta ufficialmente supportata da Adobe. La risoluzione dei problemi e il supporto tramite l’Assistenza clienti verranno gestiti caso per caso.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[Le autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnate nell&#39;interfaccia utente [!DNL Audience Manager] vengono rispettate in [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Se hai dei segmenti mappati sulla destinazione, l’eliminazione collettiva per i mapping di destinazione non riuscirà. Rimuovi i segmenti da tale destinazione nell’interfaccia utente di prima di tentare di eliminare in blocco le destinazioni. Inoltre, le cartelle di caratteristiche e segmenti devono essere vuote prima di poterle eliminare.

Per eliminare più elementi, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Headers]** e copiare le intestazioni di creazione per l&#39;elemento che si desidera aggiungere.
2. Fare clic sulla scheda **[!UICONTROL Delete]**.
3. Incollare le intestazioni di eliminazione nella prima riga del foglio di lavoro di aggiornamento.
4. Incolla o digita gli ID per gli oggetti che desideri eliminare nella colonna sotto l&#39;intestazione.
5. Fornisci le [informazioni di accesso](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) richieste e fai clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea una colonna [!UICONTROL Results]. La colonna [!UICONTROL Results] restituisce un messaggio che indica se l&#39;elemento è stato eliminato o un messaggio di errore.
Prima di immettere i dati, il foglio di lavoro per l&#39;aggiornamento in blocco deve avere un aspetto simile al seguente:

![](assets/delete.png)

Se l&#39;aggiornamento in blocco restituisce un errore o non riesce, vedere [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
