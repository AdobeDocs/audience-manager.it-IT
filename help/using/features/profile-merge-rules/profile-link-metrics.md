---
description: Le metriche Collegamento profilo forniscono dati sulle persone e sui dispositivi che eseguono l'autenticazione sul sito. I dati e i grafici in Collegamento profilo si aggiornano dinamicamente durante la creazione di regole di unione o quando si fa clic su una regola esistente dal dashboard Regole di unione profilo. Queste metriche possono includere grafico del dispositivo da Adobe Experience Cloud Device Co-op o da altre origini di grafico del dispositivo di terze parti.
seo-description: Le metriche Collegamento profilo forniscono dati sulle persone e sui dispositivi che eseguono l'autenticazione sul sito. I dati e i grafici in Collegamento profilo si aggiornano dinamicamente durante la creazione di regole di unione o quando si fa clic su una regola esistente dal dashboard Regole di unione profilo. Queste metriche possono includere grafico del dispositivo da Adobe Experience Cloud Device Co-op o da altre origini di grafico del dispositivo di terze parti.
seo-title: Metriche dei rapporti per le regole di unione dei profili
solution: Audience Manager
title: Metriche dei rapporti per le regole di unione dei profili
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Metriche dei rapporti per le regole di unione dei profili {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] le metriche forniscono dati sulle persone e sui dispositivi che eseguono l'autenticazione sul sito. I dati e i grafici in [!UICONTROL Profile Merge Rule Reports] questione si aggiornano in modo dinamico durante la creazione di una regola di unione o quando si fa clic su una regola esistente dal [!UICONTROL Profile Merge Rules] dashboard. Queste metriche possono includere grafici dispositivo da origini di grafici dispositivo [!DNL Adobe Experience Cloud Device Co-op] o da altre origini di grafici dispositivo di terze parti.

## Unisci metriche regola {#merge-rule-metrics}

I rapporti restituiscono i dati sotto forma di grafici a barre affiancati quando le regole di unione utilizzano i dati di [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) o altri grafici di dispositivi di terze parti a cui puoi accedere in [!DNL Audience Manager]. Questo consente di confrontare i dati di prime parti autenticati con i dati cross-device forniti dal grafico del dispositivo di [!UICONTROL Experience Cloud Device Co-op] o da un altro, terzo. Per informazioni sui dati restituiti da [!UICONTROL Device Co-op], vedi [Device Graph: Processi interni e output](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Questi dati vengono aggiornati ogni giorno.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Attività autenticata</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Persone</span>attive: Numero di persone che hanno eseguito l’autenticazione sul sito per gli ultimi 60 giorni. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Dispositivo</span>incrociato: Il numero totale di ID <a href="merge-rules-start.md#create-data-source"> di</a> dispositivi diversi <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> memorizzati nell'origine</a> dati del profilo <a href="merge-rule-definitions.md"></a> autenticato selezionato per tutta la durata di vita dell'origine dati. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % persone</span>attive: Mostra <span class="wintitle"> persone</span> attive come %. </li> 
    </ul> <p> <span class="wintitle"> Attività</span> autenticata consente di confrontare le origini dati per attività, volume e percentuale. Può essere utile per trovare un'origine dati con molte persone e un'alta percentuale di utenti attivi. Oppure, puoi trovare un valore nel confronto tra origini dati con un'elevata percentuale di utenti attivi rispetto alla dimensione totale del pubblico. Ad esempio, a volte un'origine dati con un numero totale di ciclo di vita basso e un'attività elevata è più preziosa di quella con risultati di durata elevata e numeri di attività ridotti. </p> <p> <p>Nota: Le metriche <span class="wintitle"> Attività</span> autenticate contengono solo dati di collegamento <span class="wintitle"></span> profilo. Questo rapporto non include i dati di <span class="wintitle"> Device Graph</span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Media dispositivi per persona</span></b> </p> </td> 
   <td colname="col2"> <p> Mostra il numero medio di dispositivi utilizzati dai visitatori che hanno eseguito l'autenticazione sul sito per l'origine dati selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Dispositivi totali</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero totale di dispositivi utilizzati per l'autenticazione al sito per l'origine dati selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Totale persone</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero totale di persone identificate in modo determinante per l'origine dati selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Metriche di Device Graph {#device-graph-metrics}

I [!UICONTROL Merge Rules] rapporti mostrano inoltre i dati sul numero totale di persone e dispositivi che hanno visitato il sito per l'origine dati selezionata e il grafico del dispositivo. Queste metriche restituiscono i dati in base a intervalli di tempo preimpostati (il periodo di look-back) che variano a seconda dell'opzione del dispositivo selezionata al momento della creazione di una regola. La tabella seguente elenca questi intervalli di rapporti per ciascuna delle opzioni del grafico del dispositivo.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione Device Graph </th> 
   <th colname="col2" class="entry"> Intervallo di ricerca report </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Collegamento profilo</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Totale persone: 60 giorni </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Dispositivi totali: 120 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Co-op Device Graph</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Totale persone: 180 giorni </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Dispositivi totali: 180 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Totale persone: 180 giorni </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Dispositivi totali: 180 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Totale persone: 60 giorni </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Dispositivi totali 60 giorni </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Report di esempio {#sample-reports}

### Report collegamento profilo standard

Un [!UICONTROL Profile Link] rapporto standard è simile al seguente. Le regole di unione che utilizzano più origini dati (fino a 3, massimo) mostrano grafici in schede separate per ogni origine dati. Questa regola di unione non include [!UICONTROL Device Co-op] dati.

![](assets/profile-link-metrics.png)

### Report Collegamento Profilo Con Dati Grafico Dispositivo

Un [!UICONTROL Profile Link Device Graph] report che include i dati del grafico del dispositivo dal grafico del dispositivo [!UICONTROL Adobe Experience Cloud Device Co-op] o da un grafico di terze parti mostra [!UICONTROL Profile Link] e i dati del grafico del dispositivo con grafici a barre affiancati. Posizionando questi grafici adiacenti è possibile valutare i vantaggi derivanti dall’utilizzo dei grafici [!UICONTROL Experience Cloud Device Co-op] rispetto a [!UICONTROL Profile Link] se stessi. Le regole di unione che utilizzano più origini dati (fino a 3, massimo) mostrano grafici in schede separate per ogni origine dati. Come promemoria, il [!UICONTROL Authenticated Activity] grafico e le metriche non restituiscono i dati dal grafico del [!DNL Adobe] dispositivo o da altri grafici del dispositivo di terze parti a cui puoi accedere in [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Grafici di tendenza collegamenti profilo {#profile-link-trend}

Oltre alle altre visualizzazioni di dati, [!UICONTROL Profile Link] i rapporti includono un grafico a linee. Il grafico a linee è progettato per mostrare le tendenze nel tempo per le regole del profilo. I grafici delle tendenze (e gli altri rapporti) sono disponibili quando si fa clic su una regola dalla pagina di [!UICONTROL Profile Merge Rules] destinazione ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Questi grafici includono i dati del grafico del dispositivo se siete membri del grafico del dispositivo [!UICONTROL Device Co-op] o di altri grafici di terze parti a cui potete accedere in [!DNL Audience Manager]. Fare clic su una linea di tendenza per visualizzare i dati sottostanti.

>[!MORE_LIKE_this]
>
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

