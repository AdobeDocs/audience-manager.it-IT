---
description: Inserire i dati nei file di registro del report Performance di consegna nelle tabelle che contengono solo ID. Inserite i metadati non ID in tabelle di ricerca separate per ridurre le dimensioni dei file e i tempi di elaborazione.
seo-description: Inserire i dati nei file di registro del report Performance di consegna nelle tabelle che contengono solo ID. Inserite i metadati non ID in tabelle di ricerca separate per ridurre le dimensioni dei file e i tempi di elaborazione.
seo-title: Migliorare i tempi di elaborazione dei file di registro con le tabelle di ricerca
solution: Audience Manager
title: Migliorare i tempi di elaborazione dei file di registro con le tabelle di ricerca
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 14%

---


# Migliorare i tempi di elaborazione dei file di registro con le tabelle di ricerca{#improve-log-file-processing-times-with-lookup-tables}

Inserire i dati nei file di registro del report Performance di consegna nelle tabelle che contengono solo ID. Inserite i metadati non ID in tabelle di ricerca separate per ridurre le dimensioni dei file e i tempi di elaborazione.

<!-- 

c_lookup_tables.xml

 -->

## I metadati del file di registro aumentano la dimensione del file e il tempo di elaborazione

Un file di registro tipico utilizzato dal report [!UICONTROL Delivery Performance] in genere contiene migliaia di righe e dozzine di colonne. È costituito da ID numerici e da informazioni leggibili dall’utente, ad esempio nomi per creativi, inserzionisti, ordini di inserimento ecc.

Queste informazioni non ID sono denominate *`metadata`* (ovvero informazioni su altre informazioni) e vengono scritte in ogni riga del file di registro.

Tuttavia, il rapporto [!UICONTROL Delivery Performance] funziona principalmente con gli ID nel file di registro. I metadati sono utili, ma ripetitivi. Aumenta le dimensioni dei file e i tempi di caricamento dei dati.

## Ridurre le dimensioni dei file e ridurre i tempi di elaborazione con le tabelle indice

Per migliorare le prestazioni, il file di dati principale deve contenere solo ID. Inserite i metadati in una tabella di ricerca (o indice) separata e collegate tali record al file principale con una variabile chiave comune a entrambi.

## Come le tabelle di ricerca riducono le dimensioni del file

Supponiamo che tu abbia un file di dati simile a quello riportato di seguito.

| ID utente | ID annuncio | Nome annuncio | ID ordine | Nome ordine | ID inserzionista | Nome inserzionista |
|---|---|---|---|---|---|---|
| 1 | 111 | Scarpa A | 456 | Snaker | 27 | Società A |
| 2 | 111 | Scarpa A | 456 | Snaker | 27 | Società A |
| 3 | 111 | Scarpa A | 456 | Snaker | 27 | Società A |
| 4 | 222 | Scarpa B | 789 | Escursione | 14 | Società B |
| 5 | 222 | Scarpa B | 789 | Escursione | 14 | Società B |

<br> 

Lo stesso file di registro con i metadati rimossi. Il file è più piccolo e facile da elaborare se è composto solo da ID.

| ID utente | ID annuncio | ID ordine | ID inserzionista |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Il file di ricerca seguente contiene i metadati e può essere collegato al file principale con l&#39;ID annuncio. Prendi nota anche della dimensione. Invece di ripetere più volte ogni inserzionista, è necessario un solo riferimento per ogni utente.

| ID annuncio | Nome annuncio | Nome ordine | Nome inserzionista |
|---|---|---|---|
| 111 | Scarpa A | Snaker | Società A |
| 222 | Scarpa B | Escursione | Società B |

## Le API possono eliminare la necessità di tabelle di ricerca

Se il sistema di gestione degli annunci ha un&#39;API, potrebbe non essere necessario inviare i metadati in un file di ricerca. Potremmo essere in grado di ottenere tali informazioni tramite l&#39;API. In questo caso, i file di registro devono contenere solo ID. Vi aiuteremo a determinare se i metadati possono essere ottenuti tramite un&#39;API.