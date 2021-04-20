---
description: In Audience Manager, una destinazione è qualsiasi sistema di terze parti (server di annunci, DSP, ad network, ecc.) con cui desideri condividere i dati. Destination Builder è lo strumento che consente di creare e gestire destinazioni da server a server, cookie e URL.
keywords: codice di integrazione, destinazione, panoramica di destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione, destinazione
landing-page-description: Per destinazione si intende qualsiasi sistema di terze parti, ad esempio ad server o DSP, con cui condividere i dati. Usa lo strumento Generatore di destinazione per creare e gestire cookie, URL o destinazioni da server a server.
seo-title: 'Destinazioni '
solution: Audience Manager
title: Destinazioni
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
translation-type: tm+mt
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# [!UICONTROL Destinations] Panoramica {#destinations}

Ad Audience Manager, un [!UICONTROL destination] è un sistema di terze parti (ad server, [!DNL DSP], ad network, ecc.) con cui desideri condividere i dati. [!UICONTROL Destination Builder] è lo strumento utilizzato per creare e gestire  [!UICONTROL cookie],  [!DNL URL], o  [!UICONTROL server-to-server destinations].

## Finalità e vantaggi {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e  [!UICONTROL Destination Builder] ti consente di creare  [!UICONTROL destinations] e inviare informazioni sugli utenti segmentati al tuo partner dati. Questo consente di:

* **Valore dei dati Protect:** invece di inviare tutti i dati utente a un  [!UICONTROL destination],  [!UICONTROL Destination Builder] consente di condividere informazioni specifiche solo sugli utenti qualificati.
* **Intervieni sui tuoi dati:** l’invio di dati a un  [!UICONTROL destination] partner li aiuta a sviluppare e indirizzare rapidamente segmenti di pubblico qualificati.
* **Riduzione del sovraccarico tecnico:** gli utenti aziendali possono impostare  [!UICONTROL destinations] in modo sicuro nell’ [!UICONTROL Destination Builder] interfaccia. Questo consente di ridurre il tempo necessario per i test pre-distribuzione. Con [!UICONTROL Destination Builder] è possibile creare, gestire ed eliminare [!UICONTROL destinations] in base alle esigenze aziendali, il tutto senza dover eseguire un lungo ciclo di sviluppo.

## Considerazioni tecniche {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La consegna dei dati dipende da come il tuo partner di dati desidera o può ricevere le informazioni [!UICONTROL destination]. I vincoli tecnici o tecnici possono impedire a [!UICONTROL destination] di ricevere dati tramite i processi [!DNL URL], [!UICONTROL cookie] o [!UICONTROL server-to-server]. Collabora con il tuo partner di terze parti per determinare quale metodo può utilizzare.

## Considerazioni aziendali {#business-considerations}

Le decisioni aziendali relative alla selezione di un metodo di consegna rispetto a un altro dipendono dalle capacità tecniche del tuo [!UICONTROL destination] partner e dalle operazioni che desideri eseguire con informazioni utente qualificate. Ad esempio, i vincoli tecnici possono limitare le opzioni se un [!UICONTROL destination] non può ricevere dati con un particolare metodo di consegna. Tuttavia, in assenza di problemi tecnici, puoi inviare informazioni in base a come desideri intervenire su tali dati. Ad esempio:

* [!DNL URL]e  [!UICONTROL cookie-based destinations] funzionano quasi in modo sincrono con le azioni degli utenti su una pagina.
* [!UICONTROL Server-to-server] sono utili per creare nel tempo segmenti di pubblico profondi.

## [!UICONTROL Destination] Tipi e usi tipici  {#destination-types}

Gli esempi nella tabella seguente possono aiutarti a capire quando utilizzare un particolare [!UICONTROL destination] e le differenze tra ciascun tipo.

| [!UICONTROL Destination]Type (Tipo) | Utilizzato generalmente quando | Esempio | Considerazioni |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Devi inviare dati ad altre soluzioni Adobe Experience Cloud. | Invio di dati ad Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Devi inviare segmenti di pubblico ad ambienti basati sulle persone, come Facebook. | Offerte personalizzate ai clienti esistenti in base alla loro cronologia degli acquisti | Il targeting del pubblico viene eseguito tramite identificatori hash. Consulta [Destinazioni basate su persone](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**da server a server**) | <ul><li>Non è necessario un trasferimento immediato dei dati.</li><li>Raccolta di dati per creare un ampio pool di pubblico di utenti qualificati.</li></ul> | Raccolta di dati nel tempo (ore o giorni) per utilizzarli in una campagna impostata per essere eseguita in una data successiva. | <ul><li>Trasferisce i dati sui visitatori del sito nuovi e precedenti. </li><li>Per qualificarsi per altri segmenti, non è necessario che i visitatori siano più visibili.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URLo  **cookie**) | È necessario trasferire immediatamente i dati in modo che una destinazione possa intervenire immediatamente su un utente qualificato. | Invio di dati da un sito di acquisto di biglietti. Utilizza un [!UICONTROL URL] o [!UICONTROL cookie destination] per qualificare l&#39;utente e rieseguire immediatamente il targeting. | <ul><li>Trasferisce dati solo sui nuovi visitatori. </li><li>I visitatori devono essere visualizzati di nuovo per qualificarsi per il segmento.</li></ul> |
