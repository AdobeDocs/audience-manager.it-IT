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


# Dashboard rapporti {#reports-dashboard}

Usa il dashboard per visualizzare le informazioni sui conteggi dei visitatori univoci suddivisi per tipo di caratteristica e segmenti, per un intervallo di tempo specificato.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] uses [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) per estendere le autorizzazioni del gruppo utente a [!UICONTROL Dashboard]. Gli utenti possono vedere solo le informazioni del dashboard che possono visualizzare. [!UICONTROL RBAC] consente di controllare quali dei team interni di dati di reporting sono in grado di visualizzare.

Ad esempio, un&#39;agenzia che gestisce diversi account pubblicitari può configurare le autorizzazioni del gruppo di utenti in modo che un team che gestisce l&#39;account dell&#39;inserzionista A non possa vedere i dati di reporting dell&#39;inserzionista B. Questa dashboard può essere utilizzata per risolvere problemi relativi alla consegna dei dati.

Ad esempio, se notate un picco o un picco in totale utenti univoci con la suddivisione del tipo di utente univoco (basato su regole e su se stesso), avete un punto di partenza migliore per tenere traccia di un potenziale problema di consegna dati. Se notate un elemento dip in totale utenti univoci e in utenti univoci, potete accedere al [!UICONTROL On-boarding Status] rapporto per verificare se si è verificato un problema con un file in entrata.

**Per accedere al dashboard:**

1. Nel menu di navigazione superiore, fate clic **[!UICONTROL Dashboard]** su.
2. *Facoltativo* Seleziona l&#39;intervallo di tempo desiderato dall&#39;elenco a discesa dell&#39;ultimo rapporto (7 giorni, 14 giorni (impostazione predefinita), 30 giorno o 60 giorni.

   A seconda del periodo selezionato, il cambiamento delta nei pannelli [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] e [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] mostra la modifica in visitatori unici nel pubblico rispetto al periodo corrente e al periodo precedente della stessa lunghezza. Ad esempio, se selezioni 7 Giorni, il delta confronta i visitatori unici con i sette giorni successivi che si ritrovano oggi stesso rispetto ai visitatori unici dei sette giorni successivi, sette giorni fa.

   >[!NOTE]
   >
   >Potete analizzare una modifica delta che sembra più ordinaria eseguendo [!UICONTROL Trend] un rapporto. Ad esempio, se durante gli ultimi sette giorni si modifica una variazione delta univoca, è possibile eseguire un [!UICONTROL Trend] rapporto per gli ultimi 14 giorni (2 x 7) per comprendere meglio i numeri.

   A seconda delle autorizzazioni dell&#39;utente connesso, vengono visualizzati i seguenti pannelli:

   * [Partner Unitques](../reporting/reports-dashboard.md#partner-uniques)
   * [Caratteristiche più grandi/più modificate](../reporting/reports-dashboard.md#largest-traits)
   * [Segmenti principali/Segmenti più modificati](../reporting/reports-dashboard.md#most-changed-segments)

3. *Facoltativo* Fate clic **[!UICONTROL Normalize]** sopra qualsiasi grafico per mostrare tutti i dati sulla stessa scala. Puoi anche passare il cursore sopra un punto dati per visualizzare ulteriori informazioni.

## Partner Unitques {#partner-uniques}

Autorizzazione necessaria per visualizzare: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Questo pannello visualizza il numero di visitatori unici nel periodo di tempo specificato. Le singole linee con codifica colori rappresentano il numero totale di visitatori univoci e il numero di visitatori unici acquisiti utilizzando caratteristiche algoritmiche, basate su regole e caricate.

>[!NOTE]
>
>Il numero totale di visitatori unici rappresenta i visitatori acquisiti tramite tratti basati su regole o su smartphone. Tuttavia, il numero totale di visitatori univoci non equivale alla somma di visitatori unici acquisiti utilizzando le caratteristiche basate su regole e caricate. Lo stesso utente univoco potrebbe essere rappresentato in uno di questi due tipi di caratteristiche.

## Caratteristiche più grandi/più modificate {#largest-traits}

Autorizzazione necessaria per visualizzare: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Questo pannello mostra il numero di visitatori unici acquisiti da diverse caratteristiche.

Usate l&#39;elenco **[!UICONTROL Show]** a discesa per visualizzare informazioni sui diversi tipi di caratteristiche: [!UICONTROL All Traits][!UICONTROL Algorithmic][!UICONTROL Onboarded], [!UICONTROL Rule-Based]o.

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

## Segmenti principali/Segmenti più modificati {#most-changed-segments}

Autorizzazione necessaria per visualizzare: [!UICONTROL View Segments].

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

