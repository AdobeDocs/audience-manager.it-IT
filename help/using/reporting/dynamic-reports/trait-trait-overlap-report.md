---
description: Restituisce i dati sul numero di utenti univoci condivisi tra tutte le caratteristiche di prima parte e terze parti.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: Rapporto di sovrapposizione caratteristica-caratteristica
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Rapporto di sovrapposizione caratteristica-caratteristica{#trait-to-trait-overlap-report}

Restituisce i dati sul numero di utenti univoci condivisi tra tutte le caratteristiche di prima parte e terze parti.

>[!NOTE]
>
>I rapporti di sovrapposizione di cui all’Audience Manager rispettano i principi RBAC. Puoi visualizzare solo le caratteristiche dalle origini dati a cui hai accesso in base al [gruppo di utenti RBAC](/help/using/features/administration/administration-overview.md) a cui appartieni.

<!-- 

c_overlap_reports.xml

 -->

## Panoramica

Il report [!UICONTROL Trait-to-Trait Overlap] restituisce dati sulla percentuale di utenti univoci condivisi tra tutte le tue caratteristiche e quelle di terze parti. In qualità di strumento di ottimizzazione, questo rapporto consente di:

* Crea segmenti con sovrapposizione alta o bassa, a seconda delle tue esigenze. Le caratteristiche con sovrapposizione elevata forniscono un pubblico mirato, ma meno visitatori univoci. Le caratteristiche con una bassa sovrapposizione possono essere utili per raggiungere un set di visitatori più grande e univoco.
* Convalidare dati sulle caratteristiche di terze parti: una forte sovrapposizione tra caratteristiche simili di prima parte e di terze parti suggerisce che la caratteristica del partner dati è accurata e affidabile. Al contrario, una bassa sovrapposizione può indicare che una caratteristica di terze parti potrebbe in realtà non contenere le stesse informazioni della tua caratteristica di prima parte simile.
* Trova una sovrapposizione imprevista tra le caratteristiche e utilizza tali informazioni per creare segmenti innovativi.

## Report di esempio

La figura seguente fornisce una panoramica di alto livello degli elementi nel report [!UICONTROL Trait-to-Trait Overlap].

>[!NOTE]
>
>Il report [!UICONTROL Trait-to-Trait Overlap] restituisce un campo vuoto quando confronta la stessa caratteristica con se stesso.

>[!NOTE]
>
>Le caratteristiche della cartella non sono disponibili per il confronto all’interno dei rapporti di sovrapposizione caratteristica-caratteristica. Creando un segmento utilizzando una particolare caratteristica della cartella, puoi eseguire l&#39;analisi tramite il [rapporto di sovrapposizione segmento-caratteristica](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md).

![](assets/trait-to-trait-overlap.png)

## Espandere i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra popup. Le azioni di clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Campi pop dati di sovrapposizione caratteristica-caratteristica definiti {#field-definitions}

Descrive le metriche visualizzate nella finestra popup quando si fa clic su un singolo punto dati.

<!-- 

r_t2t_data_pop.xml

 -->

La finestra a comparsa per il report [!UICONTROL Trait-to-Trait Overlap] contiene le metriche seguenti. La metrica Unique nella tabella rappresenta i tuoi *utenti in tempo reale*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapposizione %</span></b> </td> 
   <td colname="col2"> Mostra la percentuale di sovrapposizione univoca tra caratteristiche confrontate (univoci di sovrapposizione/univoci di caratteristica). </td> 
  </tr> 
  <tr> 
   <td colname="col1">Tipo di Source dati <b><span class="wintitle"></span></b> </td> 
   <td colname="col2">Definisce il tipo di origine dati a cui appartiene una caratteristica. Può essere: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Prime parti (la tua caratteristica). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terze parti (da un partner/fornitore esterno di dati). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID caratteristica sovrapposta</span></b> </td> 
   <td colname="col2"> ID numerico univoco della caratteristica sovrapposta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapposizione Nome Caratteristica</span></b> </td> 
   <td colname="col2"> Nome della caratteristica sovrapposta. </td> 
  </tr>
    <tr> 
   <td colname="col1">ID caratteristica <b><span class="wintitle"> 2</span></b> </td> 
   <td colname="col2"> ID numerico univoco della caratteristica nell’origine dati di base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome caratteristica 2</span></b> </td> 
   <td colname="col2"> Nome della caratteristica nell’origine dati di base. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Univoci di sovrapposizione <b><span class="wintitle"></span></b> </td> 
   <td colname="col2"> <p>Per ottenere la percentuale di sovrapposizione, in Audience Manager viene utilizzata la formula seguente:</p> <p>Univoci sovrapposti / (Univoci delle caratteristiche di base + Univoci delle caratteristiche sovrapposte - Univoci sovrapposti)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Unique di caratteristiche sovrapposte</span></b> </td> 
   <td colname="col2"> Il numero di visitatori univoci dalla caratteristica sovrapposta. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> elementi univoci di base</span></b> </td> 
   <td colname="col2"> Il numero di visitatori univoci dalla caratteristica di base. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrare i risultati dei report con i cursori di dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei report dinamici](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Icone e strumenti di report spiegati](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: pianificazione degli aggiornamenti e dimensione minima dei segmenti](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento di dati e tassi di errore nei report di Audienci Manager selezionati...](../../reporting/report-sampling.md)
>* [File CSV per report di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)
