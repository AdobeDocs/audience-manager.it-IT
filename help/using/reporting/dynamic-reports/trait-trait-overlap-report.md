---
description: Restituisce dati sul numero di utenti univoci condivisi tra tutte le caratteristiche di prima e terze parti.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: Rapporto di sovrapposizione caratteristica-caratteristica
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 7%

---

# Rapporto di sovrapposizione caratteristica-caratteristica{#trait-to-trait-overlap-report}

Restituisce dati sul numero di utenti univoci condivisi tra tutte le caratteristiche di prima e terze parti.

>[!NOTE]
>
>I rapporti di sovrapposizione in Audience Manager aderiscono ai principi RBAC. Puoi visualizzare solo le caratteristiche delle origini dati a cui hai accesso in base alla [Gruppo utenti RBAC](/help/using/features/administration/administration-overview.md) a cui appartenete.

<!-- 

c_overlap_reports.xml

 -->

## Panoramica

La [!UICONTROL Trait-to-Trait Overlap] il rapporto restituisce i dati sulla percentuale di utenti univoci condivisi tra tutte le caratteristiche personali e quelle di terze parti. Come strumento di ottimizzazione, questo rapporto ti aiuta a:

* Crea segmenti con sovrapposizione alta o bassa, a seconda delle tue esigenze. Le caratteristiche con elevata sovrapposizione ti danno un pubblico mirato, ma meno visitatori unici. Le caratteristiche con sovrapposizione bassa possono essere utili per raggiungere un set di visitatori unico e più grande.
* Convalida dei dati delle caratteristiche di terze parti: Una forte sovrapposizione tra caratteristiche di prima e terze parti simili suggerisce che la caratteristica del tuo partner dati è accurata e affidabile. Al contrario, una sovrapposizione bassa può indicare che una caratteristica di terze parti potrebbe in realtà non contenere le stesse informazioni della tua caratteristica di prima parte simile.
* Trova una sovrapposizione inaspettata tra le caratteristiche e utilizza tali informazioni per creare segmenti innovativi.

## Report di esempio

La figura seguente fornisce una panoramica di alto livello degli elementi nel [!UICONTROL Trait-to-Trait Overlap] rapporto.

>[!NOTE]
>
>La [!UICONTROL Trait-to-Trait Overlap] il report restituisce un campo vuoto quando confronta la stessa caratteristica con se stesso.

>[!NOTE]
>
>Le caratteristiche della cartella non sono disponibili per il confronto all’interno dei rapporti di sovrapposizione caratteristica-caratteristica. Creando un segmento utilizzando una particolare caratteristica della cartella, puoi eseguire analisi tramite la funzione [rapporto di sovrapposizione segmento-caratteristica](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md).

![](assets/trait-to-trait-overlap.png)

## Approfondisci i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra a comparsa. Le azioni clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Definizione dei campi pop dati di sovrapposizione caratteristica-caratteristica {#field-definitions}

Descrive le metriche visualizzate nella finestra a comparsa quando si fa clic su un singolo punto dati.

<!-- 

r_t2t_data_pop.xml

 -->

La finestra a comparsa per [!UICONTROL Trait-to-Trait Overlap] il rapporto contiene le metriche riportate di seguito. La metrica univoca nella tabella rappresenta il tuo *utenti in tempo reale*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> % sovrapposizione</span></b> </td> 
   <td colname="col2"> Mostra la percentuale di sovrapposizione univoca tra le caratteristiche confrontate (sovrapposizione univoche/caratteristiche univoche). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo di origine dati</span></b> </td> 
   <td colname="col2">Definisce il tipo di origine dati a cui appartiene una caratteristica. Può essere: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Prime parti (la tua caratteristica). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terze parti (da un partner dati/fornitore esterno). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID caratteristica di sovrapposizione</span></b> </td> 
   <td colname="col2"> ID numerico univoco per la caratteristica sovrapposta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapposizione del nome della caratteristica</span></b> </td> 
   <td colname="col2"> Nome della caratteristica sovrapposta. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> ID caratteristica 2</span></b> </td> 
   <td colname="col2"> ID numerico univoco per la caratteristica nell’origine dati di base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome caratteristica 2</span></b> </td> 
   <td colname="col2"> Nome della caratteristica nell’origine dati di base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapponi univoci</span></b> </td> 
   <td colname="col2"> <p>Per ottenere la percentuale di sovrapposizione, l'Audience Manager utilizza la seguente formula:</p> <p>Sovrapposizione di Uniques / (Uniche caratteristiche di base + Sovrapposizione di Uniche caratteristiche - Sovrapposizione di Uniche tecniche)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapposizione degli univoci delle caratteristiche</span></b> </td> 
   <td colname="col2"> Il numero di visitatori unici dalla caratteristica sovrapposta. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniche caratteristiche di base</span></b> </td> 
   <td colname="col2"> Il numero di visitatori unici dalla caratteristica di base. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrare i risultati dei report con i cursori di dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei report dinamici](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Spiegazione di icone e strumenti del rapporto](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: pianificazione degli aggiornamenti e dimensione minima dei segmenti](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento di dati e tassi di errore nei report selezionati di Audience Manager...](../../reporting/report-sampling.md)
>* [File CSV per report di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)

