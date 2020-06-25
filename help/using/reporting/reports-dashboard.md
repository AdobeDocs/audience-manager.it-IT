---
description: Utilizzate il dashboard per visualizzare informazioni sui conteggi dei visitatori univoci dei vostri partner suddivisi per tipi di caratteristiche e segmenti per un intervallo di tempo specificato.
seo-description: Utilizzate il dashboard per visualizzare informazioni sui conteggi dei visitatori univoci dei vostri partner suddivisi per tipi di caratteristiche e segmenti per un intervallo di tempo specificato.
seo-title: Pannello Rapporti
solution: Audience Manager
title: Pannello Rapporti
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 0%

---


# Pannello Rapporti {#reports-dashboard}

Utilizzate il dashboard per visualizzare informazioni sui conteggi dei visitatori univoci suddivisi per tipo di caratteristiche e segmenti, per un intervallo di tempo specificato.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utilizza [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo di utenti all’ [!UICONTROL Dashboard]. Gli utenti possono visualizzare solo le informazioni sul dashboard che dispongono delle autorizzazioni per visualizzare. [!UICONTROL RBAC] consente di controllare i dati che possono essere visualizzati dai team interni.

Ad esempio, un&#39;agenzia che gestisce diversi account di inserzionisti può configurare le autorizzazioni per gruppi di utenti in modo che un team che gestisce l&#39;account dell&#39;inserzionista A non possa vedere i dati di reporting dell&#39;inserzionista B. Questo dashboard può essere utilizzato per risolvere problemi di consegna dei dati.

Ad esempio, se noti un calo, o picco, nel totale degli utenti univoci con la suddivisione di tipo di utente univoco (basato su regole rispetto a quello a bordo), hai un punto di partenza migliore per individuare un potenziale problema di consegna dei dati. Se notate un calo negli utenti univoci totali e negli utenti univoci caricati, potete passare al [!UICONTROL On-boarding Status] rapporto per verificare se si è verificato un problema con un file in entrata.

**Per accedere al dashboard:**

1. In the top navigation menu, click **[!UICONTROL Dashboard]**.
2. *Facoltativo* Selezionare l&#39;intervallo di tempo desiderato dall&#39;ultima data del rapporto dall&#39;elenco a discesa (7 giorni, 14 giorni (impostazione predefinita), 30 giorni o 60 giorni).

   A seconda del periodo selezionato, la modifica del delta nei pannelli [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] e [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] mostra la modifica apportata ai visitatori univoci nel periodo che termina oggi rispetto al periodo precedente della stessa lunghezza. Ad esempio, se selezionate 7 giorni, il delta confronta i visitatori univoci dei sette giorni precedenti con quelli dei sette giorni precedenti che terminano oggi con quelli dei sette giorni che terminano sette giorni fa.

   >[!NOTE]
   >
   >È possibile esaminare un cambiamento delta che sembra fuori dal comune eseguendo un [!UICONTROL Trend] rapporto. Ad esempio, se notate un cambiamento delta insolitamente grande negli ultimi sette giorni, potete eseguire un [!UICONTROL Trend] rapporto per gli ultimi 14 giorni (2 x 7) per comprendere meglio i numeri.

   A seconda delle autorizzazioni dell&#39;utente connesso, vengono visualizzati i seguenti pannelli:

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Caratteristiche principali/caratteristiche più modificate](../reporting/reports-dashboard.md#largest-traits)
   * [Segmenti maggiori/Segmenti più modificati](../reporting/reports-dashboard.md#most-changed-segments)

3. *Facoltativo* Fare clic **[!UICONTROL Normalize]** sopra un grafico per visualizzare tutti i dati sulla stessa scala. È inoltre possibile passare il puntatore del mouse su un punto dati per visualizzare ulteriori informazioni.

## Partner Uniques {#partner-uniques}

Autorizzazione necessaria per visualizzare: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Questo pannello visualizza il numero di visitatori univoci nel periodo di tempo specificato. Singole righe con colori diversi rappresentano il numero totale di visitatori univoci e il numero di visitatori univoci catturati utilizzando caratteristiche algoritmiche, basate su regole e registrate.

>[!NOTE]
>
>Il numero totale di visitatori univoci rappresenta i visitatori catturati tramite caratteristiche basate su regole o registrate a bordo. Tuttavia, il numero totale di visitatori univoci non corrisponde alla somma di visitatori univoci catturati utilizzando caratteristiche basate su regola e registrate. Lo stesso utente univoco potrebbe essere rappresentato in uno di questi due tipi di caratteristiche.

## Caratteristiche principali/caratteristiche più modificate {#largest-traits}

Autorizzazione necessaria per visualizzare: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Questo pannello mostra il numero di visitatori univoci catturati da varie caratteristiche.

Utilizzate l&#39;elenco a **[!UICONTROL Show]** discesa per visualizzare informazioni sui diversi tipi di caratteristiche: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded]o [!UICONTROL Rule-Based].

Questo pannello contiene le seguenti schede:

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
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci ordinati per numero (dal più alto al più basso) ed elenca anche il cambiamento delta di visitatori univoci durante l'intervallo di tempo specificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caratteristiche più modificate</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci ordinati dalla modifica del delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segmenti maggiori/Segmenti più modificati {#most-changed-segments}

Autorizzazione necessaria per visualizzare: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Questo pannello visualizza il numero di visitatori univoci catturati da vari segmenti in tempo reale.

Questo pannello contiene le seguenti schede:

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
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci e sul cambiamento delta di visitatori univoci durante l'intervallo di tempo specificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmenti più modificati</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci ordinati dalla modifica del delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

