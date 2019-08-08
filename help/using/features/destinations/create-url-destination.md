---
description: Una destinazione URL effettua chiamate pixel da una pagina alla destinazione. Per creare una destinazione URL con Generatore di destinazione, effettuate le seguenti operazioni.
seo-description: Una destinazione URL effettua chiamate pixel da una pagina alla destinazione. Per creare una destinazione URL con Generatore di destinazione, effettuate le seguenti operazioni.
seo-title: Configurare una destinazione URL
solution: Audience Manager
title: Configurare una destinazione URL
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# Configurare una destinazione URL {#configure-url-destination}

Una [!DNL URL] destinazione effettua chiamate pixel da una pagina alla destinazione. Per creare [!DNL URL] una destinazione con [!UICONTROL Destination Builder], effettuate le seguenti operazioni.

<!-- create-url-destination.xml -->

Per creare una nuova [!DNL URL] destinazione, accedi **[!UICONTROL Audience Data > Destinations > Create New Destination]** a e completa le sezioni come descritto di seguito.

## Informazioni di base {#basic-info}

Questa sezione contiene campi e opzioni che avviano il processo di creazione di destinazione URL. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Basic Information]** esporre i controlli.
2. Denominate la destinazione. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivete la destinazione. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su una destinazione.
4. Nell **[!UICONTROL Category]** 'elenco, scegliete **[!UICONTROL Custom]**.
5. Nell **[!UICONTROL Environment]** 'elenco, selezionate l'ambiente in cui attivare la destinazione URL.
6. Nell **[!UICONTROL Type]** 'elenco, fate clic **[!UICONTROL URL]** su.
7. *(Facoltativo)* Selezionate un **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l'ID segmento alla destinazione.
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitata a 255 caratteri, massimo.
8. Fate clic per **[!UICONTROL Next]** passare alle [!UICONTROL Configuration] impostazioni o fare clic per **[!UICONTROL Data Export Labels]** applicare i controlli di esportazione alla destinazione.

## Etichette esportazione dati {#data-export-labels-dest}

Questa sezione contiene le opzioni che applicano [i controlli di esportazione dei dati](../../features/data-export-controls.md) a una [!DNL URL] destinazione. Ignorate questo passaggio se non utilizzate i controlli di esportazione dei dati. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Data Export Labels]** esporre i controlli.
2. Selezionate un'etichetta che corrisponda al controllo sull'esportazione dei dati applicato alla destinazione (per informazioni, consultate [Aggiungi etichette esportazione a una destinazione)](/help/using/features/destinations/add-data-export-labels.md) .
3. Fai clic su **[!UICONTROL Save]**.

## Configurazione {#configure-base-data}

Questa sezione contiene opzioni che consentono di impostare i delimitatori di base [!DNL URL] e di dati trasmessi dalla [!DNL URL] stringa. Questa sezione è facoltativa. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Configuration]** esporre i controlli.
1. *(Facoltativo)* Selezionate la casella **[!UICONTROL Serialize]** di controllo.
Questo consente di inviare segmenti a una destinazione in sequenza anziché effettuare chiamate separate per ogni segmento. La serializzazione contribuisce a rendere efficiente i trasferimenti di dati. Selezionando questa casella di controllo vengono visualizzati i campi URL e delimitatore. Per ulteriori informazioni, consultate [Coppie di valori standard e chiave di serie](../../features/destinations/key-value-pairs.md).
1. Se selezionate **[!UICONTROL Serialize]**, dovete anche configurare i campi URL e delimitatore descritti di seguito.

| Campo | Descrizione |
|--- |--- |
| URL di base | Parte di base di uno standard `HTTP`[!DNL URL] che non cambia. Inoltre, è necessario inserire la macro `%ALIAS%`[segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell'URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| URL protetto | Parte di base di una versione protetta `HTTPS`[!DNL URL] che non viene modificata. Inoltre, è necessario inserire la macro `%ALIAS%`[segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell'URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| Delimitatore | Simbolo che separa le variabili del segmento nella [!DNL URL] stringa. Solitamente si tratta di una virgola o di un punto e virgola. Ottieni queste informazioni dal tuo partner di destinazione. |

## Mappature segmento {#segment-mappings}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Segment Mappings]** esporre i controlli.
1. Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic **[!UICONTROL Browse All Segments]** su Sfoglia un elenco dei segmenti disponibili.
1. Fai clic **[!UICONTROL Add Selected Segments]** su quando trovi il segmento da utilizzare. L'aggiunta di un segmento apre la [!UICONTROL Edit Mapping] finestra.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Fornite le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Scegliete una data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade.
1. Fai clic su **[!UICONTROL Done]**.