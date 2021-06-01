---
description: Informazioni concettuali, descrizioni e definizioni per codice API DCS, metodi e processi.
seo-description: Informazioni concettuali, descrizioni e definizioni per codice API DCS, metodi e processi in Adobe Audience Manager (AAM).
seo-title: Panoramica dei riferimenti dell’API DCS in Adobe Audience Manager (AAM)
title: Panoramica dei riferimenti dell’API DCS
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 13%

---

# Panoramica dei riferimenti dell’API DCS

Informazioni, descrizioni e definizioni concettuali per codice, metodi e processi [!DNL DCS API].

* [Metodi dell’API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Invia i dati a [!DNL DCS API] utilizzando i metodi GET o POST.

* [Codici errore DCS, messaggi ed esempi](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Codici di errore e messaggi generati dai server di raccolta dati (DCS) elencati in ordine numerico in base all’ID del codice.

* [Monitoraggio ID e Inserire nell&#39;elenco Bloccati](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   Il DCS controlla gli ID ricevuti e aggiunge ad un elenco Bloccati quelli che vengono inviati con una frequenza insolitamente alta in un breve periodo di tempo.

* [ID dell’area geografica dei DCS, luoghi e nomi host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Il nome host del server DCS regionale è necessario per effettuare chiamate al DCS. Questo perché il DCS memorizza le informazioni in centri dati geograficamente vicini ai visitatori del sito. Le query funzioneranno se le invii al DCS sbagliato, ma queste chiamate sono inefficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fai corrispondere l’ID di regione con il nome host regionale corrispondente e crea la query con il nome host corretto.

* [Formattazione delle coppie chiave-valore nelle chiamate DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Quando effettua una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Leggi questa sezione per informazioni su come formattare dati chiave-valore standard e serializzati.

* [Race condition e gestione degli errori](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Descrive come impedire le condizioni di gara e la gestione degli errori DCS.

* [Attributi supportati per le chiamate API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che è possibile trasmettere ai server di raccolta dati (DCS, Data Collection Servers). Queste informazioni sono utili per formattare le richieste DCS e comprendere i parametri restituiti da questo sistema.
