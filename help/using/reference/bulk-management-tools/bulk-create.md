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


# Crea in blocco{#bulk-create}

La creazione in massa consente di creare più origini dati, segnali derivati, segmenti, caratteristiche e altri elementi con una singola operazione. Per effettuare una richiesta di creazione in massa, effettuate le seguenti operazioni.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>Non [!UICONTROL Bulk Management Tools]*sono* supportati da [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. Per modifiche in massa, consigliamo di lavorare con [le API](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell&#39; [!DNL Audience Manager] interfaccia utente vengono rispettate nell&#39; [!UICONTROL Bulk Management Tools]interfaccia.

>[!CAUTION]
>
>Non combinate tipi di oggetti in una richiesta di creazione in massa. Le intestazioni di ciascun oggetto sono univoche e non possono essere combinate. Cancella il foglio di lavoro e richiedi una richiesta separata per elementi diversi.

Per creare oggetti in gruppo, aprite il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fare clic sulla **[!UICONTROL Headers]** scheda e copiare le intestazioni create per l&#39;elemento da aggiungere.
1. Fare clic sulla **[!UICONTROL Create]** scheda.
1. Incolla le intestazioni create nella prima riga del foglio di lavoro di aggiornamento.
1. Incolla o digita i dati da modificare in una colonna corrispondente basata sull&#39;etichetta dell&#39;intestazione.
1. Nella barra degli strumenti del foglio di lavoro, fate clic sul pulsante Crea corrispondente all&#39;elemento che state aggiornando.
Questa azione apre la [!UICONTROL Account Information] finestra di dialogo.

1. Fornite le informazioni [richieste](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fate clic **[!UICONTROL Submit]** su.

Il foglio di lavoro crea una [!UICONTROL Results] colonna. La [!UICONTROL Results] colonna restituisce la risposta JSON per un&#39;operazione di successo. Per [esempi, consultate](../../api/rest-api-main/rest-api-main.md) API REST. Prima di inserire i dati, il foglio di lavoro di creazione in massa deve essere simile all&#39;esempio seguente. Non vengono visualizzate tutte le opzioni di creazione. Questa funzione è utile per comprendere l&#39;aspetto di un foglio di lavoro completato.

![](assets/cretetraits.png)

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consultate [Risoluzione dei problemi per strumenti di gestione collettiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
