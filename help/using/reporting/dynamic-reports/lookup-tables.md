---
description: Inserisci i dati nei file di registro del report Performance di consegna in tabelle che contengono solo ID. Inserisci metadati non ID in tabelle di ricerca separate per ridurre le dimensioni dei file e i tempi di elaborazione.
seo-description: Inserisci i dati nei file di registro del report Performance di consegna in tabelle che contengono solo ID. Inserisci metadati non ID in tabelle di ricerca separate per ridurre le dimensioni dei file e i tempi di elaborazione.
seo-title: Migliorare i tempi di elaborazione dei file di registro con le tabelle di ricerca
solution: Audience Manager
title: Migliorare i tempi di elaborazione dei file di registro con le tabelle di ricerca
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Riferimento per la generazione di rapporti
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 14%

---

# Migliorare i tempi di elaborazione dei file di registro con le tabelle di ricerca{#improve-log-file-processing-times-with-lookup-tables}

Inserisci i dati nei file di registro del report Performance di consegna in tabelle che contengono solo ID. Inserisci metadati non ID in tabelle di ricerca separate per ridurre le dimensioni dei file e i tempi di elaborazione.

<!-- 

c_lookup_tables.xml

 -->

## I metadati dei file di registro aumentano le dimensioni dei file e il tempo di elaborazione

Un file di registro tipico utilizzato dal rapporto [!UICONTROL Delivery Performance] in genere contiene migliaia di righe e decine di colonne. È costituito da ID numerici e da informazioni leggibili dagli utenti, ad esempio nomi per creativi, inserzionisti, ordini di inserimento, ecc.

Queste informazioni non ID sono denominate *`metadata`* (ovvero, informazioni su altre informazioni) e vengono scritte in ogni riga del file di registro.

Tuttavia, il rapporto [!UICONTROL Delivery Performance] funziona principalmente con gli ID nel file di registro. I metadati sono utili, ma ripetitivi. Aumenta le dimensioni dei file e i tempi di inserimento dei dati.

## Ridurre le dimensioni dei file e ridurre i tempi di elaborazione con le tabelle indice

Per migliorare le prestazioni, il file di dati principale deve contenere solo ID. Inserisci i metadati in una tabella di ricerca (o indice) separata e collega tali record al file principale con una variabile chiave comune a entrambi.

## Come le tabelle di ricerca riducono le dimensioni dei file

Supponiamo che tu abbia un file di dati simile a quello sottostante.

| ID utente | ID annuncio | Nome annuncio | ID ordine | Nome ordine | ID inserzionista | Nome inserzionista |
|---|---|---|---|---|---|---|
| 1 | 111 | Scarpa A | 456 | Sneaker | 27 | Società A |
| 2 | 111 | Scarpa A | 456 | Sneaker | 27 | Società A |
| 3 | 111 | Scarpa A | 456 | Sneaker | 27 | Società A |
| 4 | 222 | Scarpa B | 789 | Escursioni | 14 | Società B |
| 5 | 222 | Scarpa B | 789 | Escursioni | 14 | Società B |

<br> 

Ecco lo stesso file di log con i metadati rimossi. Il file è più piccolo e facile da elaborare quando è costituito solo da ID.

| ID utente | ID annuncio | ID ordine | ID inserzionista |
|---|---|---|---|
| 3 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Il file di ricerca sottostante contiene i metadati e può essere collegato nuovamente al file principale con l&#39;Ad ID. Prendi nota anche della dimensione. Invece di ripetere più volte ogni inserzionista, è necessario un solo riferimento per ogni.

| ID annuncio | Nome annuncio | Nome ordine | Nome inserzionista |
|---|---|---|---|
| 111 | Scarpa A | Sneaker | Società A |
| 222 | Scarpa B | Escursioni | Società B |

## Le API possono eliminare la necessità di tabelle di ricerca

Se il sistema di ad serving dispone di un’API, potrebbe non essere necessario inviare metadati in un file di ricerca. Potremmo essere in grado di ottenere tali informazioni tramite l&#39;API. In questo caso, i file di registro devono contenere solo ID. Collaboreremo con te per determinare se i metadati possono essere ottenuti tramite un’API.
