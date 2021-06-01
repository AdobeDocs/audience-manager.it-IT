---
description: Il rapporto di sovrapposizione unità annunci viene visualizzato come un grafico a caldo che evidenzia sovrapposizioni alte e basse tra le unità annunci.
seo-description: Il rapporto di sovrapposizione unità annunci viene visualizzato come un grafico a caldo che evidenzia sovrapposizioni alte e basse tra le unità annunci.
seo-title: Sovrapposizione di unità annunci
solution: Audience Manager
title: Sovrapposizione di unità annunci
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Rapporti di Audience Optimization
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 3%

---

# Sovrapposizione di unità annunci{#ad-unit-overlap}

Il rapporto **[!UICONTROL Ad Unit Overlap]** viene visualizzato come un grafico a caldo che evidenzia sovrapposizioni elevate e basse tra le unità annunci.

## Caso d&#39;uso {#use-cases}

Con il rapporto **[!UICONTROL Ad Unit Overlap]** puoi ottenere informazioni approfondite su dove il pubblico si sovrappone tra le tue proprietà web. Il rapporto considera le tue 100 proprietà correlate principali e mostra la sovrapposizione tra di esse.

## Utilizzo del rapporto di sovrapposizione unità annunci {#using-the-report}

Utilizza i controlli **[!UICONTROL Top N Base Ad Units]** e **[!UICONTROL Top N Overlapping Ad Units]** per selezionare il numero desiderato di unità pubblicitarie per la sovrapposizione. Puoi selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza i controlli **Intervallo giorno** e **Date Through** per regolare l&#39;intervallo di look-back. I periodi di look-back di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizza i controlli **[!UICONTROL Base Ad Unit]** e **[!UICONTROL Overlap Ad Unit]** per selezionare le unità pubblicitarie da visualizzare nel rapporto di sovrapposizione.

>[!IMPORTANT]
>
>Quando abiliti [!UICONTROL Audience Optimization for Publishers], devi includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel passaggio 3 di [Importa file di dati Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo, assicurati che il report descriva la proprietà Web come [!UICONTROL Ad Unit] invece del [!UICONTROL Ad Unit ID].

## Interpretazione dei risultati {#interpreting-results}

Il rapporto [!UICONTROL Ad Unit Overlap] potrebbe essere simile a quello riportato di seguito. Passa il puntatore del mouse su una cella per ottenere ulteriori informazioni su tale sovrapposizione. Vedi le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto di esempio.

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
   <td colname="col1"> <p><span class="wintitle"> Unità annunci di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, questo può essere uno dei tuoi siti web o un articolo sul tuo sito web. Nell'immagine qui sopra, le unità di annunci di base sono gli articoli da 9 a 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unità annunci di base</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, questo può essere uno dei tuoi siti web o un articolo sul tuo sito web. Nell'immagine qui sopra, le unità di annunci di base sono gli articoli da 1 a 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio degli Unici Unici Univoci Di Sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che hanno visitato gli elementi dell'unità annunci da 9 a 18. Queste informazioni sono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio degli Unici Unici Unici Dell'Annuncio Base</span> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che hanno visitato gli elementi dell'unità annunci da 1 a 8. Queste informazioni sono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio degli univoci di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato una <span class="wintitle"> unità annunci di base</span> e una <span class="wintitle"> unità annunci di sovrapposizione</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato una <span class="wintitle"> unità annunci di base</span> e una <span class="wintitle"> unità annunci di sovrapposizione</span>. Si tratta del <span class="wintitle"> conteggio degli univoci di sovrapposizione</span>, espresso come percentuale dell' <span class="wintitle"> unità annunci di base</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
