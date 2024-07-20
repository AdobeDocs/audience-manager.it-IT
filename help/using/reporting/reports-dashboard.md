---
description: Utilizza la dashboard per visualizzare informazioni sui conteggi di visitatori univoci dei tuoi partner suddivisi per tipi di caratteristiche e segmenti per un intervallo di tempo specificato.
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: Dashboard dei report
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Dashboard dei report {#reports-dashboard}

Utilizza la dashboard per visualizzare informazioni sui conteggi dei visitatori univoci suddivisi per tipi di caratteristiche e segmenti per un intervallo di tempo specificato.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utilizza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo utenti a [!UICONTROL Dashboard]. Gli utenti possono visualizzare solo le informazioni sul dashboard per le quali dispongono delle autorizzazioni di visualizzazione. La funzionalità [!UICONTROL RBAC] consente di controllare i dati di reporting che i team interni possono visualizzare.

Ad esempio, un’agenzia che gestisce account pubblicitari diversi può configurare le autorizzazioni per i gruppi di utenti in modo che un team che gestisce l’account dell’inserzionista A non possa visualizzare i dati di reporting dell’inserzionista B. Questo dashboard può essere utilizzato per risolvere i problemi di consegna dei dati.

Ad esempio, se noti un calo, o un picco, nel totale degli utenti univoci con la suddivisione per tipo di utente univoco (basato su regole vs. on-boarded), hai un punto di partenza migliore per individuare un potenziale problema di consegna dei dati. Se si nota un calo del totale degli utenti univoci e degli utenti univoci onboarded, è possibile andare al rapporto [!UICONTROL On-boarding Status] per vedere se c&#39;è stato un problema con un file in entrata.

**Per accedere al dashboard:**

1. Nel menu di navigazione superiore, fare clic su **[!UICONTROL Dashboard]**.
2. *Facoltativo* Selezionare dall&#39;elenco a discesa l&#39;intervallo di tempo desiderato per l&#39;ultima data del rapporto (7 giorni, 14 giorni (impostazione predefinita), 30 giorni o 60 giorni).

   A seconda del periodo selezionato, la modifica delta nei pannelli [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] e [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] mostra la modifica dei visitatori univoci nel pubblico nel periodo che termina oggi rispetto al periodo precedente della stessa durata. Ad esempio, se selezioni 7 giorni, il delta confronta i visitatori univoci dei sette giorni precedenti fino a oggi con i visitatori univoci dei sette giorni precedenti fino a sette giorni fa.

   >[!NOTE]
   >
   >È possibile analizzare una modifica delta che sembra fuori dal comune eseguendo un report [!UICONTROL Trend]. Ad esempio, se durante gli ultimi sette giorni si verifica una modifica delta insolitamente grande, è possibile eseguire un report [!UICONTROL Trend] per gli ultimi 14 giorni (2 x 7) per comprendere meglio i numeri.

   A seconda delle autorizzazioni dell’utente connesso, vengono visualizzati i seguenti pannelli:

   * [Univoci partner](../reporting/reports-dashboard.md#partner-uniques)
   * [Caratteristiche più grandi/caratteristiche più modificate](../reporting/reports-dashboard.md#largest-traits)
   * [Segmenti più grandi/Segmenti più modificati](../reporting/reports-dashboard.md#most-changed-segments)

3. *Facoltativo* Fai clic su **[!UICONTROL Normalize]** sopra qualsiasi grafico per visualizzare tutti i dati sulla stessa scala. Per visualizzare ulteriori informazioni, puoi anche passare il mouse su qualsiasi punto dati.

## Univoci partner {#partner-uniques}

Autorizzazione necessaria per visualizzare: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Questo pannello visualizza il numero di visitatori univoci durante l’intervallo di tempo specificato. Le singole linee codificate per colore rappresentano il numero totale di visitatori univoci e il numero di visitatori univoci acquisiti tramite caratteristiche algoritmiche, basate su regole e onboarded.

>[!NOTE]
>
>Il numero totale di visitatori univoci rappresenta i visitatori acquisiti tramite caratteristiche basate su regole o onboarded. Tuttavia, il numero totale di visitatori univoci non è uguale alla somma dei visitatori univoci acquisiti utilizzando le caratteristiche basate su regole e onboarded. Lo stesso utente univoco può essere rappresentato in uno di questi due tipi di caratteristiche.

## Caratteristiche più grandi/caratteristiche più modificate {#largest-traits}

Autorizzazione necessaria per visualizzare: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Questo pannello mostra il numero di visitatori univoci acquisiti da varie caratteristiche.

Utilizzare l&#39;elenco a discesa **[!UICONTROL Show]** per visualizzare informazioni su diversi tipi di caratteristiche: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] o [!UICONTROL Rule-Based].

Questo pannello contiene le seguenti schede:

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linguetta </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> caratteristiche più grandi</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci ordinati per numero (dal più alto al più basso) ed elenca anche la variazione delta dei visitatori univoci durante l’intervallo di tempo specificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> caratteristiche più modificate</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci in base alla modifica delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segmenti più grandi/Segmenti più modificati {#most-changed-segments}

Autorizzazione necessaria per visualizzare: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Questo pannello mostra in tempo reale il numero di visitatori univoci acquisiti da vari segmenti.

Questo pannello contiene le seguenti schede:

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linguetta </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> segmenti più grandi</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci e sulla variazione delta dei visitatori univoci durante l’intervallo di tempo specificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> segmenti più modificati</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci in base alla modifica delta. </p> </td> 
  </tr> 
 </tbody> 
</table>
