---
description: 'Scopri i vantaggi, i tipi e gli utilizzi delle destinazioni: qualsiasi sistema di terze parti, ad esempio un ad server o un DSP, in cui condividere i dati. Usa lo strumento Generatore di destinazione per creare e gestire cookie, URL o destinazioni da server a server.'
keywords: codice di integrazione, destinazione, panoramica di destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione
landing-page-description: 'Scopri i vantaggi, i tipi e gli utilizzi delle destinazioni: qualsiasi sistema di terze parti, ad esempio un ad server o un DSP, in cui condividere i dati. Usa lo strumento Generatore di destinazione per creare e gestire cookie, URL o destinazioni da server a server.'
short-description: Discover the advantages, types, and uses of destinations – any third-party system, such as an ad server or DSP, where you share data. Use Destination Builder to create and manage cookies, URL, or server-to-server destinations.
seo-title: Destinations
solution: Audience Manager
title: Destinazioni
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 15%

---

# [!UICONTROL Destinations] Panoramica {#destinations}

Ad Audience Manager, un [!UICONTROL destination] è qualsiasi sistema di terze parti (ad server, [!DNL DSP], ad network, ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] è lo strumento utilizzato per creare e gestire [!UICONTROL cookie], [!DNL URL]oppure [!UICONTROL server-to-server destinations].

## Scopo e vantaggi {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e [!UICONTROL Destination Builder] consente di creare [!UICONTROL destinations] e invia informazioni sugli utenti segmentati al tuo partner dati. Questo consente di:

* **Valore dati Protect:** Anziché inviare tutti i dati utente a un [!UICONTROL destination], [!UICONTROL Destination Builder] consente di condividere informazioni specifiche solo sugli utenti qualificati.
* **Intervenire sui dati:** Invio di dati a un [!UICONTROL destination] il partner consente loro di sviluppare e indirizzare rapidamente segmenti di pubblico qualificati.
* **Riduzione del carico tecnico:** Gli utenti aziendali possono configurare [!UICONTROL destinations] in sicurezza [!UICONTROL Destination Builder] interfaccia. Questo consente di ridurre il tempo necessario per i test pre-distribuzione. Con [!UICONTROL Destination Builder], puoi creare, gestire ed eliminare [!UICONTROL destinations] come la vostra azienda ha bisogno di cambiare, tutto senza lavorare attraverso un lungo ciclo di sviluppo.

## Considerazioni tecniche {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La consegna dei dati dipende da come il tuo partner di dati desidera o può ricevere [!UICONTROL destination] informazioni. I vincoli tecnici o tecnici possono impedire [!UICONTROL destination] dalla ricezione dei dati tramite [!DNL URL], [!UICONTROL cookie]oppure [!UICONTROL server-to-server] processi. Collabora con il tuo partner di terze parti per determinare quale metodo può utilizzare.

## Considerazioni commerciali {#business-considerations}

Le decisioni aziendali relative alla selezione di un metodo di consegna rispetto a un altro dipendono dalle capacità tecniche delle [!UICONTROL destination] partner e cosa desideri fare con informazioni utente qualificate. Ad esempio, i vincoli tecnici possono limitare le opzioni se un [!UICONTROL destination] non può ricevere dati con un particolare metodo di consegna. Tuttavia, in assenza di problemi tecnici, puoi inviare informazioni in base a come desideri intervenire su tali dati. Ad esempio:

* [!DNL URL]s e [!UICONTROL cookie-based destinations] funziona in modo quasi sincrono con le azioni dell’utente su una pagina.
* [!UICONTROL Server-to-server] sono utili per creare nel tempo segmenti di pubblico profondi.

## [!UICONTROL Destination] Tipi e usi tipici {#destination-types}

Gli esempi nella tabella seguente possono aiutarti a capire quando utilizzare un [!UICONTROL destination] e le differenze tra ciascun tipo.

| [!UICONTROL Destination]Type (Tipo) | Utilizzato generalmente quando | Esempio | Considerazioni |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Devi inviare dati ad altre soluzioni Adobe Experience Cloud. | Invio di dati ad Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Devi inviare segmenti di pubblico ad ambienti basati sulle persone, come Facebook. | Offerte personalizzate ai clienti esistenti in base alla loro cronologia degli acquisti | Il targeting del pubblico viene eseguito tramite identificatori hash. Vedi [Destinazioni basate su persone](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-to-server**) | <ul><li>Non è necessario un trasferimento immediato dei dati.</li><li>Raccolta di dati per creare un ampio pool di pubblico di utenti qualificati.</li></ul> | Raccolta di dati nel tempo (ore o giorni) per utilizzarli in una campagna impostata per essere eseguita in una data successiva. | <ul><li>Trasferisce i dati sui visitatori del sito nuovi e precedenti. </li><li>Per qualificarsi per altri segmenti, non è necessario che i visitatori siano più visibili.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** o **Cookie**) | È necessario trasferire immediatamente i dati in modo che una destinazione possa intervenire immediatamente su un utente qualificato. | Invio di dati da un sito di acquisto di biglietti. Utilizza un [!UICONTROL URL] o [!UICONTROL cookie destination] per qualificare l’utente e rieseguire immediatamente il targeting. | <ul><li>Trasferisce dati solo sui nuovi visitatori. </li><li>I visitatori devono essere visualizzati di nuovo per qualificarsi per il segmento.</li></ul> |
