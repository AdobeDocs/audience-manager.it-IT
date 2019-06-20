---
description: Denominate il file di metadati Ottimizzazione pubblico in base alle seguenti specifiche.
seo-description: Denominate il file di metadati Ottimizzazione pubblico in base alle seguenti specifiche.
seo-title: Convenzioni di denominazione per i file di metadati
solution: Audience Manager
title: Convenzioni di denominazione per i file di metadati
uuid: cab 55 b 2 a -2 e 54-45 f 6-aeea -3735 b 911 f 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Convenzioni di denominazione per i file di metadati{#naming-conventions-for-metadata-files}

Denominate il file di metadati Ottimizzazione pubblico in base alle seguenti specifiche.

## Categorie sintassi e ID {#syntax}

La sintassi seguente definisce la struttura di un nome file di metadati ben formattato. Nota, *il corsivo* indica un segnaposto variabile. Gli altri elementi sono costanti e non cambiano.

**Sintassi:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Non* utilizzate estensioni dei file nei file di metadati (.txt o altro).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* Il componente centrale **0** è tecnicamente l&#39;ID principale, che è un campo legacy. Il valore deve essere sempre impostato su **0**.
* L&#39;ID secondario può avere un valore compreso tra 1 e 10, a seconda della dimensione. Vedi di seguito:

## Dimensioni ID secondari {#child-dimension}

Nel nome del file di metadati, l&#39;ID secondario è un identificatore che classifica il tipo di dati in un file e lo inserisce in una gerarchia. Puoi assegnare un tag all&#39;ID secondario nel nome file con i seguenti ID categoria:

1. Campagna
1. Creative
1. Posizionamento
1. Exchange
1. Sito
1. Inserzionista (se utilizzate i codici di integrazione in un&#39;origine [dati](../../../features/manage-datasources.md#details))
1. Ordine di inserimento (IO)
1. Verticale (ovvero, un settore o categoria aziendale specifica come «computer», «auto», «beni reali», ecc.)
1. Tactic
1. Unità aziendale o marchio

## Esempio {#example}

Per un file di metadati Creative, il nome file potrebbe essere 20190115_ 0_ 2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
