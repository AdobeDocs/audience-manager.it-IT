---
description: La sezione report del gruppo di test restituisce informazioni sulle conversioni del gruppo di test, consentendo un semplice confronto dell'efficacia del segmento di test. Sono disponibili numerosi filtri e dimensioni per la visualizzazione dei dati.
seo-description: La sezione report del gruppo di test restituisce informazioni sulle conversioni del gruppo di test, consentendo un semplice confronto dell'efficacia del segmento di test. Sono disponibili numerosi filtri e dimensioni per la visualizzazione dei dati.
seo-title: Report gruppo di test
solution: Audience Manager
title: Report gruppo di test
topic: API DIL
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Report gruppo di test {#test-group-reporting}

La sezione report del gruppo di test restituisce informazioni sulle conversioni del gruppo di test, consentendo un semplice confronto dell'efficacia del segmento di test. Sono disponibili numerosi filtri e dimensioni per la visualizzazione dei dati.

[!UICONTROL Audience Lab] restituisce informazioni di reporting dettagliate per i segmenti di test creati e consente di salvare i dati di reporting come [!DNL CSV] file. Potete scegliere tra **[!UICONTROL Aggregate Reporting]** e **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** restituisce i numeri assoluti per i segmenti di test. **[!UICONTROL Trend Reporting]** restituisce un grafico della tendenza *in un periodo* specifico. Quattro schede consentono di personalizzare i rapporti:

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
   <td colname="col2"> <p>Restituisce la percentuale di dispositivi appartenenti a un particolare segmento di test, che sono stati convertiti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Convertitori</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce il numero di dispositivi che hanno mostrato le caratteristiche di conversione selezionate nei gruppi di test. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Guardate questo video</a> per apprendere come creare tratti di conversione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Totale conversioni</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce il numero di conversioni generate dai segmenti di test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Test dei segmenti</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce il numero di dispositivi appartenenti ai segmenti di test. Passa dalla popolazione <b><span class="uicontrol"> totale a quella</span></b> in tempo reale <b><span class="uicontrol"></span></b>. La differenza è spiegata nelle domande frequenti relative ai <a href="../../faq/faq-reporting.md"> rapporti</a> . </p> </td>
  </tr>
 </tbody>
</table>

È possibile selezionare una caratteristica di conversione specifica per la quale generare il rapporto oppure selezionare tutte le caratteristiche combinate. Puoi definire un intervallo di date per il quale le informazioni devono essere restituite ed esportare il rapporto come [!DNL CSV] file.

>[!NOTE]
>
>* I rapporti per un gruppo di test popoleranno il giorno dopo la data di inizio.
>* Una conversione viene conteggiata solo per un dispositivo dopo la data di inizio di un test e dopo che il dispositivo è stato aggiunto a un segmento di test. Se una conversione avviene per quel dispositivo prima che gli venga assegnato un gruppo di test, la conversione non verrà conteggiata.


Un **[!UICONTROL Aggregate Reporting]** grafico restituito potrebbe essere simile al seguente:

![](assets/aggregate-reporting.PNG)

Un **[!UICONTROL Trend Reporting]** grafico restituito potrebbe essere simile a quello riportato di seguito. Selezionare **[!UICONTROL Normalized]** nella casella di controllo se si desidera ignorare i numeri assoluti e concentrarsi semplicemente sulle tendenze dei segmenti di test.

![](assets/trend-reporting.PNG)