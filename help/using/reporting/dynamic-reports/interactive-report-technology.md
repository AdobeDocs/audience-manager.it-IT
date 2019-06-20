---
description: Descrive il software sottostante che attiva i rapporti interattivi e la pianificazione dell'aggiornamento dei dati.
seo-description: Descrive il software sottostante che attiva i rapporti interattivi e la pianificazione dell'aggiornamento dei dati.
seo-title: Report Technology
solution: Audience Manager
title: Report Technology
uuid: 5 f 3 d 815 b-e 1 e 6-42 f 2-b 848-ac 035 a 5 aa 77 d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Report Technology{#report-technology}

Descrive il software sottostante che attiva i rapporti interattivi e la pianificazione dell&#39;aggiornamento dei dati.

<!-- 

c_report_technology.xml

 -->

## I report interattivi utilizzano Tableau Technology

[!DNL Audience Manager] utilizza [il software Tableau](https://www.tableausoftware.com/) per visualizzare i dati nei rapporti interattivi. Con [!DNL Tableau]i rapporti, [!UICONTROL Delivery and Overlap] i rapporti possono essere utilizzati per essere utilizzati in modo visivo:

* Trova caratteristiche elevate e a bassa prestazioni.
* Caratteristiche tinte piatte e segmenti con sovrapposizione visitatore bassa e alta.
* Utilizzare dati di sovrapposizione per creare segmenti di destinazione.
* Amplia la portata identificando caratteristiche correlate con sovrapposizione ridotta.

## Pianificazione aggiornamento dati

I dati del report vengono aggiornati settimanalmente ogni domenica. L&#39;aggiornamento elabora i dati da sabato (il giorno prima) alla domenica precedente.

## Forme, colori e dimensioni utilizzati nei report interattivi {#shapes-colors-sizes}

La maggior parte dei rapporti interattivi visualizzano risultati con forme di dimensioni e colori diversi. Questo formato di visualizzazione è progettato per facilitare l&#39;interpretazione dei dati visivi, senza dover passare attraverso righe e colonne di numeri.

<!-- 

r_legend.xml

 -->

### Legenda report

La tabella seguente definisce forme, dimensioni e colori utilizzati nei report dinamici.

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">I cerchi indicano le caratteristiche di prime parti. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">I quadrati indicano caratteristiche di terze parti. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Colori</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Le tonalità rosse indicano <i>una sovrapposizione bassa</i> . </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Le tonalità verdi indicano <i>una sovrapposizione alta</i> . </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensioni</b> </td> 
   <td colname="col2"> Le dimensioni aumentano o diminuisce in proporzione diretta per raggiungere il risultato (il numero o il % dei clic o per gli utenti univoci in un segmento o segmento). </td> 
  </tr> 
 </tbody> 
</table>

## Icone e strumenti per report descritti {#icons-tools-explained}

Descrive come cercare e utilizzare le varie icone utilizzate nei rapporti dinamici.

<!-- 

r_icons.xml

 -->

### Icone e strumenti di dati

Le seguenti icone sono disponibili nella parte inferiore di ciascuna finestra di rapporti dinamica. L&#39;illustrazione seguente fornisce ulteriori informazioni su questi strumenti.

![](assets/tools_icons90.png)

### Esporta dati

Questi strumenti consentono di esportare i dati dal rapporto in 4 formati diversi.

| Opzione di esportazione | Esporta dati |
|---|---|
| **[!UICONTROL Image]** | Come file di immagine (. png). Utile per scaricare e condividere i dati dei rapporti nel formato grafico originale. |
| **[!UICONTROL PDF]** | Come file PDF. |
| **[!UICONTROL Data]** | In una nuova finestra del browser come dati numerici nelle colonne e nelle righe. |
| **[!UICONTROL Crosstab]** | Come file. csv. |

### Ripristina modifiche

Selezionate questo strumento per annullare eventuali modifiche interattive eventualmente apportate sul rapporto.

### Aggiornamenti automatici

I [!UICONTROL Delivery-Performance] rapporti e [!UICONTROL Trait-to-Trait Overlap] sono rapporti dinamici che rispondono e cambiano in base alle azioni di clic dell&#39;utente.

Ad esempio, supponiamo di voler selezionare diversi inserzionisti nel [!UICONTROL Overlap] rapporto. Quando sono abilitati, gli aggiornamenti automatici iniziano a restituire dati non appena selezionate una casella di controllo. Questo comportamento dinamico può interrompere il flusso di lavoro perché dovete attendere fino al termine dell&#39;elaborazione prima di selezionare un altro inserzionista. Utilizzate questo strumento per disattivare la funzione (e riattivarla), a seconda delle necessità.

### Aggiorna dati

Fai clic sull&#39;icona di aggiornamento per eseguire un rapporto o ricaricare il set di dati. Quando gli aggiornamenti automatici sono disattivati, fate clic su Aggiorna per eseguire o aggiornare il rapporto.

### Strumento Ricerca

La ricerca è rappresentata da un&#39;icona della lente di ingrandimento generica (non visualizzata). Il campo di ricerca viene nascosto finché non fate clic sulle etichette di selezione sul lato sinistro della schermata. La tabella seguente descrive la posizione dello strumento di ricerca per ogni rapporto.

| Report | Per cercare, passare il mouse su |
|---|---|
| [!UICONTROL Delivery and Performance] rapporto | Etichetta &quot;Nome creatore dell&#39;annuncio&quot;. |
| [!UICONTROL Overlap] rapporti | Etichetta &quot;Nome SID&quot;. |
