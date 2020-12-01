---
description: Le caratteristiche principali non utilizzate sono rappresentate come un diagramma a dispersione delle caratteristiche che non sono ancora membri di un segmento, in base al tipo di caratteristica, all'origine dati e alle prestazioni.
seo-description: Le caratteristiche principali non utilizzate sono rappresentate come un diagramma a dispersione delle caratteristiche che non sono ancora membri di un segmento, in base al tipo di caratteristica, all'origine dati e alle prestazioni.
seo-title: Principali caratteristiche non utilizzate
solution: Audience Manager
title: Principali caratteristiche non utilizzate
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 2%

---


# Principali caratteristiche non utilizzate{#top-unused-traits}

Le caratteristiche principali non utilizzate sono rappresentate come un diagramma a dispersione delle caratteristiche che non sono ancora membri di un segmento, in base al tipo di caratteristica, all&#39;origine dati e alle prestazioni.

## Caso d&#39;uso {#use-cases}

Con il rapporto [!UICONTROL Top Unused Traits], puoi analizzare e confrontare le prestazioni di caratteristiche di prime e terze parti che attualmente non sono mappate a un segmento. Questa visualizzazione può evidenziare le caratteristiche migliori da utilizzare in un segmento di pubblico per l&#39;ottimizzazione delle campagne o per la rete di nuove opportunità.

## Utilizzo del report Caratteristiche principali non utilizzate {#using-the-report}

Utilizzate i controlli **[!UICONTROL Data Provider Type]** per alternare tra caratteristiche di prime parti e terze parti. Selezionare **[!UICONTROL All]** per restituire caratteristiche di prima e terza parte nel rapporto.

Con il cursore **[!UICONTROL Impressions]** potete selezionare un valore minimo e massimo per le impression restituite. Eventuali caratteristiche responsabili di un numero inferiore o superiore ai limiti impostati non vengono visualizzate nel rapporto.

Utilizzare i controlli **[!UICONTROL Day Range]** e **[!UICONTROL Date Through]** per regolare l&#39;intervallo di look-back. Per questo rapporto è disponibile solo il periodo di lookback di 30 giorni.

Utilizzate la casella a discesa **[!UICONTROL Order]** per selezionare le proprietà Web nel portafoglio per cui desiderate restituire informazioni.

Nella casella a discesa **[!UICONTROL Data Provider]**, seleziona le origini dati contenenti le caratteristiche che desideri vedere nel rapporto.

Utilizzate la casella a discesa **[!UICONTROL Traits]** per selezionare le caratteristiche da visualizzare nel rapporto.

>[!IMPORTANT]
>
>Quando si abilita [!UICONTROL Audience Optimization for Publishers], è necessario includere metadati descrittivi per [!UICONTROL Order IDs], come descritto nel passaggio 3 di [Importa file di dati Google Ad Manager (precedentemente DFP) in  Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). A questo scopo, assicuratevi che il rapporto descriva la proprietà Web come [!UICONTROL Order] anziché come [!UICONTROL Order ID].

## Interpretazione dei risultati {#interpreting-results}

**Report di esempio**

Il report [!UICONTROL Top Unused Traits] potrebbe essere simile a quello riportato di seguito. Nel rapporto, fai clic su una bolla per visualizzare i dati sottostanti.

Vedere le descrizioni per le informazioni aggiuntive nella tabella sotto il rapporto campione.

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
   <td colname="col1"> <p><span class="wintitle"> Tipo provider dati</span> </p> </td> 
   <td colname="col2"> <p>Specifica se l'origine dati selezionata contiene caratteristiche di prime parti o terze parti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID caratteristica</span> </p> </td> 
   <td colname="col2"> <p>ID univoco di questa caratteristica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nome caratteristica</span> </p> </td> 
   <td colname="col2"> <p>Nome alfanumerico assegnato a questa caratteristica da voi o dal provider di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ordine</span> </p> </td> 
   <td colname="col2"> <p>Proprietà Web per la quale viene visualizzato il rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressioni</span> </p> </td> 
   <td colname="col2"> <p>Il numero di volte in cui i membri di questa caratteristica sono stati esposti al tuo inventario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caratteristiche tecniche</span> </p> </td> 
   <td colname="col2"> <p>Numero di membri delle caratteristiche negli ultimi 30 giorni. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

La posizione delle caratteristiche in un report può fornire informazioni dettagliate sulle caratteristiche che è possibile utilizzare per ottimizzare i segmenti di pubblico esistenti.

Le caratteristiche situate più in alto sull’asse Impressioni sono quelle che desiderate usare nelle campagne. Per le caratteristiche con un numero limitato di impression, è improbabile che si stia raggiungendo questo pubblico sulla proprietà Web, in base ai dati [!DNL Google Ad Manager].

Osservate a sinistra dell&#39;asse [!UICONTROL Unique Trait Realizations] per ottenere caratteristiche molto precise e a destra per quelle che possono essere ridimensionate.

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
   <td colname="col2"> <p>Numero elevato di impression, numero ridotto di realizzazioni di caratteristiche. </p> <p>Si tratta di un'audience altamente accurata che non è ancora membro di un segmento. Considerate l'opportunità di eseguire il targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a sinistra</b> </p> </td> 
   <td colname="col2"> <p>Numero basso di impression, numero basso di realizzazioni di caratteristiche. </p> <p> Escludete queste caratteristiche, in quanto i membri non contribuiscono alle impressioni sulle vostre proprietà Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In alto a destra</b> </p> </td> 
   <td colname="col2"> <p>Numero elevato di impression, numero elevato di realizzazioni di caratteristiche. </p> <p>Una portata elevata contro un pubblico che non è ancora indicato in un segmento. Questo pubblico è un candidato ideale per il targeting a causa dell'alto numero di impression e della scala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>In basso a destra</b> </p> </td> 
   <td colname="col2"> <p>Numero basso di impression, numero elevato di realizzazioni di caratteristiche. </p> <p> Potete escludere queste caratteristiche, in quanto i membri non contribuiscono alle impressioni sulle proprietà Web. </p> </td> 
  </tr> 
 </tbody> 
</table>
