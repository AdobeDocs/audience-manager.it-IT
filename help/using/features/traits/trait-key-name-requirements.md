---
description: Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile key in una coppia chiave-valore.
seo-description: Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile key in una coppia chiave-valore.
seo-title: Requisiti del nome per le variabili chiave
solution: Audience Manager
title: Requisiti del nome per le variabili chiave
uuid: fa 72 e 732-895 d -4 cf 6-bea 0-66 b 404 c 2 b 059
translation-type: tm+mt
source-git-commit: bdbc2525a13eb04898b0a844ba478cde07e83252

---


# Requisiti del nome per le variabili chiave {#name-requirements-for-key-variables}

Questo articolo descrive le convenzioni di denominazione utilizzate dalla variabile key in una coppia chiave-valore.

## Requisiti di denominazione per chiavi

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], il nome di una variabile chiave in una coppia chiave-valore può essere composto da un numero qualsiasi di cifre seguito da 1 (o più) lettere, un trattino, un carattere di sottolineatura e cifre aggiuntive.

* Nomi chiave validi: `price123``123price``price-123``c_price123`,

* Nomi chiave non validi: `123``price!123`.

## Prefisso variabili chiave con `c_`

Il `c_` prefisso è *sempre richiesto* se i parametri inviati nei dati sull&#39;URL di un invito all&#39;evento utilizzano la sintassi.