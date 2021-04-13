---
description: Utilizza il dashboard per visualizzare informazioni sui conteggi univoci dei visitatori dei tuoi partner suddivisi per tipi di caratteristiche e segmenti per un intervallo di tempo specificato.
seo-description: Utilizza il dashboard per visualizzare informazioni sui conteggi univoci dei visitatori dei tuoi partner suddivisi per tipi di caratteristiche e segmenti per un intervallo di tempo specificato.
seo-title: Dashboard dei report
solution: Audience Manager
title: Dashboard dei report
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Riferimento per la generazione di rapporti
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# Dashboard dei report {#reports-dashboard}

Utilizza il dashboard per visualizzare informazioni sui conteggi dei visitatori univoci suddivisi per tipi di caratteristiche e segmenti, per un intervallo di tempo specificato.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] utilizza  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo di utenti a  [!UICONTROL Dashboard]. Gli utenti possono visualizzare solo le informazioni sul dashboard per le quali dispongono delle autorizzazioni di visualizzazione. [!UICONTROL RBAC] consente di controllare quali dati possono essere visualizzati dai team interni.

Ad esempio, un’agenzia che gestisce diversi account inserzionista può configurare le autorizzazioni per i gruppi di utenti in modo che un team che gestisce l’account dell’inserzionista A non possa visualizzare i dati di reporting dell’inserzionista B. Questo dashboard può essere utilizzato per risolvere i problemi di consegna dei dati.

Ad esempio, se noti un calo, o picco, negli utenti univoci totali con suddivisione del tipo di utente univoco (basato su regole rispetto a quello onboarded), hai un punto di partenza migliore per tracciare un potenziale problema di consegna dei dati. Se noti un calo nel numero totale di utenti univoci e negli utenti univoci integrati, puoi passare al rapporto [!UICONTROL On-boarding Status] per verificare se si è verificato un problema relativo a un file in entrata.

**Per accedere al dashboard:**

1. Nel menu di navigazione superiore, fai clic su **[!UICONTROL Dashboard]**.
2. ** Facoltativo: seleziona l’intervallo di tempo desiderato dall’ultima data di reporting dall’elenco a discesa (7 giorni, 14 giorni (impostazione predefinita), 30 giorni o 60 giorni).

   A seconda del periodo selezionato, la modifica del delta nei pannelli [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] e [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] visualizza la modifica apportata ai visitatori unici del pubblico nel periodo che termina oggi rispetto al periodo precedente della stessa lunghezza. Ad esempio, se selezioni 7 giorni, il delta confronta i visitatori unici nei sette giorni precedenti che terminano oggi con quelli dei sette giorni terminati sette giorni fa.

   >[!NOTE]
   >
   >Puoi indagare su una modifica delta che sembra fuori dal comune eseguendo un rapporto [!UICONTROL Trend] . Ad esempio, se osservi una modifica insolitamente grande del delta negli ultimi sette giorni, puoi eseguire un rapporto [!UICONTROL Trend] per gli ultimi 14 giorni (2 x 7) per comprendere meglio i numeri.

   A seconda delle autorizzazioni dell&#39;utente connesso, vengono visualizzati i seguenti pannelli:

   * [Uniche partner](../reporting/reports-dashboard.md#partner-uniques)
   * [Caratteristiche più grandi/caratteristiche più modificate](../reporting/reports-dashboard.md#largest-traits)
   * [Segmenti più grandi/Segmenti più modificati](../reporting/reports-dashboard.md#most-changed-segments)

3. ** FacoltativoFai clic  **[!UICONTROL Normalize]** sopra un grafico per visualizzare tutti i dati sulla stessa scala. Puoi anche passare il cursore sopra un punto dati per visualizzare ulteriori informazioni.

## Uniche partner {#partner-uniques}

Autorizzazione necessaria per visualizzare: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

In questo pannello viene visualizzato il numero di visitatori unici nell&#39;intervallo di tempo specificato. Le singole righe con codice a colori rappresentano il numero totale di visitatori unici e il numero di visitatori unici acquisiti utilizzando caratteristiche algoritmiche, basate su regole e onboarded.

>[!NOTE]
>
>Il numero totale di visitatori unici rappresenta i visitatori acquisiti tramite caratteristiche basate su regole o onboarded. Tuttavia, il numero totale di visitatori univoci non è uguale alla somma di visitatori univoci acquisiti utilizzando caratteristiche basate su regole e onboarded. Lo stesso utente univoco potrebbe essere rappresentato in uno di questi due tipi di caratteristiche.

## Caratteristiche più grandi/caratteristiche più modificate {#largest-traits}

Autorizzazione necessaria per visualizzare: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Questo pannello visualizza il numero di visitatori unici acquisiti da varie caratteristiche.

Utilizza l’elenco a discesa **[!UICONTROL Show]** per visualizzare informazioni sui diversi tipi di caratteristiche: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] o [!UICONTROL Rule-Based].

Questo pannello contiene le seguenti schede:

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Scheda </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caratteristiche più grandi</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori unici ordinati per numero (dal più alto al più basso) ed elenca anche la modifica delta di visitatori univoci durante l'intervallo di tempo specificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Caratteristiche più modificate</span> </p> </td> 
   <td colname="col2"> <p>Visualizza informazioni sul numero di visitatori univoci ordinati dalla modifica del delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segmenti più grandi/Segmenti più modificati {#most-changed-segments}

Autorizzazione necessaria per visualizzare: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Questo pannello visualizza il numero di visitatori unici acquisiti da vari segmenti in tempo reale.

Questo pannello contiene le seguenti schede:

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Scheda </th> 
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
