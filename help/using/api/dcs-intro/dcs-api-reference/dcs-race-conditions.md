---
description: Descrive come impedire le condizioni di gara e la gestione degli errori DCS.
seo-description: Descrive come impedire le condizioni di gara e la gestione degli errori DCS.
seo-title: Condizioni di gara e gestione errori
solution: Audience Manager
title: Condizioni di gara e gestione errori
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---


# Condizioni di gara e gestione errori {#race-conditions-and-error-handling}

Descrive come impedire le condizioni di gara e la gestione degli [!DNL DCS] errori.

## Prevenzione delle condizioni di gara {#prevent-race-conditions}

Una condizione di gara può verificarsi se inviate più chiamate contemporaneamente (o in rapida successione) all&#39;utente [!DNL DCS] prima che quest&#39;ultimo finisca di rispondere alle query iniziali e di scrivere i dati nel cookie dell&#39;utente. Una condizione di gara non è desiderabile perché può corrompere o sovrascrivere in modo improprio i dati dei cookie. Per evitare questo problema, è consigliabile utilizzare i metodi seguenti:

* Non effettuare chiamate simultanee, o chiamate in rapida successione, allo [!DNL DCS] stesso utente.
* Attendi che ogni risposta torni prima di effettuare chiamate successive.

## Gestione errori {#error-handling}

La gestione degli errori è limitata per le query con formato non valido o non valido. Una richiesta non valida restituisce una `HTTP 200 OK` risposta e nessun dato. Inoltre, [!DNL DCS] interrompe l’elaborazione di una richiesta, elimina i dati relativi alle caratteristiche e restituisce una `HTTP 200 OK` risposta quando un utente:

* Rifiuta il tracciamento a livello di  Audience Manager o partner.
* Proviene da un&#39;area geografica non valida o non selezionata.
* Disattiva i cookie del browser (tutti o di terze parti).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).