---
description: Il rapporto di sovrapposizione da segmento ad unità annuncio viene visualizzato come un grafico a caldo che evidenzia le sovrapposizioni alte e basse tra le unità annuncio e i segmenti di Audience Manager.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: Sovrapposizione di segmenti su unità annunci
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Sovrapposizione di segmenti su unità annunci{#segment-to-ad-unit-overlap}

Il rapporto di sovrapposizione da segmento ad unità annuncio viene visualizzato come un grafico a caldo che evidenzia le sovrapposizioni alte e basse tra le unità annuncio e i segmenti di Audience Manager.

## Caso d&#39;uso {#use-cases}

Con il [!UICONTROL Segment to Ad Unit Overlap] rapporto, puoi capire quali tipi di pubblico visitano le tue proprietà web. Il rapporto mostra la sovrapposizione tra i membri del [!DNL Audience Manager] segmenti e il numero di visitatori delle proprietà web. Una sovrapposizione più elevata significa che molti membri di un segmento visitano la tua proprietà web.

## Utilizzo del rapporto di sovrapposizione segmento-unità annuncio {#using-the-report}

Utilizza il **[!UICONTROL Top N Ad Units]** e **[!UICONTROL Top N Segments]** per selezionare il numero desiderato di unità e segmenti di annunci per la sovrapposizione. Puoi selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza il **Intervallo di giorni** e **Data fino a** per regolare l&#39;intervallo di look-back. I periodi di lookback di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizza il **[!UICONTROL Segment Name]** e **[!UICONTROL Ad Unit]** caselle per filtrare segmenti e unità di annunci.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel passaggio 3 di [Importare file di dati di Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo, assicurerai che il rapporto descriva nei dettagli la proprietà web come [!UICONTROL Ad Unit] invece del [!UICONTROL Ad Unit ID].

## Interpretazione dei risultati {#interpreting-results}

Il tuo [!UICONTROL Segment to Ad Unit Overlap] Il rapporto potrebbe essere simile a quello riportato di seguito. Passa il cursore del mouse su una cella per ottenere ulteriori informazioni su quella particolare sovrapposizione. Per ulteriori informazioni, consulta la descrizione nella tabella seguente il rapporto di esempio.

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
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, può trattarsi di uno dei tuoi siti web o di un articolo sul tuo sito web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio Univoci In Tempo Reale Del Segmento</span> </p> </td> 
   <td colname="col2"> <p>Il numero di visitatori univoci visualizzati in tempo reale per l’intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visualizzati da <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio Univoci Dell’Unità Annuncio</span> </p> </td> 
   <td colname="col2"> <p>Il numero di visitatori per questa specifica unità pubblicitaria. Queste informazioni vengono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio Univoci Di Sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>I membri del segmento esposti all’elemento dell’unità pubblicitaria. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra le popolazioni di unità di annunci e segmenti. Questo è il <span class="wintitle"> Conteggio Univoci Di Sovrapposizione</span>, espresso come percentuale del <span class="wintitle"> Univoci segmento in tempo reale</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
