---
description: Informazioni teoriche, descrizioni e definizioni per codice API, metodi e processi DCS.
seo-description: Informazioni teoriche, descrizioni e definizioni per codice API, metodi e processi DCS in Adobe Audience Manager (AAM).
seo-title: Panoramica di riferimento API DCS in Adobe Audience Manager (AAM)
title: Panoramica di riferimento API DCS
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Panoramica di riferimento API DCS

Informazioni teoriche, descrizioni e definizioni per codice API, metodi e processi DCS.

* [Metodi API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Invia dati all'API DCS utilizzando i metodi GET o POST.

* [Codici errore DCS, messaggi ed esempi](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Codici di errore e messaggi generati dai server di raccolta dati (DCS) elencati in ordine numerico tramite ID codice.

* [Monitoraggio ID e Blacklisting](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-blacklisting.md)

   Il DCS monitora gli ID ricevuti e blacklist quelli che vengono inviati a un tasso di tempo elevato per un breve periodo di tempo.

* [ID regioni DCS, posizioni e nomi host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Per effettuare chiamate al DCS è necessario il nome host del server DCS regionale. poiché il DCS memorizza informazioni nei centri dati che sono geograficamente vicini ai visitatori del sito. Le tue query funzionano se li invii al DCS sbagliato, ma queste chiamate sono inefficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fai corrispondere l'ID regione al nome host regionale corrispondente e completa la query con il nome host corretto.

* [Formattazione delle coppie chiave-valore in DCS Chiamate](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Quando effettuano una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Consultate questa sezione per informazioni su come formattare i dati chiave-valore standard e serializzati.

* [Condizioni race ed Errori](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Descrive come evitare le condizioni race e la gestione degli errori DCS.

* [Attributi supportati per chiamate API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere ai server di raccolta dati (DCS). Queste informazioni possono essere utili per formattare le richieste DCS e comprendere i parametri restituiti dal sistema.
