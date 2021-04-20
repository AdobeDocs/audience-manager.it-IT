---
description: Restituisce dati sul numero di utenti univoci condivisi tra una caratteristica specifica e un segmento intero.
seo-description: Restituisce dati sul numero di utenti univoci condivisi tra una caratteristica specifica e un segmento intero.
seo-title: Rapporto di sovrapposizione segmento-caratteristica
solution: Audience Manager
title: Rapporto di sovrapposizione segmento-caratteristica
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 5%

---

# Rapporto di sovrapposizione segmento-caratteristica{#segment-to-trait-overlap-report}

Restituisce dati sul numero di utenti univoci condivisi tra una caratteristica specifica e un segmento intero.

>[!NOTE]
>
>I rapporti di sovrapposizione in Audience Manager aderiscono ai principi RBAC. Puoi visualizzare solo i segmenti e le caratteristiche delle origini dati a cui hai accesso in base al [Gruppo di utenti RBAC](/help/using/features/administration/administration-overview.md) a cui appartieni.

<!-- 

c_segment_trait_overlap.xml

 -->

## Panoramica

Come strumento di ottimizzazione, i rapporti [!UICONTROL Segment to Trait Overlap] ti consentono di creare segmenti altamente mirati o di espandere la portata dei segmenti. Ad esempio, puoi creare segmenti e caratteristiche mirati con sovrapposizione elevata per raggiungere un pubblico specifico. Tuttavia, molta sovrapposizione può significare meno utenti univoci (minore portata). Questo rapporto consente di espandere la portata rimuovendo le caratteristiche con molta sovrapposizione di segmenti e sostituendole con caratteristiche che hanno meno sovrapposizione.

### Report di esempio

La figura seguente fornisce una panoramica di alto livello del rapporto [!UICONTROL Segment-to-Trait Overlap] .

![](assets/segment-to-trait-overlap.png)

### Approfondisci i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra a comparsa. Le azioni clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Confronto di segmenti con caratteristiche {#comparing-segments-to-traits}

Descrive come confrontare segmenti e caratteristiche per ricavare informazioni significative dai risultati.

<!-- 

c_compare_s2t.xml

 -->

### Confronto di caratteristiche e univoche di segmenti: Esempio

A prima vista, può sembrare illogico confrontare i segmenti con le caratteristiche e tentare di trarre conclusioni dai risultati. Dopotutto, segmenti e caratteristiche sono diversi, quindi come possono avere significato i dati derivati da elementi diversi? Tuttavia, in questo caso, non stiamo confrontando caratteristiche e segmenti, ma il numero di visitatori unici condivisi tra di loro. Il conteggio dei visitatori univoci condivisi fornisce il valore comune che rende possibile il confronto tra segmenti e caratteristiche.

Il diagramma seguente illustra la relazione tra una caratteristica e il segmento a cui appartiene. In questo caso, abbiamo una caratteristica con 10 visitatori e un segmento con 1.000 visitatori. Condividono 3 visitatori unici in comune.

![](assets/s2t.png)

Il conteggio di visitatori univoci è il valore costante comune condiviso tra queste diverse classi di oggetti. Di conseguenza, puoi determinare la relazione di visitatori univoci tra di loro come segue:

* La caratteristica condivide il 30% dei suoi visitatori unici con il segmento (3/10 = 0,30).
* Il segmento condivide lo 0,3% dei suoi visitatori unici con la caratteristica (3/1.000 = 0,003)

### Trovare valore nei confronti tra segmenti e caratteristiche

Osservare la sovrapposizione tra caratteristiche e segmenti può essere utile per stimare il totale del pool di visitatori disponibili (previsioni) o trovare segmenti inefficienti con troppa sovrapposizione.

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
   <td colname="col2"> <p>Per determinare il pool di visitatori disponibili, somma la differenza tra il totale delle caratteristiche (meno sovrapposizione) e il totale del segmento (meno sovrapposizione). </p> <p>Questa combinazione di caratteristiche del segmento potrebbe raggiungere fino a 1004 nuovi utenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ricerca di segmenti inefficienti</b> </td> 
   <td colname="col2"> <p>Se una caratteristica fa parte di un gruppo <span class="wintitle"> AND</span> in una definizione di segmento, i visitatori univoci che hanno tale caratteristica sono già nel segmento e non sono disponibili per l’aggiunta al segmento. Puoi utilizzare questo rapporto per trovare caratteristiche rilevanti con bassa sovrapposizione e aggiungerle alla definizione del segmento, aumentando quindi la portata del pool di pubblico del segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Informazioni sui filtri di dati nel rapporto di sovrapposizione segmento-caratteristica {#data-filters-s2t-report}

Descrive il funzionamento dei cursori % di sovrapposizione caratteristica e segmento univoci.

<!-- 

r_s2t_sliders.xml

 -->

Il rapporto [!UICONTROL Segment-to-Trait overlap] ti consente di utilizzare due cursori per filtrare i dati in base alla sovrapposizione % per caratteristica o segmento.

* **[!UICONTROL Filter Trait Uniques %:]** Filtra i dati in base alla percentuale di visitatori unici condivisi tra la caratteristica e il segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtra i dati in base alla percentuale di visitatori unici che condividono tra il segmento e la caratteristica.

### Esempio

Il diagramma seguente illustra la differenza tra le caratteristiche univoche % e il segmento uniques %. In questo caso, la caratteristica e il segmento condividono 3 visitatori unici. Come proporzioni:

* La caratteristica condivide il 30% dei suoi visitatori unici con il segmento (3/10 = 0,30).
* Il segmento condivide lo 0,3% dei suoi visitatori unici con la caratteristica (3/1.000 = 0,003)

![](assets/s2t.png)

## Campi pop dati segmento-caratteristica definiti {#fields-defined}

Descrive le metriche visualizzate nella finestra a comparsa quando si fa clic su un singolo punto dati.

<!-- 

r_s2t_data_pop.xml

 -->

La finestra a comparsa del rapporto [!UICONTROL Segment-to-Trait Overlap] contiene le metriche riportate di seguito. La metrica univoca nella tabella rappresenta gli *utenti in tempo reale*.

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
   <td colname="col2"> ID numerico univoco per il segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Origine dati caratteristica  </span></b> </td> 
   <td colname="col2"> Nome del proprietario della caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo di origine dati</span></b> </td> 
   <td colname="col2">Definisce il tipo di provider a cui appartiene una caratteristica. Può essere: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Prime parti (la tua caratteristica). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terze parti (da un partner dati/fornitore esterno). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID caratteristica</span></b> </td> 
   <td colname="col2"> ID numerico univoco per la caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome della caratteristica</span></b> </td> 
   <td colname="col2"> Nome della caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % di sovrapposizione degli univoci delle caratteristiche</span></b> </td> 
   <td colname="col2"> La percentuale di visitatori unici di una caratteristica condivide con il segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % di sovrapposizione degli univoci dei segmenti</span></b> </td> 
   <td colname="col2"> La percentuale di visitatori unici che un segmento condivide con una caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapponi univoci</span></b> </td> 
   <td colname="col2"> Numero di visitatori univoci condivisi tra il segmento e la caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniche segmenti</span></b> </td> 
   <td colname="col2"> Numero di visitatori univoci nel segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniche caratteristiche</span></b> </td> 
   <td colname="col2"> Numero di visitatori unici nella caratteristica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrare i risultati dei report con i cursori di dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei rapporti interattivi](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Spiegazione di icone e strumenti del rapporto](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: pianificazione degli aggiornamenti e dimensione minima dei segmenti](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento di dati e tassi di errore nei report selezionati di Audience Manager...](../../reporting/report-sampling.md)
>* [File CSV per report di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)

