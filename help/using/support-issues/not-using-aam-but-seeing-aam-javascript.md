---
description: Non stiamo utilizzando Audience Manager, ma le chiamate Javascript di Audience Manager sono visibili nel debugger Javascript - Perché?
seo-description: Non stiamo utilizzando, ma stiamo visualizzando chiamate Javascript di Audience Manager nel debugger Javascript - Perché?
seo-title: Non stiamo utilizzando Audience Manager, ma le chiamate Javascript di Audience Manager sono visibili nel debugger Javascript - Perché?
solution: Audience Manager
title: Non stiamo utilizzando Audience Manager, ma le chiamate Javascript di Audience Manager sono visibili nel debugger Javascript - Perché?
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# Non siamo un cliente Audience Manager, ma consulta le chiamate Javascript di Audience Manager sul nostro sito

## domande

Non stiamo utilizzando Adobe Audience Manager, ma le chiamate Javascript di Audience Manager sono visibili nel debugger Javascript.  Perché succederebbe?

## Risposta

È probabile che tu stia eseguendo il servizio ID visitatore sulla tua proprietà. In caso affermativo, il riferimento AAM non fa necessariamente riferimento alla proprietà che esegue Audience Manager, ma significa che Audience Manager sta di fatto abilitando questo servizio.

La chiamata AAM solitamente viene eseguita per sincronizzare gli ID cliente del set.
