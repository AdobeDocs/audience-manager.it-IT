---
description: Un aggiornamento collettivo consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi di cartelle di segmenti o caratteristiche in un’unica operazione. Segui queste istruzioni per effettuare aggiornamenti in blocco.
keywords: baaam
seo-description: Un aggiornamento collettivo consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi di cartelle di segmenti o caratteristiche in un’unica operazione. Segui queste istruzioni per effettuare aggiornamenti in blocco.
seo-title: Aggiornamenti in blocco
solution: Audience Manager
title: Aggiornamenti in blocco
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# Aggiornamenti in blocco{#bulk-updates}

Un aggiornamento collettivo consente di modificare più segmenti, caratteristiche, modelli, origini dati ed elementi di cartelle di segmenti o caratteristiche in un’unica operazione. Segui queste istruzioni per effettuare aggiornamenti in blocco.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate in  [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, apri il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fai clic sulla scheda **[!UICONTROL Headers]** e copia le intestazioni di aggiornamento dell’elemento da modificare.
2. Fai clic sulla scheda **[!UICONTROL Update]** .
3. Incolla le intestazioni di aggiornamento nella prima riga del foglio di lavoro di aggiornamento. Tieni presente quanto segue:

   * Quando si aggiorna una cartella, sono necessarie tutte le intestazioni.
   * Quando aggiorni i segmenti o le caratteristiche, devi modificare solo l’ID segmento (SID) e l’elemento intestazione che deve essere modificato. Elimina le intestazioni non utilizzate.

4. Incolla o digita i dati da modificare in una colonna corrispondente in base all’etichetta dell’intestazione.
5. Nella barra degli strumenti del foglio di lavoro, fare clic su un pulsante di aggiornamento corrispondente al        elemento in corso di aggiornamento.
Questa azione apre la finestra di dialogo [!UICONTROL Account Information] .

6. Fornisci le [informazioni di accesso ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) richieste e fai clic su **[!UICONTROL Submit]**.

   Il foglio di lavoro crea una colonna [!UICONTROL Results]. La colonna [!UICONTROL Results] restituisce la risposta JSON per un’operazione riuscita. Per esempi, consulta [API REST](../../api/rest-api-main/rest-api-main.md) . Prima di immettere i dati, il foglio di lavoro di aggiornamento collettivo deve essere simile al seguente:

![](assets/update.png)

Se l&#39;aggiornamento collettivo restituisce un errore o non riesce, consulta [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
