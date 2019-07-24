---
description: Usa il dashboard per visualizzare le informazioni sui conteggi dei visitatori univoci dei tuoi partner suddivisi per tipo di caratteristica e segmenti per un intervallo di tempo specificato.
seo-description: Usa il dashboard per visualizzare le informazioni sui conteggi dei visitatori univoci dei tuoi partner suddivisi per tipo di caratteristica e segmenti per un intervallo di tempo specificato.
seo-title: Dashboard rapporti
solution: Audience Manager
title: Dashboard rapporti
uuid: 350 eee 2 d -72 f 7-42 a 7-916 b -60 f 9 a 362 c 5 cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Reports Dashboard {#reports-dashboard}

Usa il dashboard per visualizzare le informazioni sui conteggi dei visitatori univoci suddivisi per tipo di caratteristica e segmenti, per un intervallo di tempo specificato.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo utente a [!UICONTROL Dashboard]. Gli utenti possono vedere solo le informazioni del dashboard che possono visualizzare. [!UICONTROL RBAC] consente di controllare quali dei team interni di dati di reporting sono in grado di visualizzare.

Ad esempio, un'agenzia che gestisce diversi account pubblicitari può configurare le autorizzazioni del gruppo di utenti in modo che un team che gestisce l'account dell'inserzionista A non possa vedere i dati di reporting dell'inserzionista B. Questa dashboard può essere utilizzata per risolvere problemi relativi alla consegna dei dati.

Ad esempio, se notate un picco o un picco in totale utenti univoci con la suddivisione del tipo di utente univoco (basato su regole e su se stesso), avete un punto di partenza migliore per tenere traccia di un potenziale problema di consegna dati. If you notice a dip in total unique users and in on-boarded unique users, you can go to the [!UICONTROL On-boarding Status] report to see if there was an issue with an inbound file.

**Per accedere al dashboard:**

1. In the top navigation menu, click **[!UICONTROL Dashboard]**.
2. *Facoltativo* Seleziona l'intervallo di tempo desiderato dall'elenco a discesa dell'ultimo rapporto (7 giorni, 14 giorni (impostazione predefinita), 30 giorno o 60 giorni.

   Depending on the period selected, the delta change in the [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] and [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] panels displays the change in unique visitors in the audience over the period ending today vs. the prior period of the same length. Ad esempio, se selezioni 7 Giorni, il delta confronta i visitatori unici con i sette giorni successivi che si ritrovano oggi stesso rispetto ai visitatori unici dei sette giorni successivi, sette giorni fa.

   >[!NOTE]
   >
   >You can investigate a delta change that seems out of the ordinary by running a [!UICONTROL Trend] report. For example, if you see an unusually large delta change during the last seven days, you could run a [!UICONTROL Trend] report for the last 14 days (2 x 7) to better understand the numbers.

   A seconda delle autorizzazioni dell'utente connesso, vengono visualizzati i seguenti pannelli:

   * [Partner Unitques](../reporting/reports-dashboard.md#partner-uniques)
   * [Caratteristiche più grandi/più modificate](../reporting/reports-dashboard.md#largest-traits)
   * [Segmenti principali/Segmenti più modificati](../reporting/reports-dashboard.md#most-changed-segments)

3. *Facoltativo* Fate clic **[!UICONTROL Normalize]** sopra qualsiasi grafico per mostrare tutti i dati sulla stessa scala. Puoi anche passare il cursore sopra un punto dati per visualizzare ulteriori informazioni.

## Partner Uniques {#partner-uniques}

Permission Required to View: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Questo pannello visualizza il numero di visitatori unici nel periodo di tempo specificato. Le singole linee con codifica colori rappresentano il numero totale di visitatori univoci e il numero di visitatori unici acquisiti utilizzando caratteristiche algoritmiche, basate su regole e caricate.

>[!NOTE]
>
>Il numero totale di visitatori unici rappresenta i visitatori acquisiti tramite tratti basati su regole o su smartphone. Tuttavia, il numero totale di visitatori univoci non equivale alla somma di visitatori unici acquisiti utilizzando le caratteristiche basate su regole e caricate. Lo stesso utente univoco potrebbe essere rappresentato in uno di questi due tipi di caratteristiche.

## Largest Traits/Most Changed Traits {#largest-traits}

Permission Required to View: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Questo pannello mostra il numero di visitatori unici acquisiti da diverse caratteristiche.

Use the **[!UICONTROL Show]** drop-down list to display information about different types of traits: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded], or [!UICONTROL Rule-Based].

Questo pannello contiene le schede seguenti:

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tab </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caratteristiche più grandi</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori unici ordinati per numero (dalla più alta alla più bassa) ed elenca anche il cambio delta di visitatori unici nel periodo di tempo specificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caratteristiche più modificate</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori unici ordinati per modifica delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments/Most Changed Segments {#most-changed-segments}

Permission Required to View: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Questo pannello mostra il numero di visitatori unici acquisiti da vari segmenti in tempo reale.

Questo pannello contiene le schede seguenti:

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tab </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmenti più grandi</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci e sul cambiamento delta di visitatori unici durante l'intervallo di tempo specificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmenti più modificati</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori unici ordinati per modifica delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

