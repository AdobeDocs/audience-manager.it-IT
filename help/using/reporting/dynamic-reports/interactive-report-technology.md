---
description: Descrive il software sottostante che attiva i report interattivi e la pianificazione dell'aggiornamento dei dati.
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: Tecnologia dei rapporti
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Tecnologia dei rapporti{#report-technology}

Descrive il software sottostante che attiva i report interattivi e la pianificazione dell&#39;aggiornamento dei dati.

<!-- 

c_report_technology.xml

 -->

## I report interattivi utilizzano la tecnologia Tableau

[!DNL Audience Manager] utilizza il software [Tableau](https://www.tableausoftware.com/) per visualizzare i dati nei report interattivi. Con [!DNL Tableau], i report [!UICONTROL Delivery and Overlap] utilizzano suggerimenti visivi e simboli che consentono di:

* Trova caratteristiche ad alte e basse prestazioni.
* Tratti spot e segmenti con sovrapposizione di visitatori univoci bassa e alta.
* Utilizza i dati di sovrapposizione per creare segmenti mirati.
* Espandi la portata identificando le caratteristiche correlate con una bassa sovrapposizione.

## Pianificazione aggiornamento dati

I dati dei rapporti vengono aggiornati settimanalmente ogni domenica. L’aggiornamento elabora i dati da sabato (il giorno prima) alla domenica precedente.

## Forme, colori e dimensioni utilizzati nei report interattivi {#shapes-colors-sizes}

La maggior parte dei rapporti interattivi visualizza i risultati utilizzando forme di dimensioni e colori diversi. Questo formato di visualizzazione è progettato per aiutarti a dare un senso ai dati visivamente, senza dover scorrere righe e colonne di numeri.

<!-- 

r_legend.xml

 -->

### Legenda rapporto

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">I cerchi indicano le caratteristiche di prima parte. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">I quadrati indicano caratteristiche di terze parti. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Colori</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Le ombre rosse indicano una sovrapposizione di <i>bassa</i>. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Le ombre verdi indicano <i>alta</i> sovrapposizione. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensione</b> </td> 
   <td colname="col2"> Le dimensioni aumentano o diminuiscono in proporzione diretta per raggiungere (il numero o la percentuale di clic o di utenti univoci in una caratteristica o in un segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Documentazione di Tableau {#tableau-documentation}

Per ulteriori informazioni sui controlli Tableau visibili nei report interattivi, consulta la documentazione ufficiale di [Tableau Server su Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)
