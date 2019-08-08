---
description: Una destinazione di cookie restituisce e scrive dati in un cookie nel browser dell'utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Per creare una destinazione di cookie con [! UICONTROL Destination Builder].
seo-description: Una destinazione di cookie restituisce e scrive dati in un cookie nel browser dell'utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Per creare una destinazione di cookie con [! UICONTROL Destination Builder].
seo-title: Configurare una destinazione cookie
solution: Audience Manager
title: Configurare una destinazione cookie
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Configurare una destinazione cookie {#create-cookie-destination}

Una destinazione di cookie restituisce e scrive dati in un cookie nel browser dell'utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Per creare una destinazione di cookie con [!UICONTROL Destination Builder], effettuate le seguenti operazioni.

<!-- create-cookie-destination.xml -->

Per creare una nuova destinazione del cookie, accedete **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completate le sezioni come descritto di seguito.

## Informazioni di base {#basic-information}

Questa sezione contiene campi e opzioni che avviano il processo di creazione di destinazione del cookie. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Basic Information]** esporre i controlli.
2. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivete la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. Nell **[!UICONTROL Category]** 'elenco, scegliete **[!UICONTROL Custom]**.
5. Nell **[!UICONTROL Environment]** 'elenco, selezionate **[!UICONTROL Browser]**. Non è possibile configurare le destinazioni dei cookie per ambienti mobili nativi, ad esempio app Android o iOS.
6. Nell **[!UICONTROL Type]** 'elenco, fate clic **[!UICONTROL Cookie]** su.
7. *(Facoltativo)* Selezionate un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l'ID segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitata a 255 caratteri, massimo.
8. Fate clic per **[!UICONTROL Next]** passare alle [!UICONTROL Configuration] impostazioni o fare clic per **[!UICONTROL Data Export Labels]** applicare i controlli di esportazione alla destinazione.

## Etichette esportazione dati {#data-export-labels-cookies}

Questa sezione contiene le opzioni che applicano [i controlli di esportazione dei dati](../../features/data-export-controls.md) a una destinazione del cookie. Ignorate questo passaggio se non utilizzate i controlli di esportazione dei dati. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Data Export Labels]** esporre i controlli.
2. Selezionate un'etichetta che corrisponda al controllo sull'esportazione dei dati applicato alla destinazione (per ulteriori informazioni, consultate [Aggiungi etichette esportazione a una destinazione)](/help/using/features/destinations/add-data-export-labels.md) .
3. Fai clic su **[!UICONTROL Save]**.

## Configurazione {#configuration}

Questa sezione contiene campi e opzioni che consentono di impostare il cookie per la destinazione.

>[!NOTE]
>
>[!DNL Audience Manager] codifica i dati scritti nel cookie di destinazione. Ad esempio, gli spazi sono codificati e `%20` il punto e virgola è codificato come `%3B`.

Per completare questa sezione:

1. Fare clic per **[!UICONTROL Configuration]** esporre i controlli
1. Denominate il cookie. Evitare abbreviazioni e caratteri speciali.
1. Scegliere un'opzione di formato dati. Queste opzioni consentono di scegliere i delimitatori e i separatori per le coppie chiave-valore che inviano dati di segmento a una destinazione. Le opzioni di formattazione includono:
   * **Chiave singola:** Consente di impostare la chiave in una coppia chiave-valore. Il valore viene impostato dopo aver selezionato un segmento nella [!UICONTROL Segment Mappings] sezione di seguito.
   * **Chiave multipla:** Consente di impostare la chiave e il valore per una coppia chiave-valore. La coppia chiave-valore viene creata dopo aver selezionato un segmento nella sezione Mappature segmenti di seguito.
Per ulteriori informazioni su questi elementi di dati, vedi [Standard e chiave chiave chiave-valore.](../../features/destinations/key-value-pairs.md)
1. Fai clic su **[!UICONTROL Save]**.

Tutte le altre impostazioni sono facoltative. Per ulteriori informazioni sulle impostazioni **[!UICONTROL Cookie Domain]** e **[!UICONTROL Publish data to]** sulle impostazioni, consultate [Impostazioni facoltative per destinazioni cookie](/help/using/features/destinations/cookie-destination-options.md).

## Mappature segmento {#segments-mapping}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Segment Mappings]** esporre i controlli.
1. Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic su per **[!UICONTROL Browse All Segments]** sfogliare un elenco dei segmenti disponibili.
1. Fai clic **[!UICONTROL Add Selected Segments]** su quando trovi il segmento da utilizzare. L'aggiunta di un segmento apre la [!UICONTROL Edit Mapping] finestra.
1. Nella [!UICONTROL Edit Mapping] finestra di dialogo:
   * **[!UICONTROL Mapping]** consente di impostare un valore per la chiave specificata nella sezione Configurazione di cui sopra.
   * **[!UICONTROL Publish from]** consente di impostare la data di inizio e di fine della destinazione. Se la data di fine è vuota, la destinazione non scade.
1. Fai clic su **[!UICONTROL Save]**.
1. Fai clic su **[!UICONTROL Done]**.