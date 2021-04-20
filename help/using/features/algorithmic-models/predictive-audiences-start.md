---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-title: Gestione di Predictive Audiences
solution: Audience Manager
title: Guida introduttiva di Predictive Audiences
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 7%

---

# Guida introduttiva di Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

## Creare un modello di Predictive Audiences {#create-predictive-audiences}

Prima di creare un modello [!UICONTROL Predictive Audiences], è necessario decidere a quale origine dati assegnare le caratteristiche e i segmenti [!UICONTROL Predictive Audiences]. È possibile utilizzare un’origine dati di prime parti esistente o crearne una nuova. Per informazioni dettagliate su come creare una nuova origine dati di prime parti, consulta [Gestisci origini dati](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) .

Una volta che sai quale origine dati utilizzerai, segui i passaggi seguenti.

1. Vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Nella sezione [!UICONTROL Predictive Audiences], fai clic su **[!UICONTROL Add New]**.

   ![smart-tipo-add](assets/predictive-audiences-add.png)

1. Quindi, definisci gli utenti tipo per i quali vuoi classificare il pubblico. Puoi farlo scegliendo caratteristiche o segmenti da cui creare i tuoi utenti. Utilizza le schede [!UICONTROL Traits] e [!UICONTROL Segments] nell’angolo in alto a sinistra dello schermo per passare dal catalogo delle caratteristiche a quello dei segmenti. Dopo aver identificato le caratteristiche o i segmenti che desideri utilizzare come utenti tipo, fai clic sull’icona corrispondente **[!UICONTROL Add]** nella colonna [!UICONTROL Action] .
   ![smart-tipo-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Devi scegliere almeno due caratteristiche o due segmenti per i tuoi utenti tipo linea di base. Non puoi utilizzare una combinazione di caratteristiche e segmenti.
1. Fai clic su **[!UICONTROL Next]** dopo aver definito i tuoi utenti tipo.
1. Quindi, seleziona il pubblico di prime parti che desideri classificare scegliendo una caratteristica o un segmento di prime parti per questo pubblico. Utilizza le schede [!UICONTROL Traits] e [!UICONTROL Segments] nell’angolo in alto a sinistra dello schermo per passare dal catalogo delle caratteristiche e dei segmenti al catalogo. Seleziona la caratteristica o il segmento di prima parte che desideri utilizzare come pubblico, per aggiungerlo al modello.
   ![smart-tipo-select-audience](assets/predictive-audiences-audience.png)
1. Fai clic su **[!UICONTROL Next]** dopo aver scelto il pubblico.
1. Compila i dettagli del modello:
   * **[!UICONTROL Model Name]**: Inserisci un nome descrittivo per il modello, che ti aiuterà a identificarlo in un secondo momento. I nomi dei segmenti generati dal modello iniziano con il nome del modello.
   * **[!UICONTROL Description]**: Immetti una descrizione del modello che ti aiuterà a identificare il relativo caso d’uso.
   * **[!UICONTROL Data Source]**: Seleziona l’origine dati di prime parti a cui assegnare i  [!UICONTROL Predictive Audiences] segmenti di questo modello.
   * **[!UICONTROL Profile Merge Rule]**: Seleziona il  [!UICONTROL Profile Merge Rule] da assegnare a tutti i predittivi  [!UICONTROL segments] creati da questo modello. Se il pubblico di destinazione selezionato è un [!UICONTROL segment], è consigliabile selezionare lo stesso [!UICONTROL Profile Merge Rule] del pubblico di destinazione.
      ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. Clic **[!UICONTROL Save]**.

## Clonazione e modifica di modelli di audience predittivi {#clone-predictive-audiences}

Audience Manager non supporta la modifica di modelli [!UICONTROL Predictive Audiences] esistenti. Per modificare la configurazione di un modello, potete creare un clone di un modello esistente e modificarlo. Ecco come eseguire questa operazione:

1. Vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Fare clic sul nome del modello [!UICONTROL Predictive Audiences] da clonare.
3. Fai clic sul pulsante **[!UICONTROL Clone]** in alto a sinistra dello schermo.
   ![clone-audience-predittive](assets/predictive-audiences-clone.png)
4. Una volta clonato il modello, si passa alla pagina [!DNL Save & Configure] del modello clonato. In questa pagina, è possibile modificare il [!UICONTROL data source] e il valore assegnato[!UICONTROL Profile Merge Rule] del modello. Per modificare gli utenti tipo e il pubblico di destinazione del modello clonato, utilizza i pulsanti [!UICONTROL Back] e [!UICONTROL Next] per spostarsi tra le tre schede oppure fai clic sui tre nomi delle schede

   ![predictive-audiences-clone-navigences](assets/predictive-audiences-clone-navigate.png)

5. Al termine della modifica di un modello, fai clic su **[!UICONTROL Save]**.

## Eliminazione di Predictive Audiences {#delete-predictive-audiences}

Per eliminare un modello [!UICONTROL Predictive Audiences], vai a **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, trova il modello da eliminare e fai clic sull&#39;icona **[!UICONTROL Delete]** .
