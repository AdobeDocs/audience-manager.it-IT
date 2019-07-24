---
description: Gli acquirenti di dati Audience Marketplace accettano di riportare tutte le ad impression servite utilizzando caratteristiche contenute nel feed di dati a prezzi di base per migliaia di impressioni (CPM). L'utilizzo CPM è previsto il 5 ° giorno di ogni mese del calendario e include dati per il mese precedente. Gli abbonati a tariffa fissa non devono utilizzare l'utilizzo del report.
seo-description: Gli acquirenti di dati Audience Marketplace accettano di riportare tutte le ad impression servite utilizzando caratteristiche contenute nel feed di dati a prezzi di base per migliaia di impressioni (CPM). L'utilizzo CPM è previsto il 5 ° giorno di ogni mese del calendario e include dati per il mese precedente. Gli abbonati a tariffa fissa non devono utilizzare l'utilizzo del report.
seo-title: Fatturazione per feed feed dati
solution: Audience Manager
title: Fatturazione per feed feed dati
topic: API DIL
uuid: d 7236667-282 b -4160-9909-579721 af 4016
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Billing for Data Feed Buyers {#billing-for-data-feed-buyers}

Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions ([!DNL CPM]) basis. [!DNL CPM] l'utilizzo è previsto il 5 ° giorno di ogni mese del calendario e include dati per il mese precedente. Gli abbonati a tariffa fissa non devono utilizzare l'utilizzo del report.

## How to Report CPM Usage {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] Gli acquirenti di dati accettano di riportare tutte le ad impression servite utilizzando caratteristiche contenute nel feed di dati a prezzi di base per migliaia di impressioni ([!DNL CPM]). [!DNL CPM] l'utilizzo scade il 5 giorno di ogni mese del calendario e include i dati per il mese precedente. Gli abbonati a tariffa fissa non devono utilizzare l'utilizzo del report.

[!UICONTROL Audience Marketplace] offre due modi per utilizzare [!DNL CPM] l'utilizzo:

* **Generazione di rapporti a livello di segmento**: questo è il metodo di generazione di rapporti [!DNL CPM] consigliato. When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts, based on the algorithms described in [Cost Attribution for CPM Data Feeds](#cost-attribution).
* **Rapporti a livello di feed di dati**: Questo metodo richiede di segnalare singolarmente [!DNL CPM] l'utilizzo per ogni feed di dati, in base agli algoritmi descritti in [Attribuzione costi per feed dati CPM](#cost-attribution). Tuttavia, questo metodo è più tedioso e si verifica un errore rispetto alla generazione di rapporti a livello di segmento.

## Report CPM Usage at Segment Level {#segment-level-report}

The [!UICONTROL Segment Usage] tab allows you to report segment-level usage, while displaying the segments grouped by the destinations they are mapped to.

After reporting [!DNL CPM] usage at segment level, [!UICONTROL Audience Marketplace] automatically assigns the corresponding data feeds the correct usage, based on the [Cost Attribution for CPM Data Feeds](#cost-attribution).

To report [!DNL CPM] usage at segment level:

1. **[!UICONTROL Audience Marketplace > Payables]** Vai a.
2. Select the **[!UICONTROL Segment Usage]** tab.
3. Compilare l'utilizzo per i segmenti. You can use the [!UICONTROL Search] box to filter the segments if you only need to report usage for some of them.
4. Fai clic su **[!UICONTROL Edit Segments Usage]**.
5. Enter the [!DNL CPM] usage amount in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you're done and review the confirmation dialog.
   ![confirm-segment-use](assets/confirm-segment-usage.png)
7. Fai clic su **[!UICONTROL Confirm]**.

## Report CPM Usage at Data Feed Level {#feed-level-report}

Data feed-level reporting is a more tedious and prone to error process, since you must individually calculate [!DNL CPM] usage for each data feed. We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead.

To report [!DNL CPM] usage at segment level:

1. **[!UICONTROL Audience Marketplace > Payables]** Vai a.
2. Select the **[!UICONTROL Feed Usage]** tab.
3. Use the [!UICONTROL Search] box to filter the data feeds and identify the ones that you need to report usage for.
4. Fai clic su **[!UICONTROL Edit Feeds Usage]**.
5. Calculate the [!DNL CPM] usage for each data feed based on the [Cost Attribution for CPM Data Feeds](#cost-attribution), and enter it in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you're done and review the confirmation dialog.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Fai clic su **[!UICONTROL Confirm]**.

## Generazione di rapporti in massa

To reduce errors and overhead while reporting [!DNL CPM] usage, you can use the bulk reporting option to download a [!DNL CSV] file containing the data feeds and segments, fill in the usage, and upload it back to [!DNL Audience Manager]. Potete utilizzare la generazione di rapporti in blocco per riportare feed e utilizzo del segmento.

To update [!DNL CPM] usage in bulk:

1. **[!UICONTROL Audience Marketplace > Payables]** Vai a.
1. Select the **[!UICONTROL Feed Usage]** or **[!UICONTROL Segment Usage]** tab, depending on the type of reporting that you want to update.
1. Click **[!UICONTROL Edit Feeds Usage]** or **[!UICONTROL Edit Segments Usage]**.
1. Click **[!UICONTROL download the current usage]** to make sure you use a valid CSV file.
1. Aprite il file sul computer e compilate il rapporto sull'utilizzo.
1. Click **[!UICONTROL Choose a CSV file]** to upload the updated usage report.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] convalida il file non appena viene caricato e richiede se rileva eventuali errori presenti nel file.

### Errori di convalida in blocco

| Messaggio di errore | Descrizione | Correzione |
| ------------- | -------------| -----|
| Input non valido | [!DNL Audience Manager] rilevata una modifica nello schema [!DNL CSV] del file, ad esempio colonne mancanti o modifiche ai titoli delle colonne. | Evitare di modificare la struttura della tabella. |
| Non trovato | For [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. | For [!UICONTROL Segment Level Reporting], check the validity of the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], check the validity of the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. |
| Record duplicati trovati | [!DNL Audience Manager] rilevati record duplicati con valori di impression diversi. | Rivedete il rapporto e verificate di non aver segnalato valori di utilizzo diversi per lo stesso feed di dati o segmento. |
| Valori non supportati | [!DNL Audience Manager] rilevati valori non numerici nella [!DNL Audience Manager] colonna. | Review the report and make sure you only enter numerical values in the [!DNL Audience Manager] column. |
| Intestazioni per campi obbligatori mancanti | [!DNL Audience Manager] sono state rilevate intestazioni di tabella mancanti per campi obbligatori. For [!UICONTROL Segment Level Reporting], the mandatory fields are: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. For [!UICONTROL Feed Level Reporting], the mandatory fields are: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Controllare il rapporto e verificare che le intestazioni della tabella non siano state alterate. |

>[!NOTE]
>Removing rows from the [!DNL CSV] usage report does not have any effect on the existing usage report. [!DNL Audience Manager] elabora solo i campi inclusi nel rapporto.

## [!DNL CPM] Best practice per i rapporti

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Raccomandazioni </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Segnala sempre il numero totale di impression</b> </p> </td> 
   <td colname="col2"> <p>Per i totali impression CPM: </p>
   <p> Segnala il numero totale di impression, senza utilizzare i decimali. Audience Manager calcola automaticamente il CPM in base al numero totale di report.</p><p>Se hai bisogno di riportare 1,234,567 impression, segnalalo esattamente come. Non è necessario dividere il numero totale di impression per 1,000 per calcolare il CPM.</p><p>Le caratteristiche utilizzate per ottimizzare il contenuto Web o dell'app (ottimizzazione contenuto) mediante strumenti quali Adobe Target o una destinazione Analytics non contribuiscono ai totali d'uso per i piani CPM. I fornitori di dati vengono in genere compensati per l'ottimizzazione dei contenuti con piani a tariffa fissa.</p><p>See <a href="#cost-attribution">Cost Attribution for CPM Data Feeds</a> for more information. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Passa all'intervallo di reporting mensile</b> </p> </td> 
   <td colname="col2"> <p>Il sistema di rapporti si chiude dopo il 5 di ogni mese. Se non riesci a generare un rapporto sull'utilizzo CPM per partire da quel momento, devi aggiungere tale importo al rapporto per il mese successivo. Ad esempio, supponiamo che a ottobre utilizzi 1000 impression, perderai la scadenza di reporting di ottobre e utilizzi 1000 impression a novembre. In questo caso, nel mese di dicembre, tra il 1 ° e il 5 ° settembre, segnalerete il totale di ottobre e di novembre (2000).</p><p><b>Suggerimento</b>: Devi sempre tentare di riportare l'utilizzo CPM per il mese precedente tra il 1 ° e il 5 ° giorno del mese successivo.</p><p>Puoi riportare l'utilizzo CPM fino al 5 del nuovo mese di calendario, ma questo non è consigliato. La generazione di rapporti sull'utilizzo CPM prima del 5 di ogni mese fornisce ora di Audience Manager per controllare ed elaborare i dati.</p> </td>
  </tr> 
 </tbody> 
</table>

## Cost Attribution for CPM Data Feeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] you must self-report impression amounts each month, for each of your segments. We recommend reporting [!DNL CPM] usage at segment level, so that cost attribution is done automatically.

<!-- marketplace_cpm_billing.xml -->

### Billing Summary {#billing-summary}

You must submit [!DNL CPM] data feed impression amounts between the 1st and the 5th days of each calendar month. To do this correctly, we recommend that you [Report CPM Usage at Segment Level](#segment-level-report).

>[!TIP]
>When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts.

Should you need to [!UICONTROL Report CPM Usage at Data Feed Level], you must individually compile all impressions delivered for each feed in the previous calendar month, and report them according to the billing allocation described in this article.

After you report [!DNL CPM] number for the previous calendar month, [!DNL Adobe] will do the following:

* Create an invoice and bill you based on the [!DNL CPM] rate for each subscribed data feed.
* Pay data providers (sellers) fees owed based on your reported [!DNL CPM] use.

>[!IMPORTANT]
>
>In qualità di acquirente, tutti i totali di impression segnalati devono essere true e precisi. Se non riesci a segnalare i totali delle impression entro il 5 di ogni mese, devi includere i totali per il mese non segnalato nel mese successivo.

## Assign Impressions at Feed Level Based on Trait Qualification Rules {#assign-impressions}

The [!UICONTROL Activation] use case lets you use traits in the corresponding data feed to create segments in [Segment Builder](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) and map those segments to a destination. The Boolean operators [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT] let you set the conditions for trait and segment qualification.

When you [Report CPM Usage at Data Feed Level](#feed-level-report), you must allocate impressions proportionally for each data feed, according to the [!DNL Boolean] operators used in the trait qualification rules. Nella tabella seguente è indicato come allocare correttamente impression per regola booleana o per tipo di caratteristica.

>[!TIP]
>[Report Utilizzo CPM a livello segmento](#segment-level-report) per fare in modo che i rapporti sul livello di feed dati vengano inseriti automaticamente da Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logica o tipo di qualifica regola </th> 
   <th colname="col2" class="entry"> Distribuzione fatturazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> AND</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> AND</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OR</span> </p> </td> 
   <td colname="col2"> <p>Applica la ponderazione ponderata dei totali delle impression consegnati a tutte le caratteristiche del fornitore in un segmento basato su regole che utilizza una condizione OR booleana. L'allocazione ponderata viene calcolata utilizzando la formula seguente:</p><p><code>(Popolazione caratteristica/Popolazione segmento) * Numero di impression * Costo di CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> NOT</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmenti algoritmici </p> </td> 
   <td colname="col2"> <p>Applica il 100% dei totali delle impression consegnati a tutti i feed del fornitore in un segmento che contiene caratteristiche algoritmiche. </p> </td> 
  </tr>
 </tbody>
</table>

## Billing Examples {#billing-examples}

The examples below are meant to illustrate how [!DNL CPM] usage allocation is done at data feed level.

>[!MPORTANT]
>We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead, to have this process done automatically.

Prendiamo in considerazione il seguente scenario:

![billing-examples](assets/billing-examples.png)

### Caso 1: Segmenti con regole di qualifica AND

Questo segmento contiene 3 caratteristiche da fornitori di dati separati. Since segment qualification is based on an [!UICONTROL AND] condition, visitors have to realize the traits from all three feeds to qualify for the segment.

![](assets/billing-segment-and.png)

With an [!UICONTROL AND] condition, you must assign 100% of the impressions received during the month to all three data providers. In the [!UICONTROL Audience Marketplace > Payables] section, you credit each provider with 1,000,000 impressions.

This example applies to segments that use [!DNL Boolean] [!UICONTROL NOT] operators or for segments that contain algorithmic traits.

### Caso 2: Segmenti con regole di qualificazione OR

Questo segmento contiene 3 caratteristiche da fornitori di dati separati. Since segment qualification is based on an [!UICONTROL OR] condition, visitors have to realize at least one of the three traits to qualify for the segment.

We cannot tell which trait is responsible for an impression because qualification is based on an [!UICONTROL OR] condition. As a result, in the [!UICONTROL Audience Marketplace > Payables] section you credit each provider with a weighted allocation of the total impressions, based on trait population.

![billing-segment-or](assets/billing-segment-or.png)

>[!MORE_ LIKE_ THIS]
>
>* [Fatturazione e allocazione impression per feed dati flat](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)


## Billing and Impression Allocation for Flat Fee Data Feeds {#billing-flat-fee}

Un feed di dati a tariffa fissa addebita ogni mese un importo fisso, a prescindere dall'avvio dell'iscrizione o dal numero di impression utilizzate. Le tariffe non vengono suddivise in proporzione per uso mensile o intervalli. Come per la fatturazione CPM, Adobe genererà una fattura e la addebiterà al tasso mensile a tariffa fissa per i feed di dati iscritti.

Ad esempio, supponiamo che tu abbia deciso di attivare alcune caratteristiche in un feed a metà del mese. L'utente continuerà a essere addebitato sulla base della tariffa mensile, a prescindere dall'avvio della sottoscrizione o delle caratteristiche attivate.