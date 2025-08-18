---
description: Le caratteristiche inutilizzate principali sono rappresentate come un diagramma a dispersione di caratteristiche che non sono ancora membri di un segmento, in base al tipo di caratteristica, all’origine dati e alle prestazioni.
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: Principali caratteristiche non utilizzate
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---

# Principali caratteristiche non utilizzate{#top-unused-traits}

Le caratteristiche inutilizzate principali sono rappresentate come un diagramma a dispersione di caratteristiche che non sono ancora membri di un segmento, in base al tipo di caratteristica, all’origine dati e alle prestazioni.

## Caso d&#39;uso {#use-cases}

Con il rapporto [!UICONTROL Top Unused Traits] puoi analizzare e confrontare le prestazioni di caratteristiche di prima e terze parti attualmente non mappate a un segmento. Questa visualizzazione può evidenziare le caratteristiche migliori da utilizzare in un segmento di pubblico per l’ottimizzazione di una campagna o per creare nuove opportunità.

## Utilizzo del rapporto Principali caratteristiche non utilizzate {#using-the-report}

Utilizzare i controlli **[!UICONTROL Data Provider Type]** per alternare le caratteristiche di prima parte e terze parti. Selezionare **[!UICONTROL All]** per restituire le caratteristiche di prima e terza parte nel report.

Con il cursore **[!UICONTROL Impressions]** è possibile selezionare un valore minimo e massimo per le impression restituite. Le caratteristiche responsabili di un numero di elementi pari o superiore ai limiti impostati non vengono visualizzate nel rapporto.

Utilizzare i controlli **[!UICONTROL Day Range]** e **[!UICONTROL Date Through]** per regolare l&#39;intervallo di look-back. Per questo rapporto è disponibile solo il periodo di look-back di 30 giorni.

Utilizzare la casella a discesa **[!UICONTROL Order]** per selezionare le proprietà Web del portfolio per le quali si desidera restituire informazioni.

Nella casella a discesa **[!UICONTROL Data Provider]** selezionare le origini dati contenenti le caratteristiche che si desidera visualizzare nel report.

Utilizza la casella a discesa **[!UICONTROL Traits]** per selezionare le caratteristiche da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Order IDs], come descritto nel passaggio 3 di [Importare file di dati di Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo si assicura che il report specifichi la proprietà Web come [!UICONTROL Order] invece di [!UICONTROL Order ID].

## Interpretazione dei risultati {#interpreting-results}

**Rapporto di esempio**

Il report [!UICONTROL Top Unused Traits] potrebbe essere simile a quello riportato di seguito. Nel rapporto, fai clic su una bolla per visualizzare i dati sottostanti.

Per ulteriori informazioni, consulta la descrizione nella tabella seguente il rapporto di esempio.

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
   <td colname="col1"> <p>Tipo provider dati <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>Specifica se l'origine dati selezionata contiene caratteristiche di prima parte o terze parti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID caratteristica <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>ID univoco di questa caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome caratteristica <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>Il nome alfanumerico che tu o il fornitore di dati avete assegnato a questa caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ordine <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>La proprietà web per la quale stai visualizzando questo rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impression <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica sono stati esposti al tuo inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> caratteristiche univoche</span> </p> </td> 
   <td colname="col2"> <p>Il numero di membri della caratteristica, negli ultimi 30 giorni. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La posizione delle caratteristiche in un rapporto può indicarti molto su quali caratteristiche puoi utilizzare per ottimizzare i segmenti di pubblico esistenti.

Le caratteristiche situate più in alto sull’asse Impression sono quelle che desideri utilizzare nelle campagne. Per le caratteristiche con un basso numero di impression, è improbabile che tu stia raggiungendo questo pubblico sulla tua proprietà web, in base ai tuoi dati di [!DNL Google Ad Manager].

Osservare a sinistra dell&#39;asse [!UICONTROL Unique Trait Realizations] per le caratteristiche altamente accurate e a destra per le caratteristiche che possono guidare la scala.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Posizione </th> 
   <th colname="col2" class="entry"> Posizionamento Indica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Numero elevato di impression, numero ridotto di realizzazioni di caratteristiche. </p> <p>Si tratta di un pubblico molto accurato che non è ancora membro di un segmento. Considera per il targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Basso numero di impression, basso numero di realizzazioni di caratteristiche. </p> <p> Escludi queste caratteristiche, in quanto i membri non contribuiscono alle impression sulle proprietà web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a destra</b> </p> </td> 
   <td colname="col2"> <p>Numero elevato di impression, numero elevato di realizzazioni di caratteristiche. </p> <p>Una portata elevata contro un pubblico che non è ancora identificato in un segmento. Questo pubblico è il candidato migliore per il targeting a causa del numero elevato di impression e della scala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a destra</b> </p> </td> 
   <td colname="col2"> <p>Basso numero di impression, elevato numero di realizzazioni di caratteristiche. </p> <p> Puoi escludere queste caratteristiche, in quanto i membri non contribuiscono alle impression sulle proprietà web. </p> </td> 
  </tr> 
 </tbody> 
</table>
