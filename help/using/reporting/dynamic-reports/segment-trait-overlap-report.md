---
description: Restituisce i dati sul numero di utenti univoci condivisi tra una caratteristica specifica e un intero segmento.
seo-description: Restituisce i dati sul numero di utenti univoci condivisi tra una caratteristica specifica e un intero segmento.
seo-title: Rapporto di sovrapposizione segmento-caratteristica
solution: Audience Manager
title: Rapporto di sovrapposizione segmento-caratteristica
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Rapporto di sovrapposizione segmento-caratteristica{#segment-to-trait-overlap-report}

Restituisce i dati sul numero di utenti univoci condivisi tra una caratteristica specifica e un intero segmento.

>[!NOTE]
>
>I rapporti di sovrapposizione in Audience Manager rispettano i principi RBAC. Puoi visualizzare solo i segmenti e le caratteristiche delle origini dati a cui hai accesso in base al gruppo [di utenti](/help/using/features/administration/administration-overview.md) RBAC a cui appartieni.

<!-- 

c_segment_trait_overlap.xml

 -->

## Panoramica

Come strumento di ottimizzazione, i [!UICONTROL Segment to Trait Overlap] report consentono di creare segmenti altamente mirati o di espandere la portata dei segmenti. Ad esempio, puoi creare segmenti e caratteristiche mirati con sovrapposizione elevata per raggiungere un pubblico particolare. Tuttavia, molte sovrapposizioni possono significare meno utenti univoci (minore portata). L'esecuzione di questo rapporto consente di espandere la portata rimuovendo le caratteristiche con molte sovrapposizioni di segmenti e sostituendole con caratteristiche con meno sovrapposizione.

### Report di esempio

L'illustrazione seguente fornisce una panoramica di alto livello del [!UICONTROL Segment-to-Trait Overlap] rapporto.

![](assets/segment-to-trait-overlap.png)

### Approfondisci i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra a comparsa. Le azioni di clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Confronto tra segmenti e caratteristiche {#comparing-segments-to-traits}

Descrive come confrontare segmenti e caratteristiche per ricavare informazioni significative dai risultati.

<!-- 

c_compare_s2t.xml

 -->

### Confronto tra caratteristiche e segmenti: Esempio

A prima vista, può sembrare illogico confrontare segmenti con caratteristiche e tentare di trarre conclusioni dai risultati. Dopotutto, segmenti e caratteristiche sono diversi, quindi come possono avere significato i dati derivati da elementi diversi? Tuttavia, in questo caso, non stiamo confrontando caratteristiche e segmenti, ma il numero di visitatori univoci condivisi tra di loro. Il conteggio dei visitatori univoci condivisi fornisce il valore comune che rende possibile il confronto tra segmenti e caratteristiche.

Il diagramma seguente illustra la relazione tra una caratteristica e il segmento a cui appartiene. In questo caso, abbiamo una caratteristica con 10 visitatori e un segmento con 1000 visitatori. Condividono 3 visitatori unici in comune.

![](assets/s2t.png)

Il conteggio univoco dei visitatori è il valore costante comune condiviso tra queste diverse classi di oggetti. Di conseguenza, potete determinare la relazione visitatore univoca tra di loro come segue:

* La caratteristica condivide il 30% dei visitatori univoci con il segmento (3/10 = 0.30).
* Il segmento condivide lo 0,3% dei suoi visitatori unici con la caratteristica (3/1.000 = 0,003)

### Trova valore nei confronti tra segmenti e caratteristiche

Osservare la sovrapposizione tra caratteristiche e segmenti può essere utile stimare il pool di visitatori totale disponibile (previsione) o trovare segmenti inefficienti con eccessiva sovrapposizione.

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
   <td colname="col2"> <p>Per determinare il pool di visitatori disponibile, somma la differenza tra il totale delle caratteristiche (meno sovrapposizione) e il totale del segmento (meno sovrapposizione). </p> <p>Questa combinazione di caratteristiche del segmento potrebbe raggiungere fino a 1004 nuovi utenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trova segmenti inefficienti</b> </td> 
   <td colname="col2"> <p>Se una caratteristica fa parte di un gruppo <span class="wintitle"> AND</span> in una definizione di segmento, i visitatori univoci che hanno quella caratteristica sono già nel segmento e non sono disponibili per l’aggiunta al segmento. Puoi utilizzare questo rapporto per trovare caratteristiche rilevanti con una sovrapposizione bassa e aggiungerle alla definizione del segmento, aumentando quindi la portata del pool di audience del segmento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Informazioni sui filtri dati nel rapporto di sovrapposizione segmento-caratteristica {#data-filters-s2t-report}

Descrive il funzionamento dei cursori % della sovrapposizione caratteristica e segmento.

<!-- 

r_s2t_sliders.xml

 -->

Il [!UICONTROL Segment-to-Trait overlap] rapporto consente di utilizzare due cursori per filtrare i dati in base alla sovrapposizione % per caratteristica o segmento.

* **[!UICONTROL Filter Trait Uniques %:]** Filtra i dati in base alla percentuale di visitatori univoci condivisi tra la caratteristica e il segmento.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtra i dati in base alla percentuale di visitatori univoci condivisi tra il segmento e la caratteristica.

### Esempio 

Il diagramma seguente illustra la differenza tra l'uniques caratteristica % e l'uniques segmento %. In questo caso, la caratteristica e il segmento condividono 3 visitatori univoci. Come proporzioni:

* La caratteristica condivide il 30% dei visitatori univoci con il segmento (3/10 = 0.30).
* Il segmento condivide lo 0,3% dei suoi visitatori unici con la caratteristica (3/1.000 = 0,003)

![](assets/s2t.png)

## Segment-to-Trait Data Pop Fields Definito {#fields-defined}

Descrive le metriche visualizzate nella finestra a comparsa quando si fa clic su un singolo punto dati.

<!-- 

r_s2t_data_pop.xml

 -->

La finestra a comparsa per il [!UICONTROL Segment-to-Trait Overlap] rapporto contiene le metriche riportate di seguito. La metrica univoca nella tabella rappresenta gli utenti *in tempo* reale.

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
   <td colname="col1"><b><span class="wintitle"> Nome provider dati</span></b> </td> 
   <td colname="col2"> Nome del proprietario del segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo provider dati</span></b> </td> 
   <td colname="col2">Definisce il tipo di provider a cui appartiene una caratteristica. Può essere: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Prima parte (caratteristica propria). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terza parte (da un partner/fornitore esterno di dati). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SID</span></b> </td> 
   <td colname="col2"> ID numerico univoco per il segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome SID</span></b> </td> 
   <td colname="col2"> Nome del segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapposizione caratteristica</span></b> </td> 
   <td colname="col2"> % di visitatori univoci una caratteristica viene condivisa con il segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapposizione segmenti %</span></b> </td> 
   <td colname="col2"> % di visitatori univoci in un segmento condiviso con una caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapponi</span></b> </td> 
   <td colname="col2"> Numero di visitatori univoci condivisi tra il segmento e la caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmento di analisi</span></b> </td> 
   <td colname="col2"> Numero di visitatori univoci nel segmento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Caratteristiche tecniche</span></b> </td> 
   <td colname="col2"> Numero di visitatori univoci nella caratteristica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_this]
>
>* [Filtra i risultati dei report con i cursori dei dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei rapporti interattivi](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Informazioni su icone e strumenti del rapporto](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: Aggiorna pianificazione e dimensione minima del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento dei dati e tassi di errore nei report Audience Manager selezionati...](../../reporting/report-sampling.md)
>* [File CSV per rapporti di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)