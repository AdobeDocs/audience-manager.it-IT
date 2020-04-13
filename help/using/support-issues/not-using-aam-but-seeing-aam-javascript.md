---
description: Non stiamo utilizzando Audience Manager, ma le chiamate Javascript di Audience Manager sono visibili nel debugger Javascript - Perché?
seo-description: Non stiamo utilizzando, ma stiamo visualizzando chiamate Javascript di Audience Manager nel debugger Javascript - Perché?
seo-title: Non stiamo utilizzando Audience Manager, ma le chiamate Javascript di Audience Manager sono visibili nel debugger Javascript - Perché?
solution: Audience Manager
title: Non stiamo utilizzando Audience Manager, ma le chiamate Javascript di Audience Manager sono visibili nel debugger Javascript - Perché?
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# Non siamo un cliente Audience Manager, ma consulta le chiamate Javascript di Audience Manager sul nostro sito

## domande

Non stiamo utilizzando Adobe Audience Manager, ma le chiamate Javascript di Audience Manager sono visibili nel debugger Javascript.

Perché sta succedendo questo?

## Risposta

È probabile che tu stia eseguendo il servizio [identità](https://docs.adobe.com/content/help/en/id-service/using/home.html) Experience Cloud sulla tua proprietà. In caso affermativo, questo riferimento a Audience Manager non fa necessariamente riferimento alla proprietà che esegue Audience Manager. Significa, invece, che Audience Manager fornisce questo servizio.

La chiamata al server Audience Manager solitamente viene eseguita per [sincronizzare gli ID](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)cliente.
