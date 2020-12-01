---
description: Restituisce i dati sul numero di utenti univoci condivisi tra tutte le caratteristiche della prima e della terza parte.
seo-description: Restituisce i dati sul numero di utenti univoci condivisi tra tutte le caratteristiche della prima e della terza parte.
seo-title: Rapporto di sovrapposizione caratteristica-caratteristica
solution: Audience Manager
title: Rapporto di sovrapposizione caratteristica-caratteristica
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 8%

---


# Rapporto di sovrapposizione caratteristica-caratteristica{#trait-to-trait-overlap-report}

Restituisce i dati sul numero di utenti univoci condivisi tra tutte le caratteristiche della prima e della terza parte.

>[!NOTE]
>
>I rapporti di sovrapposizione in  Audience Manager aderiscono ai principi RBAC. È possibile visualizzare solo le caratteristiche provenienti da origini dati a cui si ha accesso in base al [Gruppo di utenti RBAC](/help/using/features/administration/administration-overview.md) a cui si appartiene.

<!-- 

c_overlap_reports.xml

 -->

## Panoramica

Il rapporto [!UICONTROL Trait-to-Trait Overlap] restituisce i dati sulla percentuale di utenti univoci condivisi tra tutte le caratteristiche personali e quelle di terze parti. Come strumento di ottimizzazione, questo rapporto consente di:

* Crea segmenti con sovrapposizione alta o bassa, a seconda delle tue esigenze. Le caratteristiche con sovrapposizione elevata ti consentono di ottenere un pubblico mirato, ma meno visitatori unici. Le caratteristiche con una sovrapposizione ridotta possono essere utili per raggiungere un set di visitatori unico e più grande.
* Convalida dei dati di caratteristiche di terze parti: Una forte sovrapposizione tra caratteristiche simili di prime e terze parti suggerisce che il tratto del partner dati è accurato e affidabile. Al contrario, una sovrapposizione bassa può indicare che una caratteristica di terze parti potrebbe non contenere le stesse informazioni della caratteristica di prime parti propria, simile.
* Trova una sovrapposizione imprevista tra caratteristiche e usa tali informazioni per creare segmenti innovativi.

## Report di esempio

L&#39;illustrazione seguente fornisce una panoramica di alto livello degli elementi nel report [!UICONTROL Trait-to-Trait Overlap].

>[!NOTE]
>
>Il rapporto [!UICONTROL Trait-to-Trait Overlap] restituisce un campo vuoto se confronta la stessa caratteristica con se stesso.

![](assets/trait-to-trait-overlap.png)

## Approfondisci i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra a comparsa. Le azioni di clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Campi Pop Dati Sovrapposizione Caratteristiche-Caratteristiche Definiti {#field-definitions}

Descrive le metriche visualizzate nella finestra a comparsa quando si fa clic su un singolo punto dati.

<!-- 

r_t2t_data_pop.xml

 -->

La finestra a comparsa del report [!UICONTROL Trait-to-Trait Overlap] contiene le metriche riportate di seguito. La metrica univoca nella tabella rappresenta gli *utenti in tempo reale*.

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
   <td colname="col2"> Mostra la percentuale di sovrapposizione univoca tra le caratteristiche confrontate (sovrapposizione di univoche/uniche caratteristiche). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo origine dati</span></b> </td> 
   <td colname="col2">Definisce il tipo di origine dati a cui una caratteristica appartiene. Può essere: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">First-party (caratteristica propria). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terza parte (da un partner/fornitore esterno di dati). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID caratteristica sovrapposto</span></b> </td> 
   <td colname="col2"> ID numerico univoco per la caratteristica sovrapposta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome caratteristica sovrapposto</span></b> </td> 
   <td colname="col2"> Nome della caratteristica sovrapposta. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait ID 2</span></b> </td> 
   <td colname="col2"> ID numerico univoco per la caratteristica nell'origine dati di base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome caratteristica 2</span></b> </td> 
   <td colname="col2"> Nome della caratteristica nell'origine dati di base. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapponi anomalie</span></b> </td> 
   <td colname="col2"> <p>Per ottenere la sovrapposizione %,  Audience Manager utilizza la seguente formula:</p> <p>Sovrapposizione di imperfezioni / (Uniche caratteristiche di base + Sovrapposizione di feature Uniche - Sovrapposizione di imperfezioni)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapposizione delle caratteristiche</span></b> </td> 
   <td colname="col2"> Il numero di visitatori univoci della caratteristica sovrapposta. </td> 
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
>* [Informazioni su icone e strumenti del rapporto](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: pianificazione degli aggiornamenti e dimensione minima dei segmenti](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento di dati e tassi di errore nei report selezionati di Audience Manager...](../../reporting/report-sampling.md)
>* [File CSV per report di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)