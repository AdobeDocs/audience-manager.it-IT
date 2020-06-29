---
description: Le API da server a server (S2S) forniscono codice e metodi che consentono di inviare e ricevere dati utente DCS e di lavorare con tali informazioni nei propri sistemi o applicazioni.
seo-description: Le API da server a server (S2S) forniscono codice e metodi che consentono di inviare e ricevere dati utente DCS e di lavorare con tali informazioni nei propri sistemi o applicazioni.
seo-title: API DCS per trasferimenti di dati da server a server
solution: Audience Manager
title: API DCS per trasferimenti di dati da server a server
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---


# API DCS per trasferimenti di dati da server a server{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]forniscono codice e metodi che consentono di inviare e ricevere dati [!DNL DCS] utente e di utilizzare tali informazioni nei propri sistemi o applicazioni.

## Casi di utilizzo comuni {#common-use-cases}

[!UICONTROL Server-to-server] i trasferimenti possono aiutarti a personalizzare le pagine di destinazione o altre interazioni in base agli interessi dei visitatori. Alcuni esempi di utilizzo comuni:

* Personalizzazione in loco: Personalizza l&#39;esperienza di un visitatore sul tuo sito aggiungendo in modo dinamico contenuti rilevanti e chiamate all&#39;azione in base ai segmenti a cui appartengono.
* Miglioramento del servizio clienti: Importa [!DNL Audience Manager] i segmenti in un sistema [!DNL CRM] o in un altro tramite un trasferimento di dati da server a server. Questi dati possono fornire servizi di chiamata o operatori chat online con informazioni pertinenti e personalizzate su un cliente.

## Requisiti: ID utente e nomi server regionali {#requirements}

Gli ID utente e gli ID di regione [!UICONTROL DCS API] devono convalidare ed effettuare richieste di dati.

* L&#39;ID utente è obbligatorio perché devi associare dati a un particolare visitatore.
* L&#39;ID di regione è richiesto per collegare le chiamate al nome di un server e perché i dati dell&#39;utente vengono memorizzati in centri dati geograficamente più vicini ai visitatori del sito.

## Introduzione {#getting-started}

Attualmente, questa guida descrive come:

* Ottenete gli ID utente e regione dai [!DNL DCS] file che potreste già ricevere come [!DNL Audience Manager] cliente.

* Ottenete gli ID utente e di regione se utilizzate il [!DNL Visitor ID Service].
* Effettua chiamate al [!DNL DCS] dopo aver ottenuto l’ID utente e di regione.

Verranno aggiunti nuovi metodi non appena disponibili. Per iniziare, consulta le sezioni seguenti.

* [Ottenere ID utente e aree geografiche da una risposta DCS](dcs-aam-ids.md)
* [Ottieni ID utente e aree geografiche tramite l’ID Experience Cloud ...](dcs-mcid-ids.md)
* [Esecuzione di chiamate API DCS da server a server](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Riferimento API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

