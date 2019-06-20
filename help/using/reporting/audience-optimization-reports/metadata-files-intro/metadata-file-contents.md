---
description: Formattate i contenuti del file di metadati Ottimizzazione pubblico in base alle seguenti specifiche.
seo-description: Formattate i contenuti del file di metadati Ottimizzazione pubblico in base alle seguenti specifiche.
seo-title: Formato contenuto per file metadati
solution: Audience Manager
title: Formato contenuto per file metadati
uuid: 9 ba 44738-3 e 17-40 c 7-9 e 8 c -5 abd 8361 e 16 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Formato contenuto per file metadati{#content-format-for-metadata-files}

Formattate i contenuti del file di metadati Ottimizzazione pubblico in base alle seguenti specifiche.

## Sintassi {#syntax}

La sintassi seguente definisce la struttura dei contenuti ben formattati in un file di metadati. Nota, *il corsivo* indica un segnaposto variabile.

**Sintassi:***ID contenuto* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

La terza colonna **-1** è tecnicamente l&#39;ID principale, un campo legacy. Il valore deve essere sempre impostato su **-1**.

>[!NOTE]
>
>È necessario un file di metadati per dimensione, quindi sono previste più file di metadati nel bucket. Le dimensioni sono elencate nelle convenzioni [di denominazione degli articoli per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Voci file separate con ^ a (control-A o ASCII 001)**

Utilizzate `^a` (control-A o ASCII 001) per separare il contenuto nei file di metadati. Poiché questi sono caratteri non stampabili, l&#39;esempio di sintassi riportato sopra mostra una barra laterale|&quot; solo a scopo di visualizzazione.

Se necessario, potete scaricare il file di esempio - [20181105_ 0_ 1](assets/20181105_0_1.zip). Decomprimete il file e modificatelo nell&#39;editor di scelte e regolatelo in base ai contenuti metadati effettivi, poiché contiene già il carattere di delimitazione richiesto.

>[!IMPORTANT]
>
>Non aggiungete righe di intestazione ai file di metadati.

## Esempi {#examples}

Vediamo come strutturare il contenuto in un file di metadati. Parte di questa struttura dipende dalla dimensione. Le dimensioni sono elencate nelle convenzioni [di denominazione degli articoli per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

In questo esempio, il titolo del file è 20180921_ 0_ 1 e le tre colonne del file sono: ID campagna, Nome e ID principale.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

In questo esempio, il titolo del file è 20180827_ 0_ 2 e le tre colonne del file sono: ID creativo, Nome e ID principale.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Sito**

In questo esempio, il titolo del file è 20180921_ 0_ 5 e le tre colonne del file sono: ID sito, Nome e ID principale.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
