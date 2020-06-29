---
description: ' gli acquirenti di dati Audience Marketplace accettano di segnalare tutte le impression pubblicitarie servite utilizzando le caratteristiche contenute nel feed di dati a un costo per migliaia di annunci (CPM). L’utilizzo di CPM è previsto il 5° giorno di ogni mese di calendario e include i dati per il mese precedente. Gli abbonati a tariffa fissa non devono segnalare l''utilizzo.'
seo-description: ' gli acquirenti di dati Audience Marketplace accettano di segnalare tutte le impression pubblicitarie servite utilizzando le caratteristiche contenute nel feed di dati a un costo per migliaia di annunci (CPM). L’utilizzo di CPM è previsto il 5° giorno di ogni mese di calendario e include i dati per il mese precedente. Gli abbonati a tariffa fissa non devono segnalare l''utilizzo.'
seo-title: Fatturazione per gli acquirenti di feed di dati
solution: Audience Manager
title: Fatturazione per gli acquirenti di feed di dati
keywords: Segment-level Reporting, segment-level, segment level
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '2027'
ht-degree: 0%

---


# Fatturazione per gli acquirenti di feed di dati {#billing-for-data-feed-buyers}

 gli acquirenti di dati Audience Marketplace accettano di segnalare tutte le impression pubblicitarie servite utilizzando le caratteristiche contenute nel feed di dati a un prezzo per migliaia di annunci ([!DNL CPM]). [!DNL CPM] l’utilizzo è previsto il 5° giorno di ogni mese di calendario e include i dati per il mese precedente. Gli abbonati a tariffa fissa non devono segnalare l&#39;utilizzo.

<br> 

## Come segnalare l’utilizzo di CPM {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] gli acquirenti di dati accettano di segnalare tutte le impression pubblicitarie servite utilizzando le caratteristiche contenute nel feed di dati a un costo per migliaia di annunci ([!DNL CPM]). [!DNL CPM] l’utilizzo è previsto il 5 giorno di ogni mese del calendario e include i dati per il mese precedente. Gli abbonati a tariffa fissa non devono segnalare l&#39;utilizzo.

[!UICONTROL Audience Marketplace] offre due modi per segnalare l&#39; [!DNL CPM] utilizzo:

* **Report** a livello di segmento: questo è il metodo di reporting [!DNL CPM] dell&#39;utilizzo consigliato. Quando si segnala [!DNL CPM] l’utilizzo a livello di segmento, la sezione di reporting a livello di feed di dati viene compilata automaticamente con gli importi di utilizzo corrispondenti, in base agli algoritmi descritti in [Attribuzione costi per feed](#cost-attribution)dati CPM.
* **Report** a livello di feed di dati: questo metodo richiede di segnalare singolarmente l’ [!DNL CPM] utilizzo di ciascun feed di dati, in base agli algoritmi descritti in [Attribuzione costi per feed](#cost-attribution)dati CPM. Tuttavia, questo metodo è più noioso e incline agli errori rispetto alla generazione di rapporti a livello di segmento.

<br> 

## Report sull’utilizzo CPM a livello di segmento {#segment-level-report}

La [!UICONTROL Segment Usage] scheda consente di generare rapporti sull&#39;utilizzo a livello di segmento, mostrando i segmenti raggruppati per le destinazioni a cui sono mappati.

Dopo aver segnalato [!DNL CPM] l’utilizzo a livello di segmento, [!UICONTROL Audience Marketplace] assegna automaticamente i dati corrispondenti al corretto utilizzo, in base all’Attribuzione [costi per feed](#cost-attribution)dati CPM.

Per segnalare [!DNL CPM] l’utilizzo a livello di segmento:

1. Vai a **[!UICONTROL Audience Marketplace > Payables]**.
1. Selezionate la **[!UICONTROL Segment Usage]** scheda.
1. Compila l’utilizzo per i tuoi segmenti. Puoi utilizzare la [!UICONTROL Search] casella per filtrare i segmenti se devi solo segnalare l’utilizzo di alcuni di essi.
1. Clic **[!UICONTROL Edit Segments Usage]**.
1. Immettete il valore [!DNL CPM] di utilizzo nella [!UICONTROL Usage] colonna.
1. Fai clic **[!UICONTROL Save]** al termine e controlla la finestra di dialogo di conferma.

   ![verify-segment-usage](assets/confirm-segment-usage.png)

1. Clic **[!UICONTROL Confirm]**.

Vedi anche la nostra dimostrazione video su come puoi segnalare l’utilizzo a livello di segmento:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Report sull&#39;utilizzo CPM a livello di feed di dati {#feed-level-report}

La generazione di rapporti a livello di feed di dati è un processo più tedioso e suscettibile di errori, in quanto è necessario calcolare singolarmente [!DNL CPM] l&#39;utilizzo di ciascun feed di dati. È invece consigliabile [segnalare l’utilizzo di CPM a livello](#segment-level-report) di segmento.

Per segnalare [!DNL CPM] l’utilizzo a livello di segmento:

1. Vai a **[!UICONTROL Audience Marketplace > Payables]**.
2. Selezionate la **[!UICONTROL Feed Usage]** scheda.
3. Utilizzate la [!UICONTROL Search] casella per filtrare i feed di dati e identificare quelli per i quali è necessario segnalare l&#39;utilizzo.
4. Clic **[!UICONTROL Edit Feeds Usage]**.
5. Calcolate l&#39; [!DNL CPM] utilizzo di ciascun feed di dati in base all&#39; [Attribuzione costi per i feed](#cost-attribution)di dati CPM e immettetelo nella [!UICONTROL Usage] colonna.
6. Fai clic **[!UICONTROL Save]** al termine e controlla la finestra di dialogo di conferma.

   ![verify-feed-usage](assets/confirm-feed-usage.png)

7. Clic **[!UICONTROL Confirm]**.

<br> 

## Generazione di rapporti in blocco

Per ridurre gli errori e il sovraccarico durante la generazione dei rapporti [!DNL CPM] di utilizzo, potete utilizzare l’opzione di reporting in blocco per scaricare un [!DNL CSV] file contenente i feed di dati e i segmenti, riempire l’utilizzo e caricarlo nuovamente in [!DNL Audience Manager]. Potete utilizzare la generazione di rapporti in massa per segnalare sia l&#39;utilizzo dei feed che quello dei segmenti.

Per aggiornare [!DNL CPM] l&#39;utilizzo in blocco:

1. Vai a **[!UICONTROL Audience Marketplace > Payables]**.
1. Selezionate la **[!UICONTROL Feed Usage]** **[!UICONTROL Segment Usage]** scheda o, a seconda del tipo di rapporto che desiderate aggiornare.
1. Fate clic **[!UICONTROL Edit Feeds Usage]** o **[!UICONTROL Edit Segments Usage]**.
1. Fate clic **[!UICONTROL download the current usage]** per essere certi di usare un file CSV valido.
1. Aprite il file sul computer e compilate il rapporto di utilizzo.
1. Fate clic **[!UICONTROL Choose a CSV file]** per caricare il rapporto di utilizzo aggiornato.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] convalida il file non appena viene caricato e vi chiede se rileva eventuali errori nel file.

<br> 

### Errori di convalida dei rapporti in blocco

| Messaggio di errore | Descrizione | Correzione |
| ------------- | -------------| -----|
| Input non valido | [!DNL Audience Manager] rilevato una modifica nello schema del [!DNL CSV] file, ad esempio colonne mancanti o modifiche ai titoli delle colonne. | Evitare di modificare la struttura della tabella. |
| Non trovato | Ad [!UICONTROL Segment Level Reporting]esempio, [!DNL Audience Manager] non è stato possibile identificare la [!UICONTROL Segment ID] combinazione e [!UICONTROL Destination ID] . Ad [!UICONTROL Feed Level Reporting]esempio, [!DNL Audience Manager] non è stato possibile identificare la [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]e [!UICONTROL Use Case] la combinazione. | Ad [!UICONTROL Segment Level Reporting]esempio, verificare la validità della [!UICONTROL Segment ID] combinazione e [!UICONTROL Destination ID] . Ad [!UICONTROL Feed Level Reporting]esempio, verificare la validità della [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]e della [!UICONTROL Use Case] combinazione. |
| Record duplicati trovati | [!DNL Audience Manager] rilevati record duplicati con valori di impression diversi. | Rivedete il rapporto e accertatevi di non riportare valori di utilizzo diversi per lo stesso feed o segmento di dati. |
| Valori non supportati | [!DNL Audience Manager] rilevati valori non numerici nella [!DNL Audience Manager] colonna. | Rivedete il rapporto e accertatevi di immettere solo valori numerici nella [!DNL Audience Manager] colonna. |
| Intestazioni per campi obbligatori mancanti | [!DNL Audience Manager] rilevate intestazioni di tabella mancanti per i campi obbligatori. Ad [!UICONTROL Segment Level Reporting]esempio, i campi obbligatori sono: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Ad [!UICONTROL Feed Level Reporting]esempio, i campi obbligatori sono: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Rivedete il rapporto e accertatevi che le intestazioni della tabella non siano state alterate. |

>[!NOTE]
>La rimozione delle righe dal rapporto sull&#39; [!DNL CSV] uso non ha alcun effetto sul rapporto sull&#39;uso esistente. [!DNL Audience Manager] elabora solo i campi inclusi nel rapporto.

<br> 

## [!DNL CPM] Tecniche consigliate per la generazione dei rapporti

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
   <td colname="col2"> <p>Per i totali di impression CPM: </p>
   <p> Segnala il numero totale di impression, senza utilizzare decimali.  Audience Manager calcola automaticamente il CPM in base al numero totale di rapporti.</p><p>Se hai bisogno di segnalare 1.234.567 impression, segnalalo esattamente così. Non è necessario dividere il numero totale di impression per 1.000 per calcolare il CPM.</p><p>Le caratteristiche utilizzate per ottimizzare il contenuto Web o dell'app (ottimizzazione del contenuto) mediante strumenti quali  Adobe Target o una destinazione Analytics  non contribuiscono ai totali di utilizzo per i piani CPM. I provider di dati vengono generalmente compensati per l'ottimizzazione dei contenuti utilizzando piani a tariffa fissa.</p><p>Per ulteriori informazioni, consulta <a href="#cost-attribution">Attribuzione dei costi per i feed</a> di dati CPM. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Attenetevi all'intervallo di reporting mensile</b> </p> </td> 
   <td colname="col2"> <p>Il sistema di report si chiude dopo il 5 di ogni mese. Se non riesci a segnalare l’utilizzo di CPM entro tale data, devi aggiungere tale importo al rapporto per il mese successivo. Ad esempio, se utilizzi 1000 impression in ottobre, non raggiungi la scadenza del rapporto di ottobre e utilizzi 1000 impression in novembre. In questo caso, segnalate il totale di ottobre e novembre (2000) in dicembre, tra il 1 e il 5.</p><p><b>Suggerimento</b>: Dovresti sempre cercare di segnalare l’utilizzo di CPM per il mese precedente tra il primo e il quinto giorno del mese successivo.</p><p>Potete segnalare l’utilizzo di CPM fino al 5° del nuovo mese di calendario, ma questo non è consigliato. La segnalazione dell’utilizzo di CPM prima del 5 di ogni mese dà  tempo ad Audience Manager di controllare ed elaborare i dati.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Attribuzione dei costi per i feed di dati CPM {#cost-attribution}

In [!UICONTROL Audience Marketplace] questo caso, devi creare rapporti con gli importi mensili delle impression, per ogni segmento. È consigliabile utilizzare i rapporti [!DNL CPM] a livello di segmento, in modo che l&#39;attribuzione dei costi venga eseguita automaticamente.

<!-- marketplace_cpm_billing.xml -->

### Riepilogo fatturazione {#billing-summary}

È necessario inviare gli importi delle impression dei feed [!DNL CPM] di dati tra il primo e il quinto giorno di ogni mese di calendario. A questo scopo, consigliamo di [segnalare l’utilizzo di CPM a livello](#segment-level-report)di segmento.

>[!TIP]
>Quando si segnala [!DNL CPM] l’utilizzo a livello di segmento, la sezione di reporting a livello di feed di dati viene compilata automaticamente con i corrispondenti importi di utilizzo.

Se necessario, [!UICONTROL Report CPM Usage at Data Feed Level]devi compilare singolarmente tutte le impression consegnate per ciascun feed nel mese di calendario precedente e segnalarle in base all&#39;allocazione di fatturazione descritta in questo articolo.

Dopo aver riportato [!DNL CPM] il numero del mese di calendario precedente, [!DNL Adobe] verrà effettuato quanto segue:

* Crea una fattura e una fattura in base alla [!DNL CPM] tariffa per ciascun feed di dati sottoscritto.
* Pagare le tariffe (venditori) dovute in base all&#39; [!DNL CPM] uso indicato.

>[!IMPORTANT]
>
>Come acquirente, tutti i totali di impression segnalati devono essere veri e precisi. Se non si segnalano i totali delle impression entro il 5° giorno di ogni mese, è necessario includere i totali per il mese non segnalato del mese successivo.

<br> 

## Assegna impression a livello di feed in base alle regole di qualifica delle caratteristiche {#assign-impressions}

Il [!UICONTROL Activation] caso d’uso consente di utilizzare le caratteristiche nel feed di dati corrispondente per creare segmenti nel Generatore [di](../../../features/segments/segment-builder.md) segmenti e mappare tali segmenti a una destinazione. Gli operatori booleani [!UICONTROL AND], [!UICONTROL OR]e [!UICONTROL NOT] consentono di impostare le condizioni per la caratteristica e la qualifica del segmento.

Quando si [segnala l&#39;utilizzo di CPM a livello](#feed-level-report)di feed di dati, è necessario allocare le impression in modo proporzionale per ciascun feed di dati, in base agli [!DNL Boolean] operatori utilizzati nelle regole di qualifica delle caratteristiche. Nella tabella seguente è illustrato come allocare correttamente le impression per regola booleana o tipo di caratteristica.

>[!TIP]
>[Segnala l’utilizzo di CPM a livello](#segment-level-report) di segmento affinché la generazione di rapporti a livello di feed di dati venga eseguita automaticamente da  Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logica o tipo di qualifica della regola </th> 
   <th colname="col2" class="entry"> Distribuzione fatturazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> AND</span> </p> </td> 
   <td colname="col2"> <p>Applicare il 100% dei totali impression forniti a tutte le caratteristiche del fornitore in un segmento basato su regole che utilizza una condizione <span class="wintitle"> AND booleana</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OR</span> </p> </td> 
   <td colname="col2"> <p>Applica l'allocazione ponderata dei totali impression consegnati a tutte le caratteristiche del fornitore in un segmento basato su regole che utilizza una condizione OR booleana. L'allocazione ponderata è calcolata utilizzando la seguente formula:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Applicare il 100% dei totali impression forniti a tutte le caratteristiche del fornitore in un segmento basato su regole che utilizza una condizione <span class="wintitle"> NOT</span> booleana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmenti algoritmici </p> </td> 
   <td colname="col2"> <p>Applica il 100% dei totali impression consegnati a tutti i feed del fornitore in un segmento contenente caratteristiche algoritmiche. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Esempi di fatturazione {#billing-examples}

Gli esempi riportati di seguito illustrano il modo in cui l&#39;allocazione [!DNL CPM] dell&#39;utilizzo viene effettuata a livello di feed di dati.

>[!IMPORTANT]
>Consigliamo invece di [segnalare l’utilizzo di CPM a livello](#segment-level-report) di segmento, affinché questo processo venga eseguito automaticamente.

Consideriamo il seguente scenario:

![esempi di fatturazione](assets/billing-examples.png)

<br> 

### Caso 1: Segmenti con regole di qualifica AND

Questo segmento contiene 3 caratteristiche di provider di dati separati. Poiché la qualifica del segmento è basata su una [!UICONTROL AND] condizione, i visitatori devono realizzare le caratteristiche di tutti e tre i feed per qualificarsi per il segmento.

![](assets/billing-segment-and.png)

In presenza di una [!UICONTROL AND] condizione, è necessario assegnare il 100% delle impression ricevute durante il mese a tutti e tre i provider di dati. Nella [!UICONTROL Audience Marketplace > Payables] sezione viene accreditato ogni provider con 1.000.000 impression.

Questo esempio si applica ai segmenti che utilizzano [!DNL Boolean] [!UICONTROL NOT] operatori o per segmenti che contengono caratteristiche algoritmiche.

<br> 

### Caso 2: Segmenti con regole di qualifica OR

Questo segmento contiene 3 caratteristiche di provider di dati separati. Poiché la qualifica del segmento è basata su una [!UICONTROL OR] condizione, i visitatori devono realizzare almeno una delle tre caratteristiche per qualificarsi per il segmento.

Non possiamo dire quale caratteristica è responsabile di un&#39;impressione perché la qualificazione è basata su una [!UICONTROL OR] condizione. Di conseguenza, nella [!UICONTROL Audience Marketplace > Payables] sezione accreditate ogni fornitore con una ripartizione ponderata delle impression totali, in base alla popolazione di caratteristiche.

![segmento di fatturazione](assets/billing-segment-or.png)

<br> 

### Caso 3: Segmenti con modelli e casi di utilizzo attivazione

Questo esempio descrive l&#39;attribuzione in base a due casi di utilizzo Feed dati: Modellazione e Attivazione. Nell&#39;esempio, stiamo esaminando due provider di dati, con le seguenti informazioni:

![feed di dati](assets/feed-use-cases.png)

Nella tabella che segue, il segmento X contiene due caratteristiche, T1 e T2, con la regola del segmento T1 O T2, dove:

* T1 è una caratteristica del feed dati A;
* T2 è una caratteristica algoritmica modellata dopo tratti di terze parti tratti da Feed dati A e Feed dati B.

Il segmento viene mappato su una destinazione e 1.000.000 impression vengono immesse per questo segmento in un mese, utilizzando [Segment-Level Reporting (Generazione rapporti a livello di segmento)](#segment-level-report).

Di queste 1.000.000 impressioni:

* T1 costituisce il 40% della popolazione del segmento, che equivale a 400.000 impression per il Feed A.
* T2 rappresenta il 60% della popolazione del segmento, che equivale a 600.000 impression per i Feed A e i Feed B.

A livello di feed di dati, le impression vengono allocate nel modo seguente:

* Feed dati A riceve 600.000 impression dalla caratteristica T2 (modellata sulle caratteristiche dei Feed dati A e Feed dati B, in modo che entrambi ricevano le impression) e 400.000 impression dalla caratteristica T1 (che è una caratteristica del Feed dati A), per un totale di 1.000.000.
* Feed dati B riceve 600.000 impression dalla caratteristica T2 (cfr. la spiegazione sopra) e 0 impressioni dalla caratteristica T1.

La suddivisione rapida per feed di dati e casi di utilizzo è la seguente:

![interruzione di corrente](assets/feed-breakdown-alt.png)

<br> 

## Allocazione fatturazione e impressione per feed di dati a tariffa fissa {#billing-flat-fee}

Un feed di dati a tariffa fissa addebita ogni mese un importo fisso, indipendentemente da quando inizia l&#39;iscrizione o da quante impression utilizzi. Le tariffe non vengono ripartite in modo proporzionale per l&#39;uso parziale dei mesi o per gli intervalli. Come per la fatturazione CPM, Adobe genererà una fattura e vi addebiterà al tasso mensile forfettario per i feed di dati sottoscritti.

Ad esempio, supponiamo che abbiate deciso di attivare alcune caratteristiche in un feed a metà del mese. L&#39;importo verrà comunque addebitato al tasso mensile completo, indipendentemente da quando è stata avviata l&#39;iscrizione o sono state attivate caratteristiche specifiche.