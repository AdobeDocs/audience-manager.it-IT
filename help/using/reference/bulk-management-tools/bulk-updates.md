---
description: Un aggiornamento in massa consente di modificare più segmenti, caratteristiche e elementi di cartelle o segmenti in una singola operazione. Segui queste istruzioni per effettuare aggiornamenti in massa.
keywords: baaam
seo-description: Un aggiornamento in massa consente di modificare più segmenti, caratteristiche e elementi di cartelle o segmenti in una singola operazione. Segui queste istruzioni per effettuare aggiornamenti in massa.
seo-title: Aggiornamenti in blocco
solution: Audience Manager
title: Aggiornamenti in blocco
uuid: 22 f 1 badd-a 274-4 d 3 e -9957-a 24 bf 8 c 1 d 0 dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Updates{#bulk-updates}

Un aggiornamento in massa consente di modificare più segmenti, caratteristiche e elementi di cartelle o segmenti in una singola operazione. Segui queste istruzioni per effettuare aggiornamenti in massa.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell' [!DNL Audience Manager] interfaccia utente vengono rispettate nell' [!UICONTROL Bulk Management Tools]interfaccia.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
1. Click the **[!UICONTROL Update]** tab.
1. Incollate le intestazioni di aggiornamento nella prima riga del foglio di lavoro di aggiornamento. Tenete presente quanto segue:

   * Quando si aggiorna una cartella, tutte le intestazioni sono richieste.
   * Quando aggiornate segmenti o caratteristiche, è necessario solo l'ID segmento (SID) e l'elemento dell'intestazione che deve essere modificato. Elimina le intestazioni non utilizzate.

1. Incolla o digita i dati da modificare in una colonna corrispondente basata sull'etichetta dell'intestazione.
1. Nella barra degli strumenti del foglio di lavoro, fate clic su un pulsante di aggiornamento corrispondente all'elemento che state aggiornando.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Prima di inserire i dati, il foglio di lavoro di aggiornamento in blocco deve essere simile a quello seguente:

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
