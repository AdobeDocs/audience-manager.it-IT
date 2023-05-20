---
description: Il rapporto Sovrapposizione unità annuncio viene visualizzato come un grafico a caldo che evidenzia le sovrapposizioni alte e basse tra le unità annuncio.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: Sovrapposizione di unità annunci
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# Sovrapposizione di unità annunci{#ad-unit-overlap}

Il **[!UICONTROL Ad Unit Overlap]** Il rapporto viene visualizzato come un grafico a caldo che evidenzia le sovrapposizioni alte e basse tra le unità annuncio.

## Caso d&#39;uso {#use-cases}

Con il **[!UICONTROL Ad Unit Overlap]** rapporto, puoi ottenere informazioni approfondite su dove il pubblico si sovrappone tra le proprietà web. Il rapporto considera le 100 proprietà correlate principali e mostra la sovrapposizione tra di esse.

## Utilizzo del rapporto di sovrapposizione unità annuncio {#using-the-report}

Utilizza il **[!UICONTROL Top N Base Ad Units]** e **[!UICONTROL Top N Overlapping Ad Units]** per selezionare il numero desiderato di unità pubblicitarie per la sovrapposizione. Puoi selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza il **Intervallo di giorni** e **Data fino a** per regolare l&#39;intervallo di look-back. I periodi di lookback di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizza il **[!UICONTROL Base Ad Unit]** e **[!UICONTROL Overlap Ad Unit]** controlli per selezionare quale unità pubblicitaria si desidera visualizzare nel rapporto di sovrapposizione.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel passaggio 3 di [Importare file di dati di Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo, assicurerai che il rapporto descriva nei dettagli la proprietà web come [!UICONTROL Ad Unit] invece del [!UICONTROL Ad Unit ID].

## Interpretazione dei risultati {#interpreting-results}

Il tuo [!UICONTROL Ad Unit Overlap] Il rapporto potrebbe essere simile a quello riportato di seguito. Passa il cursore del mouse su una cella per ottenere ulteriori informazioni su quella particolare sovrapposizione. Per ulteriori informazioni, consulta la descrizione nella tabella seguente il rapporto di esempio.

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
   <td colname="col1"> <p><span class="wintitle"> Sovrapposizione unità annunci</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, può trattarsi di uno dei tuoi siti web o di un articolo sul tuo sito web. Nell'immagine qui sopra, le unità di base sono gli articoli da 9 a 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unità annuncio base</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, può trattarsi di uno dei tuoi siti web o di un articolo sul tuo sito web. Nell'immagine qui sopra, le unità di base sono gli articoli da 1 a 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio Univoci Di Sovrapposizione Degli Annunci</span> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che hanno visitato gli elementi dell'unità pubblicitaria 9 - 18. Queste informazioni vengono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio Univoci Unità Annuncio Di Base</span> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che hanno visitato gli elementi dell’unità pubblicitaria da 1 a 8. Queste informazioni vengono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio Univoci Di Sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato un <span class="wintitle"> Unità annuncio base</span> e <span class="wintitle"> Sovrapposizione unità annunci</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato un <span class="wintitle"> Unità annuncio base</span> e <span class="wintitle"> Sovrapposizione unità annunci</span>. Questo è il <span class="wintitle"> Conteggio Univoci Di Sovrapposizione</span>, espresso come percentuale del <span class="wintitle"> Unità annuncio base</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
