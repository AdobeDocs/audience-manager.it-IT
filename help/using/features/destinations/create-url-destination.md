---
description: Una destinazione URL effettua chiamate in pixel da una pagina alla destinazione. Seguite queste istruzioni per creare una destinazione URL con Generatore di destinazione.
seo-description: Una destinazione URL effettua chiamate in pixel da una pagina alla destinazione. Seguite queste istruzioni per creare una destinazione URL con Generatore di destinazione.
seo-title: Configurare una destinazione URL
solution: Audience Manager
title: Configurare una destinazione URL
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# Configurare una destinazione URL {#configure-url-destination}

Una [!DNL URL] destinazione effettua chiamate in pixel da una pagina alla destinazione. Seguite queste istruzioni per creare una [!DNL URL] destinazione con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Per creare una nuova [!DNL URL] destinazione, andate a **[!UICONTROL Audience Data > Destinations > Create New Destination]** completare le sezioni come descritto di seguito.

## Informazioni di base {#basic-info}

Questa sezione contiene campi e opzioni che avviano il processo di creazione della destinazione URL. Per completare questa sezione:

1. Fare clic **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivere la destinazione. Una descrizione sintetica è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. Nell’ **[!UICONTROL Category]** elenco, scegliete **[!UICONTROL Custom]**.
5. Nell' **[!UICONTROL Environment]** elenco, selezionare l'ambiente in cui attivare la destinazione URL.
6. Nell' **[!UICONTROL Type]** elenco, fare clic su **[!UICONTROL URL]**.
7. *(Facoltativo)* Selezionate un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l’ID del segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri, al massimo.
8. Fate clic **[!UICONTROL Next]** per passare alle [!UICONTROL Configuration] impostazioni oppure fate clic **[!UICONTROL Data Export Labels]** per applicare i controlli di esportazione alla destinazione.

## Etichette esportazione dati {#data-export-labels-dest}

Questa sezione contiene opzioni che applicano controlli [di esportazione](../../features/data-export-controls.md) dati a una [!DNL URL] destinazione. Salta questo passaggio se non utilizzi i controlli di esportazione dei dati. Per completare questa sezione:

1. Fare clic **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Selezionare un'etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (per informazioni dettagliate, vedere [Aggiungi etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md) ).
3. Fai clic su **[!UICONTROL Save]**.

## Configurazione {#configure-base-data}

Questa sezione contiene opzioni che consentono di impostare un carattere di delimitazione di base [!DNL URL] e dati passato dalla [!DNL URL] stringa. Questa sezione è facoltativa. Per completare questa sezione:

1. Fare clic **[!UICONTROL Configuration]** per esporre i controlli.
1. *(Facoltativo)* Selezionate la **[!UICONTROL Serialize]** casella di controllo.
Questo consente di inviare i segmenti a una destinazione in sequenza anziché effettuare chiamate separate per ciascun segmento. La serializzazione contribuisce a rendere efficienti i trasferimenti di dati. Selezionando questa casella di controllo vengono visualizzati i campi URL e delimitatori. Per ulteriori informazioni, vedere Coppie chiave-valore [standard e seriale](../../features/destinations/key-value-pairs.md).
1. Se selezionate **[!UICONTROL Serialize]**, dovete anche configurare i campi URL e delimitatori descritti di seguito.

| Campo | Descrizione |
|--- |--- |
| URL di base | La parte base di uno standard `HTTP` che non [!DNL URL] viene modificata. Inoltre, è necessario inserire la macro `%ALIAS%` di [](../../features/destinations/destination-macros.md#destination-macros-defined) segnaposto nell'URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| URL sicuro | La parte base di una protezione `HTTPS` che non [!DNL URL] viene modificata. Inoltre, è necessario inserire la macro `%ALIAS%` di [](../../features/destinations/destination-macros.md#destination-macros-defined) segnaposto nell'URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| Delimitatore | Simbolo che separa le variabili di segmento nella [!DNL URL] stringa. In genere si tratta di una virgola o di un punto e virgola. Ottieni queste informazioni dal tuo partner di destinazione. |

## Mappature segmenti {#segment-mappings}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fare clic **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** Sfoglia un elenco di segmenti disponibili.
1. Fate clic **[!UICONTROL Add Selected Segments]** quando trovate il segmento da usare. Aggiungendo un segmento si apre la [!UICONTROL Edit Mapping] finestra.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Specificare le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Scegliete una data di inizio e una data di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade mai.
1. Fai clic su **[!UICONTROL Done]**.