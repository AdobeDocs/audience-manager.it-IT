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

Per creare una nuova destinazione di cookie, andate a **[!UICONTROL Audience Data > Destinations > Create New Destination]** completare le sezioni come descritto di seguito.

## Informazioni di base {#basic-information}

Questa sezione contiene campi e opzioni che avviano il processo di creazione della destinazione del cookie. Per completare questa sezione:

1. Fare clic **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivere la destinazione. Una descrizione sintetica è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. Nell’ **[!UICONTROL Category]** elenco, scegliete **[!UICONTROL Custom]**.
5. Nell&#39; **[!UICONTROL Environment]** elenco, selezionare **[!UICONTROL Browser]**. Non potete configurare le destinazioni dei cookie per gli ambienti mobili nativi, ad esempio le app Android o iOS.
6. Nell&#39; **[!UICONTROL Type]** elenco, fare clic su **[!UICONTROL Cookie]**.
7. *(Facoltativo)* Selezionate un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l’ID del segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri, al massimo.
8. Fate clic **[!UICONTROL Next]** per passare alle [!UICONTROL Configuration] impostazioni oppure fate clic **[!UICONTROL Data Export Labels]** per applicare i controlli di esportazione alla destinazione.

## Etichette esportazione dati {#data-export-labels-cookies}

Questa sezione contiene opzioni che applicano controlli [di esportazione](../../features/data-export-controls.md) dati a una destinazione di cookie. Salta questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Fare clic **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Selezionare un&#39;etichetta che corrisponde al controllo di esportazione dei dati applicato alla destinazione (per informazioni dettagliate, vedere [Aggiungi etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md) ).
3. Clic **[!UICONTROL Save]**.

## Configurazione {#configuration}

Questa sezione contiene campi e opzioni che consentono di impostare il cookie per la destinazione.

>[!NOTE]
>
>[!DNL Audience Manager] codifica i dati scritti nel cookie di destinazione. Ad esempio, gli spazi sono codificati come `%20` e i punti e virgola come `%3B`.

Per completare questa sezione:

1. Fare clic **[!UICONTROL Configuration]** per esporre i controlli
1. Denominate il cookie. Evitare abbreviazioni e caratteri speciali.
1. Scegliete un’opzione per il formato dei dati. Queste opzioni consentono di scegliere i delimitatori e i separatori per le coppie chiave-valore che inviano i dati del segmento a una destinazione. Le opzioni di formato includono:
   * **Chiave singola:** Consente di impostare la chiave in una coppia chiave-valore. Il valore verrà impostato dopo aver selezionato un segmento nella [!UICONTROL Segment Mappings] sezione seguente.
   * **Più chiavi:** Consente di impostare la chiave e il valore per una coppia chiave-valore. Dopo aver selezionato un segmento nella sezione Mappature segmenti, creerai la coppia chiave-valore qui sotto.
Per ulteriori informazioni su questi elementi di dati, vedere Coppie chiave-valore [](../../features/destinations/key-value-pairs.md) standard e seriale.
1. Clic **[!UICONTROL Save]**.

Tutte le altre impostazioni sono facoltative. Per ulteriori informazioni sulle **[!UICONTROL Cookie Domain]** impostazioni e sulle **[!UICONTROL Publish data to]** impostazioni, vedi Impostazioni [facoltative per le destinazioni](/help/using/features/destinations/cookie-destination-options.md)dei cookie.

## Mappature dei segmenti {#segments-mapping}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fare clic **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** per sfogliare un elenco di segmenti disponibili.
1. Fate clic **[!UICONTROL Add Selected Segments]** quando trovate il segmento da usare. Aggiungendo un segmento si apre la [!UICONTROL Edit Mapping] finestra.
1. Nella [!UICONTROL Edit Mapping] finestra di dialogo:
   * **[!UICONTROL Mapping]** consente di impostare un valore per la chiave specificata nella sezione Configurazione precedente.
   * **[!UICONTROL Publish from]** consente di impostare la data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade mai.
1. Clic **[!UICONTROL Save]**.
1. Clic **[!UICONTROL Done]**.