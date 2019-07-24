---
description: Restituisce dati sul numero di utenti univoci condivisi tra tutte le caratteristiche di prime e terze parti.
seo-description: Restituisce dati sul numero di utenti univoci condivisi tra tutte le caratteristiche di prime e terze parti.
seo-title: Rapporto di sovrapposizione caratteristica-caratteristica
solution: Audience Manager
title: Rapporto di sovrapposizione caratteristica-caratteristica
uuid: 7 fb 3 fc 9 e -0 e 0 b -492 a -9 c 3 a -04356 afb 19 c 7
translation-type: tm+mt
source-git-commit: 4dc8aad623198cbc24c5c76ac3818d7ee00e9a5e

---


# Rapporto di sovrapposizione caratteristica-caratteristica{#trait-to-trait-overlap-report}

Restituisce dati sul numero di utenti univoci condivisi tra tutte le caratteristiche di prime e terze parti.

>[!NOTE]
>
>I rapporti di sovrapposizione in Audience Manager aderiscono ai principi RBAC. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_overlap_reports.xml

 -->

## Panoramica

[!UICONTROL Trait-to-Trait Overlap] Il rapporto restituisce dati sul % degli utenti univoci condivisi tra tutte le caratteristiche personali e le caratteristiche di terze parti. Come strumento di ottimizzazione, questo rapporto consente di:

* Create segmenti con sovrapposizione elevata o bassa, a seconda delle esigenze. Le caratteristiche con sovrapposizione elevata offrono un pubblico di destinazione, ma meno visitatori univoci. Le caratteristiche con sovrapposizione ridotta possono essere utili per raggiungere un set di visitatori più ampio e univoco.
* Convalida dei dati delle caratteristiche di terze parti: Una forte sovrapposizione tra tratti di prime e terze parti simili suggerisce che la caratteristica del tuo partner dati sia accurata e affidabile. In modo analogo, la sovrapposizione bassa può indicare che un tratto di terze parti potrebbe non contenere le stesse informazioni del proprio tratto di prime parti simile.
* Trovate una sovrapposizione imprevista tra le caratteristiche e utilizzate tali informazioni per creare segmenti innovativi.

## Report di esempio

The following illustration provides a high-level overview of elements in the [!UICONTROL Trait-to-Trait Overlap] report.

>[!NOTE]
>
>[!UICONTROL Trait-to-Trait Overlap] Il rapporto restituisce un campo vuoto quando confronta la caratteristica con se stessa.

![](assets/trait-to-trait-overlap.png)

## Approfondire i singoli punti di dati

Selezionate un singolo punto per visualizzare i dettagli dei dati in una finestra a comparsa. Le azioni di clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Trait-to-Trait Overlap Data Pop Fields Defined {#field-definitions}

Descrive le metriche visualizzate nella finestra popup quando si fa clic su un singolo punto dati.

<!-- 

r_t2t_data_pop.xml

 -->

The popup for the [!UICONTROL Trait-to-Trait Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome provider dati</span></b> </td> 
   <td colname="col2"> Nome del proprietario della caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Tipo di provider dati</span></b> </td> 
   <td colname="col2">Definisce il tipo di fornitore a cui appartiene. Può essere: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">First-party (your own trait). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Third-party (da un partner/fornitore di dati esterno). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID caratteristica</span></b> </td> 
   <td colname="col2"> ID numerico univoco per tale caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Nome caratteristica</span></b> </td> 
   <td colname="col2"> Nome della caratteristica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapposizione %</span></b> </td> 
   <td colname="col2"> Mostra il % della sovrapposizione univoca tra le caratteristiche confrontate (sovrapposizione sovrapposizione/caratteristica). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapposizione sovrapposizione</span></b> </td> 
   <td colname="col2"> <p>Per ottenere la sovrapposizione %, Audience Manager usa la formula seguente:</p> <p>Unificazione sovrapposizione/(Uniques segmento base + Unione segmento sovrapposizione - Unificazione sovrapposizione)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Caratteristiche caratteristiche</span></b> </td> 
   <td colname="col2"> Numero di visitatori unici nella caratteristica. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Filtrare i risultati del rapporto con i cursori dati](../../reporting/dynamic-reports/data-sliders.md)
>* [Forme, colori e dimensioni utilizzati nei rapporti dinamici](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Icone e strumenti per report descritti](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: Aggiorna pianificazione e Dimensioni segmento minime](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento dei dati ed errori in Report Audience Manager selezionati…](../../reporting/report-sampling.md)
>* [File CSV per rapporti di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)