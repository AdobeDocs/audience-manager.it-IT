---
description: Una destinazione URL effettua chiamate pixel da una pagina alla tua destinazione. Segui queste istruzioni per creare una destinazione URL con Generatore di destinazione.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Configurare una destinazione URL
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# Configura [!DNL URL Destination] {#configure-url-destination}

Un [!DNL URL destination] effettua chiamate pixel da una pagina al tuo [!DNL destination]. Seguire queste istruzioni per creare un [!DNL URL] [!DNL destination] con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Per creare un nuovo [!DNL URL] [!DNL destination], passare a **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completare le sezioni come descritto di seguito.

## Informazioni di base {#basic-info}

Questa sezione contiene campi e opzioni che avviano il processo di creazione di [!DNL URL destination]. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denomina [!DNL destination]. Evita abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivere [!DNL destination]. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su [!DNL destination].
4. Nell&#39;elenco **[!UICONTROL Category]**, scegliere **[!UICONTROL Custom]**.
5. Nell&#39;elenco **[!UICONTROL Environment]** selezionare l&#39;ambiente in cui attivare [!DNL URL destination].
6. Nell&#39;elenco **[!UICONTROL Type]** fare clic su **[!UICONTROL URL]**.
7. *(Facoltativo)* Selezionare un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: aggiunge e invia automaticamente l&#39;ID segmento a [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri.
8. Fare clic su **[!UICONTROL Next]** per passare alle impostazioni di [!UICONTROL Configuration] oppure su **[!UICONTROL Data Export Labels]** per applicare i controlli di esportazione a [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Questa sezione contiene opzioni che applicano [controlli di esportazione dati](../../features/data-export-controls.md) a una destinazione [!DNL URL]. Ignora questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Selezionare un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (vedere [Aggiungere etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md) per ulteriori dettagli).
3. Fare clic su **[!UICONTROL Save]**.

## Configurazione {#configure-base-data}

Questa sezione contiene opzioni che consentono di impostare una base [!DNL URL] e delimitatori di dati passati dalla stringa [!DNL URL]. Questa sezione è facoltativa. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Configuration]** per esporre i controlli.
1. *(facoltativo)* Selezionare la casella di controllo **[!UICONTROL Serialize]**.
In questo modo è possibile inviare segmenti a [!DNL destination] in sequenza anziché effettuare chiamate separate per ciascun segmento. La serializzazione consente di rendere efficienti i trasferimenti di dati. Selezionando questa casella di controllo vengono visualizzati i campi URL e delimitatore. Per ulteriori informazioni, vedere [Coppie chiave-valore standard e seriali](../../features/destinations/key-value-pairs.md).
1. Se si seleziona **[!UICONTROL Serialize]**, è necessario configurare anche i campi URL e delimitatore descritti di seguito.

| Campo | Descrizione |
|--- |--- |
| [!UICONTROL Base URL] | Parte base di un `HTTP` [!DNL URL] standard che non cambia. È inoltre necessario inserire la `%ALIAS%` [macro segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Parte base di un `HTTPS` [!DNL URL] protetto che non cambia. È inoltre necessario inserire `%ALIAS%`   [macro segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Simbolo che separa le variabili di segmento nella stringa [!DNL URL]. In genere si tratta di una virgola o di un punto e virgola. Ottieni queste informazioni dal tuo partner di destinazione. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Questa sezione ti consente di cercare e aggiungere segmenti a [!UICONTROL destination]. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. Nella casella **[!UICONTROL Search and Add Segments]**, inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** Sfoglia un elenco di segmenti disponibili.
1. Fare clic su **[!UICONTROL Add Selected Segments]** quando si trova il segmento che si desidera utilizzare. L&#39;aggiunta di un segmento apre la finestra [!UICONTROL Edit Mapping].
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: fornire le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: scegliere una data di inizio e una data di fine per [!DNL destination]. Se la data di fine è vuota, [!DNL destination] non scade.
1. Fare clic su **[!UICONTROL Done]**.
