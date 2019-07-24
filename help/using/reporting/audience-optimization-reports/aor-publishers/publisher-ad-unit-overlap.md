---
description: Il rapporto di sovrapposizione Unità ad unità viene visualizzato come grafico caldo che evidenzia l'alta e il basso tra le unità ad unità.
seo-description: Il rapporto di sovrapposizione Unità ad unità viene visualizzato come grafico caldo che evidenzia l'alta e il basso tra le unità ad unità.
seo-title: Sovrapposizione unità ad
solution: Audience Manager
title: Sovrapposizione unità ad
uuid: e 4467 e 81-acbf -474 e-b 501-89 d 57395651 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ad Unit Overlap{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** Il rapporto viene visualizzato come grafico caldo che evidenzia l'alta e il basso tra le unità ad unità.

## Caso d'uso {#use-cases}

With the **[!UICONTROL Ad Unit Overlap]** report, you can gain insight into where your audience overlaps across your web properties. Il rapporto considera le 100 proprietà principali correlate e mostra la sovrapposizione tra di essi.

## Using the Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Base Ad Units]** and **[!UICONTROL Top N Overlapping Ad Units]** controls to select your desired number of ad units for the overlap. Potete selezionare un numero massimo di 100 elementi per ciascuno.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. I periodi di look-back di 7 giorni e 30 giorni sono disponibili solo per le date domenica.

Use the **[!UICONTROL Base Ad Unit]** and the **[!UICONTROL Overlap Ad Unit]** controls to select which of your ad units you want to display in the overlap report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Ad Unit Overlap] Il rapporto potrebbe essere simile a quello di seguito. Passa il cursore su una cella per ottenere ulteriori informazioni su quella particolare sovrapposizione. Vedere descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Sovrapposizione annunci pubblicitari</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'elemento inventario. Ad esempio, questo può essere uno dei vostri siti Web o un articolo sul sito Web. Nell'immagine sopra, le unità di base sono articoli da 9 a 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unità di base</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'elemento inventario. Ad esempio, questo può essere uno dei vostri siti Web o un articolo sul sito Web. Nell'immagine sopra, le unità di base sono articoli da 1 a 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio unificazioni unità annunci pubblicitari</span> </p> </td> 
   <td colname="col2"> <p>Numero di utenti che hanno visitato gli elementi degli annunci da 9 a 18. Queste informazioni vengono estratte dai registri DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio unificazioni unità di base</span> </p> </td> 
   <td colname="col2"> <p>Numero di utenti che hanno visitato gli elementi degli annunci da 1 a 8. Queste informazioni vengono estratte dai registri DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio unificazioni sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Base Ad Unit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
