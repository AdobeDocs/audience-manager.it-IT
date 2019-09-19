---
description: Restituisce i dati sul numero di utenti univoci condivisi tra tutte le caratteristiche della prima e della terza parte.
seo-description: Restituisce i dati sul numero di utenti univoci condivisi tra tutte le caratteristiche della prima e della terza parte.
seo-title: Rapporto di sovrapposizione caratteristica-caratteristica
solution: Audience Manager
title: Rapporto di sovrapposizione caratteristica-caratteristica
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
translation-type: tm+mt
source-git-commit: 4dc8aad623198cbc24c5c76ac3818d7ee00e9a5e

---


# Rapporto di sovrapposizione caratteristica-caratteristica{#trait-to-trait-overlap-report}

Restituisce i dati sul numero di utenti univoci condivisi tra tutte le caratteristiche della prima e della terza parte.

>[!NOTE]
>
>I rapporti di sovrapposizione in Audience Manager rispettano i principi RBAC. Potete visualizzare solo le caratteristiche provenienti da origini dati a cui avete accesso in base al gruppo [di utenti](/help/using/features/administration/administration-overview.md) RBAC a cui appartenete.

<!-- 

c_overlap_reports.xml

 -->

## Panoramica

Il [!UICONTROL Trait-to-Trait Overlap] rapporto restituisce i dati sulla percentuale di utenti univoci condivisi tra tutte le caratteristiche proprie e quelle di terze parti. Come strumento di ottimizzazione, questo rapporto consente di:

* Crea segmenti con sovrapposizione alta o bassa, a seconda delle tue esigenze. Le caratteristiche con sovrapposizione elevata ti consentono di ottenere un pubblico mirato, ma meno visitatori unici. Le caratteristiche con una sovrapposizione ridotta possono essere utili per raggiungere un set di visitatori unico e più grande.
* Convalida dei dati di caratteristiche di terze parti: Una forte sovrapposizione tra caratteristiche simili di prime e terze parti suggerisce che la caratteristica del partner dati è accurata e affidabile. Al contrario, una sovrapposizione bassa può indicare che una caratteristica di terze parti potrebbe non contenere le stesse informazioni della caratteristica di prime parti propria, simile.
* Trova una sovrapposizione imprevista tra caratteristiche e usa tali informazioni per creare segmenti innovativi.

## Report di esempio

L'illustrazione seguente fornisce una panoramica di alto livello degli elementi nel [!UICONTROL Trait-to-Trait Overlap] rapporto.

>[!NOTE]
>
>Il [!UICONTROL Trait-to-Trait Overlap] rapporto restituisce un campo vuoto se confronta la stessa caratteristica con se stesso.

![](assets/trait-to-trait-overlap.png)

## Approfondisci i singoli punti dati

Selezionare un singolo punto per visualizzare i dettagli dei dati in una finestra a comparsa. Le azioni di clic aggiornano automaticamente i dati visualizzati nel rapporto.

## Campi Pop Dati Sovrapposizione Caratteristiche-Caratteristiche Definiti {#field-definitions}

Descrive le metriche visualizzate nella finestra a comparsa quando si fa clic su un singolo punto dati.

<!-- 

r_t2t_data_pop.xml

 -->

La finestra a comparsa per il [!UICONTROL Trait-to-Trait Overlap] rapporto contiene le metriche riportate di seguito. La metrica univoca nella tabella rappresenta gli utenti *in tempo* reale.

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
   <td colname="col1"><b><span class="wintitle"> Tipo provider dati</span></b> </td> 
   <td colname="col2">Definisce il tipo di provider a cui appartiene una caratteristica. Può essere: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Prima parte (caratteristica propria). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Terza parte (da un partner/fornitore esterno di dati). </li> 
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
   <td colname="col1"><b><span class="wintitle"> % sovrapposizione</span></b> </td> 
   <td colname="col2"> Mostra la percentuale di sovrapposizione univoca tra le caratteristiche confrontate (sovrapposizione di univoche/uniche caratteristiche). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Sovrapponi</span></b> </td> 
   <td colname="col2"> <p>Per ottenere la sovrapposizione %, Audience Manager utilizza la seguente formula:</p> <p>Sovrapposizione Di Uniche / (Uniche Segmenti Di Base + Sovrapposizione Di Segmenti - Sovrapposizione Di Uniche Analisi)</p> </td> 
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
>* [Forme, colori e dimensioni utilizzati nei report dinamici](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Informazioni su icone e strumenti del rapporto](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapporti di sovrapposizione: Aggiorna pianificazione e dimensione minima del segmento](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Campionamento dei dati e tassi di errore nei report Audience Manager selezionati...](../../reporting/report-sampling.md)
>* [File CSV per rapporti di sovrapposizione](../../reporting/dynamic-reports/overlap-csv-files.md)