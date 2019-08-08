---
description: Nella pagina Destinazione di destinazione sono elencati tutti i tuoi URL, cookie e destinazioni server-to-server. Offre funzioni per creare, modificare, cercare e generare rapporti sulle destinazioni. La pagina di destinazione si trova in Data Data > Destinations (Destinazioni).
seo-description: Nella pagina Destinazione di destinazione sono elencati tutti i tuoi URL, cookie e destinazioni server-to-server. Offre funzioni per creare, modificare, cercare e generare rapporti sulle destinazioni. La pagina di destinazione si trova in Data Data > Destinations (Destinazioni).
seo-title: Gestisci destinazioni
solution: Audience Manager
title: Gestisci destinazioni
uuid: 6 b 66 ff 42-0075-49 a 7-a 58 f -7 f 8 ea 2295 fdc
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Gestisci destinazioni {#manage-destinations}

La [!UICONTROL Destination] pagina di destinazione elenca tutti i cookie [!DNL URL], i cookie e le destinazioni server-to-server. Offre funzioni per creare, modificare, cercare e generare rapporti sulle destinazioni. La pagina di destinazione si trova in **[!UICONTROL Audience Data > Destinations]**.

## Pagina di destinazione predefinita {#default-landing-page}

<!-- destinations-home.xml -->

La pagina di destinazione predefinita elenca le destinazioni in base al tipo. Potete filtrare le destinazioni utilizzando le quattro schede disponibili:

* **Tutti**: mostra tutti i tipi di destinazioni.
* **Adobe Experience Cloud**: mostra le destinazioni che inviano dati ad altre soluzioni Adobe Experience Cloud. Attualmente, l'unica opzione supportata è Adobe Analytics. Consultate [Configurare una destinazione di Analytics](/help/using/features/destinations/create-analytics-destination.md).
* **Piattaforme integrate**: mostra le destinazioni basate su dispositivo e basate su dispositivo (denominate anche destinazioni server-to-server). Le destinazioni basate su persone sono al momento disponibili solo per i clienti selezionati.
* **Personalizzato**: mostra le destinazioni di cookie e URL.


![](assets/destinations-landing.png)

## Pagina di destinazione pubblico indirizzabile {#audiences-landing-page}

Per visualizzare i dati del pubblico e le percentuali di corrispondenza per la destinazione server-to-server, seleziona **[!UICONTROL Integrated Platforms > Device-Based]**.

Per ulteriori informazioni sulle informazioni visualizzate, consulta [Interfaccia di pubblico di riferimento](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Configurare una destinazione URL {#configure-url-destination}

Una [!DNL URL] destinazione effettua chiamate pixel da una pagina alla destinazione. Per creare [!DNL URL] una destinazione con [!UICONTROL Destination Builder], effettuate le seguenti operazioni.

<!-- create-url-destination.xml -->

Per creare una nuova [!DNL URL] destinazione, accedi **[!UICONTROL Audience Data > Destinations > Create New Destination]** a e completa le sezioni come descritto di seguito.

### Informazioni di base {#basic-info}

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

### Etichette esportazione dati {#data-export-labels-dest}

Questa sezione contiene le opzioni che applicano [i controlli di esportazione dei dati](../../features/data-export-controls.md) a una [!DNL URL] destinazione. Ignorate questo passaggio se non utilizzate i controlli di esportazione dei dati. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Data Export Labels]** esporre i controlli.
2. Selezionate un'etichetta che corrisponda al controllo sull'esportazione dei dati applicato alla destinazione (per informazioni, consultate [Aggiungi etichette esportazione a una destinazione)](../../features/destinations/manage-destinations.md#add-data-export-labels) .
3. Fai clic su **[!UICONTROL Save]**.

### Configurazione {#configure-base-data}

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

### Mappature segmento {#segment-mappings}

Questa sezione consente di cercare e aggiungere segmenti alla destinazione. Per completare questa sezione:

1. Fate clic per **[!UICONTROL Segment Mappings]** esporre i controlli.
1. Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic **[!UICONTROL Browse All Segments]** su Sfoglia un elenco dei segmenti disponibili.
1. Fai clic **[!UICONTROL Add Selected Segments]** su quando trovi il segmento da utilizzare. L'aggiunta di un segmento apre la [!UICONTROL Edit Mapping] finestra.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Fornite le coppie chiave-valore utilizzate dal segmento.
   * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Scegliete una data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade.
1. Fai clic su **[!UICONTROL Done]**.

## Aggiungere o modificare segmenti per destinazioni server-to-server {#add-edit-segments}

Puoi aggiungere o modificare solo i segmenti per una destinazione server-to-server ([!DNL S2S]). Non è possibile creare [!DNL S2S] destinazioni con [!UICONTROL Destination Builder]. Contatta il tuo consulente per impostare [!DNL S2S] le destinazioni. Per aggiungere o modificare segmenti per [!DNL S2S] una destinazione, effettuate le seguenti operazioni.

<!-- destination-s2s-edit.xml -->

Per aggiungere o modificare mappature segmenti per [!DNL S2S] una destinazione:

1. **[!UICONTROL Audience Data > Destinations]** Vai a. Selezionate **Piattaforme integrate &gt; Basate su dispositivo** e individuate la [!DNL S2S] destinazione con cui desiderate lavorare.
2. Nella [!UICONTROL Action] colonna, fate clic sull'icona a forma di matita per modificare la destinazione.
   * Nella **[!UICONTROL Search and Add Segments]** casella, inizia a digitare il nome di un segmento o fai clic **[!UICONTROL Browse All Segments]** su Sfoglia un elenco dei segmenti disponibili.
   * Fai clic **[!UICONTROL Add Selected Segments]** su quando trovi il segmento da utilizzare. L'aggiunta di un segmento apre la [!UICONTROL Edit Mapping] finestra.
   * In [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Impostare un valore per la coppia [chiave-valore](../../features/destinations/key-value-pairs.md) utilizzata da questa destinazione.
      * **[!UICONTROL Start Date]** e **[!UICONTROL End Date]**: Scegliete una data di inizio e di fine per la destinazione. Se la data di fine è vuota, la destinazione non scade.
3. Fate clic **[!UICONTROL Save]****[!UICONTROL Done]** su e quindi su.

## Aggiungere etichette di esportazione dati a una destinazione {#add-data-export-labels}

[!DNL Data Export Labels] lavorare con il [!DNL Export Controls] set impostato su un'origine dati. [!DNL Data Export Labels] impedire l'aggiunta di caratteristiche limitate a un segmento e l'invio di dati di segmento a una destinazione. Potete impostare più etichette di esportazione su una nuova o esistente [!DNL cookie][!DNL URL] destinazione.

>[!NOTE]
>
>Per aggiungere un'etichetta di esportazione, dovete disporre delle autorizzazioni *di amministratore o* di privilegi sufficienti per creare o modificare una destinazione.

<!-- t_export_labels.xml -->

Per aggiungere etichette di esportazione a una destinazione:

1. Fai clic su **[!UICONTROL Audience Data]**:
   * Per nuove destinazioni: Fate clic **[!UICONTROL Create New Destination]** su. Completate [!UICONTROL Basic Information] la sezione prima di selezionare un'etichetta di esportazione dati. Per informazioni, consultate [Creare una destinazione](../../features/destinations/manage-destinations.md#create-cookie-destination) cookie o [Creare una destinazione](../../features/destinations/manage-destinations.md#configure-url-destination) URL.
   * Per le destinazioni esistenti: Usate la [!DNL Search] casella per trovare la destinazione o scorrere l'elenco e fate clic sul nome della destinazione per aprirla.
1. Seleziona una [!DNL Data Export Label]. Lasciate vuote le caselle di controllo se non desiderate impostare restrizioni di esportazione. Le etichette di esportazione includono le seguenti opzioni:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Le limitazioni di esportazione non funzionano a meno che non imposti un [controllo di esportazione corrispondente](../../features/data-export-controls.md) su un'origine dati.
1. Fai clic su **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Creare un'origine dati](../../features/manage-datasources.md#create-data-source)

