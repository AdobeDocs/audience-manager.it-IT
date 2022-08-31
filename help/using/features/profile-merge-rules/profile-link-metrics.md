---
description: Le metriche Collegamento profilo forniscono dati sulle persone e sui dispositivi che si autenticano sul sito. I dati e i grafici in Collegamento profilo vengono aggiornati dinamicamente quando crei una regola di unione o fai clic su una regola esistente dal dashboard Regole di unione profili . Queste metriche possono includere grafici dei dispositivi da altre sorgenti di grafici dei dispositivi di terze parti.
seo-description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from other third-party device graph sources.
seo-title: Report Metrics for Profile Merge Rules
solution: Audience Manager
title: Metriche di report per le regole di unione profili
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 2%

---

# Metriche di report per le regole di unione profili {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] Le metriche forniscono dati su persone e dispositivi che si autenticano sul sito. I dati e i grafici in [!UICONTROL Profile Merge Rule Reports] aggiornare dinamicamente durante la creazione di una regola di unione o quando si fa clic su una regola esistente dal [!UICONTROL Profile Merge Rules] dashboard. Queste metriche possono includere grafici dei dispositivi provenienti da altre origini di grafici dei dispositivi di terze parti.

## Metriche delle regole di unione {#merge-rule-metrics}

I rapporti restituiscono i dati sotto forma di grafici a barre affiancati quando le regole di unione utilizzano dati provenienti da grafici dei dispositivi di terze parti a cui puoi accedere in [!DNL Audience Manager]. Questo ti consente di confrontare i dati di prime parti autenticati con i dati di più dispositivi forniti da grafici dei dispositivi di terze parti. Questi dati vengono aggiornati quotidianamente.

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
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Persone attive</span>: Il numero di persone che hanno eseguito l'autenticazione sul sito per gli ultimi 60 giorni. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Cross-Device</span>: Numero totale di <a href="merge-rules-start.md#create-data-source"> ID di più dispositivi</a> memorizzati in <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html"> Origine dati</a> del <a href="merge-rule-definitions.md"> Profilo autenticato</a> per la durata in cui l'origine dati è esistita. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % persone attive</span>: Mostra <span class="wintitle"> Persone attive</span> come %. </li> 
    </ul> <p> <span class="wintitle"> Attività autenticata</span> consente di confrontare le origini dati per attività, volume e percentuale. Può essere utile per trovare un’origine dati con molte persone e un’alta percentuale di utenti attivi. Oppure, puoi trovare valore nel confrontare le origini di dati con un’alta percentuale di utenti attivi rispetto alla dimensione totale del pubblico. Ad esempio, a volte un’origine dati con un numero di vita totale basso e un’attività elevata è più preziosa di quelle con risultati a vita elevata e numeri di attività bassi. </p> <p> <p>Nota: La <span class="wintitle"> Attività autenticata</span> le metriche contengono <span class="wintitle"> Collegamento profilo</span> solo dati. Questo rapporto non include <span class="wintitle"> Device Graph</span> dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Dispositivi medi per persona</span></b> </p> </td> 
   <td colname="col2"> <p> Mostra il numero medio di dispositivi utilizzati dai visitatori che hanno eseguito l’autenticazione sul sito per l’origine dati selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Dispositivi totali</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero totale di dispositivi utilizzati per l'autenticazione sul sito per l'origine dati selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Totale persone</span></b> </p> </td> 
   <td colname="col2"> <p>Mostra il numero totale di persone identificate in modo deterministico per l’origine dati selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Metriche di Device Graph {#device-graph-metrics}

La [!UICONTROL Merge Rules] i rapporti mostrano inoltre i dati sul numero totale di persone e dispositivi che hanno visitato il sito per l’origine dati selezionata e il grafico del dispositivo. Queste metriche restituiscono dati in base a intervalli di tempo predefiniti (il periodo di look-back) che variano a seconda dell’opzione del dispositivo selezionata durante la creazione di una regola. Nella tabella seguente sono elencati questi intervalli di rapporti per ciascuna delle opzioni del grafico dei dispositivi.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione Device Graph </th> 
   <th colname="col2" class="entry"> Intervallo di look-back del rapporto </th> 
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

### Rapporto collegamenti profilo standard

Standard [!UICONTROL Profile Link] il report è simile al seguente esempio. Le regole di unione che utilizzano più origini dati (fino a 3, massimo) mostrano grafici in schede separate per ogni origine dati. Questa regola di unione non include [!UICONTROL external device graph] dati.

![](assets/profile-link-metrics.png)

### Rapporto Collegamento profilo con dati grafico dispositivo

A [!UICONTROL Profile Link Device Graph] rapporti che includono i dati del grafico dei dispositivi da grafici dei dispositivi di terze parti [!UICONTROL Profile Link] e i dati del grafico dei dispositivi con grafici a barre affiancati. Il posizionamento di questi grafici adiacenti consente di valutare i vantaggi dell’utilizzo di grafici dei dispositivi esterni rispetto a [!UICONTROL Profile Link] da solo. Le regole di unione che utilizzano più origini dati (fino a 3, massimo) mostrano grafici in schede separate per ogni origine dati. Come promemoria, [!UICONTROL Authenticated Activity] il grafico e le metriche non restituiscono i dati dal [!DNL Adobe] grafico dei dispositivi o altri grafici dei dispositivi di terze parti a cui puoi accedere in [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Grafici delle tendenze dei collegamenti profilo {#profile-link-trend}

Oltre alle altre visualizzazioni di dati, [!UICONTROL Profile Link] i rapporti includono un grafico a linee. Il grafico a linee è progettato per mostrare le tendenze nel tempo per le regole del profilo. I grafici delle tendenze (e gli altri rapporti) sono disponibili quando fai clic su una regola nel [!UICONTROL Profile Merge Rules] pagina di destinazione ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Questi grafici includono i dati dei grafici dei dispositivi se sei membro di grafici dei dispositivi di terze parti a cui puoi accedere in [!DNL Audience Manager]. Fai clic su una linea di tendenza per visualizzare i dati sottostanti.

>[!MORELIKETHIS]
>
>* [Domande frequenti sulle regole di unione dei profili](../../faq/faq-profile-merge.md)

