---
description: Il rapporto di sovrapposizione da segmento ad unità annuncio viene visualizzato come un grafico a caldo che evidenzia le sovrapposizioni alte e basse tra le unità annuncio e i segmenti di Audience Manager.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: Sovrapposizione di segmenti e unità annuncio
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# Sovrapposizione di segmenti e unità annuncio{#segment-to-ad-unit-overlap}

Il rapporto di sovrapposizione da segmento ad unità annuncio viene visualizzato come un grafico a caldo che evidenzia le sovrapposizioni alte e basse tra le unità annuncio e i segmenti di Audience Manager.

## Caso d&#39;uso {#use-cases}

Con il rapporto [!UICONTROL Segment to Ad Unit Overlap], puoi capire quali tipi di pubblico visitano le tue proprietà web. Nel report viene visualizzata la sovrapposizione tra i membri dei segmenti [!DNL Audience Manager] e il numero di visitatori delle proprietà Web. Una sovrapposizione più elevata significa che molti membri di un segmento visitano la tua proprietà web.

## Utilizzo del rapporto di sovrapposizione segmento-unità annuncio {#using-the-report}

Utilizzare i controlli **[!UICONTROL Top N Ad Units]** e **[!UICONTROL Top N Segments]** per selezionare il numero desiderato di unità e segmenti di annunci per la sovrapposizione. Puoi selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza i controlli **Intervallo giorni** e **Da data a** per modificare l&#39;intervallo di look-back. I periodi di lookback di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizzare le caselle **[!UICONTROL Segment Name]** e **[!UICONTROL Ad Unit]** per filtrare segmenti e unità di annunci.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel passaggio 3 di [Importare i file di dati di Google Ad Manager (precedentemente DFP) nell&#39;Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo si assicura che il report specifichi la proprietà Web come [!UICONTROL Ad Unit] invece di [!UICONTROL Ad Unit ID].

## Interpretazione dei risultati {#interpreting-results}

Il report [!UICONTROL Segment to Ad Unit Overlap] potrebbe essere simile a quello riportato di seguito. Passa il cursore del mouse su una cella per ottenere ulteriori informazioni su quella particolare sovrapposizione. Per ulteriori informazioni, consulta la descrizione nella tabella seguente il rapporto di esempio.

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
   <td colname="col1"> <p><span class="wintitle"> unità annuncio </span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, può trattarsi di uno dei tuoi siti web o di un articolo sul tuo sito web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Numero Univoci In Tempo Reale Del Segmento <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>Numero di visitatori univoci visualizzati in tempo reale per l'intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visualizzati dall'Audience Manager <span class="keyword"></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Numero Univoci Unità Annuncio</span> </p> </td> 
   <td colname="col2"> <p>Il numero di visitatori per questa specifica unità pubblicitaria. Queste informazioni vengono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Numero Unique Di Sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>I membri del segmento esposti all’elemento dell’unità pubblicitaria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra le popolazioni di unità di annunci e segmenti. Conteggio Unique di Sovrapposizione <span class="wintitle"></span>, espresso come percentuale del segmento <span class="wintitle"> Unique in tempo reale</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
