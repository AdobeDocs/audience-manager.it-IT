---
description: Il rapporto Sovrapposizione unità annuncio viene visualizzato come un grafico a caldo che evidenzia le sovrapposizioni alte e basse tra le unità annuncio.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: Sovrapposizione unità annuncio
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Sovrapposizione unità annuncio{#ad-unit-overlap}

Il report **[!UICONTROL Ad Unit Overlap]** viene visualizzato come grafico di calore che evidenzia sovrapposizioni alte e basse tra le unità annuncio.

## Caso d&#39;uso {#use-cases}

Con il rapporto **[!UICONTROL Ad Unit Overlap]**, puoi acquisire insight in cui il pubblico si sovrappone nelle tue proprietà web. Il rapporto considera le 100 proprietà correlate principali e mostra la sovrapposizione tra di esse.

## Utilizzo del rapporto di sovrapposizione unità annuncio {#using-the-report}

Utilizzare i controlli **[!UICONTROL Top N Base Ad Units]** e **[!UICONTROL Top N Overlapping Ad Units]** per selezionare il numero desiderato di unità pubblicitarie per la sovrapposizione. Puoi selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza i controlli **Intervallo giorni** e **Da data a** per modificare l&#39;intervallo di look-back. I periodi di lookback di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizzare i controlli **[!UICONTROL Base Ad Unit]** e **[!UICONTROL Overlap Ad Unit]** per selezionare le unità pubblicitarie da visualizzare nel report di sovrapposizione.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel passaggio 3 di [Importare file di dati di Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo si assicura che il report specifichi la proprietà Web come [!UICONTROL Ad Unit] invece di [!UICONTROL Ad Unit ID].

## Interpretazione dei risultati {#interpreting-results}

Il report [!UICONTROL Ad Unit Overlap] potrebbe essere simile a quello riportato di seguito. Passa il cursore del mouse su una cella per ottenere ulteriori informazioni su quella particolare sovrapposizione. Per ulteriori informazioni, consulta la descrizione nella tabella seguente il rapporto di esempio.

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
   <td colname="col1"> <p><span class="wintitle"> unità annunci sovrapposti</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, può trattarsi di uno dei tuoi siti web o di un articolo sul tuo sito web. Nell'immagine qui sopra, le unità di base sono gli articoli da 9 a 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unità Annuncio Di Base</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, può trattarsi di uno dei tuoi siti web o di un articolo sul tuo sito web. Nell'immagine qui sopra, le unità di base sono gli articoli da 1 a 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Numero Univoci Di Unità Annunci Di Sovrapposizione <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che hanno visitato gli elementi dell'unità pubblicitaria 9 - 18. Queste informazioni vengono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Numero Univoci Di Unità Annuncio Di Base <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che hanno visitato gli elementi dell’unità pubblicitaria da 1 a 8. Queste informazioni vengono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Numero Unique Di Sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato un'unità di annunci di base <span class="wintitle"></span> e un'unità di annunci di sovrapposizione <span class="wintitle"></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato un'unità di annunci di base <span class="wintitle"></span> e un'unità di annunci di sovrapposizione <span class="wintitle"></span>. Conteggio Unique di Sovrapposizione <span class="wintitle"></span>, espresso come percentuale dell'unità Annuncio di base <span class="wintitle"></span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
