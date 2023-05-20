---
description: Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi della cartella di segmenti o caratteristiche in un’unica operazione. Segui queste istruzioni per effettuare aggiornamenti in blocco.
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Aggiornamenti in blocco
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 1%

---

# Aggiornamenti in blocco{#bulk-updates}

Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi della cartella di segmenti o caratteristiche in un’unica operazione. Segui queste istruzioni per effettuare aggiornamenti in blocco.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnato in [!DNL Audience Manager] L’interfaccia utente di è rispettata in [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, apri [!UICONTROL Bulk Management Tools] foglio di lavoro e

1. Fai clic su **[!UICONTROL Headers]** e copiare le intestazioni di aggiornamento per l&#39;elemento da modificare.
2. Fai clic su **[!UICONTROL Update]** scheda.
3. Incollare le intestazioni di aggiornamento nella prima riga del foglio di lavoro di aggiornamento. Tieni presente quanto segue:

   * Quando si aggiorna una cartella, sono necessarie tutte le intestazioni.
   * Quando si aggiornano segmenti o caratteristiche, è necessario solo l’ID segmento (SID) e l’elemento intestazione che devono essere modificati. Elimina le intestazioni non utilizzate.

4. Incolla o digita i dati che desideri modificare in una colonna corrispondente in base all’etichetta dell’intestazione.
5. Nella barra degli strumenti del foglio di lavoro fare clic su un pulsante di aggiornamento corrispondente all&#39;elemento che si sta aggiornando.
Questa azione apre il [!UICONTROL Account Information] .

6. Fornisci il necessario [informazioni di accesso](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fai clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea un [!UICONTROL Results] colonna. Il [!UICONTROL Results] restituisce la risposta JSON per un’operazione riuscita. Consulta la [API REST](../../api/rest-api-main/rest-api-main.md) ad esempio. Prima di immettere i dati, il foglio di lavoro per l&#39;aggiornamento in blocco deve avere un aspetto simile al seguente:

![](assets/update.png)

Se l’aggiornamento in blocco restituisce un errore o non riesce, consulta [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
