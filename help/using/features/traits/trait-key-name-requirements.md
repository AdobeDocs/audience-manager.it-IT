---
description: Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.
seo-description: Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.
seo-title: Requisiti di denominazione delle variabili chiave
solution: Audience Manager
title: Requisiti di denominazione delle variabili chiave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: 'Caratteristiche '
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 12%

---

# Requisiti di denominazione delle variabili chiave {#name-requirements-for-key-variables}

Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.

## Requisiti per la denominazione delle chiavi

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], il nome di una variabile chiave in una coppia chiave-valore può essere costituito da qualsiasi numero di cifre seguito da 1 (o più) lettere, un trattino, un trattino basso e cifre aggiuntive.

* Nomi di chiave validi: `price123`, `123price`, `price-123`, `c_price123`.

* Nomi di chiave non validi: `123`, `price!123`.

## Prefissaggio delle variabili chiave con `c_`

Il prefisso `c_` è *sempre* obbligatorio se i parametri che inviano dati in un URL di chiamata dell’evento utilizzano tale sintassi.
