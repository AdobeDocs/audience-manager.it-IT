---
description: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
seo-description: 'Non lo utilizzo, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
seo-title: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
solution: Audience Manager
title: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 100%

---


# Non sono cliente di Audience Manager, ma visualizzo chiamate Javascript di Audience Manager sul mio sito

## Domanda

Non utilizzo Adobe Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript.

Perché succede?

## Risposta

È probabile che tu stia eseguendo il servizio [Experience Cloud Identity Service](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) sulla tua proprietà. Se è così, questo riferimento a Audience Manager non fa necessariamente riferimento alla proprietà che esegue Audience Manager. Significa, invece, che il tuo servizio è basato su Audience Manager.

La chiamata al server Audience Manager solitamente viene eseguita per [sincronizzare gli ID cliente](https://docs.adobe.com/content/help/it-IT/id-service/using/id-service-api/methods/setcustomerids.html).
