---
description: Le metriche di collegamento profilo forniscono dati su persone e dispositivi che si autenticano sul sito. I dati e i grafici in Collegamento profilo vengono aggiornati dinamicamente quando si crea una regola di unione o quando si fa clic su una regola esistente dal dashboard Regole di unione profili. Queste metriche possono includere grafici dei dispositivi da altre origini di grafici dei dispositivi di terze parti.
seo-description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from other third-party device graph sources.
seo-title: Report Metrics for Profile Merge Rules
solution: Audience Manager
title: Metriche di rapporto per regole di unione profili
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# Metriche di rapporto per regole di unione profili {#report-metrics-for-profile-merge-rules}

Le metriche [!UICONTROL Profile Merge Rule] forniscono dati su persone e dispositivi che si autenticano nel sito. I dati e i grafici in [!UICONTROL Profile Merge Rule Reports] vengono aggiornati dinamicamente quando si crea una regola di unione o quando si fa clic su una regola esistente dal dashboard [!UICONTROL Profile Merge Rules]. Queste metriche possono includere grafici dei dispositivi provenienti da altre origini di grafici dei dispositivi di terze parti.

## Metriche delle regole di unione {#merge-rule-metrics}

I report restituiscono dati in grafici a barre affiancate quando le regole di unione utilizzano dati di grafici di dispositivi di terze parti a cui è possibile accedere in [!DNL Audience Manager]. Questo consente di confrontare i dati autenticati di prime parti con i dati cross-device forniti da grafici per dispositivi di terze parti. Questi dati vengono aggiornati quotidianamente.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> attività autenticata</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> persone attive</span>: numero di persone che hanno eseguito l'autenticazione nel sito negli ultimi 60 giorni. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> tra dispositivi</span>: numero totale di <a href="merge-rules-start.md#create-data-source"> ID tra dispositivi</a> archiviati in <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html"> Data Source</a> del <a href="merge-rule-definitions.md"> profilo autenticato selezionato</a> per la durata dell'origine dati. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % persone attive</span>: mostra <span class="wintitle"> persone attive</span> come %. </li> 
    </ul> <p> <span class="wintitle"> attività autenticata</span> consente di confrontare le origini dati per attività, volume e percentuale. Può aiutarti a trovare un’origine dati con molte persone e un’alta percentuale di utenti attivi. In alternativa, potrebbe essere utile confrontare le origini dati con un’alta proporzione di utenti attivi rispetto alla dimensione totale del pubblico. Ad esempio, a volte un’origine dati con un numero di vita totale basso e un’attività elevata ha un valore maggiore rispetto a quelle con risultati di vita elevati e numeri di attività bassi. </p> <p> <p>Nota: le metriche dell'attività autenticata <span class="wintitle"></span> contengono solo i dati del collegamento del profilo <span class="wintitle"></span>. Questo report non include i dati del grafico del dispositivo <span class="wintitle"></span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> dispositivi medi per persona</span></b> </p> </td> 
   <td colname="col2"> <p> Mostra il numero medio di dispositivi utilizzati dai visitatori che hanno eseguito l'autenticazione sul sito per l'origine dati selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> dispositivi totali</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero totale di dispositivi utilizzati dagli utenti per l'autenticazione sul sito per l'origine dati selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> persone totali</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero totale di persone identificate in modo deterministico per l'origine dati selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Metriche del grafico dei dispositivi {#device-graph-metrics}

Nei report [!UICONTROL Merge Rules] vengono inoltre visualizzati i dati sul numero totale di persone e dispositivi che hanno visitato il sito per l&#39;origine dati e il grafico dei dispositivi selezionati. Queste metriche restituiscono dati in base a intervalli di tempo predefiniti (il periodo di look-back) che variano a seconda dell’opzione del dispositivo selezionata al momento della creazione di una regola. Nella tabella seguente sono elencati questi intervalli di rapporti per ciascuna delle opzioni del grafico dei dispositivi.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione Device Graph </th> 
   <th colname="col2" class="entry"> Intervallo di look-back del rapporto </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Collegamento profilo <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Persone totali: 60 giorni </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Dispositivi totali: 120 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Persone totali: 180 giorni </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Dispositivi totali: 180 giorni </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Persone totali: 60 giorni </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Dispositivi totali 60 giorni </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Report di esempio {#sample-reports}

### Rapporto collegamento profilo standard

Un report [!UICONTROL Profile Link] standard ha l&#39;aspetto seguente. Le regole di unione che utilizzano più origini dati (fino a un massimo di 3) visualizzano i grafici in schede separate per ogni origine dati. Questa regola di unione non include i dati [!UICONTROL external device graph].

![](assets/profile-link-metrics.png)

### Rapporto Collegamento Profilo Con Dati Grafici Dei Dispositivi

Un report [!UICONTROL Profile Link Device Graph] che include dati di grafici dei dispositivi da grafici dei dispositivi di terze parti mostra [!UICONTROL Profile Link] e dati di grafici dei dispositivi con grafici a barre affiancati. Il posizionamento di questi grafici adiacenti consente di valutare i vantaggi dell&#39;utilizzo di grafici dei dispositivi esterni rispetto a [!UICONTROL Profile Link]. Le regole di unione che utilizzano più origini dati (fino a un massimo di 3) visualizzano i grafici in schede separate per ogni origine dati. Come promemoria, il grafico e le metriche di [!UICONTROL Authenticated Activity] non restituiscono dati dal grafico dei dispositivi di [!DNL Adobe] o da altri grafici dei dispositivi di terze parti a cui è possibile accedere in [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Grafici delle tendenze dei collegamenti dei profili {#profile-link-trend}

Oltre alle altre visualizzazioni dati, i rapporti di [!UICONTROL Profile Link] includono un grafico a linee. Il grafico a linee è progettato per mostrare le tendenze nel tempo per le regole del profilo. I grafici delle tendenze (e gli altri rapporti) sono disponibili quando si fa clic su una regola dalla pagina di destinazione [!UICONTROL Profile Merge Rules] ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Questi grafici includono i dati dei grafici dei dispositivi se sei membro di grafici dei dispositivi di terze parti a cui puoi accedere in [!DNL Audience Manager]. Fai clic su una linea di tendenza per visualizzare i dati sottostanti.

>[!MORELIKETHIS]
>
>* [Domande frequenti sulle regole di unione profili](../../faq/faq-profile-merge.md)
