---
description: Le caratteristiche non utilizzate principali sono rappresentate da un diagramma a dispersione di caratteristiche non ancora membri di un segmento, in base al tipo di caratteristica, all'origine dati e alle prestazioni.
seo-description: Le caratteristiche non utilizzate principali sono rappresentate da un diagramma a dispersione di caratteristiche non ancora membri di un segmento, in base al tipo di caratteristica, all'origine dati e alle prestazioni.
seo-title: Caratteristiche principali non utilizzate
solution: Audience Manager
title: Caratteristiche principali non utilizzate
uuid: 90 bcd 333-41 b 8-416 e-aa 4 e-a 8661891 df 50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Caratteristiche principali non utilizzate{#top-unused-traits}

Le caratteristiche non utilizzate principali sono rappresentate da un diagramma a dispersione di caratteristiche non ancora membri di un segmento, in base al tipo di caratteristica, all&#39;origine dati e alle prestazioni.

## Caso d&#39;uso {#use-cases}

Con [!UICONTROL Top Unused Traits] il rapporto, puoi analizzare e confrontare le prestazioni delle caratteristiche prime e terze parti attualmente non mappate a un segmento. Questa vista può indicare le caratteristiche migliori da utilizzare in un segmento di audience per ottimizzare le campagne o le nuove opportunità.

## Utilizzo del report Traits principale {#using-the-report}

Utilizzate **[!UICONTROL Data Provider Type]** i controlli per alternare tra le caratteristiche di prime parti e terze parti. Seleziona **[!UICONTROL All]** per restituire le caratteristiche prima e terza al rapporto.

Con il **[!UICONTROL Impressions]** cursore, potete selezionare un valore minimo e massimo per le impression restituite. Qualsiasi caratteristica responsabile per meno o più dei limiti impostata non viene visualizzata nel rapporto.

Utilizza i **[!UICONTROL Day Range]****[!UICONTROL Date Through]** controlli e regola l&#39;intervallo di look-back. Per questo rapporto è disponibile solo il periodo di look-back di 30 giorni.

Utilizzate il **[!UICONTROL Order]** menu a discesa per selezionare le proprietà Web nel portfolio per il quale desiderate restituire le informazioni.

Nel menu **[!UICONTROL Data Provider]** a discesa, seleziona le origini dati contenenti le caratteristiche che desideri vedere nel rapporto.

Utilizzate il **[!UICONTROL Traits]** menu a discesa per selezionare le caratteristiche da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando abilitate [!UICONTROL Audience Optimization for Publishers], dovete includere metadati descrittivi per [!UICONTROL Order IDs], come descritto nel Passaggio 3 di [Importa file di dati DFP in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In tal modo, assicuratevi che il report contenga la proprietà Web come [!UICONTROL Order] invece [!UICONTROL Order ID]della proprietà.

## Interpretazione dei risultati {#interpreting-results}

**Report di esempio**

[!UICONTROL Top Unused Traits] Il rapporto potrebbe essere simile a quello di seguito. Nel rapporto, fai clic su una bolla per visualizzare i dati sottostanti.

Vedere descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tipo di provider dati</span> </p> </td> 
   <td colname="col2"> <p>Specifica se l'origine dati selezionata contiene caratteristiche di terze parti o di terze parti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID caratteristica</span> </p> </td> 
   <td colname="col2"> <p>L'ID univoco di questa caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nome caratteristica</span> </p> </td> 
   <td colname="col2"> <p>Nome alfanumerico assegnato a voi o al fornitore di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ordine</span> </p> </td> 
   <td colname="col2"> <p>La proprietà Web per la quale stai visualizzando il rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressioni</span> </p> </td> 
   <td colname="col2"> <p>Numero di volte in cui i membri di questa caratteristica sono stati esposti alle scorte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caratteristiche caratteristiche</span> </p> </td> 
   <td colname="col2"> <p>Numero di membri delle caratteristiche negli ultimi 30 giorni. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La posizione delle caratteristiche in un rapporto può dirvi molto sulle caratteristiche che potete utilizzare per ottimizzare segmenti di pubblico esistenti.

Le caratteristiche più alte sull&#39;asse Impression sono quelle che desiderate utilizzare nelle campagne. Per caratteristiche con un numero limitato di impression, è improbabile che tu stia raggiungendo questo pubblico sulla proprietà Web, in base ai dati DFP.

Osservate a sinistra dell&#39; [!UICONTROL Unique Trait Realizations] asse per caratteristiche altamente precise e verso destra per le caratteristiche che possono essere ridimensionate.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posizione </th> 
   <th colname="col2" class="entry"> Posizionamento indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Numero elevato di impression, numero ridotto di realizzazioni. </p> <p>Si tratta di un pubblico altamente accurato che non è ancora membro di un segmento. Prendere in considerazione il targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Numero limitato di impression, numero ridotto di realizzazioni. </p> <p> Escludete queste caratteristiche in quanto i membri non contribuiscono alle impression sulle proprietà Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a destra</b> </p> </td> 
   <td colname="col2"> <p>Numero elevato di impression, numero elevato di realizzazioni. </p> <p>Un pubblico elevato rispetto a un'audience che non viene ancora denotata in un segmento. Questo pubblico è un candidato principale per il targeting a causa dell'elevato numero di impression e della scala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a destra</b> </p> </td> 
   <td colname="col2"> <p>Numero limitato di impression, numero elevato di realizzazioni. </p> <p> Potete escludere queste caratteristiche, poiché i membri non contribuiscono alle impression sulle proprietà Web. </p> </td> 
  </tr> 
 </tbody> 
</table>
