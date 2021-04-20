---
description: Le caratteristiche principali non utilizzate sono rappresentate come un diagramma a dispersione delle caratteristiche che non sono ancora membri di un segmento, in base al tipo di caratteristica, all’origine dati e alle prestazioni.
seo-description: Le caratteristiche principali non utilizzate sono rappresentate come un diagramma a dispersione delle caratteristiche che non sono ancora membri di un segmento, in base al tipo di caratteristica, all’origine dati e alle prestazioni.
seo-title: Principali caratteristiche non utilizzate
solution: Audience Manager
title: Principali caratteristiche non utilizzate
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 2%

---

# Principali caratteristiche non utilizzate{#top-unused-traits}

Le caratteristiche principali non utilizzate sono rappresentate come un diagramma a dispersione delle caratteristiche che non sono ancora membri di un segmento, in base al tipo di caratteristica, all’origine dati e alle prestazioni.

## Caso d&#39;uso {#use-cases}

Con il rapporto [!UICONTROL Top Unused Traits] puoi analizzare e confrontare le prestazioni di caratteristiche di prima e terze parti che al momento non sono mappate su un segmento. Questa visualizzazione può evidenziare le caratteristiche migliori da utilizzare in un segmento di pubblico per l’ottimizzazione di una campagna o per nuove opportunità.

## Utilizzo del rapporto Principali caratteristiche non utilizzate {#using-the-report}

Utilizza i controlli **[!UICONTROL Data Provider Type]** per alternare tra caratteristiche di prima parte e di terze parti. Seleziona **[!UICONTROL All]** per restituire le caratteristiche di prima e terza parte nel rapporto.

Con il cursore **[!UICONTROL Impressions]** puoi selezionare un valore minimo e massimo per le impression restituite. Eventuali caratteristiche responsabili di un numero inferiore o superiore ai limiti impostati non vengono visualizzate nel rapporto.

Utilizza i controlli **[!UICONTROL Day Range]** e **[!UICONTROL Date Through]** per regolare l&#39;intervallo di look-back. Per questo rapporto è disponibile solo il periodo di look-back di 30 giorni.

Utilizza la casella a discesa **[!UICONTROL Order]** per selezionare le proprietà web nel tuo portfolio per cui desideri restituire informazioni.

Nella casella a discesa **[!UICONTROL Data Provider]** , seleziona le origini dati contenenti le caratteristiche che desideri visualizzare nel rapporto.

Utilizza la casella a discesa **[!UICONTROL Traits]** per selezionare le caratteristiche da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando abiliti [!UICONTROL Audience Optimization for Publishers], devi includere metadati descrittivi per [!UICONTROL Order IDs], come descritto nel passaggio 3 di [Importa file di dati Google Ad Manager (precedentemente DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). In questo modo, assicurati che il report descriva la proprietà Web come [!UICONTROL Order] invece del [!UICONTROL Order ID].

## Interpretazione dei risultati {#interpreting-results}

**Report di esempio**

Il rapporto [!UICONTROL Top Unused Traits] potrebbe essere simile a quello riportato di seguito. Nel rapporto fare clic su una bolla per visualizzare i dati sottostanti.

Vedi le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto di esempio.

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
   <td colname="col1"> <p><span class="wintitle"> Tipo di fornitore dati</span> </p> </td> 
   <td colname="col2"> <p>Specifica se l'origine dati selezionata contiene caratteristiche di prima parte o di terze parti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID caratteristica</span> </p> </td> 
   <td colname="col2"> <p>ID univoco della caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nome della caratteristica</span> </p> </td> 
   <td colname="col2"> <p>Il nome alfanumerico assegnato a questa caratteristica dall'utente o dal provider di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ordine</span> </p> </td> 
   <td colname="col2"> <p>La proprietà Web per la quale viene visualizzato questo rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressioni</span> </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica sono stati esposti al tuo inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Uniche caratteristiche</span> </p> </td> 
   <td colname="col2"> <p>Il numero di membri della caratteristica, negli ultimi 30 giorni. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La posizione delle caratteristiche in un rapporto può spiegarti molte informazioni sulle caratteristiche da utilizzare per ottimizzare i segmenti di pubblico esistenti.

Le caratteristiche situate più in alto sull’asse Impression sono quelle che desideri utilizzare nelle campagne. Per le caratteristiche con un numero ridotto di impression, è improbabile che tu stia raggiungendo questo pubblico nella tua proprietà web, in base ai dati [!DNL Google Ad Manager].

Osserva a sinistra dell’asse [!UICONTROL Unique Trait Realizations] per ottenere caratteristiche altamente precise e a destra per quelle che possono influenzare la scala.

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
   <td colname="col2"> <p>Numero elevato di impression, numero ridotto di realizzazioni di caratteristiche. </p> <p>Si tratta di un pubblico altamente preciso che non è ancora membro di un segmento. Considera il targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Basso numero di impression, scarso numero di realizzazioni di caratteristiche. </p> <p> Escludi queste caratteristiche, in quanto i membri non contribuiscono alle impression sulle proprietà web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a destra</b> </p> </td> 
   <td colname="col2"> <p>Elevato numero di impression, elevato numero di realizzazioni di caratteristiche. </p> <p>Una portata elevata contro un pubblico che non è ancora identificato in un segmento. Questo pubblico è un candidato ideale per il targeting a causa dell’alto numero di impression e della scala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a destra</b> </p> </td> 
   <td colname="col2"> <p>Numero ridotto di impression, numero elevato di realizzazioni di caratteristiche. </p> <p> Puoi escludere queste caratteristiche, in quanto i membri non contribuiscono alle impression sulle proprietà web. </p> </td> 
  </tr> 
 </tbody> 
</table>
