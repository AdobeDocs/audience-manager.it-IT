---
description: Domande e problemi comuni relativi al reporting.
seo-description: Domande e problemi comuni relativi al reporting.
seo-title: Domande frequenti sul reporting
solution: Audience Manager
title: Domande frequenti sul reporting
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Reporting
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 100%

---


# Domande frequenti sul reporting {#reporting-faq}

Domande e problemi comuni relativi al reporting.

<br> 

<!-- 

faq_reports.xml

 -->

**Per le nuove caratteristiche onboarded, perché il [!UICONTROL Trait Graph] talvolta mostra numeri inferiori a quelli previsti o 0?**

A volte, dopo che carichi le caratteristiche, il [!UICONTROL Trait Graph] non mostra alcun risultato o mostra numeri inferiori a quelli previsti. Ciò si verifica quando il volume di dati ricevuti è talmente elevato che il processo di elaborazione in entrata non può completare l’acquisizione di tali informazioni fino a dopo la scadenza del reporting per quel giorno.

Di conseguenza, questi dati vengono inviati al sistema di reporting in ritardo e non vengono visualizzati nell’intervallo di reporting di 1 giorno utilizzato per tracciare il [!UICONTROL Trait Graph]. Tuttavia, puoi visualizzare questi dati negli intervalli di reporting di 7, 14, 30 e 60 giorni in un report [Trend](../reporting/trend-reports.md#trend-report-overview) o [General](../reporting/general-reports.md#general-reports-overview) il giorno successivo.

<br> 

**Mancano alcuni segmenti da un report [!UICONTROL Overlap]. Dove sono?**

Per ridurre la domanda di calcolo, questi report omettono dati statisticamente non rilevanti dai risultati. I segmenti non sono mancanti, vengono semplicemente eliminati perché non producono risultati significativi o insiemi di utenti utili di cui puoi effettuare il targeting. Vedi anche:

* [Reports and Data Sampling Methodologies](../reporting/report-sampling.md)
* [Counting Unique Users in Overlap and General Reports](../reporting/unique-user-counts.md).

<br> 

**Se eseguo una campagna di marketing e-mail, come posso determinare se gli utenti reindirizzati arrivano sul mio sito da tale campagna o da altre sorgenti?**

Aggiungi una stringa di query specifica per la campagna all’URL della sezione del sito che desideri monitorare. Poi, imposta una regola di caratteristiche per acquisire tale variabile. Ad esempio, se l’URL viene trasmesso in un ID campagna come `www.test123.com/electronics?campaign=123`, crea una regola di caratteristiche per acquisire i dati dalla variabile `h_referer` che cerchi un’intestazione del tipo `h_referer = 'campaign=123'`.

<br> 

**Qual è la differenza tra il conteggio della popolazione del segmento in tempo reale e totale?**

* **In tempo reale:** il numero di utenti univoci che fanno parte del segmento e sono attivi sulle tue proprietà durante un periodo di tempo impostato (ovvero, [!DNL Audience Manager] deve avere un’attività registrata per un utente per il periodo di tempo specifico).

* **Popolazione totale del segmento:** un’aggregazione di tutti gli utenti attualmente classificati in quel segmento.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Ho un segmento composto da una sola caratteristica. Se osservo le metriche di reporting, i conteggi non corrispondono. Perché?**

Consulta [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Immetto un file e la ricevuta in entrata mostra un numero elevato di report elaborati correttamente, ma il reporting mostra numeri molto più bassi. Perché?**

Nel back-end, i dati onboarded vengono collegati solo agli utenti che sono ancora attivi in AAM (l’utente deve aver avuto attività [!DNL DCS] recente negli ultimi 120 giorni). Di conseguenza, se effettui l’onboarding di dati per gli utenti che sono già scaduti in [!DNL Audience Manager], [!UICONTROL Inbound] potrebbe indicarti che è stato effettuato l’onboarding di un certo numero di record degli utenti, ma se questi utenti non hanno effettuato alcuna attività recente, questi dati vengono ignorati quando raggiungono il nostro [!UICONTROL User Profile Store] e ciò emergerà nel reporting.

<br> 

**Perché gli univoci delle caratteristiche univoche per le mie caratteristiche multi-dispositivo sono molto più elevati del numero totale di record onboarded?**

Se carichi un file per un provider di dati multi-dispositivo ricavato dall’ID cliente, Audience Manager esegue una ricerca per ottenere tutti gli ID dispositivo associati a ciascuno degli ID cliente caricati. Audience Manager quindi assegna le caratteristiche onboarded all’ID dispositivo associato all’ID cliente.

Ad esempio, supponiamo che tu abbia effettuato l’onboarding di 100 record. Per ciascuno di questi ID cliente, in media, AAM ha associato tre ID dispositivo. Di conseguenza, la caratteristica di cui è stato effettuato l’onboarding viene assegnata a 300 ID dispositivo.

Esistono due motivi per cui un singolo ID cliente multi-dispositivo può essere associato a più ID dispositivo:

* Gli utenti accedono allo stesso account multi-dispositivo da più computer/browser.
* Gli utenti cancellano i loro cookie. Nota: I cookie “Abandoned” vengono eliminati dopo 120 giorni di inattività dell’utente.

<br> 

**Perché le [!UICONTROL Total Trait Realizations] per le mie caratteristiche onboarded sono sempre 0?**

Le [!UICONTROL Total Trait Realizations] corrispondono ai caricamenti di pagina. Le[!UICONTROL Total Trait Realizations] forniscono il numero di volte in cui una caratteristica specifica è stata attivata in tempo reale. Questo numero è calcolato solo per le caratteristiche basate su regole. Le caratteristiche onboarded mostrano sempre 0 [!UICONTROL Total Trait Realizations].

<br> 

**Ho creato una caratteristica e il [!UICONTROL Trait Graph] mostra un numero maggiore di [!UICONTROL Unique Trait Realizations] rispetto alla [!UICONTROL Total Trait Population]. È normale?**

Questo accade perché le [!UICONTROL Unique Trait Realizations] sono metriche in tempo reale, ma i processi di reporting che effettuiamo per calcolare la [!UICONTROL Total Trait Population] non sono in tempo reale. La [!UICONTROL Total Trait Population] dovrebbe superare le [!UICONTROL Unique Trait Realizations] entro un paio di giorni.
