---
description: Il rapporto Segmento su unità ad unità viene visualizzato come grafico caldo che evidenzia l'alta e il basso tra i segmenti Ad Units e Audience Manager.
seo-description: Il rapporto Segmento su unità ad unità viene visualizzato come grafico caldo che evidenzia l'alta e il basso tra i segmenti Ad Units e Audience Manager.
seo-title: Tra segmenti e sovrapposizione unità ad
solution: Audience Manager
title: Tra segmenti e sovrapposizione unità ad
uuid: aaa 20163-58 aa -42 c 9-8 f 72-a 1 dfb 0 d 20 e 57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment to Ad Unit Overlap{#segment-to-ad-unit-overlap}

Il rapporto Segmento su unità ad unità viene visualizzato come grafico caldo che evidenzia l'alta e il basso tra i segmenti Ad Units e Audience Manager.

## Caso d'uso {#use-cases}

With the [!UICONTROL Segment to Ad Unit Overlap] report, you can understand which audiences visit your web properties. The report displays the overlap between members of your [!DNL Audience Manager] segments and the number of visitors to your web properties. Una sovrapposizione più elevata implica che molti membri di un segmento visitano la proprietà Web.

## Using the Segment to Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Ad Units]** and **[!UICONTROL Top N Segments]** controls to select your desired number of ad units and segments for the overlap. Potete selezionare un numero massimo di 100 elementi per ciascuno.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. I periodi di look-back di 7 giorni e 30 giorni sono disponibili solo per le date domenica.

Use the **[!UICONTROL Segment Name]** and the **[!UICONTROL Ad Unit]** boxes to filter any of segments and ad units.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment to Ad Unit Overlap] Il rapporto potrebbe essere simile a quello di seguito. Passa il cursore su una cella per ottenere ulteriori informazioni su quella particolare sovrapposizione. Vedere descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unità annuncio </span> </p> </td> 
   <td colname="col2"> <p>Nome dell'elemento inventario. Ad esempio, questo può essere uno dei vostri siti Web o un articolo sul sito Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio unificazioni tempo reale</span> </p> </td> 
   <td colname="col2"> <p>The number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio unitario unità pubblicitaria</span> </p> </td> 
   <td colname="col2"> <p>Numero di visitatori per questa specifica unità di annunci. Queste informazioni vengono estratte dai registri DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio unificazioni sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>I membri del segmento che sono stati esposti all'elemento dell'unità pubblicitaria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra le popolazioni di annunci e segmenti. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Segment Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

