---
description: Denomina il file di metadati Audience Optimization in base a queste specifiche.
seo-description: Denomina il file di metadati Audience Optimization in base a queste specifiche.
seo-title: Convenzioni di denominazione per i file di metadati
solution: Audience Manager
title: Convenzioni di denominazione per i file di metadati
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: File di registro
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 8%

---

# Convenzioni di denominazione per i file di metadati{#naming-conventions-for-metadata-files}

Denomina il file di metadati Audience Optimization in base a queste specifiche.

## Categorie di sintassi e ID {#syntax}

La sintassi seguente definisce la struttura di un nome file di metadati ben formato. Nota: *corsivo* indica un segnaposto variabile. Gli altri elementi sono costanti e non cambiano.

**Sintassi:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Non* utilizzare estensioni di file nei file di metadati (.txt o altro).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* Il componente centrale **0** è tecnicamente l’ID principale, che è un campo legacy. Il valore deve sempre essere impostato come **0**.
* L’ID figlio può avere un valore compreso tra 1 e 10, a seconda della dimensione. Vedi sotto:

## Dimensioni ID figlio {#child-dimension}

Nel nome del file di metadati, l’ID figlio è un identificatore che classifica il tipo di dati in un file e lo inserisce in una gerarchia. Puoi assegnare l’ID figlio nel nome del file con i seguenti ID categoria:

1. Campagna
1. Creativo
1. Posizionamento
1. Exchange
1. Sito
1. Inserzionista (se si utilizzano i codici di integrazione in una [origine dati](../../../features/manage-datasources.md#details))
1. Ordine di inserimento (IO)
1. Verticale (vale a dire, un settore o una categoria di attività specifica come &quot;computer&quot;, &quot;automobili&quot;, &quot;immobili&quot;, ecc.)
1. Tattico
1. Business unit o marchio

## Esempio {#example}

Per un file di metadati creativi, il nome del file potrebbe essere 20190115_0_2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
