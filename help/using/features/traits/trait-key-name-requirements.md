---
description: Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.
seo-description: Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.
seo-title: Requisiti del nome per le variabili chiave
solution: Audience Manager
title: Requisiti del nome per le variabili chiave
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
translation-type: tm+mt
source-git-commit: bdbc2525a13eb04898b0a844ba478cde07e83252

---


# Requisiti del nome per le variabili chiave {#name-requirements-for-key-variables}

Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile chiave in una coppia chiave-valore.

## Requisiti per la denominazione delle chiavi

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], il nome di una variabile chiave in una coppia chiave-valore può essere costituito da un numero qualsiasi di cifre seguito da 1 (o più) lettere, un trattino, un carattere di sottolineatura e cifre aggiuntive.

* Nomi chiave validi: `price123`, `123price`, `price-123`, `c_price123`.

* Nomi chiave non validi: `123`, `price!123`..

## Prefisso delle variabili chiave con `c_`

Il `c_` prefisso è *sempre* richiesto se i parametri che inviano dati in un URL di chiamata dell'evento utilizzano tale sintassi.