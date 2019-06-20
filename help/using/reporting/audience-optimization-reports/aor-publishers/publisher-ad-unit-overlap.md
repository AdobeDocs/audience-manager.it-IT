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


# Sovrapposizione unità ad{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** Il rapporto viene visualizzato come grafico caldo che evidenzia l&#39;alta e il basso tra le unità ad unità.

## Caso d&#39;uso {#use-cases}

Con **[!UICONTROL Ad Unit Overlap]** il rapporto, puoi ottenere informazioni approfondite su dove il pubblico si sovrappone alle tue proprietà web. Il rapporto considera le 100 proprietà principali correlate e mostra la sovrapposizione tra di essi.

## Utilizzo del rapporto di sovrapposizione unità annuncio {#using-the-report}

Usate i **[!UICONTROL Top N Base Ad Units]** controlli e **[!UICONTROL Top N Overlapping Ad Units]** per selezionare il numero desiderato di unità ad hoc per la sovrapposizione. Potete selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza i **controlli Intervallo** giorno e **Data mediante** per regolare l&#39;intervallo di look-back. I periodi di look-back di 7 giorni e 30 giorni sono disponibili solo per le date domenica.

Utilizzate i **[!UICONTROL Base Ad Unit]****[!UICONTROL Overlap Ad Unit]** controlli e i controlli per selezionare le unità da visualizzare nel rapporto di sovrapposizione.

>[!IMPORTANT]
>
>Quando abilitate [!UICONTROL Audience Optimization for Publishers], dovete includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel Passaggio 3 di [Importa file di dati DFP in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In tal modo, assicuratevi che il report contenga la proprietà Web come [!UICONTROL Ad Unit] invece [!UICONTROL Ad Unit ID]della proprietà.

## Interpretazione dei risultati {#interpreting-results}

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
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato un <span class="wintitle"> 'unità ad annuncio</span> e <span class="wintitle"> di sovrapposizione</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato un <span class="wintitle"> 'unità ad annuncio</span> e <span class="wintitle"> di sovrapposizione</span>. Si tratta del <span class="wintitle"> Conteggio</span>unificato, espresso come percentuale dell' <span class="wintitle"> Unità Ad annuncio</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
