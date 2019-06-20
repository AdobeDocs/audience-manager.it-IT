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


# Tra segmenti e sovrapposizione unità ad{#segment-to-ad-unit-overlap}

Il rapporto Segmento su unità ad unità viene visualizzato come grafico caldo che evidenzia l&#39;alta e il basso tra i segmenti Ad Units e Audience Manager.

## Caso d&#39;uso {#use-cases}

Con [!UICONTROL Segment to Ad Unit Overlap] il rapporto, puoi capire quali tipi di pubblico visita le tue proprietà web. Il rapporto mostra la sovrapposizione tra i membri [!DNL Audience Manager] dei segmenti e il numero di visitatori alle proprietà Web. Una sovrapposizione più elevata implica che molti membri di un segmento visitano la proprietà Web.

## Utilizzo del rapporto di sovrapposizione tra segmento e unità ad unità {#using-the-report}

Usate i **[!UICONTROL Top N Ad Units]** controlli e **[!UICONTROL Top N Segments]** per selezionare il numero desiderato di unità e segmenti per la sovrapposizione. Potete selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza i **controlli Intervallo** giorno e **Data mediante** per regolare l&#39;intervallo di look-back. I periodi di look-back di 7 giorni e 30 giorni sono disponibili solo per le date domenica.

Utilizzate le **[!UICONTROL Segment Name]** caselle e **[!UICONTROL Ad Unit]** le caselle per filtrare i segmenti e le unità di annunci.

>[!IMPORTANT]
>
>Quando abilitate [!UICONTROL Audience Optimization for Publishers], dovete includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel Passaggio 3 di [Importa file di dati DFP in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In tal modo, assicuratevi che il report contenga la proprietà Web come [!UICONTROL Ad Unit] invece [!UICONTROL Ad Unit ID]della proprietà.

## Interpretazione dei risultati {#interpreting-results}

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
   <td colname="col2"> <p>Il numero di visitatori unici che sono stati visti in tempo reale per l'intervallo di tempo specificato e che sono stati qualificati per il segmento nel momento in cui sono stati visti <span class="keyword"> da Audience Manager</span>. </p> </td> 
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
   <td colname="col2"> <p>La sovrapposizione tra le popolazioni di annunci e segmenti. Si tratta del <span class="wintitle"> Conteggio</span>unificato di sovrapposizione, espresso come percentuale del <span class="wintitle"> segmento Tempo reale segmento</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

