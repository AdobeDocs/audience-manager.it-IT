---
description: 'Scopri i vantaggi, i tipi e gli utilizzi delle destinazioni: qualsiasi sistema di terze parti, ad esempio un ad server o un DSP, in cui condividere i dati. Usa lo strumento Generatore di destinazione per creare e gestire cookie, URL o destinazioni da server a server.'
keywords: integration code, destination, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
landing-page-description: 'Scopri i vantaggi, i tipi e gli utilizzi delle destinazioni: qualsiasi sistema di terze parti, ad esempio un ad server o un DSP, in cui condividere i dati. Usa lo strumento Generatore di destinazione per creare e gestire cookie, URL o destinazioni da server a server.'
short-description: 'Scopri i vantaggi, i tipi e gli utilizzi delle destinazioni: qualsiasi sistema di terze parti, ad esempio un ad server o un DSP, in cui condividere i dati. Usa lo strumento Generatore di destinazione per creare e gestire cookie, URL o destinazioni da server a server.'
seo-title: Destinations
solution: Audience Manager
title: Destinazioni
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 20%

---

# [!UICONTROL Destinations] Panoramica {#destinations}

Ad Audience Manager, un [!UICONTROL destination] è un sistema di terze parti (ad server, [!DNL DSP], ad network, ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] è lo strumento utilizzato per creare e gestire [!UICONTROL cookie], [!DNL URL], o [!UICONTROL server-to-server destinations].

## Finalità e vantaggi {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e [!UICONTROL Destination Builder] ti consente di creare [!UICONTROL destinations] e invia informazioni sugli utenti segmentati al tuo partner dati. Questo consente di:

* **Valore dati Protect:** Anziché inviare tutti i dati utente a [!UICONTROL destination], [!UICONTROL Destination Builder] consente di condividere informazioni specifiche solo sugli utenti qualificati.
* **Intervieni sui tuoi dati:** Invio di dati a una [!UICONTROL destination] partner li aiuta a sviluppare e rivolgersi rapidamente a segmenti di pubblico qualificati.
* **Riduzione dei costi tecnici:** Gli utenti aziendali possono configurare [!UICONTROL destinations] in modo sicuro [!UICONTROL Destination Builder] di rete. Questo consente di ridurre il tempo necessario per i test di pre-distribuzione. Con [!UICONTROL Destination Builder], puoi creare, gestire ed eliminare [!UICONTROL destinations] in base alle esigenze aziendali, senza dover affrontare un lungo ciclo di sviluppo.

## Considerazioni tecniche {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La distribuzione dei dati dipende da come il tuo partner dati desidera o può ricevere [!UICONTROL destination] informazioni. Vincoli tecnici o di progettazione possono impedire [!UICONTROL destination] dalla ricezione dei dati tramite [!DNL URL], [!UICONTROL cookie], o [!UICONTROL server-to-server] processi. Collabora con il tuo partner di terze parti per determinare quale metodo possono utilizzare.

## Considerazioni aziendali {#business-considerations}

Le decisioni aziendali relative alla selezione di un metodo di consegna rispetto a un altro dipendono dalle capacità tecniche del [!UICONTROL destination] e le operazioni che si desidera eseguire con le informazioni qualificate dell&#39;utente. Ad esempio, i vincoli tecnici possono limitare le opzioni se [!UICONTROL destination] non può ricevere dati da un particolare metodo di consegna. Tuttavia, se non ci sono problemi tecnici, puoi inviare informazioni in base a come desideri intervenire su tali dati. Ad esempio:

* [!DNL URL]s e [!UICONTROL cookie-based destinations] funziona in modo quasi sincrono con le azioni degli utenti su una pagina.
* [!UICONTROL Server-to-server] I metodi sono utili per creare segmenti di pubblico profondi nel tempo.

## [!UICONTROL Destination] Tipi e utilizzi tipici {#destination-types}

Gli esempi nella tabella seguente possono essere utili per capire quando utilizzare un particolare [!UICONTROL destination] e le differenze tra ciascun tipo.

| [!UICONTROL Destination]Type (Tipo) | Utilizzato Di Solito Quando | Esempio | Considerazioni |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | È necessario inviare dati ad altre soluzioni Adobe Experience Cloud. | Invio di dati ad Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | È necessario inviare segmenti di pubblico ad ambienti basati sulle persone, come Facebook. | Distribuzione di offerte personalizzate ai clienti esistenti, in base alla cronologia degli acquisti | Il targeting del pubblico viene eseguito tramite identificatori con hash. Consulta [Destinazioni basate su persone](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-to-server**) | <ul><li>Non è necessario il trasferimento immediato dei dati.</li><li>Raccolta di dati per creare un ampio pool di tipi di pubblico di utenti qualificati.</li></ul> | Raccolta di dati nel tempo (ore o giorni) per utilizzarli in un set di campagne da eseguire in una data successiva. | <ul><li>Trasferisce dati sui visitatori nuovi e precedenti del sito. </li><li>I visitatori non devono essere visti di nuovo per qualificarsi per altri segmenti.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** o **Cookie**) | Devi trasferire i dati immediatamente in modo che una destinazione possa intervenire immediatamente su un utente qualificato. | Invio di dati da una sede di acquisto di biglietti. Utilizza un [!UICONTROL URL] o [!UICONTROL cookie destination] per qualificare l’utente ed eseguire immediatamente il retargeting. | <ul><li>Trasferisce dati solo sui nuovi visitatori. </li><li>I visitatori devono essere visti di nuovo per qualificarsi per il segmento.</li></ul> |
