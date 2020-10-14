---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-title: Gestione dell'audience predittiva
solution: Audience Manager
title: Predictive Audiences di Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 48bf17a2899fd06c525ba6b4fddb9ec805efb5c3
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 7%

---


# Guida introduttiva di Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

## Creare un modello di pubblico predittivo {#create-predictive-audiences}

Prima di creare un [!UICONTROL Predictive Audiences] modello, è necessario stabilire a quale origine dati di prime parti si desidera assegnare [!UICONTROL Predictive Audiences] caratteristiche e segmenti. È possibile utilizzare un&#39;origine dati di prime parti esistente o crearne una nuova. Consulta [Gestione origini](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) dati per informazioni dettagliate su come creare una nuova origine dati di prime parti.

Una volta ottenuta l&#39;origine dati da utilizzare, segui i passaggi descritti di seguito.

1. Vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Nella [!UICONTROL Predictive Audiences] sezione fare clic su **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Quindi, definite le persone per le quali desiderate classificare il pubblico. A tal fine, puoi scegliere caratteristiche o segmenti da cui creare le persone. Utilizzate le schede [!UICONTROL Traits] e nell&#39; [!UICONTROL Segments] angolo superiore sinistro dello schermo per passare dal catalogo delle caratteristiche a quello dei segmenti e viceversa. Dopo aver identificato le caratteristiche o i segmenti che si desidera utilizzare come personaggi, fai clic sull’ **[!UICONTROL Add]** icona corrispondente nella [!UICONTROL Action] colonna.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Devi scegliere almeno due caratteristiche o due segmenti per le tue figure di base. Non è possibile utilizzare una combinazione di caratteristiche e segmenti.
1. Fai clic **[!UICONTROL Next]** dopo aver definito le tue personalità.
1. Quindi, selezionate il pubblico di prime parti che desiderate classificare scegliendo una caratteristica o un segmento di prime parti per questo pubblico. Utilizzate le schede [!UICONTROL Traits] e nell&#39; [!UICONTROL Segments] angolo superiore sinistro dello schermo per passare dal catalogo delle caratteristiche e dei segmenti al catalogo. Selezionate la caratteristica o il segmento di prime parti che desiderate utilizzare come pubblico, per aggiungerlo al modello.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. Fate clic **[!UICONTROL Next]** dopo aver selezionato il pubblico.
1. Compila i dettagli del modello:
   * **[!UICONTROL Model Name]**: Inserite un nome descrittivo per il modello, che vi aiuterà a identificarlo in un secondo momento. I nomi dei segmenti generati dal modello inizieranno con il nome del modello.
   * **[!UICONTROL Description]**: Inserire una descrizione del modello che consenta di identificare il relativo caso di utilizzo.
   * **[!UICONTROL Data Source]**: Selezionare l&#39;origine dati di prime parti a cui si desidera assegnare i [!UICONTROL Predictive Audiences] segmenti di questo modello.
   * **[!UICONTROL Profile Merge Rule]**: Selezionare l&#39;opzione [!UICONTROL Profile Merge Rule] da assegnare a tutti i predittivi [!UICONTROL segments] creati da questo modello. Se il pubblico di destinazione selezionato è un [!UICONTROL segment], si consiglia di selezionare lo stesso [!UICONTROL Profile Merge Rule] del pubblico di destinazione.
      ![predictive-audience-save](assets/predictive-audiences-save.png)
1. Clic **[!UICONTROL Save]**.

## Clonazione e modifica di modelli di audience predittivi {#clone-predictive-audiences}

 Audience Manager non supporta la modifica di [!UICONTROL Predictive Audiences] modelli esistenti. Per modificare la configurazione di un modello, è possibile creare un clone di un modello esistente e modificarlo. È possibile effettuare le seguenti operazioni:

1. Vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Fare clic sul nome del [!UICONTROL Predictive Audiences] modello da clonare.
3. Fate clic sul **[!UICONTROL Clone]** pulsante in alto a sinistra nella schermata.
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. Una volta clonato il modello, si viene portati alla [!DNL Save & Configure] pagina del modello clonato. In questa pagina, è possibile modificare il modello [!UICONTROL data source] e l&#39;assegnazione[!UICONTROL Profile Merge Rule] . Per modificare le persone e il pubblico di destinazione del modello clonato, utilizzare i [!UICONTROL Back] pulsanti e [!UICONTROL Next] per spostarsi tra le tre schede, oppure fare clic sui tre nomi delle schede

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. Dopo aver modificato un modello, fare clic su **[!UICONTROL Save]**.

## Eliminazione di audience predittive {#delete-predictive-audiences}

Per eliminare un [!UICONTROL Predictive Audiences] modello, passare a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, individuare il modello da eliminare e fare clic sull&#39; **[!UICONTROL Delete]** icona.
