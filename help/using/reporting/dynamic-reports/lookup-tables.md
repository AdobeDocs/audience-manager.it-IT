---
description: Inserisci i dati nei file di registro del rapporto Prestazioni consegna in tabelle che contengono solo ID. Inserisci metadati non ID in tabelle di ricerca separate per ridurre le dimensioni dei file e i tempi di elaborazione.
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: Migliorare i tempi di elaborazione dei file di registro con le tabelle di ricerca
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 12%

---

# Migliorare i tempi di elaborazione dei file di registro con le tabelle di ricerca{#improve-log-file-processing-times-with-lookup-tables}

Inserisci i dati nei file di registro del rapporto Prestazioni consegna in tabelle che contengono solo ID. Inserisci metadati non ID in tabelle di ricerca separate per ridurre le dimensioni dei file e i tempi di elaborazione.

<!-- 

c_lookup_tables.xml

 -->

## I metadati del file di registro aumentano le dimensioni del file e il tempo di elaborazione

Un file di log tipico utilizzato dal report [!UICONTROL Delivery Performance] contiene in genere migliaia di righe e decine di colonne. È costituito da ID numerici e informazioni leggibili dall’uomo come nomi di creativi, inserzionisti, ordini di inserimento e così via.

Queste informazioni non ID sono denominate *`metadata`* (ovvero informazioni su altre informazioni) e vengono scritte in ogni riga del file di log.

Tuttavia, il report [!UICONTROL Delivery Performance] funziona principalmente con gli ID nel file di log. I metadati sono utili, ma ripetitivi. Aumenta le dimensioni dei file e i tempi di acquisizione dei dati.

## Riduzione delle dimensioni dei file e riduzione dei tempi di elaborazione con le tabelle indice

Per migliorare le prestazioni, il file di dati principale deve contenere solo ID. Inserisci i metadati in una tabella di ricerca (o indice) separata e collega tali record al file principale con una variabile chiave comune a entrambi.

## Riduzione delle dimensioni dei file nelle tabelle di ricerca

Supponiamo che tu abbia un file di dati simile a quello seguente.

| ID utente | ID annuncio | Nome annuncio | ID ordine | Nome ordine | ID inserzionista | Nome inserzionista |
|---|---|---|---|---|---|---|
| 1 | 111 | Scarpa A | 456 | Sneakers | 27 | Società A |
| 2 | 111 | Scarpa A | 456 | Sneakers | 27 | Società A |
| 3 | 111 | Scarpa A | 456 | Sneakers | 27 | Società A |
| 4 | 222 | Scarpa B | 789 | Trekking | 14 | Società B |
| 5 | 222 | Scarpa B | 789 | Trekking | 14 | Società B |

<br> 

Ecco lo stesso file di registro con i metadati rimossi. Il file è più piccolo e facile da elaborare quando è costituito solo da ID.

| ID utente | ID annuncio | ID ordine | ID inserzionista |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Il file di ricerca seguente contiene i metadati e può essere collegato nuovamente al file principale con l’ID annuncio. Prendi nota anche delle dimensioni. Invece di ripetere più volte ogni inserzionista, è necessario un solo riferimento per ciascuno di essi.

| ID annuncio | Nome annuncio | Nome ordine | Nome inserzionista |
|---|---|---|---|
| 111 | Scarpa A | Sneakers | Società A |
| 222 | Scarpa B | Trekking | Società B |

## Le API possono eliminare la necessità di tabelle di ricerca

Se il sistema ad serving dispone di un’API, potrebbe non essere necessario inviare metadati in un file di ricerca. Potremmo essere in grado di ottenere tali informazioni tramite l’API. In questo caso, i file di registro devono contenere solo ID. Collaboreremo con te per determinare se i metadati possono essere ottenuti tramite un’API.
