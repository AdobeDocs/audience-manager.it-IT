---
description: Le API server-to-server (S 2 S) forniscono codice e metodi che consentono di inviare e ricevere dati utente DCS e di lavorare con tali informazioni nei propri sistemi o applicazioni.
seo-description: Le API server-to-server (S 2 S) forniscono codice e metodi che consentono di inviare e ricevere dati utente DCS e di lavorare con tali informazioni nei propri sistemi o applicazioni.
seo-title: API DCS per trasferimenti di dati server-to-server
solution: Audience Manager
title: API DCS per trasferimenti di dati server-to-server
uuid: 8 c 369166-c 8 a 7-46 b 0-9913-4 c 027 f 5 b 1 df 9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS APIs for Server-to-Server Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s provide code and methods that let you send and receive [!UICONTROL DCS] user data and work with this information in your own systems or applications.

## Common Use Cases {#common-use-cases}

[!UICONTROL Server-to-server] I trasferimenti possono essere utili per personalizzare le pagine di destinazione o altre interazioni in base agli interessi dei visitatori. Alcuni casi d'uso comuni includono:

* Personalizzazione sul sito: Personalizza l'esperienza di un visitatore sul tuo sito aggiungendo in modo dinamico contenuti e chiamate pertinenti all'azione in base ai segmenti a cui appartengono.
* Improve customer service: Import [!DNL Audience Manager] segments into a [!DNL CRM] or other system through a server-to-server data transfer. Questi dati possono fornire agli operatori chat online o on-line informazioni pertinenti e personalizzate su un cliente.

## Requirements: User IDs and Regional Server Names {#requirements}

The [!UICONTROL DCS API] requires user IDs and region IDs to validate and make data requests.

* L'ID utente è richiesto perché è necessario associare dati a un particolare visitatore.
* L'ID regione è richiesto per collegare le chiamate al nome di un server e perché i dati utente vengono memorizzati nei centri dati geograficamente più vicini ai visitatori del sito.

## Introduzione {#getting-started}

Al momento, questa guida illustra come:

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

Aggiungeremo nuovi metodi man mano che diventano disponibili. Per iniziare, consultare le sezioni seguenti.

* [Ottieni ID utente e regioni da una risposta DCS](dcs-aam-ids.md)
* [Ottieni ID utente e regioni tramite l'Experience Cloud ID…](dcs-mcid-ids.md)
* [Effettuare chiamate API Server-to-Server DCS](dcs-s2s-calls.md)

>[!MORE_ LIKE_ THIS]
>
>* [Riferimento API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

