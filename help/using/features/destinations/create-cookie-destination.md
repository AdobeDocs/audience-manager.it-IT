---
description: Una destinazione di cookie restituisce e scrive i dati in un cookie nel browser dell'utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Seguite queste istruzioni per creare una destinazione di cookie con [!UICONTROL Destination Builder].
seo-description: Una destinazione di cookie restituisce e scrive i dati in un cookie nel browser dell'utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Seguite queste istruzioni per creare una destinazione di cookie con [!UICONTROL Destination Builder].
seo-title: Configurare una destinazione cookie
solution: Audience Manager
title: Configurare una destinazione cookie
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 3%

---


# Configurare una destinazione cookie {#create-cookie-destination}

Una destinazione di cookie restituisce e scrive i dati in un cookie nel browser dell&#39;utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Seguite queste istruzioni per creare una destinazione di cookie con [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Per creare una nuova destinazione di cookie, andate a **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completate le sezioni come descritto di seguito.

## Informazioni di base {#basic-information}

Questa sezione contiene campi e opzioni che avviano il processo di creazione della destinazione del cookie. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivere la destinazione. Una descrizione sintetica è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. Nell&#39;elenco **[!UICONTROL Category]**, scegliere **[!UICONTROL Custom]**.
5. Nell&#39;elenco **[!UICONTROL Environment]**, selezionare **[!UICONTROL Browser]**. Non potete configurare le destinazioni dei cookie per gli ambienti mobili nativi, ad esempio le app Android o iOS.
6. Nell&#39;elenco **[!UICONTROL Type]**, fare clic su **[!UICONTROL Cookie]**.
7. *(Facoltativo)* Selezionate un  **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l’ID del segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri, al massimo.
8. Fare clic su **[!UICONTROL Next]** per passare alle impostazioni [!UICONTROL Configuration] oppure su **[!UICONTROL Data Export Labels]** per applicare i controlli di esportazione alla destinazione.

## Etichette esportazione dati {#data-export-labels-cookies}

Questa sezione contiene opzioni che applicano i controlli di esportazione [dei dati](../../features/data-export-controls.md) a una destinazione di cookie. Salta questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Selezionare un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (per ulteriori informazioni, vedere [Aggiungi etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md)).
3. Clic **[!UICONTROL Save]**.

## Configurazione {#configuration}

Questa sezione contiene campi e opzioni che consentono di impostare il cookie per la destinazione.

>[!NOTE]
>
>[!DNL Audience Manager] codifica i dati scritti nel cookie di destinazione. Ad esempio, gli spazi sono codificati come `%20` e i punti e virgola come `%3B`.

Per completare questa sezione:

1. Fare clic su **[!UICONTROL Configuration]** per esporre i controlli
1. Denominate il cookie. Evitare abbreviazioni e caratteri speciali.
1. Scegliete un’opzione per il formato dei dati. Queste opzioni consentono di scegliere i delimitatori e i separatori per le coppie chiave-valore che inviano i dati del segmento a una destinazione. Le opzioni di formato includono:
   * **Tasto singolo:** consente di impostare la chiave in una coppia chiave-valore. Il valore verrà impostato dopo aver selezionato un segmento nella sezione [!UICONTROL Segment Mappings] seguente.
   * **Multi-key:** consente di impostare la chiave e il valore per una coppia chiave-valore. Dopo aver selezionato un segmento nella sezione Mappature segmenti, creerai la coppia chiave-valore qui sotto.
Per ulteriori informazioni su questi elementi, vedere [Coppie chiave-valore standard e seriale](../../features/destinations/key-value-pairs.md).
1. Clic **[!UICONTROL Save]**.

Tutte le altre impostazioni sono facoltative. Per ulteriori informazioni sulle impostazioni **[!UICONTROL Cookie Domain]** e **[!UICONTROL Publish data to]**, vedere [Impostazioni facoltative per le destinazioni dei cookie](/help/using/features/destinations/cookie-destination-options.md).

## Mappature segmento {#segments-mapping}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. Nella casella **[!UICONTROL Search and Add Segments]**, inizia a digitare il nome di un segmento oppure fai clic su **[!UICONTROL Browse All Segments]** per sfogliare un elenco di segmenti disponibili.
1. Fare clic su **[!UICONTROL Add Selected Segments]** quando si trova il segmento da utilizzare. Aggiungendo un segmento si apre la finestra [!UICONTROL Edit Mapping].
1. Nella finestra di dialogo [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mapping]** consente di impostare un valore per la chiave specificata nella sezione Configurazione precedente.
   * **[!UICONTROL Publish from]** consente di impostare la data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade mai.
1. Clic **[!UICONTROL Save]**.
1. Clic **[!UICONTROL Done]**.