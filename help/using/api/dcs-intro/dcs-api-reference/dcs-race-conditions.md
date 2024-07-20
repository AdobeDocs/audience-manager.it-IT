---
description: Descrive come evitare le race condition e la gestione degli errori DCS.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Race condition e gestione degli errori
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# Race condition, limitazione della frequenza e gestione degli errori {#race-conditions-and-error-handling}

Descrive come evitare le race condition e la gestione degli errori [!DNL DCS].

## Prevenzione delle race condition {#prevent-race-conditions}

Una situazione di tipo &quot;race condition&quot; può verificarsi se si inviano più chiamate contemporaneamente (o in rapida successione) a [!DNL DCS] prima che termini la risposta alle query iniziali e la scrittura dei dati nel cookie dell&#39;utente. Una situazione di tipo &quot;race condition&quot; non è consigliabile in quanto può danneggiare o sovrascrivere in modo non corretto i dati dei cookie. Come best practice, considera i seguenti metodi per evitare questo problema:

* Non effettuare chiamate simultanee o in rapida successione a [!DNL DCS] dallo stesso utente.
* Attendi che venga restituita ogni risposta prima di effettuare chiamate successive.

## Limitazione di velocità {#rate-limiting}

Adobe può introdurre una limitazione della frequenza se rileva chiamate API DCS eccessive che potrebbero avere un impatto negativo sulla disponibilità del servizio.

Se la limitazione della frequenza è abilitata, potresti ricevere un codice di stato di risposta HTTP `429 Too Many Requests` nelle chiamate DCS. Quando ricevi questa risposta HTTP, riprova le chiamate API in un secondo momento.

## Gestione degli errori {#error-handling}

La gestione degli errori è limitata per le query non valide o con formato non corretto. Una richiesta non valida restituisce una risposta `HTTP 200 OK` e nessun dato. Inoltre, [!DNL DCS] smette di elaborare una richiesta, scarta i dati sulle caratteristiche e restituisce una risposta `HTTP 200 OK` quando un utente:

* Rinuncia al tracciamento a livello di Audience Manager o partner.
* Proviene da un’area geografica non valida/non selezionata.
* Disattiva i cookie del browser (tutti o di terze parti).

Vedi anche [Codici errore DCS, messaggi ed esempi](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
