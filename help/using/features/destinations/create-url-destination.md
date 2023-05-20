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
source-wordcount: '486'
ht-degree: 2%

---

# Configurare un [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] effettua chiamate pixel da una pagina al tuo [!DNL destination]. Segui queste istruzioni per creare una [!DNL URL] [!DNL destination] con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Per creare un nuovo [!DNL URL] [!DNL destination], vai a **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completare le sezioni come descritto di seguito.

## Informazioni di base {#basic-info}

Questa sezione contiene campi e opzioni che avviano [!DNL URL destination] processo di creazione. Per completare questa sezione:

1. Clic **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denomina il [!DNL destination]. Evita abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivi la [!DNL destination]. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su un [!DNL destination].
4. In **[!UICONTROL Category]** elenco, scegli **[!UICONTROL Custom]**.
5. In **[!UICONTROL Environment]** , seleziona l&#39;ambiente in cui attivare il [!DNL URL destination].
6. In **[!UICONTROL Type]** , fare clic su **[!UICONTROL URL]**.
7. *(Facoltativo)* Seleziona un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: aggiunge e invia automaticamente l’ID segmento al [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri.
8. Clic **[!UICONTROL Next]** per passare al [!UICONTROL Configuration] o fai clic su **[!UICONTROL Data Export Labels]** per applicare i controlli sulle esportazioni al [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Questa sezione contiene le opzioni applicabili [controlli sull’esportazione dei dati](../../features/data-export-controls.md) a un [!DNL URL] destinazione. Ignora questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Clic **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Selezionare un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (vedere [Aggiungere etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md) per i dettagli).
3. Clic **[!UICONTROL Save]**.

## Configurazione {#configure-base-data}

Questa sezione contiene opzioni che consentono di impostare una base [!DNL URL] e delimitatori di dati trasmessi da [!DNL URL] stringa. Questa sezione è facoltativa. Per completare questa sezione:

1. Clic **[!UICONTROL Configuration]** per esporre i controlli.
1. *(Facoltativo)* Seleziona la **[!UICONTROL Serialize]** casella di controllo.
Questo ti consente di inviare segmenti a un [!DNL destination] in sequenza anziché effettuare chiamate separate per ciascun segmento. La serializzazione consente di rendere efficienti i trasferimenti di dati. Selezionando questa casella di controllo vengono visualizzati i campi URL e delimitatore. Per ulteriori informazioni, consulta [Coppie chiave-valore standard e seriali](../../features/destinations/key-value-pairs.md).
1. Se si seleziona **[!UICONTROL Serialize]**, devi anche configurare i campi URL e delimitatore descritti di seguito.

| Campo | Descrizione |
|--- |--- |
| [!UICONTROL Base URL] | Parte base di uno standard `HTTP` [!DNL URL] questo non cambia. Inoltre, è necessario inserire `%ALIAS%`  [macro segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell’URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Parte di base di una protezione `HTTPS` [!DNL URL] questo non cambia. Inoltre, è necessario inserire `%ALIAS%`   [macro segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell’URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Simbolo che separa le variabili di segmento nel [!DNL URL] stringa. In genere si tratta di una virgola o di un punto e virgola. Ottieni queste informazioni dal tuo partner di destinazione. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Questa sezione ti consente di cercare e aggiungere segmenti al tuo [!UICONTROL destination]. Per completare questa sezione:

1. Clic **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. In **[!UICONTROL Search and Add Segments]** , inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** sfoglia un elenco di segmenti disponibili.
1. Clic **[!UICONTROL Add Selected Segments]** quando trovi il segmento che desideri utilizzare. L’aggiunta di un segmento apre il [!UICONTROL Edit Mapping] finestra.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: fornisci le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: scegli una data di inizio e una data di fine per [!DNL destination]. Se la data di fine è vuota, la [!DNL destination] non scade mai.
1. Clic **[!UICONTROL Done]**.
