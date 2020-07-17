---
description: Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.
seo-description: Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.
seo-title: Requisiti di denominazione delle variabili chiave
solution: Audience Manager
title: Requisiti di denominazione delle variabili chiave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 12%

---


# Requisiti di denominazione delle variabili chiave {#name-requirements-for-key-variables}

Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.

## Requisiti per la denominazione delle chiavi

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], il nome di una variabile chiave in una coppia chiave-valore può essere costituito da un numero qualsiasi di cifre seguito da 1 (o più) lettere, un trattino, un carattere di sottolineatura e cifre aggiuntive.

* Nomi chiave validi: `price123`, `123price`, `price-123`, `c_price123`.

* Nomi chiave non validi: `123`, `price!123`.

## Prefisso delle variabili chiave con `c_`

Il `c_` prefisso è *sempre* richiesto se i parametri che inviano dati in un URL di chiamata dell&#39;evento utilizzano tale sintassi.