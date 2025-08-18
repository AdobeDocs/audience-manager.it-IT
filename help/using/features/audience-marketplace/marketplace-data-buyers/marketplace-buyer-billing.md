---
description: Gli acquirenti di dati di Audience Marketplace accettano di segnalare tutte le impression pubblicitarie servite utilizzando le caratteristiche contenute nel feed di dati il cui prezzo è calcolato su un costo per migliaia di impression pubblicitarie (CPM). L’utilizzo di CPM è previsto per il 5° giorno di ogni mese di calendario e include i dati del mese precedente. Gli abbonati con tariffa fissa non devono segnalare l’utilizzo.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: Fatturazione per gli acquirenti di feed di dati
keywords: Reporting a livello di segmento, livello di segmento, livello di segmento
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 0%

---

# Fatturazione per gli acquirenti di feed di dati {#billing-for-data-feed-buyers}

Gli acquirenti di dati di Audience Marketplace accettano di segnalare tutte le impression pubblicitarie distribuite utilizzando le caratteristiche contenute nel feed di dati il cui prezzo è calcolato su un costo per migliaia di impression pubblicitarie ([!DNL CPM]). L&#39;utilizzo di [!DNL CPM] scade il 5 di ogni mese del calendario e include i dati relativi al mese precedente. Gli abbonati con tariffa fissa non devono segnalare l’utilizzo.

<br> 

## Come segnalare l’utilizzo di CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] acquirenti di dati accettano di segnalare tutte le impression pubblicitarie distribuite utilizzando le caratteristiche contenute nel feed di dati il cui prezzo è calcolato su un costo per migliaia di impression pubblicitarie ([!DNL CPM]). L&#39;utilizzo di [!DNL CPM] scade il 5 giorno di ogni mese del calendario e include i dati del mese precedente. Gli abbonati con tariffa fissa non devono segnalare l’utilizzo.

[!UICONTROL Audience Marketplace] offre due modi per segnalare l&#39;utilizzo di [!DNL CPM]:

* **Generazione rapporti a livello di segmento**: metodo consigliato per la generazione rapporti sull&#39;utilizzo di [!DNL CPM]. Quando si segnala l&#39;utilizzo di [!DNL CPM] a livello di segmento, la sezione di generazione rapporti a livello di feed di dati viene compilata automaticamente con gli importi di utilizzo corrispondenti, in base agli algoritmi descritti in [Attribuzione costi per feed dati di CPM](#cost-attribution).
* **Generazione rapporti a livello di feed dati**: questo metodo richiede di segnalare singolarmente l&#39;utilizzo di [!DNL CPM] per ogni feed dati, in base agli algoritmi descritti in [Attribuzione costi per feed dati di CPM](#cost-attribution). Tuttavia, questo metodo è più noioso e soggetto a errori rispetto al reporting a livello di segmento.

<br> 

## Segnala l’utilizzo di CPM a livello di segmento {#segment-level-report}

La scheda [!UICONTROL Segment Usage] ti consente di segnalare l&#39;utilizzo a livello di segmento, visualizzando al contempo i segmenti raggruppati per le destinazioni a cui sono mappati.

Dopo aver segnalato l&#39;utilizzo di [!DNL CPM] a livello di segmento, [!UICONTROL Audience Marketplace] assegna automaticamente ai feed di dati corrispondenti l&#39;utilizzo corretto, in base a [Attribuzione costi per feed di dati di CPM](#cost-attribution).

Per segnalare l&#39;utilizzo di [!DNL CPM] a livello di segmento:

1. Vai a **[!UICONTROL Audience Marketplace > Payables]**.
1. Selezionare la scheda **[!UICONTROL Segment Usage]**.
1. Compila l’utilizzo per i segmenti. È possibile utilizzare la casella [!UICONTROL Search] per filtrare i segmenti se è necessario segnalare solo l&#39;utilizzo di alcuni di essi.
1. Fare clic su **[!UICONTROL Edit Segments Usage]**.
1. Immettere il valore di utilizzo [!DNL CPM] nella colonna [!UICONTROL Usage].
1. Al termine, fai clic su **[!UICONTROL Save]** e controlla la finestra di dialogo di conferma.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Fare clic su **[!UICONTROL Confirm]**.

Guarda anche il nostro video dimostrativo su come segnalare l’utilizzo a livello di segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Segnalare l’utilizzo di CPM a livello di feed dati {#feed-level-report}

La generazione di rapporti a livello di feed di dati è un processo più noioso e soggetto a errori, in quanto è necessario calcolare singolarmente l&#39;utilizzo di [!DNL CPM] per ogni feed di dati. Ti consigliamo invece di [segnalare l&#39;utilizzo di CPM a livello di segmento](#segment-level-report).

Per segnalare l&#39;utilizzo di [!DNL CPM] a livello di segmento:

1. Vai a **[!UICONTROL Audience Marketplace > Payables]**.
2. Selezionare la scheda **[!UICONTROL Feed Usage]**.
3. Utilizzare la casella [!UICONTROL Search] per filtrare i feed di dati e identificare quelli per i quali è necessario segnalare l&#39;utilizzo.
4. Fare clic su **[!UICONTROL Edit Feeds Usage]**.
5. Calcola l&#39;utilizzo di [!DNL CPM] per ogni feed di dati in base a [Attribuzione costi per feed di dati di CPM](#cost-attribution) e inseriscilo nella colonna [!UICONTROL Usage].
6. Al termine, fai clic su **[!UICONTROL Save]** e controlla la finestra di dialogo di conferma.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Fare clic su **[!UICONTROL Confirm]**.

<br> 

## Generazione rapporti in blocco

Per ridurre gli errori e il sovraccarico durante il reporting dell&#39;utilizzo di [!DNL CPM], è possibile utilizzare l&#39;opzione di reporting in blocco per scaricare un file [!DNL CSV] contenente i feed e i segmenti di dati, compilare l&#39;utilizzo e caricarlo nuovamente in [!DNL Audience Manager]. Puoi utilizzare il reporting in blocco per segnalare sia l’utilizzo di feed che di segmenti.

Per aggiornare l&#39;utilizzo di [!DNL CPM] in blocco:

1. Vai a **[!UICONTROL Audience Marketplace > Payables]**.
1. Selezionare la scheda **[!UICONTROL Feed Usage]** o **[!UICONTROL Segment Usage]**, a seconda del tipo di report che si desidera aggiornare.
1. Fare clic su **[!UICONTROL Edit Feeds Usage]** o **[!UICONTROL Edit Segments Usage]**.
1. Fare clic su **[!UICONTROL download the current usage]** per assicurarsi di utilizzare un file CSV valido.
1. Apri il file sul computer e compila il rapporto di utilizzo.
1. Fare clic su **[!UICONTROL Choose a CSV file]** per caricare il report di utilizzo aggiornato.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] convalida il file non appena viene caricato e richiede se vengono rilevati errori nel file.

<br> 

### Errori di convalida della generazione di rapporti in blocco

| Messaggio di errore | Descrizione | Correzione |
| ------------- | -------------| -----|
| Input non valido | [!DNL Audience Manager] ha rilevato una modifica nello schema del file [!DNL CSV], ad esempio colonne mancanti o modifiche ai titoli delle colonne. | Evita di modificare la struttura della tabella. |
| Non trovato | Per [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] non è stato in grado di identificare la combinazione [!UICONTROL Segment ID] e [!UICONTROL Destination ID]. Per [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] non è stato in grado di identificare la combinazione [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] e [!UICONTROL Use Case]. | Per [!UICONTROL Segment Level Reporting], verificare la validità della combinazione [!UICONTROL Segment ID] e [!UICONTROL Destination ID]. Per [!UICONTROL Feed Level Reporting], verificare la validità della combinazione [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] e [!UICONTROL Use Case]. |
| Record duplicati trovati | [!DNL Audience Manager] ha rilevato record duplicati con valori di impression diversi. | Esamina il rapporto e assicurati di non segnalare valori di utilizzo diversi per lo stesso feed di dati o segmento. |
| Valori non supportati | [!DNL Audience Manager] ha rilevato valori non numerici nella colonna [!DNL Audience Manager]. | Esaminare il report e assicurarsi di immettere solo valori numerici nella colonna [!DNL Audience Manager]. |
| Intestazioni per campi obbligatori mancanti | [!DNL Audience Manager] ha rilevato intestazioni di tabella mancanti per i campi obbligatori. Per [!UICONTROL Segment Level Reporting], i campi obbligatori sono: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Per [!UICONTROL Feed Level Reporting], i campi obbligatori sono: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Esamina il rapporto e assicurati che le intestazioni della tabella non siano state manomesse. |

>[!NOTE]
>La rimozione delle righe dal report di utilizzo [!DNL CSV] non ha alcun effetto sul report di utilizzo esistente. [!DNL Audience Manager] elabora solo i campi inclusi nel report.

<br> 

## Best practice per la generazione di rapporti di [!DNL CPM]

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
   <td colname="col2"> <p>Per i totali delle impression CPM: </p>
   <p> Segnala il numero totale di impression, senza l’utilizzo di decimali. Audience Manager calcola automaticamente il CPM in base al numero totale riportato.</p><p>Se devi segnalare 1.234.567 impression, segnalalo esattamente in questo modo. Per calcolare il CPM non è necessario dividere per 1.000 il numero totale di impression.</p><p>Le caratteristiche utilizzate per ottimizzare il contenuto web o dell’app (ottimizzazione del contenuto) utilizzando strumenti come Adobe Target o una destinazione di Analytics non contribuiscono ai totali di utilizzo per i piani di CPM. I fornitori di dati ricevono in genere un compenso per l’ottimizzazione dei contenuti utilizzando piani tariffari fissi.</p><p>Per ulteriori informazioni, vedere <a href="#cost-attribution">Attribuzione costi per feed dati di CPM</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Attenersi all'intervallo di reporting mensile</b> </p> </td> 
   <td colname="col2"> <p>Il sistema di reporting viene chiuso dopo il 5 di ogni mese. Se entro tale data non si segnala l'utilizzo di CPM, è necessario aggiungere tale importo al rapporto per il mese successivo. Ad esempio, supponiamo che tu utilizzi 1000 impression in ottobre, che non rispetti la scadenza del reporting di ottobre e che utilizzi 1000 impression in novembre. In questo caso, si riporta il totale di ottobre e novembre (2000) in dicembre, tra il 1° e il 5.</p><p><b>Suggerimento</b>: provare sempre a segnalare l'utilizzo di CPM per il mese precedente tra il primo e il quinto giorno del mese successivo.</p><p>È possibile segnalare l’utilizzo di CPM fino al 5 del nuovo mese di calendario, ma non è consigliabile. Il reporting sull’utilizzo di CPM prima del 5 di ogni mese consente ad Audience Manager di verificare ed elaborare i dati.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Attribuzione costi per feed dati di CPM {#cost-attribution}

In [!UICONTROL Audience Marketplace] devi segnalare autonomamente gli importi delle impression ogni mese, per ogni segmento. È consigliabile segnalare l&#39;utilizzo di [!DNL CPM] a livello di segmento, in modo che l&#39;attribuzione dei costi venga eseguita automaticamente.

<!-- marketplace_cpm_billing.xml -->

### Riepilogo fatturazione {#billing-summary}

È necessario inviare [!DNL CPM] quantità di impression del feed di dati tra il primo e il quinto giorno di ogni mese di calendario. Per farlo correttamente, ti consigliamo di [segnalare l&#39;utilizzo di CPM a livello di segmento](#segment-level-report).

>[!TIP]
>Quando si segnala l&#39;utilizzo di [!DNL CPM] a livello di segmento, la sezione di reporting a livello di feed di dati viene compilata automaticamente con gli importi di utilizzo corrispondenti.

Se devi [!UICONTROL Report CPM Usage at Data Feed Level], devi compilare singolarmente tutte le impression consegnate per ciascun feed nel mese di calendario precedente e segnalarle in base all&#39;allocazione di fatturazione descritta in questo articolo.

Dopo aver segnalato il numero [!DNL CPM] per il mese di calendario precedente, [!DNL Adobe] eseguirà le seguenti operazioni:

* Creare una fattura e fatturarla in base alla tariffa [!DNL CPM] per ogni feed di dati sottoscritto.
* Paga le tariffe dei provider di dati (venditori) dovute in base all&#39;utilizzo [!DNL CPM] segnalato.

>[!IMPORTANT]
>
>In qualità di acquirente, tutti i totali delle impression riportati devono essere veri e precisi. Se non riesci a segnalare i totali delle impression entro il 5° giorno di ogni mese, devi includere i totali per il mese non segnalato nel mese successivo.

<br> 

## Assegnare impressioni a livello di feed in base alle regole di qualificazione delle caratteristiche {#assign-impressions}

Il caso d&#39;uso [!UICONTROL Activation] consente di utilizzare le caratteristiche nel feed di dati corrispondente per creare segmenti in [Segment Builder](../../../features/segments/segment-builder.md) e mappare tali segmenti a una destinazione. Gli operatori booleani [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT] ti consentono di impostare le condizioni per la qualifica di caratteristiche e segmenti.

Quando [segnali l&#39;utilizzo di CPM a livello di feed dati](#feed-level-report), è necessario allocare le impression in modo proporzionale per ciascun feed dati, in base agli operatori [!DNL Boolean] utilizzati nelle regole di qualificazione delle caratteristiche. Nella tabella seguente viene illustrato come allocare correttamente le impression in base a una regola booleana o a un tipo di caratteristica.

>[!TIP]
>[Segnala l&#39;utilizzo di CPM a livello di segmento](#segment-level-report) affinché il reporting a livello di feed di dati venga eseguito automaticamente da Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logica o tipo di qualifica della regola </th> 
   <th colname="col2" class="entry"> Distribuzione fatturazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> E</span> </p> </td> 
   <td colname="col2"> <p>Applica il 100% dei totali delle impression distribuite a tutte le caratteristiche del provider in un segmento basato su regole che utilizza una condizione booleana <span class="wintitle"> AND</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> O</span> </p> </td> 
   <td colname="col2"> <p>Applica l’allocazione ponderata dei totali delle impression consegnate a tutte le caratteristiche del provider in un segmento basato su regole che utilizza una condizione booleana OR. L'allocazione ponderata viene calcolata utilizzando la seguente formula:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Applica il 100% dei totali delle impression distribuite a tutte le caratteristiche del provider in un segmento basato su regole che utilizza una condizione booleana <span class="wintitle"> NOT</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmenti algoritmici </p> </td> 
   <td colname="col2"> <p>Applica il 100% dei totali delle impression fornite a tutti i feed del provider in un segmento contenente caratteristiche algoritmiche. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Esempi di fatturazione {#billing-examples}

Gli esempi seguenti illustrano come viene eseguita l&#39;allocazione dell&#39;utilizzo [!DNL CPM] a livello di feed di dati.

>[!IMPORTANT]
>Ti consigliamo invece di [segnalare l&#39;utilizzo di CPM a livello di segmento](#segment-level-report), per eseguire automaticamente questa procedura.

Prendiamo in considerazione lo scenario seguente:

![esempi di fatturazione](assets/billing-examples.png)

<br> 

### Caso 1: segmenti con regole di qualificazione e

Questo segmento contiene 3 caratteristiche di fornitori di dati separati. Poiché la qualificazione del segmento si basa su una condizione [!UICONTROL AND], i visitatori devono realizzare le caratteristiche da tutti e tre i feed per qualificarsi per il segmento.

![](assets/billing-segment-and.png)

Con una condizione [!UICONTROL AND], devi assegnare il 100% delle impression ricevute durante il mese a tutti e tre i provider di dati. Nella sezione [!UICONTROL Audience Marketplace > Payables] si attribuisce a ogni provider 1.000.000 di impression.

Questo esempio si applica ai segmenti che utilizzano gli operatori [!DNL Boolean] [!UICONTROL NOT] o per i segmenti che contengono caratteristiche algoritmiche.

<br> 

### Caso 2: segmenti con regole di qualificazione OR

Questo segmento contiene 3 caratteristiche di fornitori di dati separati. Poiché la qualificazione del segmento si basa su una condizione [!UICONTROL OR], i visitatori devono realizzare almeno una delle tre caratteristiche per qualificarsi per il segmento.

Impossibile stabilire quale caratteristica è responsabile di un&#39;impression perché la qualifica si basa su una condizione [!UICONTROL OR]. Di conseguenza, nella sezione [!UICONTROL Audience Marketplace > Payables] si attribuisce a ogni fornitore un&#39;allocazione ponderata delle impression totali, in base alla popolazione delle caratteristiche.

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### Caso 3: segmenti con casi di utilizzo di modellazione e attivazione

Questo esempio descrive l’attribuzione in base a due casi di utilizzo di feed dati: Modeling e Activation. Nell’esempio, vengono esaminati due fornitori di dati, con le seguenti informazioni:

![feed-dati](assets/feed-use-cases.png)

Nella tabella seguente, il segmento X contiene due caratteristiche, T1 e T2, con la regola del segmento T1 o T2, dove:

* T1 è una caratteristica del feed di dati A;
* T2 è una caratteristica algoritmica modellata sulle caratteristiche di terze parti dai feed di dati A e B.

Il segmento è mappato a una destinazione e vengono immesse 1.000.000 impression per questo segmento in un mese, utilizzando [Generazione rapporti a livello di segmento](#segment-level-report).

Di queste 1.000.000 impression:

* T1 rappresenta il 40% della popolazione del segmento, che si traduce in 400.000 impression per il feed A.
* T2 rappresenta il 60% della popolazione del segmento, che si traduce in 600.000 impression per Feed A e Feed B.

A livello di feed di dati, il modo in cui vengono allocate le impression è:

* Il feed di dati A riceve 600.000 impression dalla caratteristica T2 (modellata sulle caratteristiche dal feed di dati A e dal feed di dati B, in modo che entrambi ricevano le impression) e 400.000 impression dalla caratteristica T1 (una caratteristica dal feed di dati A), per un totale di 1.000.000 di impression.
* Il feed di dati B riceve 600.000 impression dalla caratteristica T2 (vedi spiegazione qui sopra) e 0 impression dalla caratteristica T1.

La suddivisione immediata per feed di dati e caso d’uso è la seguente:

![feed-breakdown](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Per il caso di utilizzo della modellazione, devi segnalare solo l’utilizzo di CPM al momento dell’attivazione. Se esegui solo un modello ma non lo attivi, non è necessario alcun rapporto sull’utilizzo.

<br> 

## Allocazione fatturazione e impression per feed di dati a tariffa fissa {#billing-flat-fee}

Un feed di dati a canone fisso ti fattura un importo fisso ogni mese, indipendentemente da quando inizia l’abbonamento o dal numero di impression utilizzate. Le tariffe non vengono ripartite proporzionalmente per l&#39;utilizzo o gli intervalli di mesi parziali. Come per la fatturazione di CPM, Adobe genera una fattura e la fattura alla tariffa mensile forfettaria per i feed di dati sottoscritti.

Ad esempio, supponiamo che tu abbia deciso di attivare alcune caratteristiche in un feed a metà mese. Verrai comunque fatturato alla tariffa piena mensile indipendentemente da quando hai iniziato l’abbonamento o hai attivato caratteristiche specifiche.
