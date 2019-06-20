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


# API DCS per trasferimenti di dati server-to-server{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]forniscono codice e metodi che consentono di inviare e ricevere [!UICONTROL DCS] dati utente e di lavorare con tali informazioni nei propri sistemi o applicazioni.

## Casi d&#39;uso comuni {#common-use-cases}

[!UICONTROL Server-to-server] I trasferimenti possono essere utili per personalizzare le pagine di destinazione o altre interazioni in base agli interessi dei visitatori. Alcuni casi d&#39;uso comuni includono:

* Personalizzazione sul sito: Personalizza l&#39;esperienza di un visitatore sul tuo sito aggiungendo in modo dinamico contenuti e chiamate pertinenti all&#39;azione in base ai segmenti a cui appartengono.
* Miglioramento del servizio clienti: Importa [!DNL Audience Manager] i segmenti in un [!DNL CRM] altro sistema tramite un trasferimento di dati da server a server. Questi dati possono fornire agli operatori chat online o on-line informazioni pertinenti e personalizzate su un cliente.

## Requisiti: ID utente e nomi server regionali {#requirements}

L&#39;utente [!UICONTROL DCS API] richiede ID utente e ID di regione per convalidare e effettuare richieste di dati.

* L&#39;ID utente è richiesto perché è necessario associare dati a un particolare visitatore.
* L&#39;ID regione è richiesto per collegare le chiamate al nome di un server e perché i dati utente vengono memorizzati nei centri dati geograficamente più vicini ai visitatori del sito.

## Introduzione {#getting-started}

Al momento, questa guida illustra come:

* Ottenete gli ID utente e regione dai [!UICONTROL DCS] file che potete già ricevere come [!DNL Audience Manager] cliente.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Effettua chiamate all&#39; [!UICONTROL DCS] ID di utenti e regione.

Aggiungeremo nuovi metodi man mano che diventano disponibili. Per iniziare, consultare le sezioni seguenti.

* [Ottieni ID utente e regioni da una risposta DCS](dcs-aam-ids.md)
* [Ottieni ID utente e regioni tramite l&#39;Experience Cloud ID…](dcs-mcid-ids.md)
* [Effettuare chiamate API Server-to-Server DCS](dcs-s2s-calls.md)

>[!MORE_ LIKE_ THIS]
>
>* [Riferimento API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

