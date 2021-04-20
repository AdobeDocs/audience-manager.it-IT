---
description: Il rapporto di sovrapposizione segmento-unità annunci viene visualizzato come un grafico a caldo che evidenzia sovrapposizioni alte e basse tra le unità annunci e i segmenti di Audience Manager.
seo-description: Il rapporto di sovrapposizione segmento-unità annunci viene visualizzato come un grafico a caldo che evidenzia sovrapposizioni alte e basse tra le unità annunci e i segmenti di Audience Manager.
seo-title: Sovrapposizione di segmenti su unità annunci
solution: Audience Manager
title: Sovrapposizione di segmenti su unità annunci
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# Sovrapposizione di segmenti su unità annunci{#segment-to-ad-unit-overlap}

Il rapporto di sovrapposizione segmento-unità annunci viene visualizzato come un grafico a caldo che evidenzia sovrapposizioni alte e basse tra le unità annunci e i segmenti di Audience Manager.

## Caso d&#39;uso {#use-cases}

Con il rapporto [!UICONTROL Segment to Ad Unit Overlap] puoi capire quali tipi di pubblico visitano le tue proprietà web. Nel rapporto viene visualizzata la sovrapposizione tra i membri dei segmenti [!DNL Audience Manager] e il numero di visitatori delle proprietà web. Una sovrapposizione più elevata significa che molti membri di un segmento visitano la tua proprietà web.

## Utilizzo del rapporto di sovrapposizione segmento-unità annunci {#using-the-report}

Utilizza i controlli **[!UICONTROL Top N Ad Units]** e **[!UICONTROL Top N Segments]** per selezionare il numero desiderato di unità e segmenti di annunci per la sovrapposizione. Puoi selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza i controlli **Intervallo giorno** e **Date Through** per regolare l&#39;intervallo di look-back. I periodi di look-back di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizza le caselle **[!UICONTROL Segment Name]** e **[!UICONTROL Ad Unit]** per filtrare segmenti e unità di annunci.

>[!IMPORTANT]
>
>Quando abiliti [!UICONTROL Audience Optimization for Publishers], devi includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel passaggio 3 di [Importa file di dati Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo, assicurati che il report descriva la proprietà Web come [!UICONTROL Ad Unit] invece del [!UICONTROL Ad Unit ID].

## Interpretazione dei risultati {#interpreting-results}

Il rapporto [!UICONTROL Segment to Ad Unit Overlap] potrebbe essere simile a quello riportato di seguito. Passa il puntatore del mouse su una cella per ottenere ulteriori informazioni su tale sovrapposizione. Vedi le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto di esempio.

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
   <td colname="col1"> <p><span class="wintitle"> Unità annunci  </span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, questo può essere uno dei tuoi siti web o un articolo sul tuo sito web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio degli univoci in tempo reale del segmento</span> </p> </td> 
   <td colname="col2"> <p>Il numero di visitatori unici visti in tempo reale per l'intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti da <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio degli Unici Unici Annunci</span> </p> </td> 
   <td colname="col2"> <p>Il numero di visitatori per questa specifica unità pubblicitaria. Queste informazioni sono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio degli univoci di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>I membri del segmento esposti all’elemento dell’unità dell’annuncio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra le popolazioni di unità di annunci e segmenti. Si tratta del <span class="wintitle"> conteggio delle univoche di sovrapposizione</span>, espresso come percentuale del <span class="wintitle"> segmento Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
