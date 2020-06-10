---
description: Informazioni concettuali, descrizioni e definizioni per codice, metodi e processi API DCS.
seo-description: Informazioni concettuali, descrizioni e definizioni per codice, metodi e processi API DCS in Adobe Audience Manager (AAM).
seo-title: Panoramica di riferimento API DCS in Adobe Audience Manager (AAM)
title: Panoramica di riferimento API DCS
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---


# Panoramica di riferimento API DCS

Informazioni concettuali, descrizioni e definizioni per codice, metodi e processi API DCS.

* [Metodi API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Inviare i dati all&#39;API DCS utilizzando i metodi GET o POST.

* [Codici errore DCS, messaggi ed esempi](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Codici di errore e messaggi generati dai Data Collection Servers (DCS) elencati in ordine numerico in base all&#39;ID del codice.

* [Monitoraggio ID e denylist](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   Il DCS controlla gli ID ricevuti e aggiunge a un elenco di negazioni quelli inviati a un tasso insolitamente elevato in un breve periodo di tempo.

* [ID regione DCS, posizioni e nomi host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Il nome host del server DCS regionale è richiesto per effettuare chiamate al DCS. Questo perché il DCS memorizza le informazioni in centri dati geograficamente vicini ai visitatori del sito. Le query funzioneranno se le inviate al DCS sbagliato, ma queste chiamate non sono efficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fate corrispondere l’ID di regione al nome host regionale corrispondente e create la query con il nome host corretto.

* [Formattazione delle coppie chiave-valore nelle chiamate DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Quando si effettua una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Leggere questa sezione per informazioni su come formattare dati chiave-valore standard e serializzati.

* [Condizioni di gara e gestione errori](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Descrive come impedire le condizioni di gara e la gestione degli errori DCS.

* [Attributi supportati per le chiamate API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere ai Data Collection Servers (DCS). Queste informazioni sono utili per formattare le richieste DCS e comprendere i parametri restituiti dal sistema.
