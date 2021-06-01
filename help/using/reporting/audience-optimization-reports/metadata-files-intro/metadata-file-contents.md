---
description: Formatta il contenuto del file di metadati di Audience Optimization in base a queste specifiche.
seo-description: Formatta il contenuto del file di metadati di Audience Optimization in base a queste specifiche.
seo-title: Formato del contenuto dei file di metadati
solution: Audience Manager
title: Formato del contenuto dei file di metadati
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: File di registro
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 5%

---

# Formato del contenuto dei file di metadati{#content-format-for-metadata-files}

Formatta il contenuto del file di metadati di Audience Optimization in base a queste specifiche.

## Sintassi {#syntax}

La sintassi seguente definisce la struttura del contenuto ben formato in un file di metadati. Nota: *corsivo* indica un segnaposto variabile.

**Sintassi:**  *ID contenuto*  |  *nome*  |  *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

La terza colonna **-1** è tecnicamente l’ID principale, che è un campo legacy. Il valore deve sempre essere impostato come **-1**.

>[!NOTE]
>
>È necessario un file di metadati per dimensione, pertanto sono previsti più file di metadati nel bucket. Le dimensioni sono elencate nell’articolo [Convenzioni di denominazione per file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Voci di file separate con ^a (control-A o ASCII 001)**

Utilizza `^a` (control-A o ASCII 001) per separare i contenuti nei file di metadati. Poiché si tratta di caratteri non stampabili, l&#39;esempio di sintassi riportato sopra mostra una barra verticale &quot;|&quot; solo a scopo di visualizzazione.

Se necessario, puoi scaricare il file di esempio - [20181105_0_1](assets/20181105_0_1.zip). Decomprimi e modifica nell’editor desiderato e regola in base al contenuto effettivo dei metadati, in quanto contiene già il delimitatore richiesto.

>[!IMPORTANT]
>
>Non aggiungere righe di intestazione ai file di metadati.

## Esempi {#examples}

Diamo un&#39;occhiata a come strutturare il contenuto in un file di metadati. Parte di questa struttura dipende dalla dimensione. Le dimensioni sono elencate nell’articolo [Convenzioni di denominazione per file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

In questo esempio, il titolo del file è 20180921_0_1 e le tre colonne nel file sono: ID campagna, nome e ID padre.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creativo**

In questo esempio, il titolo del file è 20180827_0_2 e le tre colonne nel file sono: ID creativo, nome e ID padre.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Sito**

In questo esempio, il titolo del file è 20180921_0_5 e le tre colonne nel file sono: ID sito, nome e ID padre.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
