---
description: L’eliminazione in blocco consente di rimuovere più segmenti, caratteristiche, cartelle, segnali derivati, origini dati, modelli e destinazioni con una singola operazione. Segui queste istruzioni per effettuare una richiesta di cancellazione in blocco.
seo-description: L’eliminazione in blocco consente di rimuovere più segmenti, caratteristiche, cartelle, segnali derivati, origini dati, modelli e destinazioni con una singola operazione. Segui queste istruzioni per effettuare una richiesta di cancellazione in blocco.
seo-title: Eliminazione in blocco
solution: Audience Manager
title: Eliminazione in blocco
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Eliminazione in blocco{#bulk-delete}

L’eliminazione in blocco consente di rimuovere più segmenti, caratteristiche, cartelle, segnali derivati, origini dati, modelli e destinazioni con una singola operazione. Segui queste istruzioni per effettuare una richiesta di cancellazione in blocco.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate in  [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Un&#39;eliminazione in blocco per le mappature di destinazione avrà esito negativo se hai mappato segmenti sulla destinazione. Rimuovi i segmenti da tale destinazione nell’interfaccia utente prima di tentare di eliminare in massa le destinazioni. Inoltre, le cartelle di caratteristiche e segmenti devono essere vuote prima di poter essere eliminate.

Per eliminare più elementi, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fai clic sulla scheda **[!UICONTROL Headers]** e copia le intestazioni create per l’elemento che desideri aggiungere.
2. Fai clic sulla scheda **[!UICONTROL Delete]** .
3. Incolla le intestazioni di eliminazione nella prima riga del foglio di lavoro di aggiornamento.
4. Incolla o digita gli ID per gli oggetti da eliminare nella colonna sotto l’intestazione.
5. Fornisci le [informazioni di accesso ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) richieste e fai clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea una colonna [!UICONTROL Results]. La colonna [!UICONTROL Results] restituisce un messaggio che indica se l’elemento è stato eliminato o se è stato visualizzato un messaggio di errore.
Prima di immettere i dati, il foglio di lavoro di aggiornamento collettivo deve essere simile al seguente:

![](assets/delete.png)

Se l&#39;aggiornamento collettivo restituisce un errore o non riesce, consulta [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
