---
description: La creazione in massa consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con una singola operazione. Per effettuare una richiesta di creazione in massa, effettuate le seguenti operazioni.
seo-description: La creazione in massa consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con una singola operazione. Per effettuare una richiesta di creazione in massa, effettuate le seguenti operazioni.
seo-title: Crea in blocco
solution: Audience Manager
title: Crea in blocco
uuid: 1 e 09 bcfa -783 e -4 e 9 b -9 ead -147 f 8 d 1381 c 8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Create{#bulk-create}

La creazione in massa consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con una singola operazione. Per effettuare una richiesta di creazione in massa, effettuate le seguenti operazioni.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell' [!DNL Audience Manager] interfaccia utente vengono rispettate nell' [!UICONTROL Bulk Management Tools]interfaccia.

>[!CAUTION]
>
>Non combinate tipi di oggetti in una richiesta di creazione in massa. Le intestazioni di ciascun oggetto sono univoche e non possono essere combinate. Cancella il foglio di lavoro e richiedi una richiesta separata per elementi diversi.

To create objects in bulk, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
1. Click the **[!UICONTROL Create]** tab.
1. Incolla le intestazioni create nella prima riga del foglio di lavoro di aggiornamento.
1. Incolla o digita i dati da modificare in una colonna corrispondente basata sull'etichetta dell'intestazione.
1. Nella barra degli strumenti del foglio di lavoro, fate clic sul pulsante Crea corrispondente all'elemento che state aggiornando.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Prima di inserire i dati, il foglio di lavoro di creazione in massa deve essere simile all'esempio seguente. Non vengono visualizzate tutte le opzioni di creazione. Questa funzione è utile per comprendere l'aspetto di un foglio di lavoro completato.

![](assets/cretetraits.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
