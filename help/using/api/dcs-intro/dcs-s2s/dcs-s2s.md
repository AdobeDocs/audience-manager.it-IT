---
description: Le API server-to-server (S2S) forniscono codice e metodi che ti consentono di inviare e ricevere dati utente DCS e di lavorare con tali informazioni nei tuoi sistemi o applicazioni.
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: API DCS per trasferimenti di dati server-to-server
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# API DCS per trasferimenti di dati server-to-server{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s fornisce codice e metodi che consentono di inviare e ricevere dati utente di [!DNL DCS] e di utilizzare tali informazioni nei propri sistemi o applicazioni.

## Casi d’uso comuni {#common-use-cases}

I trasferimenti [!UICONTROL Server-to-server] possono essere utili per personalizzare le pagine di destinazione o altre interazioni in base agli interessi dei visitatori. Alcuni casi d’uso comuni includono:

* Personalizzazione nel sito: personalizza l’esperienza di un visitatore sul sito aggiungendo in modo dinamico contenuti rilevanti e inviti all’azione in base ai segmenti a cui appartiene.
* Miglioramento del servizio clienti: importa [!DNL Audience Manager] segmenti in un [!DNL CRM] o in un altro sistema tramite un trasferimento di dati server-to-server. Questi dati possono fornire informazioni pertinenti e personalizzate su un cliente al servizio di chiamata o agli operatori di chat online.

## Requisiti: ID utente e nomi server regionali {#requirements}

[!UICONTROL DCS API] richiede ID utente e ID di regione per convalidare ed effettuare richieste di dati.

* L’ID utente è necessario perché devi associare i dati a un visitatore specifico.
* L’ID di regione è necessario per collegare le chiamate a un nome di server e perché i dati dell’utente vengono memorizzati in data center geograficamente più vicini ai visitatori del sito.

## Introduzione {#getting-started}

Attualmente, questa guida illustra come:

* Ottieni gli ID utente e area geografica dai file [!DNL DCS] che potresti già ricevere come cliente [!DNL Audience Manager].

* Ottenere gli ID utente e di regione se si utilizza [!DNL Visitor ID Service].
* Effettua chiamate a [!DNL DCS] dopo aver ottenuto l&#39;ID utente e di regione.

Aggiungeremo nuovi metodi non appena saranno disponibili. Per iniziare, consulta le sezioni seguenti.

* [Ottenere ID utente e aree geografiche da una risposta DCS](dcs-aam-ids.md)
* [Ottieni ID utente e aree geografiche tramite Experience Cloud ID...](dcs-mcid-ids.md)
* [Esecuzione di chiamate API DCS server-to-server](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Riferimento API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
