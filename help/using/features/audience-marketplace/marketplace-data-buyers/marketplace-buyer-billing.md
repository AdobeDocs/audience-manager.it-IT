---
description: Gli acquirenti di dati di Audience Marketplace accettano di segnalare tutte le impressioni degli annunci serviti utilizzando le caratteristiche contenute nel feed di dati a un prezzo base per migliaia di ad impression (CPM). L’utilizzo di CPM è dovuto il 5° giorno di ogni mese solare e include i dati del mese precedente. Gli abbonati a canone fisso non devono segnalare l’utilizzo.
seo-description: Gli acquirenti di dati di Audience Marketplace accettano di segnalare tutte le impressioni degli annunci serviti utilizzando le caratteristiche contenute nel feed di dati a un prezzo base per migliaia di ad impression (CPM). L’utilizzo di CPM è dovuto il 5° giorno di ogni mese solare e include i dati del mese precedente. Gli abbonati a canone fisso non devono segnalare l’utilizzo.
seo-title: Fatturazione per gli acquirenti di feed di dati
solution: Audience Manager
title: Fatturazione per gli acquirenti di feed di dati
keywords: Reporting a livello di segmento, a livello di segmento, a livello di segmento
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
translation-type: tm+mt
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2064'
ht-degree: 1%

---

# Fatturazione per gli acquirenti di feed di dati {#billing-for-data-feed-buyers}

Gli acquirenti di dati di Audience Marketplace accettano di segnalare tutte le impressioni degli annunci servite utilizzando le caratteristiche contenute nel feed di dati a un prezzo per migliaia di ad impression ([!DNL CPM]). [!DNL CPM] l’utilizzo è dovuto il 5° giorno di ogni mese di calendario e include i dati del mese precedente. Gli abbonati a canone fisso non devono segnalare l’utilizzo.

<br> 

## Come segnalare l’utilizzo di CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] gli acquirenti di dati accettano di segnalare tutte le impression pubblicitarie servite utilizzando le caratteristiche contenute nel feed di dati a un prezzo base per migliaia di ad impression ([!DNL CPM]). [!DNL CPM] l’utilizzo è dovuto il 5 giorno di ogni mese di calendario e include i dati del mese precedente. Gli abbonati a canone fisso non devono segnalare l’utilizzo.

[!UICONTROL Audience Marketplace] offre due modi per segnalare l’ [!DNL CPM] utilizzo:

* **Generazione di rapporti** a livello di segmento: questo è il metodo di reporting  [!DNL CPM] sull&#39;utilizzo consigliato. Quando segnali l’utilizzo di [!DNL CPM] a livello di segmento, la sezione di reporting a livello di feed di dati viene compilata automaticamente con gli importi di utilizzo corrispondenti, in base agli algoritmi descritti in [Attribuzione dei costi per i feed di dati CPM](#cost-attribution).
* **Generazione di rapporti a livello di feed di dati**: questo metodo richiede di segnalare singolarmente l’ [!DNL CPM] utilizzo di ciascun feed di dati, in base agli algoritmi descritti in  [Attribuzione costi per feed di dati CPM](#cost-attribution). Tuttavia, questo metodo è più noioso e soggetto a errori rispetto alla generazione di rapporti a livello di segmento.

<br> 

## Segnala l’utilizzo del CPM a livello di segmento {#segment-level-report}

La scheda [!UICONTROL Segment Usage] ti consente di segnalare l’utilizzo a livello di segmento, mentre visualizzi i segmenti raggruppati in base alle destinazioni a cui sono mappati.

Dopo aver segnalato l’utilizzo [!DNL CPM] a livello di segmento, [!UICONTROL Audience Marketplace] assegna automaticamente i dati corrispondenti per alimentare l’utilizzo corretto, in base alla [Attribuzione dei costi per i feed di dati CPM](#cost-attribution).

Per segnalare l’utilizzo di [!DNL CPM] a livello di segmento:

1. Vai a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleziona la scheda **[!UICONTROL Segment Usage]** .
1. Compila l’utilizzo dei segmenti. Puoi utilizzare la casella [!UICONTROL Search] per filtrare i segmenti se devi solo utilizzarli per alcuni di essi.
1. Clic **[!UICONTROL Edit Segments Usage]**.
1. Immetti la quantità di utilizzo [!DNL CPM] nella colonna [!UICONTROL Usage] .
1. Al termine, fai clic su **[!UICONTROL Save]** e controlla la finestra di dialogo di conferma.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Clic **[!UICONTROL Confirm]**.

Guarda anche il nostro video dimostrativo su come puoi segnalare l’utilizzo a livello di segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Segnala l&#39;utilizzo di CPM a livello di feed di dati {#feed-level-report}

La generazione di rapporti a livello di feed di dati è più noiosa e suscettibile di errori, in quanto è necessario calcolare singolarmente l’ [!DNL CPM] utilizzo per ciascun feed di dati. Ti consigliamo invece di [segnalare l’utilizzo di CPM al livello di segmento](#segment-level-report).

Per segnalare l’utilizzo di [!DNL CPM] a livello di segmento:

1. Vai a **[!UICONTROL Audience Marketplace > Payables]**.
2. Seleziona la scheda **[!UICONTROL Feed Usage]** .
3. Utilizza la casella [!UICONTROL Search] per filtrare i feed di dati e identificare quelli di cui hai bisogno per segnalare l’utilizzo.
4. Clic **[!UICONTROL Edit Feeds Usage]**.
5. Calcola l’utilizzo di [!DNL CPM] per ciascun feed di dati in base alla [Attribuzione costi per feed di dati CPM](#cost-attribution) e inseriscilo nella colonna [!UICONTROL Usage].
6. Al termine, fai clic su **[!UICONTROL Save]** e controlla la finestra di dialogo di conferma.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. Clic **[!UICONTROL Confirm]**.

<br> 

## Generazione rapporti in blocco

Per ridurre gli errori e il sovraccarico durante la generazione di rapporti relativi all’utilizzo di [!DNL CPM], puoi utilizzare l’opzione di reporting in blocco per scaricare un file [!DNL CSV] contenente i feed di dati e i segmenti, compilarlo e caricarlo nuovamente su [!DNL Audience Manager]. Puoi utilizzare la funzione di reporting in blocco per segnalare sia l’utilizzo dei feed che quello dei segmenti.

Per aggiornare l&#39;utilizzo [!DNL CPM] in blocco:

1. Vai a **[!UICONTROL Audience Marketplace > Payables]**.
1. Seleziona la scheda **[!UICONTROL Feed Usage]** o **[!UICONTROL Segment Usage]** , a seconda del tipo di rapporto che desideri aggiornare.
1. Fare clic su **[!UICONTROL Edit Feeds Usage]** o su **[!UICONTROL Edit Segments Usage]**.
1. Fai clic su **[!UICONTROL download the current usage]** per assicurarti di utilizzare un file CSV valido.
1. Apri il file sul computer e compila il rapporto di utilizzo.
1. Fai clic su **[!UICONTROL Choose a CSV file]** per caricare il rapporto di utilizzo aggiornato.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] convalida il file non appena lo carichi e richiede se rileva eventuali errori nel file.

<br> 

### Errori di convalida della segnalazione in blocco

| Messaggio di errore | Descrizione | Correzione |
| ------------- | -------------| -----|
| Input non valido | [!DNL Audience Manager] rilevato una modifica nello schema del  [!DNL CSV] file, ad esempio colonne mancanti o modifiche ai titoli delle colonne. | Evitare di modificare la struttura della tabella. |
| Non trovato | Per [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] non è stato possibile identificare la combinazione [!UICONTROL Segment ID] e [!UICONTROL Destination ID]. Per [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] non è in grado di identificare la combinazione [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] e [!UICONTROL Use Case]. | Per [!UICONTROL Segment Level Reporting], controlla la validità della combinazione [!UICONTROL Segment ID] e [!UICONTROL Destination ID]. Per [!UICONTROL Feed Level Reporting], controlla la validità della combinazione [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] e [!UICONTROL Use Case]. |
| Record duplicati trovati | [!DNL Audience Manager] rilevati record duplicati con valori di impression diversi. | Rivedi il rapporto e assicurati di non segnalare valori di utilizzo diversi per lo stesso feed di dati o segmento. |
| Valori non supportati | [!DNL Audience Manager] rilevati valori non numerici nella  [!DNL Audience Manager] colonna. | Rivedi il rapporto e assicurati di inserire solo valori numerici nella colonna [!DNL Audience Manager] . |
| Intestazioni per campi obbligatori mancanti | [!DNL Audience Manager] rilevati intestazioni di tabella mancanti per i campi obbligatori. Per [!UICONTROL Segment Level Reporting], i campi obbligatori sono: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Per [!UICONTROL Feed Level Reporting], i campi obbligatori sono: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case] | Rivedi il rapporto e assicurati che le intestazioni della tabella non siano state manomesse. |

>[!NOTE]
>La rimozione delle righe dal report di utilizzo [!DNL CSV] non ha alcun effetto sul report di utilizzo esistente. [!DNL Audience Manager] elabora solo i campi inclusi nel rapporto.

<br> 

## [!DNL CPM] Tecniche consigliate per la generazione di rapporti

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
   <p> Segnala il numero totale di impression senza utilizzare decimali. Audience Manager calcola automaticamente il CPM in base al numero totale riportato.</p><p>Se hai bisogno di segnalare 1.234.567 impression, segnalalo esattamente così. Non è necessario dividere il numero totale di impression per 1.000 per calcolare il CPM.</p><p>Le caratteristiche utilizzate per ottimizzare il contenuto web o dell’app (ottimizzazione del contenuto) utilizzando strumenti come Adobe Target o una destinazione Analytics non contribuiscono ai totali di utilizzo per i piani CPM. I provider di dati vengono generalmente compensati per l'ottimizzazione dei contenuti utilizzando piani a canone fisso.</p><p>Per ulteriori informazioni, consulta <a href="#cost-attribution">Attribuzione dei costi per i feed di dati CPM</a> . </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Attieniti all'intervallo di reporting mensile</b> </p> </td> 
   <td colname="col2"> <p>Il sistema di report si chiude dopo il 5 di ogni mese. Se non riesci a segnalare l’utilizzo di CPM entro tale data, devi aggiungere tale importo al rapporto per il mese successivo. Ad esempio, se utilizzi 1000 impression in ottobre, mantieni la scadenza del rapporto di ottobre e utilizza 1000 impression in novembre. In questo caso, segnalerai il totale di ottobre e novembre (2000) in dicembre, tra il 1° e il 5°.</p><p><b>Suggerimento</b>: Devi sempre cercare di segnalare l’utilizzo di CPM per il mese precedente tra il 1° e il 5° giorno del mese successivo.</p><p>Puoi segnalare l’utilizzo di CPM fino al 5° del nuovo mese solare, ma questo non è consigliato. La generazione di rapporti sull’utilizzo di CPM prima del 5 di ogni mese dà un tempo Audience Manager per controllare ed elaborare i dati.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Attribuzione dei costi per i feed di dati CPM {#cost-attribution}

In [!UICONTROL Audience Marketplace] è necessario indicare gli importi mensili delle impression con rapporto automatico per ciascuno dei segmenti. È consigliabile utilizzare [!DNL CPM] per la generazione di rapporti a livello di segmento, in modo che l’attribuzione dei costi venga eseguita automaticamente.

<!-- marketplace_cpm_billing.xml -->

### Riepilogo fatturazione {#billing-summary}

Devi inviare [!DNL CPM] gli importi delle impression dei feed di dati tra il primo e il quinto giorno di ciascun mese solare. Per farlo correttamente, ti consigliamo di [segnalare l’utilizzo di CPM a livello di segmento](#segment-level-report).

>[!TIP]
>Quando segnali l’utilizzo di [!DNL CPM] a livello di segmento, la sezione di reporting a livello di feed di dati viene compilata automaticamente con le quantità di utilizzo corrispondenti.

Se devi [!UICONTROL Report CPM Usage at Data Feed Level], devi compilare singolarmente tutte le impression consegnate per ciascun feed nel mese di calendario precedente e segnalarle in base all’allocazione di fatturazione descritta in questo articolo.

Dopo aver segnalato il numero [!DNL CPM] del mese di calendario precedente, [!DNL Adobe] eseguirà le seguenti operazioni:

* Crea una fattura e una fattura in base al tasso [!DNL CPM] per ogni feed di dati abbonati.
* Paga le tariffe dovute dai fornitori di dati (venditori) in base all&#39;uso segnalato [!DNL CPM].

>[!IMPORTANT]
>
>Come acquirente, tutti i totali delle impression segnalati devono essere veritieri e accurati. Se non si segnalano i totali delle impression entro il 5° giorno di ogni mese, è necessario includere i totali per il mese non segnalato del mese successivo.

<br> 

## Assegnare impressioni a livello di feed in base alle regole di qualifica delle caratteristiche {#assign-impressions}

Il caso d’uso [!UICONTROL Activation] ti consente di utilizzare le caratteristiche nel feed di dati corrispondente per creare segmenti in [Generatore di segmenti](../../../features/segments/segment-builder.md) e mappare tali segmenti su una destinazione. Gli operatori booleani [!UICONTROL AND], [!UICONTROL OR] e [!UICONTROL NOT] consentono di impostare le condizioni per la qualifica di caratteristiche e segmenti.

Quando si [Segnala l&#39;utilizzo di CPM a livello di feed di dati](#feed-level-report), è necessario allocare le impression in modo proporzionale per ciascun feed di dati, in base agli operatori [!DNL Boolean] utilizzati nelle regole di qualificazione delle caratteristiche. La tabella seguente elenca come allocare correttamente le impression per regola booleana o tipo di caratteristica.

>[!TIP]
>[Segnala l’utilizzo di CPM a livello di segmento](#segment-level-report) per eseguire automaticamente, per Audience Manager, la generazione di rapporti a livello di feed di dati.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logica o tipo di qualifica della regola </th> 
   <th colname="col2" class="entry"> Distribuzione di fatturazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> E</span> </p> </td> 
   <td colname="col2"> <p>Applica il 100% dei totali delle impression consegnati a tutte le caratteristiche del provider in un segmento basato su regole che utilizza una condizione booleana <span class="wintitle"> E</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> O</span> </p> </td> 
   <td colname="col2"> <p>Applica l'allocazione ponderata dei totali delle impression consegnate a tutte le caratteristiche del fornitore in un segmento basato su regole che utilizza una condizione booleana OR. L'allocazione ponderata è calcolata utilizzando la seguente formula:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Applica il 100% dei totali delle impression consegnati a tutte le caratteristiche del provider in un segmento basato su regole che utilizza una condizione booleana <span class="wintitle"> NOT</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmenti algoritmici </p> </td> 
   <td colname="col2"> <p>Applica il 100% dei totali delle impression consegnati a tutti i feed del provider in un segmento contenente caratteristiche algoritmiche. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Esempi di fatturazione {#billing-examples}

Gli esempi seguenti illustrano come [!DNL CPM] viene effettuata l’allocazione dell’utilizzo a livello di feed di dati.

>[!IMPORTANT]
>Consigliamo invece di [Segnalare l’utilizzo di CPM al livello di segmento](#segment-level-report), per eseguire questo processo automaticamente.

Consideriamo il seguente scenario:

![esempi di fatturazione](assets/billing-examples.png)

<br> 

### Caso 1: Segmenti con regole di qualifica AND

Questo segmento contiene 3 caratteristiche di fornitori di dati separati. Poiché la qualificazione dei segmenti si basa su una condizione [!UICONTROL AND], i visitatori devono realizzare le caratteristiche di tutti e tre i feed per qualificarsi per il segmento.

![](assets/billing-segment-and.png)

Con una condizione [!UICONTROL AND], devi assegnare il 100% delle impression ricevute durante il mese a tutti e tre i provider di dati. Nella sezione [!UICONTROL Audience Marketplace > Payables] puoi accreditare ogni provider con 1.000.000 impression.

Questo esempio si applica ai segmenti che utilizzano operatori [!DNL Boolean] [!UICONTROL NOT] o ai segmenti che contengono caratteristiche algoritmiche.

<br> 

### Caso 2: Segmenti con regole di qualifica OR

Questo segmento contiene 3 caratteristiche di fornitori di dati separati. Poiché la qualificazione dei segmenti si basa su una condizione [!UICONTROL OR], i visitatori devono realizzare almeno una delle tre caratteristiche per qualificarsi per il segmento.

Non è possibile sapere quale caratteristica è responsabile di un&#39;impression perché la qualifica si basa su una condizione [!UICONTROL OR]. Di conseguenza, nella sezione [!UICONTROL Audience Marketplace > Payables] accreditate ogni provider con un’allocazione ponderata delle impression totali, in base alla popolazione delle caratteristiche.

![segmento di fatturazione-o](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmenti con modelli e casi di utilizzo dell’attivazione

Questo esempio descrive l’attribuzione in base a due casi d’uso di Feed dati: Modeling e Activation. Nell’esempio, stiamo esaminando due provider di dati, con le seguenti informazioni:

![feed di dati](assets/feed-use-cases.png)

Nella tabella seguente, il segmento X contiene due caratteristiche, T1 e T2, con la regola del segmento T1 O T2, in cui:

* T1 è una caratteristica del feed dati A;
* T2 è una caratteristica algoritmica modellata dopo caratteristiche di terze parti da Feed dati A e Feed dati B.

Il segmento è mappato su una destinazione e vengono immesse 1.000.000 impression per questo segmento in un mese, utilizzando [Reporting a livello di segmento](#segment-level-report).

Di queste 1.000.000 impressioni:

* T1 rappresenta il 40% della popolazione del segmento, il che equivale a 400.000 impression per il feed A.
* T2 rappresenta il 60% della popolazione del segmento, il che equivale a 600.000 impression per i feed A e i feed B.

A livello di feed di dati, le impression vengono allocate in modo diverso:

* Feed di dati A riceve 600.000 impression dalla caratteristica T2 (che è modellata sulle caratteristiche dai Feed di dati A e Feed di dati B, in modo che entrambi ricevano le impression) e 400.000 impression dalla caratteristica T1 (che è una caratteristica dal Feed di dati A), per un totale di 1.000.000 impression.
* Feed dati B riceve 600.000 impression dal tratto T2 (vedi spiegazione sopra) e 0 impression dal tratto T1.

La suddivisione a colpo d&#39;occhio per feed di dati e caso d&#39;uso è la seguente:

![interruzione dei feed](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Per il caso di utilizzo della modellazione, è consigliabile segnalare l’utilizzo di CPM solo al momento dell’attivazione. Se si esegue solo un modello, ma non lo si attiva, non è necessario alcun reporting sull&#39;utilizzo.

<br> 

## Allocazione di fatturazione e impression per feed di dati a canone fisso {#billing-flat-fee}

Un feed di dati a canone fisso indica un importo fisso ogni mese, indipendentemente da quando inizia l’abbonamento o da quante impression utilizzi. Le tariffe non vengono ripartite in modo proporzionale per l’utilizzo o gli intervalli di un mese parziale. Come per la fatturazione del CPM, l&#39;Adobe genererà una fattura e ti fatturerà al tasso mensile forfettario per i feed di dati abbonati.

Ad esempio, supponiamo che tu abbia deciso di attivare alcune caratteristiche in un feed a metà mese. Sarai comunque fatturato al tasso mensile completo, indipendentemente da quando hai avviato l’abbonamento o attivato caratteristiche specifiche.
