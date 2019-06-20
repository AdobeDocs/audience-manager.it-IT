---
description: La sezione di reporting dei gruppi di test restituisce informazioni sulle conversioni dei gruppi di test, consentendo un confronto semplice tra l'efficacia dei segmenti di test. Sono disponibili numerosi filtri e dimensioni per la visualizzazione dei dati.
seo-description: La sezione di reporting dei gruppi di test restituisce informazioni sulle conversioni dei gruppi di test, consentendo un confronto semplice tra l'efficacia dei segmenti di test. Sono disponibili numerosi filtri e dimensioni per la visualizzazione dei dati.
seo-title: Test dei rapporti di gruppo
solution: Audience Manager
title: Test dei rapporti di gruppo
topic: API DIL
uuid: 21303 c 3 e -4 c 05-4728-a 759-96 c 2 a 1 d 99 b 69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Test dei rapporti di gruppo {#test-group-reporting}

La sezione di reporting dei gruppi di test restituisce informazioni sulle conversioni dei gruppi di test, consentendo un confronto semplice tra l&#39;efficacia dei segmenti di test. Sono disponibili numerosi filtri e dimensioni per la visualizzazione dei dati.

[!UICONTROL Audience Lab] restituisce informazioni di reporting dettagliate per i segmenti di prova creati e consente di salvare i dati di reporting come [!DNL CSV] file. Potete selezionare tra **[!UICONTROL Aggregate Reporting]** e **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** restituisce i numeri assoluti per i segmenti di prova. **[!UICONTROL Trend Reporting]** restituisce un grafico della tendenza *per un periodo specifico*. Quattro schede consentono di personalizzare i rapporti:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tasso di conversione popolazione</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce la percentuale di dispositivi appartenenti a un particolare segmento di test che sono convertiti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Convertitori</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce il numero di dispositivi che hanno rivelato le caratteristiche di conversione selezionate nei gruppi di test. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Guardate questo video</a> per imparare a creare caratteristiche di conversione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Totale conversioni</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce il numero di conversioni generate dai segmenti di prova. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Test Populations Population</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce il numero di dispositivi appartenenti ai segmenti di prova. Passa dalla <b><span class="uicontrol"> popolazione totale</span></b> alla <b><span class="uicontrol"> popolazione in tempo reale</span></b>. La differenza è descritta nelle domande frequenti <a href="../../faq/faq-reporting.md"> sul rapporto</a> . </p> </td>
  </tr>
 </tbody>
</table>

Potete selezionare una caratteristica di conversione specifica per la quale generare il rapporto oppure selezionare tutte le caratteristiche combinate. Puoi definire un intervallo di date per il quale restituire le informazioni ed esportare il rapporto come [!DNL CSV] file.

>[!NOTE]
>
>* I rapporti per un gruppo di test popoleranno il giorno dopo la data di inizio.
>* Una conversione viene conteggiata solo per un dispositivo dopo la data di inizio di un test e dopo che il dispositivo è stato aggiunto a un segmento di prova. Se viene eseguita una conversione per quel dispositivo prima che gli venga assegnato un gruppo di test, la conversione non verrà conteggiata.


Un grafico restituito **[!UICONTROL Aggregate Reporting]** potrebbe presentarsi come segue:

![](assets/aggregate-reporting.PNG)

Un grafico restituito **[!UICONTROL Trend Reporting]** avrà un aspetto simile a quello riportato di seguito. Seleziona **[!UICONTROL Normalized]** nella casella di controllo se desideri ignorare i numeri assoluti e solo concentrarsi sulle tendenze dei segmenti di prova.

![](assets/trend-reporting.PNG)