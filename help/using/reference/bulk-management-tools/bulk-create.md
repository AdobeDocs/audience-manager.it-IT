---
description: La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con un'unica operazione. Seguite queste istruzioni per effettuare una richiesta di creazione in blocco.
seo-description: La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con un'unica operazione. Seguite queste istruzioni per effettuare una richiesta di creazione in blocco.
seo-title: Creazione in blocco
solution: Audience Manager
title: Creazione in blocco
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Creazione in blocco{#bulk-create}

La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con un'unica operazione. Seguite queste istruzioni per effettuare una richiesta di creazione in blocco.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>Le [!UICONTROL Bulk Management Tools] opzioni non *sono supportate da* [!DNL Audience Manager]. Questo strumento è fornito per comodità e solo come cortesia. Per modifiche di massa, consigliamo di lavorare con le API [](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Non mescolare tipi di oggetto in una richiesta di creazione in blocco. Le intestazioni di ciascun oggetto sono univoche e non possono essere combinate. Cancellare il foglio di lavoro ed effettuare una richiesta separata per elementi diversi.

Per creare oggetti in blocco, aprire il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fate clic sulla **[!UICONTROL Headers]** scheda e copiate le intestazioni create per l’elemento da aggiungere.
1. Click the **[!UICONTROL Create]** tab.
1. Incolla le intestazioni create nella prima riga del foglio di lavoro di aggiornamento.
1. Incollate o digitate i dati da modificare in una colonna corrispondente in base all'etichetta dell'intestazione.
1. Nella barra degli strumenti del foglio di lavoro, fare clic sul pulsante Crea che corrisponde all’elemento da aggiornare.
Questa azione consente di aprire la [!UICONTROL Account Information] finestra di dialogo.

1. Fornite le informazioni [di](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) accesso richieste e fate clic su **[!UICONTROL Submit]**.

Il foglio di lavoro crea una [!UICONTROL Results] colonna. La [!UICONTROL Results] colonna restituisce la risposta JSON per un'operazione riuscita. Per gli esempi, consultate [REST API](../../api/rest-api-main/rest-api-main.md) . Prima di immettere i dati, il foglio di lavoro creato in blocco deve essere simile al seguente esempio. Nota: qui non vengono visualizzate tutte le diverse opzioni di creazione. Questa opzione è inclusa per comprendere l'aspetto di un foglio di lavoro completato.

![](assets/cretetraits.png)

Se l'aggiornamento in blocco restituisce un errore o non riesce, consultate Risoluzione dei [problemi relativi agli strumenti](../../reference/bulk-management-tools/bulk-troubleshooting.md)di gestione in blocco.
