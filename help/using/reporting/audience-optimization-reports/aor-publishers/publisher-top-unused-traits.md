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


# Top Unused Traits{#top-unused-traits}

Le caratteristiche non utilizzate principali sono rappresentate da un diagramma a dispersione di caratteristiche non ancora membri di un segmento, in base al tipo di caratteristica, all'origine dati e alle prestazioni.

## Caso d'uso {#use-cases}

With the [!UICONTROL Top Unused Traits] report, you can analyze and compare the performance of first and third party traits that are currently not mapped to a segment. Questa vista può indicare le caratteristiche migliori da utilizzare in un segmento di audience per ottimizzare le campagne o le nuove opportunità.

## Using the Top Unused Traits Report {#using-the-report}

Use the **[!UICONTROL Data Provider Type]** controls to toggle between first party and third party traits. Select **[!UICONTROL All]** to return first and third party traits in the report.

With the **[!UICONTROL Impressions]** slider, you can select a minimum and maximum value for returned impressions. Qualsiasi caratteristica responsabile per meno o più dei limiti impostata non viene visualizzata nel rapporto.

Use the **[!UICONTROL Day Range]** and **[!UICONTROL Date Through]** controls to adjust your look-back range. Per questo rapporto è disponibile solo il periodo di look-back di 30 giorni.

Use the **[!UICONTROL Order]** drop-down box to select the web properties in your portfolio for which you want to return information.

In the **[!UICONTROL Data Provider]** drop-down box, select the data sources containing the traits you want to see in the report.

Use the **[!UICONTROL Traits]** drop-down box to select which traits you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Order IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Order] instead of the [!UICONTROL Order ID].

## Interpreting the Results {#interpreting-results}

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

Le caratteristiche più alte sull'asse Impression sono quelle che desiderate utilizzare nelle campagne. Per caratteristiche con un numero limitato di impression, è improbabile che tu stia raggiungendo questo pubblico sulla proprietà Web, in base ai dati DFP.

Look to the left of the [!UICONTROL Unique Trait Realizations] axis for highly accurate traits and to the right for traits that can drive scale.

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
