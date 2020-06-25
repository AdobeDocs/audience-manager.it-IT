---
description: Non stiamo utilizzando  Audience Manager, ma  chiamate Audience Manager Javascript nel debugger Javascript - Perché?
seo-description: Non stiamo utilizzando, ma  le chiamate Audience Manager Javascript nel debugger Javascript - Perché?
seo-title: Non stiamo utilizzando  Audience Manager, ma  chiamate Audience Manager Javascript nel debugger Javascript - Perché?
solution: Audience Manager
title: Non stiamo utilizzando  Audience Manager, ma  chiamate Audience Manager Javascript nel debugger Javascript - Perché?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 1%

---


# Non siamo un cliente Audience Manager , ma vedi le  chiamate Audience Manager Javascript sul nostro sito

## domande

Non stiamo utilizzando  Adobe Audience Manager, ma  le chiamate Audience Manager Javascript nel debugger Javascript.

Perché sta succedendo questo?

## Risposta

È probabile che tu stia eseguendo il [Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) sulla tua proprietà. In caso affermativo, se si dispone di questo riferimento  Audience Manager non si fa necessariamente riferimento alla proprietà in esecuzione  Audience Manager. Significa che  Audience Manager sta fornendo questo servizio.

La chiamata al server Audience Manager  solitamente viene eseguita per [sincronizzare gli ID](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)cliente.
