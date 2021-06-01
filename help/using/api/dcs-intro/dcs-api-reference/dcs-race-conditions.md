---
description: Descrive come impedire le condizioni di gara e la gestione degli errori DCS.
seo-description: Descrive come impedire le condizioni di gara e la gestione degli errori DCS.
seo-title: Race condition e gestione degli errori
solution: Audience Manager
title: Race condition e gestione degli errori
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---

# Race condition e gestione degli errori {#race-conditions-and-error-handling}

Descrive come impedire le condizioni di corsa e la gestione degli errori [!DNL DCS].

## Prevenzione delle condizioni di corsa {#prevent-race-conditions}

Una race condition può verificarsi se si inviano più chiamate contemporaneamente (o in rapida successione) al [!DNL DCS] prima che termini la risposta alle query iniziali e la scrittura di dati nel cookie dell’utente. Una situazione di tipo &quot;race condition&quot; non è auspicabile perché può corrompere o sovrascrivere in modo errato i dati dei cookie. Come best practice, considera i seguenti metodi per evitare questo problema:

* Non effettuare chiamate simultanee, o in rapida successione, allo [!DNL DCS] dello stesso utente.
* Attendi che ogni risposta torni prima di effettuare chiamate successive.

## Gestione degli errori {#error-handling}

La gestione degli errori è limitata per le query non valide o con formato insufficiente. Una richiesta non valida restituisce una risposta `HTTP 200 OK` e nessun dato. Inoltre, [!DNL DCS] smette di elaborare una richiesta, elimina i dati delle caratteristiche e restituisce una risposta `HTTP 200 OK` quando un utente:

* Rinuncia al tracciamento a livello di Audience Manager o di partner.
* Proviene da un&#39;area geografica non valida/non selezionata.
* Disattiva i cookie del browser (tutti o di terze parti).

Vedi anche [Codici di errore DCS, messaggi ed esempi](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
