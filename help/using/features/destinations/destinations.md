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
ht-degree: 18%

---

# Panoramica di [!UICONTROL Destinations] {#destinations}

In Audience Manager, [!UICONTROL destination] è qualsiasi sistema di terze parti (ad server, [!DNL DSP], ad network, ecc.) con cui si desidera condividere i dati. [!UICONTROL Destination Builder] è lo strumento utilizzato per creare e gestire [!UICONTROL cookie], [!DNL URL] o [!UICONTROL server-to-server destinations].

## Finalità e vantaggi {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e [!UICONTROL Destination Builder] ti consentono di creare [!UICONTROL destinations] e inviare informazioni sugli utenti segmentati al tuo partner dati. Questo consente di:

* **Proteggi valore dati:** Anziché inviare tutti i dati utente a un [!UICONTROL destination], [!UICONTROL Destination Builder] ti consente di condividere informazioni specifiche solo su utenti qualificati.
* **Intervieni sui tuoi dati:** L&#39;invio di dati a un partner [!UICONTROL destination] li aiuta a sviluppare e indirizzare rapidamente segmenti di pubblico qualificati.
* **Riduzione del sovraccarico tecnico:** Gli utenti aziendali possono configurare [!UICONTROL destinations] in modo sicuro nell&#39;interfaccia [!UICONTROL Destination Builder]. Questo consente di ridurre il tempo necessario per i test di pre-distribuzione. Con [!UICONTROL Destination Builder], puoi creare, gestire ed eliminare [!UICONTROL destinations] in base alle esigenze della tua azienda, senza dover affrontare un lungo ciclo di sviluppo.

## Considerazioni tecniche {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La distribuzione dei dati dipende dal modo in cui il partner dati desidera o può ricevere le informazioni di [!UICONTROL destination]. I vincoli tecnici o di progettazione possono impedire a [!UICONTROL destination] di ricevere dati tramite [!DNL URL], [!UICONTROL cookie] o [!UICONTROL server-to-server] processi. Collabora con il tuo partner di terze parti per determinare quale metodo possono utilizzare.

## Considerazioni aziendali {#business-considerations}

Le decisioni aziendali relative alla selezione di un metodo di consegna rispetto a un altro dipendono dalle capacità tecniche del partner [!UICONTROL destination] e dalle operazioni che si desidera eseguire con le informazioni utente qualificate. Ad esempio, i vincoli tecnici possono limitare le opzioni se un [!UICONTROL destination] non può ricevere dati con un particolare metodo di consegna. Tuttavia, se non ci sono problemi tecnici, puoi inviare informazioni in base a come desideri intervenire su tali dati. Ad esempio:

* [!DNL URL] e [!UICONTROL cookie-based destinations] funzionano in modo quasi sincrono con le azioni dell&#39;utente su una pagina.
* I metodi [!UICONTROL Server-to-server] sono utili per la creazione di segmenti di pubblico profondo nel tempo.

## [!UICONTROL Destination] tipi e utilizzi tipici {#destination-types}

Gli esempi nella tabella seguente consentono di comprendere quando utilizzare un particolare [!UICONTROL destination] e le differenze tra ciascun tipo.

| Tipo [!UICONTROL Destination] | Utilizzato Di Solito Quando | Esempio | Considerazioni |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | È necessario inviare dati ad altre soluzioni Adobe Experience Cloud. | Invio di dati ad Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | È necessario inviare segmenti di pubblico ad ambienti basati sulle persone, come Facebook. | Distribuzione di offerte personalizzate ai clienti esistenti, in base alla cronologia degli acquisti | Il targeting del pubblico viene eseguito tramite identificatori con hash. Vedi [Destinazioni basate su persone](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-to-server**) | <ul><li>Non è necessario il trasferimento immediato dei dati.</li><li>Raccolta di dati per creare un ampio pool di tipi di pubblico di utenti qualificati.</li></ul> | Raccolta di dati nel tempo (ore o giorni) per utilizzarli in un set di campagne da eseguire in una data successiva. | <ul><li>Trasferisce dati sui visitatori nuovi e precedenti del sito. </li><li>I visitatori non devono essere visti di nuovo per qualificarsi per altri segmenti.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** o **Cookie**) | Devi trasferire i dati immediatamente in modo che una destinazione possa intervenire immediatamente su un utente qualificato. | Invio di dati da una sede di acquisto di biglietti. Utilizza [!UICONTROL URL] o [!UICONTROL cookie destination] per qualificare l&#39;utente e rieseguire immediatamente il targeting. | <ul><li>Trasferisce dati solo sui nuovi visitatori. </li><li>I visitatori devono essere visti di nuovo per qualificarsi per il segmento.</li></ul> |
