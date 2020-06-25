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
ht-degree: 0%

---


# Creazione in blocco{#bulk-create}

La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con un&#39;unica operazione. Seguite queste istruzioni per effettuare una richiesta di creazione in blocco.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Non mescolare tipi di oggetto in una richiesta di creazione in blocco. Le intestazioni di ciascun oggetto sono univoche e non possono essere combinate. Cancellare il foglio di lavoro ed effettuare una richiesta separata per elementi diversi.

Per creare oggetti in blocco, aprire il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fate clic sulla **[!UICONTROL Headers]** scheda e copiate le intestazioni create per l’elemento da aggiungere.
2. Fate clic sulla **[!UICONTROL Create]** scheda.
3. Incolla le intestazioni create nella prima riga del foglio di lavoro di aggiornamento.
4. Incollate o digitate i dati da modificare in una colonna corrispondente in base all&#39;etichetta dell&#39;intestazione.
5. Nella barra degli strumenti del foglio di lavoro, fare clic sul pulsante Crea che corrisponde all’elemento da aggiornare.
Questa azione consente di aprire la [!UICONTROL Account Information] finestra di dialogo.
6. Fornite le informazioni [di](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) accesso richieste e fate clic su **[!UICONTROL Submit]**.

Il foglio di lavoro crea una [!UICONTROL Results] colonna. La [!UICONTROL Results] colonna restituisce la risposta JSON per un&#39;operazione riuscita. Per gli esempi, consultate [REST API](../../api/rest-api-main/rest-api-main.md) . Prima di immettere i dati, il foglio di lavoro creato in blocco deve essere simile al seguente esempio. Nota: qui non vengono visualizzate tutte le diverse opzioni di creazione. Questa opzione è inclusa per comprendere l&#39;aspetto di un foglio di lavoro completato.

![](assets/cretetraits.png)

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consulta Risoluzione dei [problemi relativi agli strumenti](../../reference/bulk-management-tools/bulk-troubleshooting.md)di gestione in blocco.
