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


# Content Format for Metadata Files{#content-format-for-metadata-files}

Formattate i contenuti del file di metadati Ottimizzazione pubblico in base alle seguenti specifiche.

## Sintassi {#syntax}

La sintassi seguente definisce la struttura dei contenuti ben formattati in un file di metadati. Note, *italics* indicates a variable placeholder.

**Sintassi:***ID contenuto* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

The third column **-1** is technically the Parent ID, which is a legacy field. The value should always be set as **-1**.

>[!NOTE]
>
>È necessario un file di metadati per dimensione, quindi sono previste più file di metadati nel bucket. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Voci file separate con ^ a (control-A o ASCII 001)**

Use `^a` (control-A or ASCII 001) to separate content in your metadata files. Poiché questi sono caratteri non stampabili, l'esempio di sintassi riportato sopra mostra una barra laterale|" solo a scopo di visualizzazione.

If needed, you may download the example file - [20181105_0_1](assets/20181105_0_1.zip). Decomprimete il file e modificatelo nell'editor di scelte e regolatelo in base ai contenuti metadati effettivi, poiché contiene già il carattere di delimitazione richiesto.

>[!IMPORTANT]
>
>Non aggiungete righe di intestazione ai file di metadati.

## Esempi {#examples}

Vediamo come strutturare il contenuto in un file di metadati. Parte di questa struttura dipende dalla dimensione. The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

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
