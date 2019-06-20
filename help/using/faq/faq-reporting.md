---
description: Domande e problemi comuni relativi al reporting.
seo-description: Domande e problemi comuni relativi al reporting.
seo-title: Domande frequenti sulla generazione di rapporti
solution: Audience Manager
title: Domande frequenti sulla generazione di rapporti
uuid: 78 cd 6 c 86-8 a 4 a -4748-ab 71-b 6 e 8 d 6078 c 94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domande frequenti sulla generazione di rapporti{#reporting-faq}

Domande e problemi comuni relativi al reporting.

<br> 

<!-- 

faq_reports.xml

 -->

**Per le nuove caratteristiche caricate, perché[!UICONTROL Trait Graph]talvolta la visualizzazione è inferiore ai numeri previsti o 0?**

A volte, dopo aver caricato le caratteristiche, i [!UICONTROL Trait Graph] risultati non vengono visualizzati o visualizzati inferiore a quelli previsti. Questo avviene quando il volume di dati ricevuti è molto elevato che il processo di elaborazione in ingresso non può terminare l&#39;assimilazione di queste informazioni fino alla scadenza del rapporto di quel giorno.

As a result, this data is sent to the reporting system late and won&#39;t show up in the 1-day reporting interval which is used for plotting the [!UICONTROL Trait Graph]. Tuttavia, potete visualizzare tali dati negli intervalli dei report 7, 14, 30 e 60 giorni in [una Tendenza](../reporting/trend-reports.md#trend-report-overview) o [in un Rapporto](../reporting/general-reports.md#general-reports-overview) generale il giorno seguente.

<br> 

**Alcuni segmenti mancano da un[!UICONTROL Overlap]rapporto. Dove sono?**

Per ridurre la richiesta computazionale, questi report omettono dati statisticamente insignificanti dai risultati. I segmenti non mancano, sono semplicemente rilasciati perché non producono risultati significativi o utili pool di utenti che potete destinare. Vedi anche:

* [Report e metodologie di campionamento dei dati](../reporting/report-sampling.md)
* [Conteggio degli utenti univoci in Sovrapposizione e Rapporti generali](../reporting/unique-user-counts.md).

<br> 

**Se esegui una campagna di marketing e-mail, come posso determinare se gli utenti reindirizzati arrivano al mio sito da quella campagna o da altre fonti?**

Aggiungete una stringa query specifica per la campagna all&#39;URL della sezione del sito da monitorare. Quindi, impostate una regola di caratteristica per acquisire questa variabile. Ad esempio, se l&#39;URL passa in un ID campagna come questo, `www.test123.com/electronics?campaign=123`create una regola caratteristica per acquisire quei dati dalla `h_referer` variabile con una regola caratteristica che cerca un&#39;intestazione come `h_referer = 'campaign=123'`).

<br> 

**Qual è la differenza tra i conteggi di popolazione in tempo reale e totale?**

* **Tempo reale:** Il numero di utenti unici che fanno parte del segmento e attivi sulle proprietà durante un periodo di tempo impostato (ovvero, deve aver [!DNL Audience Manager] registrato l&#39;attività per quell&#39;utente per il periodo di tempo specificato).

* **Popolazione segmento totale:** Un&#39;aggregazione di tutti gli utenti attualmente classificati in tale segmento.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Ho un segmento composto di una sola caratteristica. Quando visualizzi le metriche di reporting, i relativi conteggi non corrispondono. Perché?**

Consulta [Caratteristiche e dati demografici segmenti in Segment Builder](../features/segments/segment-builder-data.md)(Generatore segmenti).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**I In entrata un file e la ricevuta in entrata mostrano un numero elevato di record elaborati con successo, ma i rapporti mostrano numeri molto più bassi. Perché?**

Nel back-backend, i dati caricati vengono allegati solo agli utenti ancora attivi in AAM (l&#39;utente deve aver avuto attività recenti [!UICONTROL DCS] negli ultimi 120 giorni). Pertanto, se i dati per gli utenti che sono già scaduti sono [!DNL Audience Manager]già scaduti, [!UICONTROL Inbound] potrebbe essere necessario ricordare che alcuni record utente sono stati caricati, ma se questi utenti non hanno attività recenti, questi dati vengono ignorati al momento della creazione del report [!UICONTROL User Profile Store] .

<br> 

**Perché le caratteristiche delle caratteristiche per la mia interazione con più dispositivi sono molto più alta rispetto al numero totale di record caricati?**

Se distribuisci un file per un fornitore di dati cross-device che disabilita l&#39;ID cliente, Audience Manager esegue una ricerca per ottenere tutti gli ID dispositivo associati a ciascun ID cliente caricato. Audience Manager quindi assegna le caratteristiche caricate all&#39;ID dispositivo associato all&#39;ID cliente.

Ad esempio, supponiamo che siano stati caricati 100 record. Per ognuno di questi ID cliente, in media, AAM ha associato tre ID dispositivo. Di conseguenza, la caratteristica inserita è assegnata a 300 ID dispositivo.

Esistono due motivi per cui un singolo ID cliente multi-dispositivo può essere associato a più ID dispositivo:

* Gli utenti accedono allo stesso account cross-device da più computer/browser.
* Gli utenti stanno cancellando i loro cookie. Nota: I cookie «Abbandonato» vengono eliminati dopo 120 giorni dall&#39;inattività dell&#39;utente.

<br> 

**Perché[!UICONTROL Total Trait Realizations]per le mie caratteristiche dettagliate è sempre 0?**

[!UICONTROL Total Trait Realizations] corrisponde alla pagina caricata. [!UICONTROL Total Trait Realizations] specifica il numero di volte in cui la caratteristica specifica è stata lanciata in tempo reale. Questo numero viene calcolato solo per le caratteristiche basate su regole. Le caratteristiche caricate vengono sempre visualizzate [!UICONTROL Total Trait Realizations] come 0.

<br> 

**I create a trait and the[!UICONTROL Trait Graph]shows un numero più grande[!UICONTROL Unique Trait Realizations]di the[!UICONTROL Total Trait Population]. È normale?**

Ciò si verifica perché le [!UICONTROL Unique Trait Realizations] metriche in tempo reale, ma i processi di reporting che facciamo per calcolare il [!UICONTROL Total Trait Population] numero non sono in tempo reale. Deve [!UICONTROL Total Trait Population] essere più grande [!UICONTROL Unique Trait Realizations] di un paio di giorni.
