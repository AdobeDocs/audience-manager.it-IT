---
description: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 136
ht-degree: 98%

---

# Non sono cliente di Audience Manager, ma visualizzo chiamate Javascript di Audience Manager sul mio sito

## Domanda

Non utilizzo Adobe Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript.

Perché succede?

## Risposta

È probabile che tu stia eseguendo il servizio [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) sulla tua proprietà. Se è così, questo riferimento a Audience Manager non fa necessariamente riferimento alla proprietà che esegue Audience Manager. Significa, invece, che il tuo servizio è basato su Audience Manager.

La chiamata al server Audience Manager solitamente viene eseguita per [sincronizzare gli ID cliente](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=it).
