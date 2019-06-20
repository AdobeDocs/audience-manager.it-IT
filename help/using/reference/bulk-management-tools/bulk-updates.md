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


# Aggiornamenti in blocco{#bulk-updates}

Un aggiornamento in massa consente di modificare più segmenti, caratteristiche e elementi di cartelle o segmenti in una singola operazione. Segui queste istruzioni per effettuare aggiornamenti in massa.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>Non [!UICONTROL Bulk Management Tools]*sono* supportati da [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. Per modifiche in massa, consigliamo di lavorare con [le API](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell&#39; [!DNL Audience Manager] interfaccia utente vengono rispettate nell&#39; [!UICONTROL Bulk Management Tools]interfaccia.

Per effettuare aggiornamenti in massa, apri il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fare clic sulla **[!UICONTROL Headers]** scheda e copiare le intestazioni di aggiornamento dell&#39;elemento da modificare.
1. Fare clic sulla **[!UICONTROL Update]** scheda.
1. Incollate le intestazioni di aggiornamento nella prima riga del foglio di lavoro di aggiornamento. Tenete presente quanto segue:

   * Quando si aggiorna una cartella, tutte le intestazioni sono richieste.
   * Quando aggiornate segmenti o caratteristiche, è necessario solo l&#39;ID segmento (SID) e l&#39;elemento dell&#39;intestazione che deve essere modificato. Elimina le intestazioni non utilizzate.

1. Incolla o digita i dati da modificare in una colonna corrispondente basata sull&#39;etichetta dell&#39;intestazione.
1. Nella barra degli strumenti del foglio di lavoro, fate clic su un pulsante di aggiornamento corrispondente all&#39;elemento che state aggiornando.
Questa azione apre la [!UICONTROL Account Information] finestra di dialogo.

1. Fornite le informazioni [richieste](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fate clic **[!UICONTROL Submit]** su.

   Il foglio di lavoro crea una [!UICONTROL Results] colonna. La [!UICONTROL Results] colonna restituisce la risposta JSON per un&#39;operazione di successo. Per [esempi, consultate](../../api/rest-api-main/rest-api-main.md) API REST. Prima di inserire i dati, il foglio di lavoro di aggiornamento in blocco deve essere simile a quello seguente:

![](assets/update.png)

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consultate [Risoluzione dei problemi per strumenti di gestione collettiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
