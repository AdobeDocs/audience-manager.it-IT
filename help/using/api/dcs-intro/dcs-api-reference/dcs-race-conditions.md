---
description: Descrive come evitare le condizioni race e la gestione degli errori DCS.
seo-description: Descrive come evitare le condizioni race e la gestione degli errori DCS.
seo-title: Condizioni race ed Errori
solution: Audience Manager
title: Condizioni race ed Errori
uuid: b 0 aac 960-6732-4 e 96-87 a 5-40 ba 2755 e 02 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Race Conditions and Error Handling {#race-conditions-and-error-handling}

Describes how to prevent race conditions and [!UICONTROL DCS] error handling.

## Preventing Race Conditions {#prevent-race-conditions}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!UICONTROL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. Una condizione race è indesiderata perché può danneggiare o sovrascrivere erroneamente i dati del cookie. Come procedura ottimale, considerate i seguenti metodi per evitare il problema:

* Don't make simultaneous calls, or calls in rapid succession, to the [!UICONTROL DCS] from the same user.
* Attendete che ogni risposta torni prima di effettuare chiamate successive.

## Error Handling {#error-handling}

La gestione degli errori è limitata per query non valide o non corrette. An invalid request returns an `HTTP 200 OK` response and no data. Also, the [!UICONTROL DCS] stops processing a request, discards trait data, and returns an `HTTP 200 OK` response when a user:

* Rifiuta il monitoraggio a livello di Audience Manager o partner.
* Proviene da un'area geografica non valida/non selezionata.
* Disabilita i cookie del browser (tutto o terze parti).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).