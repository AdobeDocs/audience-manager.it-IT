---
description: La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con una singola operazione. Segui queste istruzioni per effettuare una richiesta di creazione in blocco.
seo-description: La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con una singola operazione. Segui queste istruzioni per effettuare una richiesta di creazione in blocco.
seo-title: Creazione in blocco
solution: Audience Manager
title: Creazione in blocco
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Creazione in blocco{#bulk-create}

La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con una singola operazione. Segui queste istruzioni per effettuare una richiesta di creazione in blocco.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate in  [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Non combinare tipi di oggetti in una richiesta di creazione in blocco. Le intestazioni di ciascun oggetto sono univoche e non possono essere combinate. Cancella il foglio di lavoro ed effettua una richiesta separata per elementi diversi.

Per creare oggetti in blocco, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fai clic sulla scheda **[!UICONTROL Headers]** e copia le intestazioni create per l’elemento che desideri aggiungere.
2. Fai clic sulla scheda **[!UICONTROL Create]** .
3. Incolla le intestazioni create nella prima riga del foglio di lavoro di aggiornamento.
4. Incolla o digita i dati da modificare in una colonna corrispondente in base all’etichetta dell’intestazione.
5. Nella barra degli strumenti del foglio di lavoro, fare clic sul pulsante crea corrispondente all&#39;elemento che si sta aggiornando.
Questa azione apre la finestra di dialogo [!UICONTROL Account Information] .
6. Fornisci le [informazioni di accesso ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) richieste e fai clic su **[!UICONTROL Submit]**.

Il foglio di lavoro crea una colonna [!UICONTROL Results]. La colonna [!UICONTROL Results] restituisce la risposta JSON per un’operazione riuscita. Per esempi, consulta [API REST](../../api/rest-api-main/rest-api-main.md) . Prima di immettere i dati, il foglio di lavoro creato in blocco deve essere simile all&#39;esempio seguente. In questo caso non vengono visualizzate tutte le diverse opzioni di creazione. Questa funzionalità è inclusa per comprendere l&#39;aspetto di un foglio di lavoro completato.

![](assets/cretetraits.png)

Se l&#39;aggiornamento collettivo restituisce un errore o non riesce, consulta [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
