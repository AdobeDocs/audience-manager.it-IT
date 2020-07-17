---
description: Informazioni concettuali, descrizioni e definizioni per codice, metodi e processi API DCS.
seo-description: Informazioni concettuali, descrizioni e definizioni per codice API DCS, metodi e processi in  Adobe Audience Manager (AAM).
seo-title: Panoramica di riferimento API DCS in  Adobe Audience Manager (AAM)
title: Panoramica dei riferimenti dell’API DCS
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 13%

---


# Panoramica dei riferimenti dell’API DCS

Informazioni concettuali, descrizioni e definizioni per [!DNL DCS API] codice, metodi e processi.

* [Metodi dell’API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Inviare i dati ai [!DNL DCS API] destinatari utilizzando i metodi GET o POST.

* [Codici errore DCS, messaggi ed esempi](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Codici di errore e messaggi generati dai Data Collection Servers (DCS) elencati in ordine numerico in base all&#39;ID del codice.

* [Monitoraggio e Inserire nell&#39;elenco Bloccati ID](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   Il DCS controlla gli ID ricevuti e aggiunge a un elenco Bloccati  quelli inviati a un tasso eccezionalmente elevato in un breve periodo di tempo.

* [ID dell’area geografica dei DCS, luoghi e nomi host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Il nome host del server DCS regionale è richiesto per effettuare chiamate al DCS. Questo perché il DCS memorizza le informazioni in centri dati geograficamente vicini ai visitatori del sito. Le query funzioneranno se le inviate al DCS sbagliato, ma queste chiamate non sono efficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fate corrispondere l’ID di regione al nome host regionale corrispondente e create la query con il nome host corretto.

* [Formattazione delle coppie chiave-valore nelle chiamate DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Quando si effettua una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Leggere questa sezione per informazioni su come formattare dati chiave-valore standard e serializzati.

* [Race condition e gestione degli errori](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Descrive come impedire le condizioni di gara e la gestione degli errori DCS.

* [Attributi supportati per le chiamate API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere ai Data Collection Servers (DCS). Queste informazioni sono utili per formattare le richieste DCS e comprendere i parametri restituiti dal sistema.
