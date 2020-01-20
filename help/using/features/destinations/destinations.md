---
description: In Audience Manager, una destinazione è qualsiasi sistema di terze parti (server di annunci, DSP, rete di annunci ecc.) con cui condividere i dati. Generatore di destinazione è lo strumento utilizzato per creare e gestire cookie, URL o destinazioni da server a server.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: In Audience Manager, una destinazione è qualsiasi sistema di terze parti (server di annunci, DSP, rete di annunci ecc.) con cui condividere i dati. Generatore di destinazione è lo strumento utilizzato per creare e gestire cookie, URL o destinazioni da server a server.
seo-title: Destinazioni
solution: Audience Manager
title: Destinazioni
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: e141d04201b94bac30cdbe97818cb8eb91ebbaea

---


# Panoramica delle destinazioni {#destinations}

In Audience Manager, una destinazione è qualsiasi sistema di terze parti (server di annunci, [!DNL DSP]reti di annunci ecc.) con cui condividere i dati. [!UICONTROL Destination Builder] è lo strumento utilizzato per creare e gestire cookie, destinazioni [!DNL URL]da server a server.

## Finalità e vantaggi {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e [!UICONTROL Destination Builder] consente di creare destinazioni e inviare informazioni sugli utenti segmentati al partner dati. Questo consente di:

* **** Protezione del valore dei dati: Anziché inviare tutti i dati utente a una destinazione, [!UICONTROL Destination Builder] potete condividere informazioni specifiche solo sugli utenti qualificati.
* **** Segui i tuoi dati: L&#39;invio di dati a un partner di destinazione consente loro di sviluppare e indirizzare rapidamente segmenti di pubblico qualificati.
* **** Riduzione del carico tecnico: Gli utenti aziendali possono configurare le destinazioni in modo sicuro nell&#39; [!UICONTROL Destination Builder] interfaccia. Questo consente di ridurre il tempo necessario per il test pre-distribuzione. Con [!UICONTROL Destination Builder], puoi creare, gestire ed eliminare le destinazioni in base alle tue esigenze aziendali, il tutto senza dover affrontare un lungo ciclo di sviluppo.

## Considerazioni Tecniche {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La consegna dei dati dipende dal modo in cui il partner dati desidera ricevere o può ricevere le informazioni di destinazione. I vincoli tecnici o tecnici possono impedire a una destinazione di ricevere dati tramite processi [!DNL URL], cookie o server-to-server. Collabora con il partner di terze parti per determinare il metodo che possono utilizzare.

## Considerazioni aziendali {#business-considerations}

Le decisioni aziendali relative alla selezione di un metodo di consegna rispetto a un altro dipendono dalle capacità tecniche del partner di destinazione e da ciò che si desidera fare con le informazioni utente qualificate. Ad esempio, i vincoli tecnici possono limitare le opzioni se una destinazione non può ricevere dati con un particolare metodo di consegna. Tuttavia, in assenza di problemi tecnici, puoi inviare informazioni in base a come vuoi intervenire su tali dati. Ad esempio:

* [!DNL URL]Le destinazioni basate su cookie e s funzionano quasi in modo sincrono con le azioni degli utenti su una pagina.
* I metodi server-to-server sono utili per creare segmenti di pubblico profondi nel tempo.

## Tipi di destinazione e usi tipici {#destination-types}

Gli esempi riportati nella tabella seguente consentono di comprendere quando utilizzare una particolare destinazione e le differenze tra i vari tipi.

| Tipo di destinazione | Generalmente utilizzato quando | Esempio  | Considerazioni |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Devi inviare dati ad altre soluzioni Adobe Experience Cloud. | Invio di dati ad Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Devi inviare segmenti di pubblico ad ambienti basati su persone, come Facebook. | Offrire offerte personalizzate ai clienti esistenti, in base alla loro cronologia di acquisto | Il targeting dell&#39;audience viene eseguito tramite identificatori con hash. Vedi Destinazioni [basate sulle](people-based-destinations-overview.md)persone. |
| **[!UICONTROL Device-Based Destinations]**(da** server a server **) | <ul><li>Il trasferimento immediato dei dati non è richiesto.</li><li>Raccolta di dati per creare un ampio gruppo di utenti qualificati.</li></ul> | Raccolta di dati nel tempo (ore o giorni) per utilizzarli in una campagna impostata per essere eseguita in una data successiva. | <ul><li>Trasferisce i dati sui visitatori del sito nuovi e precedenti. </li><li>I visitatori non devono essere più visualizzati per qualificarsi per altri segmenti.</li></ul> |
| **[!UICONTROL Custom Destinations]**(** URL **o** cookie **) | Devi trasferire immediatamente i dati in modo che una destinazione possa intervenire immediatamente su un utente qualificato. | Invio di dati da un sito di acquisto di biglietti. Utilizzate un URL o una destinazione di cookie per qualificare l&#39;utente e riutilizzarla immediatamente. | <ul><li>Trasferisce i dati solo sui nuovi visitatori. </li><li>Per qualificarsi per il segmento, è necessario rivedere i visitatori.</li></ul> |
