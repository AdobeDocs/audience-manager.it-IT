---
description: Una destinazione URL effettua chiamate pixel da una pagina alla destinazione. Segui queste istruzioni per creare una destinazione URL con Generatore di destinazione.
seo-description: Una destinazione URL effettua chiamate pixel da una pagina alla destinazione. Segui queste istruzioni per creare una destinazione URL con Generatore di destinazione.
seo-title: Configurare una destinazione URL
solution: Audience Manager
title: Configurare una destinazione URL
feature: Nozioni di base sulle destinazioni
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 3%

---

# Configura un [!DNL URL Destination] {#configure-url-destination}

Un [!DNL URL destination] effettua chiamate pixel da una pagina al [!DNL destination]. Segui queste istruzioni per creare un [!DNL URL] [!DNL destination] con [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Per creare un nuovo [!DNL URL] [!DNL destination], vai a **[!UICONTROL Audience Data > Destinations > Create New Destination]** e completa le sezioni come descritto di seguito.

## Informazioni di base {#basic-info}

Questa sezione contiene campi e opzioni che avviano il processo di creazione [!DNL URL destination]. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Basic Information]** per esporre i controlli.
2. Denomina il simbolo [!DNL destination]. Evitare abbreviazioni e caratteri speciali.
3. *(Facoltativo)* Descrivi il  [!DNL destination]. Una descrizione concisa è un modo efficace per definire o fornire ulteriori informazioni su un [!DNL destination].
4. Nell’elenco **[!UICONTROL Category]**, scegli **[!UICONTROL Custom]**.
5. Nell&#39;elenco **[!UICONTROL Environment]**, selezionare l&#39;ambiente in cui attivare il [!DNL URL destination].
6. Nell’elenco **[!UICONTROL Type]**, fai clic su **[!UICONTROL URL]**.
7. *(Facoltativo)* Seleziona un  **[!UICONTROL Auto-fill Destination Mapping]**. Le opzioni includono:
   * **[!UICONTROL Segment ID]**: Aggiunge e invia automaticamente l’ID del segmento a  [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Aggiunge e invia automaticamente il codice di integrazione del segmento alla mappatura di destinazione. Il codice di integrazione è un identificatore univoco creato e utilizzato dal cliente. È limitato a 255 caratteri, massimo.
8. Fai clic su **[!UICONTROL Next]** per passare alle impostazioni [!UICONTROL Configuration] oppure fai clic su **[!UICONTROL Data Export Labels]** per applicare i controlli di esportazione a [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Questa sezione contiene opzioni che applicano [controlli di esportazione dati](../../features/data-export-controls.md) a una destinazione [!DNL URL]. Ignora questo passaggio se non utilizzi i controlli di esportazione dati. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Data Export Labels]** per esporre i controlli.
2. Seleziona un&#39;etichetta che corrisponda al controllo di esportazione dei dati applicato alla destinazione (consulta [Aggiungi etichette di esportazione a una destinazione](/help/using/features/destinations/add-data-export-labels.md) per ulteriori informazioni).
3. Clic **[!UICONTROL Save]**.

## Configurazione {#configure-base-data}

Questa sezione contiene opzioni che consentono di impostare un carattere di delimitazione dati [!DNL URL] di base e valori passati dalla stringa [!DNL URL]. Questa sezione è facoltativa. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Configuration]** per esporre i controlli.
1. *(Facoltativo)* Seleziona la  **[!UICONTROL Serialize]** casella di controllo.
Questo ti consente di inviare i segmenti a un [!DNL destination] in sequenza anziché effettuare chiamate separate per ciascun segmento. La serializzazione aiuta a rendere efficienti i trasferimenti di dati. Selezionando questa casella di controllo vengono visualizzati i campi URL e delimitatore. Per ulteriori informazioni, vedere [Coppie chiave-valore standard e seriali](../../features/destinations/key-value-pairs.md).
1. Se selezioni **[!UICONTROL Serialize]**, devi anche configurare i campi URL e delimitatori descritti di seguito.

| Campo | Descrizione |
|--- |--- |
| [!UICONTROL Base URL] | La parte base di uno standard `HTTP` [!DNL URL] che non cambia. Inoltre, è necessario inserire la `%ALIAS%` [macro segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | La parte base di un `HTTPS` [!DNL URL] protetto che non viene modificata. Inoltre, è necessario inserire il `%ALIAS%`   [macro segnaposto](../../features/destinations/destination-macros.md#destination-macros-defined) nell&#39;URL di base. Esempio: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Simbolo che separa le variabili del segmento nella stringa [!DNL URL]. Di solito è una virgola o un punto e virgola. Ottieni queste informazioni dal tuo partner di destinazione. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

Questa sezione ti consente di cercare e aggiungere segmenti al tuo [!UICONTROL destination]. Per completare questa sezione:

1. Fare clic su **[!UICONTROL Segment Mappings]** per esporre i controlli.
1. Nella casella **[!UICONTROL Search and Add Segments]**, inizia a digitare il nome di un segmento o fai clic su **[!UICONTROL Browse All Segments]** sfoglia un elenco di segmenti disponibili.
1. Fai clic su **[!UICONTROL Add Selected Segments]** quando trovi il segmento da utilizzare. Aggiungendo un segmento si apre la finestra [!UICONTROL Edit Mapping].
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Specifica le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e  **[!UICONTROL End Date]**: Scegli una data di inizio e una data di fine per  [!DNL destination]. Se la data di fine è vuota, la [!DNL destination] non scade mai.
1. Clic **[!UICONTROL Done]**.
