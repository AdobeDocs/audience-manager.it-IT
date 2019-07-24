---
description: Inserire i dati nei file di registro dei report Prestazioni consegna in tabelle contenenti solo ID. In tabelle di ricerca separate, potete inserire metadati non ID per ridurre le dimensioni dei file e i tempi di elaborazione.
seo-description: Inserire i dati nei file di registro dei report Prestazioni consegna in tabelle contenenti solo ID. In tabelle di ricerca separate, potete inserire metadati non ID per ridurre le dimensioni dei file e i tempi di elaborazione.
seo-title: Miglioramento dei tempi di elaborazione dei file di registro con le tabelle di ricerca
solution: Audience Manager
title: Miglioramento dei tempi di elaborazione dei file di registro con le tabelle di ricerca
uuid: ffc 77618-474 b -455 e -9 c 91-15 b 32 fc 151 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Improve Log File Processing Times with Lookup Tables{#improve-log-file-processing-times-with-lookup-tables}

Inserire i dati nei file di registro dei report Prestazioni consegna in tabelle contenenti solo ID. In tabelle di ricerca separate, potete inserire metadati non ID per ridurre le dimensioni dei file e i tempi di elaborazione.

<!-- 

c_lookup_tables.xml

 -->

## I metadati del file di registro aumentano le dimensioni del file e il tempo di elaborazione

A typical log file used by the [!UICONTROL Delivery Performance] report usually contains thousands of rows and dozens of columns. Consiste di ID numerici e informazioni leggibili dall'uomo, ad esempio nomi per creativi, inserzionisti, ordini di inserimento, ecc.

This non-ID information is referred to as *`metadata`* (i.e., information about other information) and gets written in each row of the log file.

However, the [!UICONTROL Delivery Performance] report mainly works with the IDs in the log file. I metadati sono utili, ma ripetitivi. Aumenta le dimensioni dei file e i tempi di assimilazione dei dati.

## Riduci dimensioni file e abbreviazione tempo elaborazione con tabelle indice

Per migliorare le prestazioni, il file di dati principale deve contenere solo ID. Inserire i metadati in una tabella di ricerca (o indice) separata e collegare tali record al file principale con una variabile chiave comune a entrambe.

## Come ridurre le dimensioni del file nelle tabelle di ricerca

Supponiamo che tu abbia un file di dati simile a quello di seguito.

| ID utente | ID annuncio | Nome annuncio | ID ordine | Nome ordine | ID inserzionista | Nome creatore dell'annuncio |
|---|---|---|---|---|---|---|
| 1 | 111 | Scarpe A | 456 | Sneaker | 27 | Società A |
| 2 | 111 | Scarpe A | 456 | Sneaker | 27 | Società A |
| 3 | 111 | Scarpe A | 456 | Sneaker | 27 | Società A |
| 4 | 222 | Scarpe B | 789 | Hiking | 14 | Company B |
| 5 | 222 | Scarpe B | 789 | Hiking | 14 | Company B |

<br> 

Segue lo stesso file di registro con i metadati rimossi. Il file è più piccolo e di facile elaborazione quando è composto da ID.

| ID utente | ID annuncio | ID ordine | ID inserzionista |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Il file di ricerca di seguito contiene i metadati e può essere collegato al file principale con l'ID annuncio. Prendete nota anche delle dimensioni. Invece di ripetere ogni inserzionista più volte, è necessario un solo riferimento per ciascuno.

| ID annuncio | Nome annuncio | Nome ordine | Nome creatore dell'annuncio |
|---|---|---|---|
| 111 | Scarpe A | Sneaker | Società A |
| 222 | Scarpe B | Hiking | Company B |

## Le API possono eliminare la necessità di usare le tabelle di ricerca

Se il sistema di gestione degli annunci contiene un'API, potrebbe non essere necessario inviare metadati in un file di ricerca. Possiamo essere in grado di ottenere tali informazioni tramite l'API. In tal caso, i file di registro devono contenere solo ID. Collaboreremo con voi per determinare se i metadati possono essere ottenuti tramite un'API.

>[!MORE_ LIKE_ THIS]
>
>* [Report sulla distribuzione e sulle prestazioni](../../reporting/dynamic-reports/delivery-performance-report.md)

