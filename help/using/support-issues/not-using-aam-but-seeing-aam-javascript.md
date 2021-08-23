---
description: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
seo-description: 'Non lo utilizzo, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
seo-title: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
solution: Audience Manager
title: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
feature: 'Supporto '
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 92%

---

# Non sono cliente di Audience Manager, ma visualizzo chiamate Javascript di Audience Manager sul mio sito

## Domanda

Non utilizzo Adobe Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript.

Perché succede?

## Risposta

È probabile che tu stia eseguendo il servizio [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) sulla tua proprietà. Se è così, questo riferimento a Audience Manager non fa necessariamente riferimento alla proprietà che esegue Audience Manager. Significa, invece, che il tuo servizio è basato su Audience Manager.

La chiamata al server Audience Manager solitamente viene eseguita per [sincronizzare gli ID cliente](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html).
