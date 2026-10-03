---
description: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: 'Non utilizzo Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript: perché?'
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: 'https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 88%
---
# Non sono cliente di Audience Manager, ma visualizzo chiamate Javascript di Audience Manager sul mio sito

## Domanda

Non utilizzo Adobe Audience Manager, ma visualizzo chiamate Javascript di Audience Manager nel debugger Javascript.

Perché succede?

## Risposta

È probabile che tu stia eseguendo il servizio [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) sulla tua proprietà. Se è così, questo riferimento a Audience Manager non fa necessariamente riferimento alla proprietà che esegue Audience Manager. Significa, invece, che il tuo servizio è basato su Audience Manager.

La chiamata al server Audience Manager solitamente viene eseguita per [sincronizzare gli ID cliente](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=it).
