---
description: La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con una singola operazione. Segui queste istruzioni per effettuare una richiesta di creazione in blocco.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Creazione in blocco
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Creazione in blocco{#bulk-create}

La creazione in blocco consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con una singola operazione. Segui queste istruzioni per effettuare una richiesta di creazione in blocco.

>[!IMPORTANT]
>
>Gli strumenti di gestione in blocco non sono un’offerta di Adobe ufficialmente supportata. La risoluzione dei problemi e il supporto tramite l’Assistenza clienti verranno gestiti caso per caso.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Le autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnate nell&#39;interfaccia utente [!DNL Audience Manager] vengono rispettate in [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Non combinare tipi di oggetto in una richiesta di creazione in blocco. Le intestazioni di ciascun oggetto sono univoche e non possono essere combinate. Cancellare il foglio di lavoro e effettuare una richiesta separata per i diversi elementi.

Per creare oggetti in blocco, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Headers]** e copiare le intestazioni di creazione per l&#39;elemento che si desidera aggiungere.
2. Fare clic sulla scheda **[!UICONTROL Create]**.
3. Incollare le intestazioni create nella prima riga del foglio di lavoro di aggiornamento.
4. Incolla o digita i dati che desideri modificare in una colonna corrispondente in base all’etichetta dell’intestazione.
5. Nella barra degli strumenti del foglio di lavoro fare clic sul pulsante Crea corrispondente all&#39;elemento che si sta aggiornando.
Questa azione apre la finestra di dialogo [!UICONTROL Account Information].
6. Fornisci le [informazioni di accesso](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) richieste e fai clic su **[!UICONTROL Submit]**.

Il foglio di lavoro crea una colonna [!UICONTROL Results]. La colonna [!UICONTROL Results] restituisce la risposta JSON per un&#39;operazione riuscita. Per esempi, consulta le [API REST](../../api/rest-api-main/rest-api-main.md). Prima di immettere i dati, il foglio di lavoro per la creazione in blocco deve avere un aspetto simile a quello dell&#39;esempio seguente. Non tutte le diverse opzioni di creazione sono visualizzate qui. Questo è incluso per aiutarti a capire come potrebbe essere un foglio di lavoro completato.

![](assets/cretetraits.png)

Se l&#39;aggiornamento in blocco restituisce un errore o non riesce, vedere [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
