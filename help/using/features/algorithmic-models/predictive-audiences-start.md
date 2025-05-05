---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: Guida introduttiva di Predictive Audiences
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 2%

---

# Guida introduttiva di Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

## Creare un modello Predictive Audiences {#create-predictive-audiences}

Prima di creare un modello [!UICONTROL Predictive Audiences], è necessario decidere a quale origine dati di prime parti assegnare le caratteristiche e i segmenti di [!UICONTROL Predictive Audiences]. È possibile utilizzare un&#39;origine dati di prime parti esistente o crearne una nuova. Consulta [Gestisci origini dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) per informazioni dettagliate su come creare una nuova origine dati di prime parti.

Una volta individuata l’origine dati da utilizzare, effettua le seguenti operazioni.

1. Vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Nella sezione [!UICONTROL Predictive Audiences], fare clic su **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Quindi, definisci gli utenti tipo in base ai quali classificare il pubblico. Per farlo, puoi scegliere caratteristiche o segmenti da cui creare gli utenti tipo. Utilizza le schede [!UICONTROL Traits] e [!UICONTROL Segments] nell&#39;angolo superiore sinistro dello schermo per passare dal catalogo delle caratteristiche a quello dei segmenti. Dopo aver identificato le caratteristiche o i segmenti che desideri utilizzare come utenti tipo, fai clic sull&#39;icona **[!UICONTROL Add]** corrispondente nella colonna [!UICONTROL Action].
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Devi scegliere almeno due caratteristiche o due segmenti per gli utenti tipo di linea di base. Non puoi utilizzare una combinazione di caratteristiche e segmenti.
1. Fai clic su **[!UICONTROL Next]** dopo aver definito i tuoi utenti tipo.
1. Quindi, seleziona il pubblico di prime parti che desideri classificare scegliendo una caratteristica o un segmento di prime parti per questo pubblico. Utilizza le schede [!UICONTROL Traits] e [!UICONTROL Segments] nell&#39;angolo superiore sinistro dello schermo per passare dal catalogo delle caratteristiche a quello dei segmenti. Per aggiungerlo al modello, seleziona la caratteristica o il segmento di prime parti che desideri utilizzare come pubblico.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. Fai clic su **[!UICONTROL Next]** dopo aver scelto il pubblico.
1. Compila i dettagli del modello:
   * **[!UICONTROL Model Name]**: immettere un nome descrittivo per il modello, che consentirà di identificarlo in seguito. I nomi dei segmenti generati dal modello iniziano con il nome del modello.
   * **[!UICONTROL Description]**: immettere una descrizione del modello che consenta di identificarne il caso d&#39;uso.
   * **[!UICONTROL Data Source]**: selezionare l&#39;origine dati di prime parti a cui si desidera assegnare i segmenti [!UICONTROL Predictive Audiences] di questo modello.
   * **[!UICONTROL Profile Merge Rule]**: selezionare [!UICONTROL Profile Merge Rule] da assegnare per tutti i [!UICONTROL segments] predittivi creati da questo modello. Se il pubblico di destinazione selezionato è un [!UICONTROL segment], si consiglia di selezionare lo stesso [!UICONTROL Profile Merge Rule] del pubblico di destinazione.

     ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. Fare clic su **[!UICONTROL Save]**.

## Clonazione e modifica di modelli di audience predittivi {#clone-predictive-audiences}

L&#39;Audience Manager non supporta la modifica dei modelli [!UICONTROL Predictive Audiences] esistenti. Per modificare la configurazione di un modello, potete creare un clone di un modello esistente e modificarlo. Ecco come eseguire questa operazione:

1. Vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Fare clic sul nome del modello [!UICONTROL Predictive Audiences] da clonare.
3. Fare clic sul pulsante **[!UICONTROL Clone]** in alto a sinistra nella schermata.
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. Dopo aver clonato il modello, si passa alla pagina [!DNL Save & Configure] del modello clonato. In questa pagina è possibile modificare [!UICONTROL data source] e l&#39;assegnato[!UICONTROL Profile Merge Rule] del modello. Per modificare gli utenti tipo e il pubblico di destinazione del modello clonato, utilizzare i pulsanti [!UICONTROL Back] e [!UICONTROL Next] per spostarsi tra le tre schede oppure fare clic sui tre nomi di scheda

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. Dopo aver modificato un modello, fare clic su **[!UICONTROL Save]**.

## Eliminazione dei Predictive Audiences {#delete-predictive-audiences}

Per eliminare un modello [!UICONTROL Predictive Audiences], passare a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, trovare il modello che si desidera eliminare e fare clic sull&#39;icona **[!UICONTROL Delete]**.
