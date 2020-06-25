---
description: Il rapporto Segment to Ad Unit Overlap (Segmento su unità annuncio) viene visualizzato come grafico a caldo che evidenzia sovrapposizioni elevate e basse tra le unità annuncio e  segmenti Audience Manager.
seo-description: Il rapporto Segment to Ad Unit Overlap (Segmento su unità annuncio) viene visualizzato come grafico a caldo che evidenzia sovrapposizioni elevate e basse tra le unità annuncio e  segmenti Audience Manager.
seo-title: Sovrapposizione segmento a unità annuncio
solution: Audience Manager
title: Sovrapposizione segmento a unità annuncio
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---


# Sovrapposizione segmento a unità annuncio{#segment-to-ad-unit-overlap}

Il rapporto Segment to Ad Unit Overlap (Segmento su unità annuncio) viene visualizzato come grafico a caldo che evidenzia sovrapposizioni elevate e basse tra le unità annuncio e  segmenti Audience Manager.

## Caso d&#39;uso {#use-cases}

Con il [!UICONTROL Segment to Ad Unit Overlap] rapporto puoi capire quali tipi di pubblico visitano le tue proprietà web. Il rapporto mostra la sovrapposizione tra i membri dei [!DNL Audience Manager] segmenti e il numero di visitatori delle proprietà Web. Una sovrapposizione più elevata indica che molti membri di un segmento visitano la proprietà Web.

## Utilizzo del report Segmento per l&#39;overlap delle unità di annuncio {#using-the-report}

Utilizzate i controlli **[!UICONTROL Top N Ad Units]** e **[!UICONTROL Top N Segments]** per selezionare il numero desiderato di unità e segmenti di annuncio per la sovrapposizione. Potete selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza i controlli Intervallo **** giorno e **Passaggio** data per regolare l’intervallo di look-back. I periodi di lookback di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizzate le **[!UICONTROL Segment Name]** caselle e le **[!UICONTROL Ad Unit]** caselle per filtrare segmenti e unità annuncio.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel Passaggio 3 di [Importa file di dati DFP in  Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). A questo scopo, assicuratevi che nel rapporto sia indicata la proprietà Web come [!UICONTROL Ad Unit] anziché come [!UICONTROL Ad Unit ID].

## Interpretazione dei risultati {#interpreting-results}

Il tuo [!UICONTROL Segment to Ad Unit Overlap] rapporto potrebbe essere simile a quello riportato di seguito. Passate il puntatore del mouse sopra una cella per ottenere ulteriori informazioni su tale sovrapposizione. Vedere le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

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
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, questo può essere uno dei vostri siti Web o un articolo sul vostro sito Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio delle analisi in tempo reale del segmento</span> </p> </td> 
   <td colname="col2"> <p>Il numero di visitatori univoci visti in tempo reale per l'intervallo di tempo specificato e qualificati per il segmento nel momento in cui sono stati visti da <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio Uniche Unità Annunci</span> </p> </td> 
   <td colname="col2"> <p>Numero di visitatori per questa specifica unità pubblicitaria. Queste informazioni vengono estratte dai registri DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Sovrapponi numero di uniche</span> </p> </td> 
   <td colname="col2"> <p>I membri del segmento esposti all’elemento dell’unità annuncio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra le popolazioni di unità annuncio e segmento. Questo è il conteggio <span class="wintitle"> delle</span>sovrapposizioni, espresso come percentuale delle <span class="wintitle"> analisi in tempo reale</span>del segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

