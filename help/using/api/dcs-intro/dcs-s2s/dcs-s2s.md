---
description: Le API server-to-server (S2S) forniscono codice e metodi che consentono di inviare e ricevere dati utente DCS e lavorare con tali informazioni nei propri sistemi o applicazioni.
seo-description: Le API server-to-server (S2S) forniscono codice e metodi che consentono di inviare e ricevere dati utente DCS e lavorare con tali informazioni nei propri sistemi o applicazioni.
seo-title: API DCS per trasferimenti di dati server-to-server
solution: Audience Manager
title: API DCS per trasferimenti di dati server-to-server
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---

# API DCS per trasferimenti di dati server-to-server{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]forniscono codice e metodi che consentono di inviare e ricevere [!DNL DCS] dati utente e lavorare con tali informazioni nei propri sistemi o applicazioni.

## Casi d&#39;uso comuni {#common-use-cases}

[!UICONTROL Server-to-server] I trasferimenti possono essere utili per personalizzare le pagine di destinazione o altre interazioni in base agli interessi dei visitatori. Alcuni casi d’uso comuni includono:

* Personalizzazione on-site: Personalizza l’esperienza di un visitatore sul tuo sito aggiungendo in modo dinamico contenuti rilevanti e chiamate all’azione in base ai segmenti a cui appartiene.
* Migliorare il servizio clienti: Importa i segmenti [!DNL Audience Manager] in un [!DNL CRM] o in un altro sistema tramite un trasferimento di dati da server a server. Questi dati possono fornire servizi di chiamata o chat online con informazioni pertinenti e personalizzate su un cliente.

## Requisiti: ID utente e nomi server regionali {#requirements}

Il [!UICONTROL DCS API] richiede gli ID utente e gli ID di regione per convalidare ed effettuare richieste di dati.

* L&#39;ID utente è obbligatorio perché devi associare i dati a un particolare visitatore.
* L&#39;ID di regione è necessario per collegare le chiamate al nome di un server e perché i dati utente vengono memorizzati in centri dati geograficamente più vicini ai visitatori del sito.

## Introduzione {#getting-started}

Attualmente, questa guida descrive come:

* Ottieni gli ID utente e regione dai file [!DNL DCS] che potresti già ricevere come [!DNL Audience Manager] cliente.

* Ottieni gli ID utente e regione se utilizzi [!DNL Visitor ID Service].
* Effettua chiamate al [!DNL DCS] dopo aver ottenuto l&#39;ID utente e di regione.

Verranno aggiunti nuovi metodi man mano che diventano disponibili. Per iniziare, consulta le sezioni seguenti .

* [Ottenere ID utente e aree geografiche da una risposta DCS](dcs-aam-ids.md)
* [Ottieni ID utente e aree geografiche tramite l’ID Experience Cloud...](dcs-mcid-ids.md)
* [Esecuzione di chiamate API DCS server-to-server](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [Riferimenti dell’API DCS ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

