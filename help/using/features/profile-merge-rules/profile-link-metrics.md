---
description: Le metriche Collegamento profilo forniscono dati sulle persone e sui dispositivi che si autenticano sul sito. I dati e i grafici in Collegamento profilo si aggiornano dinamicamente man mano che crei una regola di unione o quando fai clic su una regola esistente dal dashboard Regole unione profilo. Queste metriche possono includere grafico dispositivo da Adobe Experience Cloud Device Co-op o da altre sorgenti grafico dispositivo di terze parti.
seo-description: Le metriche Collegamento profilo forniscono dati sulle persone e sui dispositivi che si autenticano sul sito. I dati e i grafici in Collegamento profilo si aggiornano dinamicamente man mano che crei una regola di unione o quando fai clic su una regola esistente dal dashboard Regole unione profilo. Queste metriche possono includere grafico dispositivo da Adobe Experience Cloud Device Co-op o da altre sorgenti grafico dispositivo di terze parti.
seo-title: Metriche di report per regole di unione profilo
solution: Audience Manager
title: Metriche di report per regole di unione profilo
uuid: 76 a 86 ff 0-4 c 64-4734-aec 0-0 a 8828942096
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Report Metrics for Profile Merge Rules {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Link] forniscono dati sulle persone e sui dispositivi che si autenticano sul sito. The data and graphs in [!UICONTROL Profile Link] update dynamically as you create a merge rules or when you click an existing rule from the [!UICONTROL Profile Merge Rules] dashboard. These metrics can include device graph from the [!DNL Adobe Experience Cloud Device Co-op] or other third-party device graph sources.

## Merge Rule Metrics {#merge-rule-metrics}

Reports return data in side-by-side bar graphs when your merge rules use data from the [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) or other, third-party device graphs you may have access to in [!DNL Audience Manager]. This lets you compare your authenticated, first-party data with cross-device data provided by the [!UICONTROL Experience Cloud Device Co-op] or another, third-party device graph. For information about data returned by the [!UICONTROL Device Co-op], see [The Device Graph: Internal Processes and Output](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Questi dati vengono aggiornati ogni giorno.

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
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Persone attive</span>: Numero di persone che hanno eseguito l'autenticazione sul sito per gli ultimi 60 giorni. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Cross Device</span>: Il numero totale degli ID dispositivo <a href="../../features/profile-merge-rules/merge-rules-start.md#create-data-source"> incrociati</a> memorizzati nell'origine <a href="../../features/manage-datasources.md#create-data-source"> dati</a> del profilo <a href="../../features/profile-merge-rules/merge-rule-definitions.md"> autenticato selezionato</a> per la durata in cui l'origine dati è stata rilevata. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % Active People</span>: Mostra <span class="wintitle"> Persone attive</span> come %. </li> 
    </ul> <p> <span class="wintitle"> L'attività autenticata</span> consente di confrontare le origini dati per attività, volume e percentuale. Può essere utile per trovare un'origine dati con molte persone e una percentuale alta di utenti attivi. Oppure, potete trovare un valore nel confronto delle origini dati con elevata proporzione di utenti attivi rispetto alla dimensione totale del pubblico. Ad esempio, a volte un'origine dati con numeri di durata totale ridotti e un'attività elevata sono più utili rispetto a quelle con risultati di durata elevata e numeri di attività ridotti. </p> <p> <p>Note: The <span class="wintitle"> Authenticated Activity</span> metrics contain <span class="wintitle"> Profile Link</span> data only. This report does not include <span class="wintitle"> Device Graph</span> data. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Media Devices per Person</span></b> </p> </td> 
   <td colname="col2"> <p> Mostra il numero medio di dispositivi utilizzati dai visitatori che hanno eseguito l'autenticazione al sito per l'origine dati selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Dispositivi totali</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero totale di dispositivi utilizzati da persone per l'autenticazione sul sito per l'origine dati selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Totale persone</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero totale di persone identificate in modo determinico per l'origine dati selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Device Graph Metrics {#device-graph-metrics}

The [!UICONTROL Merge Rules] reports also show data on the total number of people and devices who have visited your site for the selected data source and device graph. Queste metriche restituiscono dati in base agli intervalli di tempo preimpostati (il periodo di look-back) che varia a seconda dell'opzione del dispositivo selezionata durante la creazione di una regola. Nella tabella seguente sono elencati questi intervalli di report per ciascuna opzione del grafico dispositivo.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione Grafico dispositivo </th> 
   <th colname="col2" class="entry"> Intervallo di look-back report </th> 
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
   <td colname="col1"> <p><span class="wintitle"> Liveramp</span> </p> </td> 
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

## Sample Reports {#sample-reports}

### Rapporto collegamento profilo standard

A standard [!UICONTROL Profile Link] report looks like the following example. Le regole di unione che utilizzano più origini dati (fino a 3, massimo) mostrano i grafici in schede separate per ogni origine dati. This merge rule does not include [!UICONTROL Device Co-op] data.

![](assets/coop-metrics1.png)

### Rapporto collegamento profilo con dati grafico dispositivo

[!UICONTROL Profile Link] Un rapporto che include dati grafici del dispositivo provenienti da [!UICONTROL Adobe Experience Cloud Device Co-op] un grafico di dispositivo di terze parti o da [!UICONTROL Profile Link] un grafico di terze parti con grafici a barre affiancati. Placing these graphs adjacent to each other lets you evaluate the benefits of using the [!UICONTROL Experience Cloud Device Co-op] compared to [!UICONTROL Profile Link] by itself. Le regole di unione che utilizzano più origini dati (fino a 3, massimo) mostrano i grafici in schede separate per ogni origine dati. As a reminder, the [!UICONTROL Authenticated Activity] graph and metrics do not return data from the [!DNL Adobe] device graph or other, third-party device graphs you may have access to in [!DNL Audience Manager].

![](assets/coop-metrics2.png)

## Profile Link Trend Graphs {#profile-link-trend}

In addition to the other data visualizations, [!UICONTROL Profile Link] reports include a line graph. Il grafico a linee è progettato per mostrare le tendenze nel tempo per le regole del profilo. Trend graphs (and the other reports) are available when you click a rule from the [!UICONTROL Profile Merge Rules] landing page ( **[!UICONTROL Audience Data > Profile Merge Rules]**). These graphs include device graph data if you're a member of the [!UICONTROL Device Co-op] or other, third-party device graphs you may have access to in [!DNL Audience Manager]. Fai clic su una linea di tendenza per vedere i dati sottostanti.

![](assets/authenticated_trends.png)

>[!MORE_ LIKE_ THIS]
>
>* [Domande frequenti sulle regole di unione profilo](../../faq/faq-profile-merge.md)

