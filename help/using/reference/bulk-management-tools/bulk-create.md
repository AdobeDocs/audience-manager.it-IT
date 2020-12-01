---
description: La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con un'unica operazione. Seguite queste istruzioni per effettuare una richiesta di creazione in blocco.
seo-description: La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con un'unica operazione. Seguite queste istruzioni per effettuare una richiesta di creazione in blocco.
seo-title: Creazione in blocco
solution: Audience Manager
title: Creazione in blocco
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 2%

---


# Creazione in blocco{#bulk-create}

La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con un&#39;unica operazione. Seguite queste istruzioni per effettuare una richiesta di creazione in blocco.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella  [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Non mescolare tipi di oggetto in una richiesta di creazione in blocco. Le intestazioni di ciascun oggetto sono univoche e non possono essere combinate. Cancellare il foglio di lavoro ed effettuare una richiesta separata per elementi diversi.

Per creare oggetti in blocco, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Headers]** e copiare le intestazioni di creazione per l&#39;elemento da aggiungere.
2. Fare clic sulla scheda **[!UICONTROL Create]**.
3. Incolla le intestazioni create nella prima riga del foglio di lavoro di aggiornamento.
4. Incollate o digitate i dati da modificare in una colonna corrispondente in base all&#39;etichetta dell&#39;intestazione.
5. Nella barra degli strumenti del foglio di lavoro, fare clic sul pulsante Crea che corrisponde all’elemento da aggiornare.
Questa azione apre la finestra di dialogo [!UICONTROL Account Information].
6. Specificare le informazioni di accesso [necessarie](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fare clic su **[!UICONTROL Submit]**.

Il foglio di lavoro crea una colonna [!UICONTROL Results]. La colonna [!UICONTROL Results] restituisce la risposta JSON per un&#39;operazione riuscita. Per gli esempi, vedere [REST APIs](../../api/rest-api-main/rest-api-main.md). Prima di immettere i dati, il foglio di lavoro creato in blocco deve essere simile al seguente esempio. Nota: qui non vengono visualizzate tutte le diverse opzioni di creazione. Questa opzione è inclusa per comprendere l&#39;aspetto di un foglio di lavoro completato.

![](assets/cretetraits.png)

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, vedere [Risoluzione dei problemi per gli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
