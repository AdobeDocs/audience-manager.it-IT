---
description: Domande e problemi comuni relativi ai rapporti.
seo-description: Domande e problemi comuni relativi ai rapporti.
seo-title: Domande frequenti sulla generazione di rapporti
solution: Audience Manager
title: Domande frequenti sulla generazione di rapporti
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domande frequenti sulla generazione di rapporti{#reporting-faq}

Domande e problemi comuni relativi ai rapporti.

<br> 

<!-- 

faq_reports.xml

 -->

**Per le nuove caratteristiche registrate, perché[!UICONTROL Trait Graph]talvolta vengono visualizzati numeri inferiori a quelli previsti o 0?**

A volte, dopo il caricamento delle caratteristiche, [!UICONTROL Trait Graph] non vengono visualizzati risultati o numeri inferiori a quelli previsti. Ciò si verifica quando il volume di dati ricevuti è talmente elevato che il processo di elaborazione in entrata non può completare l'acquisizione di queste informazioni fino a dopo la scadenza del rapporto per quel giorno.

Di conseguenza, questi dati vengono inviati al sistema di reporting in ritardo e non vengono visualizzati nell'intervallo di reporting di 1 giorno utilizzato per tracciare il [!UICONTROL Trait Graph]. Tuttavia, potete visualizzare questi dati negli intervalli di rapporti di 7, 14, 30 e 60 giorni in un rapporto [Tendenza](../reporting/trend-reports.md#trend-report-overview) o Rapporto [](../reporting/general-reports.md#general-reports-overview) generale il giorno successivo.

<br> 

**Mancano alcuni segmenti da un[!UICONTROL Overlap]report. Dove sono?**

Per ridurre la domanda di calcolo, questi rapporti omettono dati statisticamente insignificanti dai risultati. I segmenti non mancano, vengono semplicemente eliminati perché non producono risultati significativi o insiemi di utenti utili ai quali potete rivolgervi. Vedi anche:

* [Metodi di campionamento dei report e dei dati](../reporting/report-sampling.md)
* [Conteggio di utenti univoci in sovrapposizione e rapporti](../reporting/unique-user-counts.md)generali.

<br> 

**Se eseguo una campagna di e-mail marketing, come posso determinare se gli utenti reindirizzati arrivano sul mio sito da tale campagna o da altre fonti?**

Aggiungete una stringa di query specifica per la campagna all’URL della sezione del sito da monitorare. Quindi, impostare una regola di caratteristiche per acquisire questa variabile. Ad esempio, se l’URL passa in un ID campagna come questo, `www.test123.com/electronics?campaign=123`, create una regola di caratteristiche per acquisire i dati dalla `h_referer` variabile con una regola di caratteristiche che cerca un’intestazione come `h_referer = 'campaign=123'`).

<br> 

**Qual è la differenza tra il conteggio della popolazione del segmento in tempo reale e totale?**

* **** In tempo reale: Il numero di utenti univoci che fanno parte del segmento e sono attivi sulle proprietà durante un periodo di tempo impostato (ovvero, [!DNL Audience Manager] devono avere un'attività registrata per quell'utente per il periodo di tempo specifico).

* **** Popolazione del segmento totale: Un'aggregazione di tutti gli utenti attualmente classificati in quel segmento.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Ho un segmento composto da un solo tratto. Se osservo le metriche di reporting, i loro conteggi non corrispondono. Perché?**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**In entrata un file e la ricevuta in entrata mostra un numero elevato di record elaborati correttamente, ma il rapporto mostra numeri molto più bassi. Perché?**

Nel backend, i dati caricati vengono collegati solo agli utenti che sono ancora attivi in AAM (l'utente deve aver avuto [!UICONTROL DCS] attività recente negli ultimi 120 giorni). Di conseguenza, se a bordo dei dati per gli utenti che sono già scaduti in [!DNL Audience Manager], [!UICONTROL Inbound] potrebbe essere indicato che un certo numero di record utente sono stati registrati, ma se questi utenti non hanno avuto alcuna attività recente, questi dati vengono ignorati quando raggiungono il nostro [!UICONTROL User Profile Store] e i rapporti risulteranno tali.

<br> 

**Perché le uniche caratteristiche per i miei tratti a bordo cross-device sono molto più elevate del numero totale di record a bordo?**

Se caricate un file per un provider di dati multi-dispositivo con un ID cliente disattivato, Audience Manager esegue una ricerca per ottenere tutti gli ID dispositivo associati a ciascuno degli ID cliente caricati. Audience Manager quindi assegna le caratteristiche registrate all'ID dispositivo associato all'ID cliente.

Ad esempio, supponiamo che siano stati caricati 100 record. Per ciascuno di questi ID cliente, in media, AAM ha associato tre ID dispositivo. Di conseguenza, la caratteristica impostata viene assegnata a 300 ID dispositivo.

Esistono due motivi per cui un singolo ID cliente cross-device può essere associato a più ID dispositivo:

* Gli utenti accedono allo stesso account cross-device da più computer/browser.
* Gli utenti stanno cancellando i loro cookie. Nota: I cookie "Abbandonati" vengono eliminati dopo 120 giorni di inattività dell’utente.

<br> 

**Perché[!UICONTROL Total Trait Realizations]le mie caratteristiche integrate sono sempre 0?**

[!UICONTROL Total Trait Realizations] corrispondono ai caricamenti di pagina. [!UICONTROL Total Trait Realizations] specificare quante volte la caratteristica specifica è stata attivata in tempo reale. Questo numero è calcolato solo per le caratteristiche basate su regola. I tratti caricati vengono sempre visualizzati [!UICONTROL Total Trait Realizations] come 0.

<br> 

**Ho creato una caratteristica e[!UICONTROL Trait Graph]mostra un numero maggiore di[!UICONTROL Unique Trait Realizations]rispetto alla[!UICONTROL Total Trait Population]. Questo è normale?**

Questo accade perché [!UICONTROL Unique Trait Realizations] si tratta di metriche in tempo reale, ma i processi di reporting che facciamo per calcolare l'operazione non [!UICONTROL Total Trait Population] sono in tempo reale. Le dimensioni [!UICONTROL Total Trait Population] dovrebbero essere maggiori di quelle [!UICONTROL Unique Trait Realizations] entro un paio di giorni.
