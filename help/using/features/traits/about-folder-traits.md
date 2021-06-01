---
description: Le caratteristiche della cartella consentono di aggregare automaticamente le caratteristiche che si trovano all’interno della stessa cartella e tutte le cartelle secondarie in un segmento di destinazione.
keywords: stima dimensioni segmento;sse
seo-description: Le caratteristiche della cartella consentono di aggregare automaticamente le caratteristiche che si trovano all’interno della stessa cartella e tutte le cartelle secondarie in un segmento di destinazione.
seo-title: Caratteristiche delle cartelle
solution: Audience Manager
title: Caratteristiche delle cartelle
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: 'Caratteristiche '
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# Informazioni sulle caratteristiche cartella {#folder-traits-about}

[!UICONTROL Folder traits] consente di aggregare automaticamente le caratteristiche che risiedono all’interno della stessa cartella e tutte le cartelle secondarie in un segmento di destinazione.

## Vantaggi dell’utilizzo delle caratteristiche delle cartelle {#benefits}

Un [!UICONTROL folder trait] contiene tutte le caratteristiche in una cartella principale e le relative cartelle secondarie associate. Questo consente di segmentare e indirizzare automaticamente gli utenti a diversi livelli di cartella. Ad esempio, supponiamo che tu disponga di una struttura di cartelle come questa:

`*` Elettronica (genitore)

    `*` Laptop (bambini)

        `*` Marchi (nipote)

[!UICONTROL Folder traits] qualifica tutti gli utenti di queste cartelle in una creazione automatica  [!DNL Electronics] [!UICONTROL Folder Trait] (in base al nome della cartella principale). E questo processo si ripete mentre ci si sposta verso il basso nella struttura del file. In questo caso, le caratteristiche della cartella acquisiscono tutti gli utenti nelle cartelle Laptop e Brands in un Laptop creato automaticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sono selezionabili nelle espressioni di segmento. La selezione di un elemento [!UICONTROL folder trait] equivale alla selezione di tutte le caratteristiche all’interno della cartella e delle relative sottocartelle con un raggruppamento [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Realizzazione delle caratteristiche della cartella - Attualità e frequenza {#folder-traits-realization}

Il conteggio di frequenza di una caratteristica della cartella è la somma delle realizzazioni delle caratteristiche nella cartella e nelle cartelle secondarie. L’illustrazione seguente mostra le caratteristiche A, B e C, presenti nella cartella Automobile. Considera che ciascuna delle caratteristiche presenta le seguenti realizzazioni:

* Caratteristica A: 5
* Caratteristica B: 1
* Tratto C: 1

In questo caso, il [!DNL Automobile Folder Trait] ha 7 realizzazioni.

![](assets/folder_traits_rollup_border.png)

## Reporting delle caratteristiche delle cartelle {#folder-traits-reporting}

[!UICONTROL Folder traits] acquisire tutti gli utenti dalle caratteristiche nella struttura delle cartelle sottostante. Se sposti una caratteristica da una cartella a un&#39;altra, la modifica si propaga ai nostri [server di raccolta dati](../../reference/system-components/components-data-collection.md) proprio come una modifica della regola delle caratteristiche. Gli aggiornamenti dei rapporti nel reporting successivo vengono eseguiti per riflettere questa modifica tra gli intervalli di date dei rapporti (1, 7, 14, 30, 60, 90). I vecchi numeri dei rapporti dei giorni precedenti non cambieranno.

## Autorizzazioni per controlli di accesso basati sul ruolo {#role-based-access-controls}

Per le aziende che utilizzano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), gli utenti con le autorizzazioni [!UICONTROL RBAC] appropriate possono modificare l&#39;origine dati associata a [!UICONTROL folder trait]. Un utente deve appartenere a un gruppo con una delle seguenti caratteristiche:

* `READ` e  `WRITE` raggruppare le autorizzazioni per un’origine dati delle caratteristiche.
* `VIEW_ALL_TRAITS` e le autorizzazioni dei  `EDIT_ALL_TRAITS` caratteri jolly per le origini dati dei tratti.

Scopri come assegnare le autorizzazioni [!UICONTROL RBAC] nella nostra [documentazione di amministrazione](../../features/administration/administration-overview.md#create-group).

## Limiti e altre considerazioni {#limits}

| Elemento | Descrizione |
|---|---|
| Tipo di caratteristica | [!UICONTROL Onboarded traits] e  [!UICONTROL algorithmic traits] contribuire al massimo 1 realizzazione alla frequenza  [!UICONTROL folder trait]di una. |
| Spostamento delle caratteristiche tra le cartelle | Lo spostamento di una caratteristica da una cartella a un’altra comporta la rimozione della caratteristica dalla prima cartella e la qualifica per la seconda [!UICONTROL folder trait]. Ciò significa che se elimini o sposti una caratteristica dalla cartella, gli utenti nella popolazione della caratteristica verranno rimossi dai segmenti utilizzando la caratteristica della cartella come espressione di segmento. <br> Quando mappi segmenti o suite di rapporti di Adobe Analytics nell’organizzazione Experience Cloud, in Audience Manager vengono creati automaticamente nuovi segmenti e caratteristiche di sola lettura corrispondenti. Non puoi modificare o modificare il percorso di archiviazione di queste caratteristiche a partire da Audience Manager. Tuttavia, qualsiasi modifica eseguita sui segmenti Adobe Analytics o sulle suite di rapporti mappati viene visualizzata in Audience Manager. |
| Variabili di sistema | [!UICONTROL Folder traits] non può essere realizzato nelle chiamate evento utilizzando il  `d_sid` parametro . |
| Generazione di report | [!UICONTROL Folder traits] sono caratteristiche autocalcolizzate e non vengono visualizzate in  **[!UICONTROL Overlap Reports]**. |
