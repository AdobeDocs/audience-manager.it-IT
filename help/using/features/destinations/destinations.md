---
description: In Audience Manager, una destinazione è un sistema di terze parti (server pubblicitario, DSP, rete di annunci ecc.) con cui condividere i dati. Generatore di destinazione è lo strumento utilizzato per creare e gestire cookie, URL o destinazioni server-to-server.
keywords: codice integrazione, destinazione, panoramica della destinazione
seo-description: In Audience Manager, una destinazione è un sistema di terze parti (server pubblicitario, DSP, rete di annunci ecc.) con cui condividere i dati. Generatore di destinazione è lo strumento utilizzato per creare e gestire cookie, URL o destinazioni server-to-server.
seo-title: Destinazioni
solution: Audience Manager
title: Destinazioni
uuid: 5 c 7 dbdec-f 73 f -46 fe -9 f 12-7685 e 8 d 7334 f
translation-type: tm+mt
source-git-commit: 157e70906b80bd0a23ba6e7721d2c456d378ffb5

---


# Destinazioni {#destinations}

In Audience Manager, a destination is any third-party system (ad server, [!DNL DSP], ad network, etc.) con cui condividere i dati. [!UICONTROL Destination Builder] è lo strumento utilizzato per creare e gestire cookie, [!DNL URL]o destinazioni server-to-server.

## Purpose and Advantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] e [!UICONTROL Destination Builder] puoi creare delle destinazioni e inviare informazioni sugli utenti segmentati al tuo partner dati. Questo consente di:

* **Protezione dei valori dei dati:** Anziché inviare tutti i dati utente a una destinazione, [!UICONTROL Destination Builder] puoi condividere informazioni specifiche solo sugli utenti idonei.
* **Intraprendere azioni sui tuoi dati:** L'invio di dati a un partner di destinazione consente di sviluppare e indirizzare rapidamente i segmenti di pubblico qualificati.
* **Riduzione del sovraccarico tecnico:** Gli utenti aziendali possono configurare le destinazioni in modo sicuro nell' [!UICONTROL Destination Builder] interfaccia. Questo consente di ridurre il tempo necessario per il test di pre-distribuzione. With [!UICONTROL Destination Builder], you create, manage, and delete destinations as your business needs change, all without working through a long development cycle.

## Technical Considerations {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La distribuzione dei dati dipende da come il partner di dati desidera, o può, ricevere le informazioni sulla destinazione. Technical or engineering constraints may prevent a destination from receiving data via [!DNL URL], cookie, or server-to-server processes. Collabora con il tuo partner di terze parti per determinare quale metodo possono utilizzare.

## Business Considerations {#business-considerations}

Le decisioni aziendali per la selezione di un metodo di consegna su un altro dipendono dalle capacità tecniche del partner di destinazione e da cosa fare con le informazioni utente qualificate. Ad esempio, i vincoli tecnici possono limitare le opzioni se una destinazione non riesce a ricevere dati in base a un particolare metodo di consegna. Tuttavia, se non sono presenti problemi tecnici, puoi inviare informazioni in base alla modalità di azione su tali dati. Ad esempio:

* [!DNL URL]Le destinazioni basate su cookie funzionano quasi sincronamente con le azioni degli utenti su una pagina.
* I metodi server-to-server sono buoni per creare segmenti di audience profondi nel tempo.

## Destination Types and Typical Uses {#destination-types}

Gli esempi riportati nella tabella seguente consentono di comprendere quando utilizzare una destinazione particolare e le differenze tra ciascun tipo.

| Tipo di destinazione | Generalmente utilizzato quando | Esempio  | Considerazioni |
|--- |--- |--- |--- |
| **URL** o **cookie** | Devi trasferire immediatamente i dati in modo che una destinazione possa intervenire subito su un utente qualificato. | Invio di dati da un sito di acquisto di biglietti. Utilizzate un URL o una destinazione di cookie per qualificare l'utente e eseguire immediatamente il targeting. | <ul><li>Trasferisce dati solo ai nuovi visitatori. </li><li>I visitatori devono essere visti di nuovo per qualificarlo.</li></ul> |
| **Server-to-server** | <ul><li>Il trasferimento immediato dei dati non è obbligatorio.</li><li>Raccogliere dati per creare un pool di destinatari di grandi dimensioni.</li></ul> | Raccogliere dati nel tempo (ore o giorni) per utilizzarli in una campagna impostata in un secondo momento. | <ul><li>Trasferisce i dati sui visitatori nuovi e precedenti del sito. </li><li>I visitatori non devono essere visti nuovamente per essere idonei per altri segmenti.</li></ul> |
