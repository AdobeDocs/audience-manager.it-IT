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
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Aggiornamenti in blocco{#bulk-updates}

Un aggiornamento in blocco consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi della cartella di segmenti o caratteristiche in un’unica operazione. Segui queste istruzioni per effettuare aggiornamenti in blocco.

>[!IMPORTANT]
>
>Gli strumenti di gestione in blocco non sono un’offerta di Adobe ufficialmente supportata. La risoluzione dei problemi e il supporto tramite l’Assistenza clienti verranno gestiti caso per caso.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Le autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnate nell&#39;interfaccia utente [!DNL Audience Manager] vengono rispettate in [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Headers]** e copiare le intestazioni di aggiornamento per l&#39;elemento da modificare.
2. Fare clic sulla scheda **[!UICONTROL Update]**.
3. Incollare le intestazioni di aggiornamento nella prima riga del foglio di lavoro di aggiornamento. Tieni presente quanto segue:

   * Quando si aggiorna una cartella, sono necessarie tutte le intestazioni.
   * Quando si aggiornano segmenti o caratteristiche, è necessario solo l’ID segmento (SID) e l’elemento intestazione che devono essere modificati. Elimina le intestazioni non utilizzate.

4. Incolla o digita i dati che desideri modificare in una colonna corrispondente in base all’etichetta dell’intestazione.
5. Nella barra degli strumenti del foglio di lavoro fare clic su un pulsante di aggiornamento corrispondente al        elemento da aggiornare.
Questa azione apre la finestra di dialogo [!UICONTROL Account Information].

6. Fornisci le [informazioni di accesso](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) richieste e fai clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea una colonna [!UICONTROL Results]. La colonna [!UICONTROL Results] restituisce la risposta JSON per un&#39;operazione riuscita. Per esempi, consulta le [API REST](../../api/rest-api-main/rest-api-main.md). Prima di immettere i dati, il foglio di lavoro per l&#39;aggiornamento in blocco deve avere un aspetto simile al seguente:

![](assets/update.png)

Se l&#39;aggiornamento in blocco restituisce un errore o non riesce, vedere [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
