---
description: Il rapporto Overlap unità annuncio viene visualizzato come grafico a caldo che evidenzia sovrapposizioni elevate e basse tra le unità annuncio.
seo-description: Il rapporto Overlap unità annuncio viene visualizzato come grafico a caldo che evidenzia sovrapposizioni elevate e basse tra le unità annuncio.
seo-title: Sovrapposizione di unità annunci
solution: Audience Manager
title: Sovrapposizione di unità annunci
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 3%

---


# Sovrapposizione di unità annunci{#ad-unit-overlap}

Il **[!UICONTROL Ad Unit Overlap]** rapporto viene visualizzato come grafico a caldo che evidenzia sovrapposizioni elevate e basse tra le unità annuncio.

## Caso d&#39;uso {#use-cases}

Con il **[!UICONTROL Ad Unit Overlap]** rapporto, puoi capire dove il pubblico si sovrappone tra le tue proprietà Web. Il rapporto considera le 100 proprietà principali correlate e mostra la sovrapposizione tra di esse.

## Utilizzo del rapporto di sovrapposizione unità annuncio {#using-the-report}

Utilizzate i controlli **[!UICONTROL Top N Base Ad Units]** e **[!UICONTROL Top N Overlapping Ad Units]** per selezionare il numero desiderato di unità pubblicitarie per la sovrapposizione. Potete selezionare un numero massimo di 100 elementi per ciascuno.

Utilizza i controlli Intervallo **** giorno e **Passaggio** data per regolare l’intervallo di look-back. I periodi di lookback di 7 e 30 giorni sono disponibili solo per le date di domenica.

Utilizzate i controlli **[!UICONTROL Base Ad Unit]** e **[!UICONTROL Overlap Ad Unit]** per selezionare quale delle unità annuncio desiderate visualizzare nel rapporto di sovrapposizione.

>[!IMPORTANT]
>
>Quando [!UICONTROL Audience Optimization for Publishers]abilitate, dovete includere metadati descrittivi per [!UICONTROL Ad Unit IDs], come descritto nel Passaggio 3 di [Importa file di dati Google Ad Manager (ex DFP) in  Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). A questo scopo, assicuratevi che nel rapporto sia indicata la proprietà Web come [!UICONTROL Ad Unit] anziché come [!UICONTROL Ad Unit ID].

## Interpretazione dei risultati {#interpreting-results}

Il tuo [!UICONTROL Ad Unit Overlap] rapporto potrebbe essere simile a quello riportato di seguito. Passate il puntatore del mouse sopra una cella per ottenere ulteriori informazioni su tale sovrapposizione. Vedere le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

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
   <td colname="col1"> <p><span class="wintitle"> Sovrapponi unità annuncio</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, questo può essere uno dei vostri siti Web o un articolo sul vostro sito Web. Nell'immagine qui sopra, la base e le unità sono articoli da 9 a 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unità annuncio di base</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'articolo di magazzino. Ad esempio, questo può essere uno dei vostri siti Web o un articolo sul vostro sito Web. Nell'immagine qui sopra, la base e le unità sono articoli da 1 a 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Sovrapponi numero di analisi delle unità annuncio</span> </p> </td> 
   <td colname="col2"> <p>Il numero di utenti che hanno visitato gli annunci 9 - 18. Queste informazioni vengono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Conteggio Uniche Unità Annunci Base</span> </p> </td> 
   <td colname="col2"> <p>Numero di utenti che hanno visitato gli elementi dell'unità pubblicitaria 1 - 8. Queste informazioni vengono estratte dai registri di Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Sovrapponi numero di uniche</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato una <span class="wintitle"> Base Ad Unit</span> e <span class="wintitle"> Overlap Ad Unit</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Percentuale di sovrapposizione</span> </p> </td> 
   <td colname="col2"> <p>La sovrapposizione tra gli utenti che hanno visitato una <span class="wintitle"> Base Ad Unit</span> e <span class="wintitle"> Overlap Ad Unit</span>. Si tratta del <span class="wintitle"> conteggio</span>delle <span class="wintitle"> sovrapposizioni, espresso come percentuale dell'</span>Unitàannuncio di base. </p> </td> 
  </tr> 
 </tbody> 
</table>
