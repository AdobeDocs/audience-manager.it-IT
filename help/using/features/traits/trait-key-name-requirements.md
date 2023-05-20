---
description: Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Requisiti di denominazione delle variabili chiave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 9%

---

# Requisiti di denominazione delle variabili chiave {#name-requirements-for-key-variables}

Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.

## Requisiti di denominazione per le chiavi

<!-- c_tb_key_name_requirements.xml -->

In entrata [!UICONTROL Expression Builder], il nome di una variabile chiave in una coppia chiave-valore può essere costituito da un numero qualsiasi di cifre seguite da una o più lettere, un trattino, un carattere di sottolineatura e cifre aggiuntive.

* Nomi chiave validi: `price123`, `123price`, `price-123`, `c_price123`.

* Nomi chiave non validi: `123`, `price!123`.

## Prefisso delle variabili chiave con `c_`

Il `c_` il prefisso è *sempre* obbligatorio se i parametri che inviano dati su un URL di chiamata evento usano tale sintassi.
