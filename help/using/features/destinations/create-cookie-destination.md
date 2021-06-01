---
description: Una destinazione cookie restituisce e scrive i dati in un cookie nel browser dell'utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Segui queste istruzioni per creare una destinazione cookie con [!UICONTROL Destination Builder].
seo-description: Una destinazione cookie restituisce e scrive i dati in un cookie nel browser dell'utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Segui queste istruzioni per creare una destinazione cookie con [!UICONTROL Destination Builder].
seo-title: Configurare una destinazione cookie
solution: Audience Manager
title: Configurare una destinazione cookie
feature: Nozioni di base sulle destinazioni
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 3%

---

# Configurare una destinazione cookie {#create-cookie-destination}

Una destinazione cookie restituisce e scrive i dati in un cookie nel browser dell&#39;utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Segui queste istruzioni per creare una destinazione cookie con [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Per creare una nuova destinazione cookie, vai su **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completa le sezioni come descritto di seguito.

## Informazioni di base {#basic-information}

Questa sezione contiene campi e opzioni che avviano il processo di creazione della destinazione dei cookie. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denomina la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivi la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. Nell’elenco **[!UICONTROL Category]**, scegli **[!UICONTROL Custom]**.
5. Nell’elenco **[!UICONTROL Environment]**, selezionare **[!UICONTROL Browser]**. Non è possibile configurare le destinazioni dei cookie per gli ambienti mobile nativi, ad esempio le app Android o iOS.
6. Nell’elenco **[!UICONTROL Type]**, fai clic su **[!UICONTROL Cookie]**.
7. *(Facoltativo)* Seleziona un  **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l’ID del segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri, massimo.
8. Fai clic su **[!UICONTROL Next]** per passare alle impostazioni [!UICONTROL Configuration] oppure fai clic su **[!UICONTROL Data Export Labels]** per applicare i controlli di esportazione alla destinazione.

## Etichette esportazione dati {#data-export-labels-cookies}

Questa sezione contiene opzioni che applicano [controlli di esportazione dati](../../features/data-export-controls.md) a una destinazione cookie. Ignora questo passaggio se non utilizzi i controlli di esportazione dati. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Seleziona un&#39;etichetta che corrisponde al controllo dell&#39;esportazione dei dati applicato alla destinazione (consulta [Aggiungi etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md) per ulteriori informazioni).
3. Clic **[!UICONTROL Save]**.

## Configurazione {#configuration}

Questa sezione contiene campi e opzioni che consentono di impostare il cookie per la destinazione.

>[!NOTE]
>
>[!DNL Audience Manager] codifica i dati scritti nel cookie di destinazione. Ad esempio, gli spazi vengono codificati come `%20` e i punti e virgola come `%3B`.

Per completare questa sezione:

1. Fare clic su **[!UICONTROL Configuration]** per esporre i controlli
1. Denomina il cookie. Evitare abbreviazioni e caratteri speciali.
1. Scegli un’opzione per il formato dei dati. Queste opzioni consentono di scegliere i delimitatori e i separatori per le coppie chiave-valore che inviano i dati del segmento a una destinazione. Le opzioni di formato includono:
   * **Chiave singola:** consente di impostare la chiave in una coppia chiave-valore. Imposta il valore dopo aver selezionato un segmento nella sezione [!UICONTROL Segment Mappings] seguente.
   * **Chiave multipla:** consente di impostare la chiave e il valore per una coppia chiave-valore. Puoi creare la coppia chiave-valore dopo aver selezionato un segmento nella sezione Segment Mappings (Mappature segmento) qui sotto.
Per ulteriori informazioni su questi elementi di dati, consulta [Coppie chiave-valore standard e seriali](../../features/destinations/key-value-pairs.md) .
1. Clic **[!UICONTROL Save]**.

Tutte le altre impostazioni sono facoltative. Per ulteriori informazioni sulle impostazioni **[!UICONTROL Cookie Domain]** e **[!UICONTROL Publish data to]**, consulta [Impostazioni facoltative per le destinazioni cookie](/help/using/features/destinations/cookie-destination-options.md).

## Mappature dei segmenti {#segments-mapping}

Questa sezione ti consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. Nella casella **[!UICONTROL Search and Add Segments]**, inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** per sfogliare un elenco di segmenti disponibili.
1. Fai clic su **[!UICONTROL Add Selected Segments]** quando trovi il segmento da utilizzare. Aggiungendo un segmento si apre la finestra [!UICONTROL Edit Mapping].
1. Nella finestra di dialogo [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mapping]** consente di impostare un valore per la chiave specificata nella sezione Configurazione di cui sopra.
   * **[!UICONTROL Publish from]** consente di impostare la data di inizio e la data di fine della destinazione. Se la data di fine è vuota, la destinazione non scade mai.
1. Clic **[!UICONTROL Save]**.
1. Clic **[!UICONTROL Done]**.
