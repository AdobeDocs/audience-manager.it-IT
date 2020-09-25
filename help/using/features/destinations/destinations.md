---
description: In  Audience Manager, una destinazione è qualsiasi sistema di terze parti (server di annunci, DSP, rete di annunci ecc.) con cui desideri condividere i dati. Usate lo strumento Generatore di destinazione per creare e gestire cookie, URL o destinazioni da server a server.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: In  Audience Manager, una destinazione è qualsiasi sistema di terze parti (server di annunci, DSP, rete di annunci ecc.) con cui desideri condividere i dati. Generatore di destinazione è lo strumento che consente di creare e gestire cookie, URL o destinazioni da server a server.
seo-title: 'Destinazioni '
solution: Audience Manager
title: 'Destinazioni '
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 8027f278aa2b879b6cb277f44caf4b62dc75e2c3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# [!UICONTROL Destinations] Panoramica {#destinations}

In  Audience Manager, un [!UICONTROL destination] è qualsiasi sistema di terze parti (server di annunci, [!DNL DSP]reti di annunci ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] è lo strumento utilizzato per creare e gestire [!UICONTROL cookie], [!DNL URL]o [!UICONTROL server-to-server destinations].

## Finalità e vantaggi {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e [!UICONTROL Destination Builder] consente di creare [!UICONTROL destinations] e inviare informazioni sugli utenti segmentati al partner dati. Questo consente di:

* **Valore dati Protect:** Anziché inviare tutti i dati utente a un [!UICONTROL destination], [!UICONTROL Destination Builder] consente di condividere informazioni specifiche solo sugli utenti qualificati.
* **Segui i tuoi dati:** L&#39;invio di dati a un [!UICONTROL destination] partner consente loro di sviluppare e indirizzare rapidamente segmenti di pubblico qualificati.
* **Riduzione del carico tecnico:** Gli utenti aziendali possono configurare [!UICONTROL destinations] in modo sicuro nell&#39; [!UICONTROL Destination Builder] interfaccia. Questo consente di ridurre il tempo necessario per il test pre-distribuzione. Con [!UICONTROL Destination Builder], puoi creare, gestire ed eliminare [!UICONTROL destinations] in base alle tue esigenze di business, il tutto senza dover affrontare un lungo ciclo di sviluppo.

## Considerazioni Tecniche {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La consegna dei dati dipende da come il partner dati desidera o può ricevere [!UICONTROL destination] le informazioni. I vincoli tecnici o tecnici possono impedire [!UICONTROL destination] la ricezione di dati tramite [!DNL URL], [!UICONTROL cookie]o [!UICONTROL server-to-server] processi. Collabora con il partner di terze parti per determinare il metodo che possono utilizzare.

## Considerazioni aziendali {#business-considerations}

Le decisioni aziendali relative alla selezione di un metodo di consegna rispetto a un altro dipendono dalle capacità tecniche del [!UICONTROL destination] partner e dalle operazioni che desiderate eseguire con le informazioni utente qualificate. Ad esempio, vincoli tecnici possono limitare le opzioni se [!UICONTROL destination] non è possibile ricevere dati con un particolare metodo di consegna. Tuttavia, in assenza di problemi tecnici, puoi inviare informazioni in base a come vuoi intervenire su tali dati. Ad esempio:

* [!DNL URL]e [!UICONTROL cookie-based destinations] funziona quasi in modo sincrono con le azioni degli utenti su una pagina.
* [!UICONTROL Server-to-server] sono utili per creare segmenti di pubblico profondi nel tempo.

## [!UICONTROL Destination] Tipi e usi tipici {#destination-types}

Gli esempi riportati nella tabella seguente consentono di comprendere quando utilizzare un particolare [!UICONTROL destination] e le differenze tra i vari tipi.

| [!UICONTROL Destination]Type (Tipo) | Generalmente utilizzato quando | Esempio | Considerazioni |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Devi inviare dati ad altre soluzioni Adobe Experience Cloud. | Invio di dati a  Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Devi inviare segmenti di pubblico ad ambienti basati su persone, come Facebook. | Offrire offerte personalizzate ai clienti esistenti, in base alla loro cronologia di acquisto | Il targeting dell&#39;audience viene eseguito tramite identificatori con hash. Vedi Destinazioni [basate sulle](people-based-destinations-overview.md)persone. |
| **[!UICONTROL Device-Based Destinations]** (da **server a server**) | <ul><li>Il trasferimento immediato dei dati non è richiesto.</li><li>Raccolta di dati per creare un ampio gruppo di utenti qualificati.</li></ul> | Raccolta di dati nel tempo (ore o giorni) per utilizzarli in una campagna impostata per essere eseguita in una data successiva. | <ul><li>Trasferisce i dati sui visitatori del sito nuovi e precedenti. </li><li>I visitatori non devono essere più visualizzati per qualificarsi per altri segmenti.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** o **cookie**) | Devi trasferire immediatamente i dati in modo che una destinazione possa intervenire immediatamente su un utente qualificato. | Invio di dati da un sito di acquisto di biglietti. Utilizzate un oggetto [!UICONTROL URL] o [!UICONTROL cookie destination] per qualificare l&#39;utente e riutilizzarlo immediatamente. | <ul><li>Trasferisce i dati solo sui nuovi visitatori. </li><li>Per qualificarsi per il segmento, è necessario rivedere i visitatori.</li></ul> |
