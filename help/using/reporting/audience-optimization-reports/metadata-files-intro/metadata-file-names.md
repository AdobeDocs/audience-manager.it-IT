---
description: Denomina il file di metadati di Audience Optimization in base a queste specifiche.
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: Convenzioni di denominazione per i file di metadati
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 1%

---

# Convenzioni di denominazione per i file di metadati{#naming-conventions-for-metadata-files}

Denomina il file di metadati di Audience Optimization in base a queste specifiche.

## Sintassi e categorie ID {#syntax}

La sintassi seguente definisce la struttura di un nome di file di metadati ben formato. Nota: *corsivo* indica un segnaposto variabile. Gli altri elementi sono costanti e non cambiano.

**Sintassi:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Non* utilizzare estensioni di file nei file di metadati (.txt o altro).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* Il componente intermedio **0** è tecnicamente l&#39;ID padre, che è un campo legacy. Il valore deve essere sempre impostato come **0**.
* L’ID figlio può avere un valore compreso tra 1 e 10, a seconda della dimensione. Vedi di seguito:

## Dimensioni ID figlio {#child-dimension}

Nel nome del file di metadati, l’ID figlio è un identificatore che classifica il tipo di dati in un file e lo inserisce in una gerarchia. Puoi assegnare all’ID figlio nel nome file i seguenti ID categoria:

1. Campagna
1. Creative
1. Posizionamento
1. Exchange
1. Sito
1. Inserzionista (se si utilizzano codici di integrazione in una [origine dati](../../../features/manage-datasources.md#details))
1. Ordine di inserimento (IO)
1. Verticale (ovvero, un settore specifico o una categoria aziendale come &quot;computer&quot;, &quot;automobili&quot;, &quot;beni immobili&quot;, ecc.)
1. Tattico
1. Business unit o marchio

## Esempio {#example}

Per un file di metadati di Creative, il nome del file potrebbe essere 20190115_0_2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
