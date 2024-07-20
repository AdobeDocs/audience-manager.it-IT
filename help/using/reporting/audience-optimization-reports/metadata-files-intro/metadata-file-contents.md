---
description: Formatta il contenuto del file di metadati di Audience Optimization in base a queste specifiche.
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: Formato contenuto per file metadati
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# Formato contenuto per file metadati{#content-format-for-metadata-files}

Formatta il contenuto del file di metadati di Audience Optimization in base a queste specifiche.

## Sintassi {#syntax}

La sintassi seguente definisce la struttura di contenuti ben formati in un file di metadati. Nota: *corsivo* indica un segnaposto variabile.

**Sintassi:** *ID contenuto* | *nome* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

La terza colonna **-1** è tecnicamente l&#39;ID padre, che è un campo legacy. Il valore deve essere sempre impostato come **-1**.

>[!NOTE]
>
>Tieni presente che è necessario un file di metadati per dimensione, pertanto nel bucket sono previsti più file di metadati. Le dimensioni sono elencate nell&#39;articolo [Convenzioni di denominazione per il file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Voci di file separate con ^a (controllo-A o ASCII 001)**

Utilizzare `^a` (controllo-A o ASCII 001) per separare il contenuto nei file di metadati. Poiché si tratta di caratteri non stampabili, l&#39;esempio di sintassi precedente mostra una barra verticale &quot;|&quot; solo a scopo di visualizzazione.

Se necessario, è possibile scaricare il file di esempio - [20181105_0_1](assets/20181105_0_1.zip). Decomprimi e modifica nell’editor desiderato e regola in base al contenuto effettivo dei metadati, poiché contiene già il delimitatore richiesto.

>[!IMPORTANT]
>
>Non aggiungere righe di intestazione ai file di metadati.

## Esempi {#examples}

Vediamo come struttureresti il contenuto in un file di metadati. Parte di questa struttura dipende dalla dimensione. Le dimensioni sono elencate nell&#39;articolo [Convenzioni di denominazione per il file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

In questo esempio, il titolo del file è 20180921_0_1 e le tre colonne del file sono: ID campagna, Nome e ID padre.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creativo**

In questo esempio, il titolo del file è 20180827_0_2 e le tre colonne del file sono: ID creativo, Nome e ID padre.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Sito**

In questo esempio, il titolo del file è 20180921_0_5 e le tre colonne del file sono: ID sito, Nome e ID padre.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
