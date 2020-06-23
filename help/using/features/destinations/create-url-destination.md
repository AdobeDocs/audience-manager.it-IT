---
description: Una destinazione URL effettua chiamate in pixel da una pagina alla destinazione. Seguite queste istruzioni per creare una destinazione URL con Generatore di destinazione.
seo-description: Una destinazione URL effettua chiamate in pixel da una pagina alla destinazione. Seguite queste istruzioni per creare una destinazione URL con Generatore di destinazione.
seo-title: Configurare una destinazione URL
solution: Audience Manager
title: Configurare una destinazione URL
translation-type: tm+mt
source-git-commit: d83b07a542dd337773d287f4eba0960c6e258504
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 1%

---



# Configurare un [!DNL URL Destination] {#configure-url-destination}

Un utente [!DNL URL destination] effettua chiamate pixel da una pagina all’altra [!DNL destination]. Seguite queste istruzioni per creare un [!DNL URL] file [!DNL destination] con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Per creare una nuova [!DNL URL][!DNL destination], passare a **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completare le sezioni come descritto di seguito.

## Informazioni di base {#basic-info}

Questa sezione contiene campi e opzioni che avviano il processo di [!DNL URL destination] creazione. Per completare questa sezione:

1. Fare clic **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denominate il [!DNL destination]. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivete il [!DNL destination]. Una descrizione sintetica è un modo efficace per definire o fornire ulteriori informazioni su un [!DNL destination].
4. Nell’ **[!UICONTROL Category]** elenco, scegliete **[!UICONTROL Custom]**.
5. Nell&#39; **[!UICONTROL Environment]** elenco, selezionare l&#39;ambiente in cui attivare l&#39; [!DNL URL destination].
6. Nell&#39; **[!UICONTROL Type]** elenco, fare clic su **[!UICONTROL URL]**.
7. *(Facoltativo)* Selezionate un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l’ID del segmento al [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri, al massimo.
8. Fate clic **[!UICONTROL Next]** per passare alle [!UICONTROL Configuration] impostazioni oppure fate clic **[!UICONTROL Data Export Labels]** per applicare i controlli di esportazione al [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Questa sezione contiene opzioni che applicano controlli [di esportazione](../../features/data-export-controls.md) dati a una [!DNL URL] destinazione. Salta questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Fare clic **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Selezionare un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (per informazioni dettagliate, vedere [Aggiungi etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md) ).
3. Clic **[!UICONTROL Save]**.

## Configurazione {#configure-base-data}

Questa sezione contiene opzioni che consentono di impostare un carattere di delimitazione di base [!DNL URL] e dati passato dalla [!DNL URL] stringa. Questa sezione è facoltativa. Per completare questa sezione:

1. Fare clic **[!UICONTROL Configuration]** per esporre i controlli.
1. *(Facoltativo)* Selezionate la **[!UICONTROL Serialize]** casella di controllo.
Questo consente di inviare i segmenti a un segmento in [!DNL destination] sequenza anziché effettuare chiamate separate per ciascun segmento. La serializzazione contribuisce a rendere efficienti i trasferimenti di dati. Selezionando questa casella di controllo vengono visualizzati i campi URL e delimitatori. Per ulteriori informazioni, vedere Coppie chiave-valore [standard e seriale](../../features/destinations/key-value-pairs.md).
1. Se selezionate **[!UICONTROL Serialize]**, dovete anche configurare i campi URL e delimitatori descritti di seguito.

| Campo | Descrizione |
|--- |--- |
| [!UICONTROL Base URL] | La parte base di uno standard `HTTP` che non [!DNL URL] viene modificata. Inoltre, è necessario inserire la macro `%ALIAS%` di [](../../features/destinations/destination-macros.md#destination-macros-defined) segnaposto nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | La parte base di una protezione `HTTPS` che non [!DNL URL] viene modificata. Inoltre, è necessario inserire la macro `%ALIAS%` di [](../../features/destinations/destination-macros.md#destination-macros-defined) segnaposto nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Simbolo che separa le variabili di segmento nella [!DNL URL] stringa. In genere si tratta di una virgola o di un punto e virgola. Ottieni queste informazioni dal tuo partner di destinazione. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Questa sezione consente di cercare e aggiungere segmenti al [!UICONTROL destination]. Per completare questa sezione:

1. Fare clic **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** Sfoglia un elenco di segmenti disponibili.
1. Fate clic **[!UICONTROL Add Selected Segments]** quando trovate il segmento da usare. Aggiungendo un segmento si apre la [!UICONTROL Edit Mapping] finestra.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Specificare le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Scegliete una data di inizio e di fine per il [!DNL destination]. Se la data di fine è vuota, la data di scadenza [!DNL destination] non scade mai.
1. Clic **[!UICONTROL Done]**.