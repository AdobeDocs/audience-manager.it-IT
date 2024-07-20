---
description: Una destinazione di cookie restituisce e scrive i dati in un cookie nel browser dell’utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Segui queste istruzioni per creare una destinazione cookie con [!UICONTROL Destination Builder].
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Configurare una destinazione cookie
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Configurare una destinazione cookie {#create-cookie-destination}

Una destinazione di cookie restituisce e scrive i dati in un cookie nel browser dell’utente. Il cookie contiene dati che possono essere letti da altre piattaforme che hanno accesso alla pagina. Segui queste istruzioni per creare una destinazione cookie con [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Per creare una nuova destinazione cookie, passare a **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completare le sezioni come descritto di seguito.

## Informazioni di base {#basic-information}

Questa sezione contiene campi e opzioni che avviano il processo di creazione della destinazione cookie. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denomina la destinazione. Evita abbreviazioni e caratteri speciali.
3. *(facoltativo)* Descrivere la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. Nell&#39;elenco **[!UICONTROL Category]**, scegliere **[!UICONTROL Custom]**.
5. Nell&#39;elenco **[!UICONTROL Environment]**, selezionare **[!UICONTROL Browser]**. Non è possibile configurare le destinazioni dei cookie per gli ambienti mobile nativi, ad esempio le app Android o iOS.
6. Nell&#39;elenco **[!UICONTROL Type]** fare clic su **[!UICONTROL Cookie]**.
7. *(Facoltativo)* Selezionare un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: aggiunge e invia automaticamente l&#39;ID segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri.
8. Fare clic su **[!UICONTROL Next]** per passare alle impostazioni di [!UICONTROL Configuration] oppure su **[!UICONTROL Data Export Labels]** per applicare i controlli di esportazione alla destinazione.

## Etichette esportazione dati {#data-export-labels-cookies}

Questa sezione contiene opzioni che applicano [controlli per l&#39;esportazione dei dati](../../features/data-export-controls.md) a una destinazione cookie. Ignora questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Selezionare un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (vedere [Aggiungere etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md) per i dettagli).
3. Fare clic su **[!UICONTROL Save]**.

## Configurazione {#configuration}

Questa sezione contiene campi e opzioni che ti consentono di impostare il cookie per la tua destinazione.

>[!NOTE]
>
>[!DNL Audience Manager] codifica i dati scritti nel cookie di destinazione. Ad esempio, gli spazi sono codificati come `%20` e i punti e virgola come `%3B`.

Per completare questa sezione:

1. Fare clic su **[!UICONTROL Configuration]** per esporre i controlli
1. Denomina il cookie. Evita abbreviazioni e caratteri speciali.
1. Scegliere un&#39;opzione di formato dati. Queste opzioni ti consentono di scegliere i delimitatori e i separatori per le coppie chiave-valore che inviano i dati del segmento a una destinazione. Le opzioni di formato includono:
   * **Chiave singola:** consente di impostare la chiave in una coppia chiave-valore. Il valore verrà impostato dopo aver selezionato un segmento nella sezione [!UICONTROL Segment Mappings] seguente.
   * **Più chiavi:** consente di impostare la chiave e il valore per una coppia chiave-valore. Creerai la coppia chiave-valore dopo aver selezionato un segmento nella sezione Mappature segmento di seguito.
Per ulteriori informazioni su questi elementi dati, vedere [Coppie chiave-valore standard e seriali](../../features/destinations/key-value-pairs.md).
1. Fare clic su **[!UICONTROL Save]**.

Tutte le altre impostazioni sono facoltative. Per ulteriori informazioni sulle impostazioni **[!UICONTROL Cookie Domain]** e **[!UICONTROL Publish data to]**, vedere [Impostazioni facoltative per le destinazioni dei cookie](/help/using/features/destinations/cookie-destination-options.md).

## Mappature dei segmenti {#segments-mapping}

Questa sezione ti consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. Nella casella **[!UICONTROL Search and Add Segments]**, inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** per sfogliare un elenco di segmenti disponibili.
1. Fare clic su **[!UICONTROL Add Selected Segments]** quando si trova il segmento che si desidera utilizzare. L&#39;aggiunta di un segmento apre la finestra [!UICONTROL Edit Mapping].
1. Nella finestra di dialogo [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mapping]** consente di impostare un valore per la chiave specificata nella sezione Configurazione precedente.
   * **[!UICONTROL Publish from]** consente di impostare la data di inizio e la data di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade mai.
1. Fare clic su **[!UICONTROL Save]**.
1. Fare clic su **[!UICONTROL Done]**.
