---
description: La sezione di reporting sul gruppo di test restituisce informazioni sulle conversioni del gruppo di test, consentendo un facile confronto dell'efficacia del segmento di test. Per la visualizzazione dei dati sono disponibili numerosi filtri e dimensioni.
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: Reporting sui gruppi di test
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Reporting sui gruppi di test {#test-group-reporting}

La sezione di reporting sul gruppo di test restituisce informazioni sulle conversioni del gruppo di test, consentendo un facile confronto dell&#39;efficacia del segmento di test. Per la visualizzazione dei dati sono disponibili numerosi filtri e dimensioni.

[!UICONTROL Audience Lab] restituisce informazioni di reporting dettagliate per i segmenti di test creati e consente di salvare i dati di reporting come file [!DNL CSV]. È possibile selezionare tra **[!UICONTROL Aggregate Reporting]** e **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** restituisce i numeri assoluti per i segmenti di test. **[!UICONTROL Trend Reporting]** restituisce un grafico della tendenza *in un periodo specifico*. Quattro schede consentono di personalizzare i rapporti:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Tasso di conversione popolazione <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce la percentuale di dispositivi appartenenti a un particolare segmento di test che sono stati convertiti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> convertitori</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce il numero di dispositivi che hanno presentato le caratteristiche di conversione selezionate nei gruppi di test. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Guarda questo video</a> per scoprire come creare caratteristiche di conversione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> conversioni totali</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce il numero di conversioni generate dai segmenti di test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Popolazioni segmento di prova</span></b> </p> </td> 
   <td colname="col2"> <p>Restituisce il numero di dispositivi appartenenti ai segmenti di test. Consente di passare da <b><span class="uicontrol"> popolazione totale</span></b> a <b><span class="uicontrol"> popolazione in tempo reale</span></b>. La differenza è spiegata nelle <a href="../../faq/faq-reporting.md"> Domande frequenti sul reporting</a>. </p> </td>
  </tr>
 </tbody>
</table>

Puoi selezionare una caratteristica di conversione specifica per la quale generare il rapporto oppure puoi selezionare tutte le caratteristiche combinate. È possibile definire un intervallo di date per il quale le informazioni devono essere restituite ed esportare il report come file [!DNL CSV].

>[!NOTE]
>
>* Il reporting per un gruppo di test verrà popolato il giorno successivo alla data di inizio.
>* Una conversione viene conteggiata solo per un dispositivo dopo la data di inizio di un test e dopo che il dispositivo è stato aggiunto a un segmento di test. Se si verifica una conversione per tale dispositivo prima che gli venga assegnato un gruppo di test, la conversione non verrà conteggiata.

Un grafico **[!UICONTROL Aggregate Reporting]** restituito potrebbe essere simile al seguente:

![](assets/aggregate-reporting.PNG)

Un grafico **[!UICONTROL Trend Reporting]** restituito potrebbe essere simile al seguente. Selezionare **[!UICONTROL Normalized]** nella casella di controllo se si desidera ignorare i numeri assoluti e concentrarsi semplicemente sulle tendenze dei segmenti di test.

![](assets/trend-reporting.PNG)
