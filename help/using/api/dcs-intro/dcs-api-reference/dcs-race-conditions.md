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


# Condizioni race ed Errori {#race-conditions-and-error-handling}

Descrive come evitare condizioni race ed [!UICONTROL DCS] errori.

## Impedire la presenza di condizioni race {#prevent-race-conditions}

Una condizione race può verificarsi se inviate più chiamate contemporaneamente (o in rapida successione) al [!UICONTROL DCS] prima che termini a rispondere alle query iniziali e a scrivere dati nel cookie dell&#39;utente. Una condizione race è indesiderata perché può danneggiare o sovrascrivere erroneamente i dati del cookie. Come procedura ottimale, considerate i seguenti metodi per evitare il problema:

* Non effettuare chiamate simultanee, o chiamate in rapida successione, [!UICONTROL DCS] allo stesso utente.
* Attendete che ogni risposta torni prima di effettuare chiamate successive.

## Gestione errori {#error-handling}

La gestione degli errori è limitata per query non valide o non corrette. Una richiesta non valida restituisce `HTTP 200 OK` una risposta e nessun dato. Inoltre, l&#39;elaborazione [!UICONTROL DCS] interrompe una richiesta, elimina i dati delle caratteristiche e restituisce una `HTTP 200 OK` risposta quando un utente:

* Rifiuta il monitoraggio a livello di Audience Manager o partner.
* Proviene da un&#39;area geografica non valida/non selezionata.
* Disabilita i cookie del browser (tutto o terze parti).

Vedi anche Codici di errore, messaggi ed esempi [DCS](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).