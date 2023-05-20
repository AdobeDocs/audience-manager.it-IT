---
description: Informazioni concettuali, descrizioni e definizioni per il codice, i metodi e i processi dell’API DCS.
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: Panoramica dei riferimenti dell’API DCS
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 14%

---

# Panoramica dei riferimenti dell’API DCS

Informazioni concettuali, descrizioni e definizioni per [!DNL DCS API] codice, metodi e processi.

* [Metodi dell’API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Invia dati a [!DNL DCS API] utilizzando i metodi GET o POST.

* [Codici errore DCS, messaggi ed esempi](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Codici di errore e messaggi generati dai server di raccolta dati (DCS, Data Collection Servers) elencati in ordine numerico per ID codice.

* [Monitoraggio degli ID e Inserisce nell&#39;elenco Bloccati degli ID](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   Il DCS monitora gli ID ricevuti e aggiunge a un elenco Bloccati quelli che vengono inviati con una frequenza insolitamente alta in un breve periodo di tempo.

* [ID dell’area geografica dei DCS, luoghi e nomi host](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Per effettuare chiamate al DCS è necessario specificare il nome host del server DCS regionale. Questo perché il DCS memorizza le informazioni in centri dati geograficamente vicini ai visitatori del sito. Le query funzioneranno se le invii al DCS sbagliato, ma queste chiamate sono inefficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fai corrispondere l’ID di regione al nome host regionale corrispondente e crea la query con il nome host corretto.

* [Formattazione delle coppie chiave-valore nelle chiamate DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Quando effettua una chiamata, il DCS accetta dati chiave-valore in formato standard o serializzato. Consulta questa sezione per informazioni su come formattare dati chiave-valore standard e serializzati.

* [Race condition e gestione degli errori](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Descrive come evitare le race condition e la gestione degli errori DCS.

* [Attributi supportati per le chiamate API DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Elenca e descrive la sintassi e gli attributi supportati (o coppie chiave-valore) che puoi trasmettere ai server di raccolta dati (DCS, Data Collection Servers). Queste informazioni possono essere utili per formattare le richieste DCS e comprendere i parametri restituiti dal sistema.
