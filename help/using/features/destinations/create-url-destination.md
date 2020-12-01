---
description: Una destinazione URL effettua chiamate in pixel da una pagina alla destinazione. Seguite queste istruzioni per creare una destinazione URL con Generatore di destinazione.
seo-description: Una destinazione URL effettua chiamate in pixel da una pagina alla destinazione. Seguite queste istruzioni per creare una destinazione URL con Generatore di destinazione.
seo-title: Configurare una destinazione URL
solution: Audience Manager
title: Configurare una destinazione URL
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# Configurare un [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] effettua chiamate pixel da una pagina all&#39; [!DNL destination]. Seguire queste istruzioni per creare un [!DNL URL] [!DNL destination] con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Per creare una nuova [!DNL URL] [!DNL destination], passare a **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completare le sezioni come descritto di seguito.

## Informazioni di base {#basic-info}

Questa sezione contiene campi e opzioni che avviano il processo di creazione di [!DNL URL destination]. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denominate il simbolo [!DNL destination]. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivete il  [!DNL destination]pulsante. Una descrizione sintetica è un modo efficace per definire o fornire ulteriori informazioni su un [!DNL destination].
4. Nell&#39;elenco **[!UICONTROL Category]**, scegliere **[!UICONTROL Custom]**.
5. Nell&#39;elenco **[!UICONTROL Environment]**, selezionare l&#39;ambiente in cui attivare la [!DNL URL destination].
6. Nell&#39;elenco **[!UICONTROL Type]**, fare clic su **[!UICONTROL URL]**.
7. *(Facoltativo)* Selezionate un  **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l’ID del segmento al  [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri, al massimo.
8. Fare clic su **[!UICONTROL Next]** per passare alle impostazioni [!UICONTROL Configuration] oppure su **[!UICONTROL Data Export Labels]** per applicare i controlli di esportazione a [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Questa sezione contiene opzioni che applicano i controlli di esportazione [dei dati](../../features/data-export-controls.md) a una destinazione [!DNL URL]. Salta questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Selezionare un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (per ulteriori informazioni, vedere [Aggiungi etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md)).
3. Clic **[!UICONTROL Save]**.

## Configurazione {#configure-base-data}

Questa sezione contiene opzioni che consentono di impostare una [!DNL URL] base e delimitatori di dati passati dalla stringa [!DNL URL]. Questa sezione è facoltativa. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Configuration]** per esporre i controlli.
1. *(Facoltativo)* Selezionare la  **[!UICONTROL Serialize]** casella di controllo.
Questo consente di inviare i segmenti a un [!DNL destination] in sequenza anziché effettuare chiamate separate per ciascun segmento. La serializzazione contribuisce a rendere efficienti i trasferimenti di dati. Selezionando questa casella di controllo vengono visualizzati i campi URL e delimitatori. Per ulteriori informazioni, vedere [Coppie chiave-valore standard e seriale](../../features/destinations/key-value-pairs.md).
1. Se si seleziona **[!UICONTROL Serialize]**, è necessario configurare anche i campi URL e delimitatori descritti di seguito.

| Campo | Descrizione |
|--- |--- |
| [!UICONTROL Base URL] | La parte base di un `HTTP` [!DNL URL] standard che non viene modificata. Inoltre, è necessario inserire la `%ALIAS%` [macro segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | La parte base di un `HTTPS` [!DNL URL] protetto che non viene modificata. Inoltre, è necessario inserire la variabile `%ALIAS%`   [macro segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Simbolo che separa le variabili di segmento nella stringa [!DNL URL]. In genere si tratta di una virgola o di un punto e virgola. Ottieni queste informazioni dal tuo partner di destinazione. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Questa sezione consente di cercare e aggiungere segmenti al [!UICONTROL destination]. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. Nella casella **[!UICONTROL Search and Add Segments]**, inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** per sfogliare un elenco di segmenti disponibili.
1. Fare clic su **[!UICONTROL Add Selected Segments]** quando si trova il segmento da utilizzare. Aggiungendo un segmento si apre la finestra [!UICONTROL Edit Mapping].
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Specificare le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e  **[!UICONTROL End Date]**: Scegliete una data di inizio e di fine per il  [!DNL destination]. Se la data di fine è vuota, la [!DNL destination] non scade mai.
1. Clic **[!UICONTROL Done]**.