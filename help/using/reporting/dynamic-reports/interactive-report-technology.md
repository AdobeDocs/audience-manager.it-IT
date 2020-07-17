---
description: Descrive il software sottostante che abilita i report interattivi e la pianificazione dell'aggiornamento dei dati.
seo-description: Descrive il software sottostante che abilita i report interattivi e la pianificazione dell'aggiornamento dei dati.
seo-title: Tecnologia dei report
solution: Audience Manager
title: Tecnologia dei report
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 2%

---


# Tecnologia dei report{#report-technology}

Descrive il software sottostante che abilita i report interattivi e la pianificazione dell&#39;aggiornamento dei dati.

<!-- 

c_report_technology.xml

 -->

## Report interattivi che utilizzano la tecnologia Tableau

[!DNL Audience Manager] utilizza il software [Tableau](https://www.tableausoftware.com/) per visualizzare i dati nei rapporti interattivi. Con [!DNL Tableau], i [!UICONTROL Delivery and Overlap] rapporti utilizzano suggerimenti visivi e simboli che consentono di:

* Trovate caratteristiche ad alte e basse prestazioni.
* Caratteristiche e segmenti spot con sovrapposizione di visitatore univoca bassa e alta.
* Utilizzate i dati di sovrapposizione per creare segmenti mirati.
* Ampliate la portata identificando le caratteristiche correlate con una sovrapposizione ridotta.

## Pianificazione aggiornamento dati

I dati del rapporto vengono aggiornati ogni domenica. L&#39;aggiornamento elabora i dati da sabato (il giorno precedente) alla domenica precedente.

## Forme, colori e dimensioni utilizzati nei rapporti interattivi {#shapes-colors-sizes}

La maggior parte dei rapporti interattivi visualizza i risultati utilizzando forme di dimensioni e colori diversi. Questo formato di visualizzazione è progettato per aiutarti a dare un senso ai dati visivamente, senza dover scorrere righe e colonne di numeri.

<!-- 

r_legend.xml

 -->

### Legenda report

La tabella seguente definisce le forme, le dimensioni e i colori utilizzati nei rapporti dinamici.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento dati </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Forme</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">I cerchi indicano le proprie caratteristiche di prime parti. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">I quadrati indicano caratteristiche di terze parti. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Colori</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Le sfumature rosse indicano una sovrapposizione <i>bassa</i> . </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Le sfumature verdi indicano una sovrapposizione <i>elevata</i> . </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensioni</b> </td> 
   <td colname="col2"> Le dimensioni aumentano o diminuiscono in proporzione diretta per raggiungere (il numero o la % di clic o di utenti univoci in una caratteristica o segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Documentazione di Tableau {#tableau-documentation}

Per ulteriori informazioni sui controlli Tableau che potete vedere nei nostri rapporti interattivi, consultate la documentazione ufficiale per [Tableau Server su Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)