---
description: Restituisce i dati sul numero di utenti univoci condivisi tra una particolare caratteristica e un intero segmento.
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: Rapporto di sovrapposizione segmento-caratteristica
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%

---

# Rapporto di sovrapposizione segmento-caratteristica{#segment-to-trait-overlap-report}

Restituisce i dati sul numero di utenti univoci condivisi tra una particolare caratteristica e un intero segmento.

>[!NOTE]
>
>I rapporti di sovrapposizione di cui all’Audience Manager rispettano i principi RBAC. Puoi visualizzare solo segmenti e caratteristiche da origini dati a cui hai accesso in base al [gruppo di utenti RBAC](/help/using/features/administration/administration-overview.md) a cui appartieni.

<!-- 

c_segment_trait_overlap.xml

 -->

## Panoramica

Come strumento di ottimizzazione, i report [!UICONTROL Segment to Trait Overlap] consentono di creare segmenti con particolare attenzione o di espandere la portata dei segmenti. Ad esempio, puoi creare segmenti mirati e caratteristiche con sovrapposizione elevata per raggiungere un pubblico particolare. Tuttavia, molte sovrapposizioni possono significare meno utenti univoci (portata inferiore). Eseguire questo rapporto per aiutare a espandere la portata rimuovendo le caratteristiche con molta sovrapposizione di segmenti e sostituendole con caratteristiche con meno sovrapposizioni.

### Report di esempio

Nella figura seguente viene fornita una panoramica di alto livello del report [!UICONTROL Segment-to-Trait Overlap].

![](assets/segment-to-trait-overlap.png)

### Espandere i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra popup. Le azioni di clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Confronto di segmenti con caratteristiche {#comparing-segments-to-traits}

Descrive come confrontare segmenti e caratteristiche per ricavare informazioni significative dai risultati.

<!-- 

c_compare_s2t.xml

 -->

### Confronto tra caratteristiche e univoci dei segmenti: un esempio

A prima vista, può sembrare illogico confrontare segmenti con caratteristiche e tentare di trarre conclusioni dai risultati. Dopo tutto, i segmenti e le caratteristiche sono diversi, quindi come possono avere significato i dati derivati da elementi diversi? Tuttavia, in questo caso, non stiamo confrontando caratteristiche e segmenti, ma il numero di visitatori univoci condivisi tra di loro. Il conteggio di visitatori univoci condivisi fornisce il valore comune che rende possibile il confronto tra segmenti e caratteristiche.

Il diagramma seguente illustra la relazione tra una caratteristica e il segmento a cui appartiene. In questo caso, abbiamo una caratteristica con 10 visitatori e un segmento con 1.000 visitatori. Condividono 3 visitatori univoci in comune.

![](assets/s2t.png)

Il conteggio dei visitatori univoci è il valore comune e costante condiviso tra queste diverse classi di oggetti. Di conseguenza, puoi determinare la relazione di visitatore univoco tra di loro come segue:

* La caratteristica condivide il 30% dei suoi visitatori univoci con il segmento (3/10 = 0,30).
* Il segmento condivide lo 0,3% dei suoi visitatori univoci con la caratteristica (3/1.000 = 0,003)

### Trovare valore nel confronto tra segmenti e caratteristiche

Osservare la sovrapposizione tra caratteristiche e segmenti può essere utile per stimare il pool di visitatori totale disponibile (previsione) o per trovare segmenti inefficienti con una sovrapposizione eccessiva.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Previsione</b> </td> 
   <td colname="col2"> <p>Per determinare il pool di visitatori disponibile, somma la differenza tra il totale delle caratteristiche (meno sovrapposizione) e il totale del segmento (meno sovrapposizione). </p> <p>Questa combinazione segmento-caratteristica potrebbe raggiungere fino a 1004 nuovi utenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trovare Segmenti Inefficienti</b> </td> 
   <td colname="col2"> <p>Se una caratteristica fa parte di un gruppo <span class="wintitle"> AND</span> in una definizione di segmento, i visitatori univoci con tale caratteristica sono già presenti nel segmento e non sono disponibili per l'aggiunta al segmento. Puoi utilizzare questo rapporto per trovare caratteristiche rilevanti con bassa sovrapposizione e aggiungerle alla definizione del segmento, aumentando così la portata del pool di pubblico del segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Filtri di dati nel rapporto di sovrapposizione segmento-caratteristica {#data-filters-s2t-report}

Descrive il funzionamento dei cursori % di sovrapposizione univoca per caratteristiche e segmenti.

<!-- 

r_s2t_sliders.xml

 -->

Il report [!UICONTROL Segment-to-Trait overlap] consente di utilizzare due cursori per filtrare i dati in base alla percentuale di sovrapposizione per caratteristica o segmento.

* **[!UICONTROL Filter Trait Uniques %:]** Filtra i dati in base alla percentuale di visitatori univoci condivisi tra la caratteristica e il segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtra i dati in base alla percentuale di visitatori univoci condivisi tra il segmento e la caratteristica.

### Esempio

Il diagramma seguente illustra la differenza tra % univoci di caratteristica e % univoci di segmento. In questo caso, la caratteristica e il segmento condividono 3 visitatori univoci. In proporzioni:

* La caratteristica condivide il 30% dei suoi visitatori univoci con il segmento (3/10 = 0,30).
* Il segmento condivide lo 0,3% dei suoi visitatori univoci con la caratteristica (3/1.000 = 0,003)

![](assets/s2t.png)

## Campi pop-up di dati segmento-caratteristica definiti {#fields-defined}

Descrive le metriche visualizzate nella finestra popup quando si fa clic su un singolo punto dati.

<!-- 

r_s2t_data_pop.xml

 -->

La finestra a comparsa per il report [!UICONTROL Segment-to-Trait Overlap] contiene le metriche seguenti. La metrica Unique nella tabella rappresenta i tuoi *utenti in tempo reale*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID segmento</span></b> </td> 
   <td colname="col2"> ID numerico univoco del segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> caratteristica Source </span></b> </td> 
   <td colname="col2"> Nome del proprietario della caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Tipo di Source dati <b><span class="wintitle"></span></b> </td> 
   <td colname="col2">Definisce il tipo di provider a cui appartiene una caratteristica. Può essere: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Prime parti (la tua caratteristica). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terze parti (da un partner/fornitore esterno di dati). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1">ID caratteristica <b><span class="wintitle"></span></b> </td> 
   <td colname="col2"> ID numerico univoco della caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Nome caratteristica <b><span class="wintitle"></span></b> </td> 
   <td colname="col2"> Nome della caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Sovrapposizione Unique Di <b><span class="wintitle"> Caratteristiche %</span></b> </td> 
   <td colname="col2"> % di visitatori univoci con una caratteristica condivisa con il segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Sovrapposizione Unique Segmento <b><span class="wintitle"> %</span></b> </td> 
   <td colname="col2"> % di visitatori univoci che un segmento condivide con una caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Univoci di sovrapposizione <b><span class="wintitle"></span></b> </td> 
   <td colname="col2"> Numero di visitatori univoci condivisi tra il segmento e la caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Univoci Segmento</span></b> </td> 
   <td colname="col2"> Numero di visitatori univoci nel segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> caratteristiche univoche</span></b> </td> 
   <td colname="col2"> Numero di visitatori univoci nella caratteristica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrare i risultati dei report con i cursori di dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei report interattivi](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Icone e strumenti di report spiegati](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: pianificazione degli aggiornamenti e dimensione minima dei segmenti](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento di dati e tassi di errore nei report di Audienci Manager selezionati...](../../reporting/report-sampling.md)
>* [File CSV per report di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)
