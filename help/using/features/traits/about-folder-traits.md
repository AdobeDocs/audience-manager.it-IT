---
description: Le caratteristiche della cartella consentono di aggregare automaticamente in un segmento di destinazione le caratteristiche che si trovano all’interno della stessa cartella e tutte le cartelle secondarie.
keywords: stimatore dimensioni segmento;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Informazioni sulle caratteristiche della cartella
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# Informazioni sulle caratteristiche cartella {#folder-traits-about}

[!UICONTROL Folder traits] consente di aggregare automaticamente in un segmento di destinazione le caratteristiche che risiedono nella stessa cartella e tutte le cartelle secondarie.

## Vantaggi dell’utilizzo delle caratteristiche della cartella {#benefits}

A [!UICONTROL folder trait] contiene tutte le caratteristiche di una cartella principale e delle relative cartelle secondarie associate. Questo consente di segmentare e indirizzare automaticamente gli utenti a diversi livelli di cartella. Ad esempio, supponiamo che tu abbia una struttura di cartelle come questa:

`*` Elettronica (padre)

    `*` Notebook (secondari)

        `*` Marche (nipote)

[!UICONTROL Folder traits] qualifica tutti gli utenti in queste cartelle in un [!DNL Electronics] [!UICONTROL Folder Trait] (in base al nome della cartella principale). Questo processo si ripete man mano che ci si sposta verso il basso nella struttura del file. In questo caso, le caratteristiche della cartella catturano tutti gli utenti nelle cartelle dei notebook e dei marchi in un notebook creato automaticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sono selezionabili nelle espressioni di segmento. Selezione di un [!UICONTROL folder trait] equivale a selezionare tutte le caratteristiche all’interno di quella cartella e delle relative sottocartelle con un tag [!UICONTROL OR] raggruppamento.

![](assets/folder-traits-compare-border.jpg)

## Realizzazione delle caratteristiche della cartella - Attualità e frequenza {#folder-traits-realization}

Il conteggio della frequenza di una caratteristica della cartella è la somma delle realizzazioni delle caratteristiche nella sua cartella e nelle sue cartelle secondarie. L’illustrazione seguente mostra le caratteristiche A, B e C, presenti nella cartella Automobile. Considera che ciascuna delle caratteristiche ha le seguenti realizzazioni:

* Caratteristica A: 5
* Caratteristica B: 1
* Caratteristica C: 1

In questo caso, il [!DNL Automobile Folder Trait] ha 7 realizzazioni.

![](assets/folder_traits_rollup_border.png)

## Generazione rapporti sulle caratteristiche delle cartelle {#folder-traits-reporting}

[!UICONTROL Folder traits] acquisire tutti gli utenti dalle caratteristiche nella struttura di cartelle sottostante. Se sposti una caratteristica da una cartella a un’altra, la modifica si propaga al [server di raccolta dati](../../reference/system-components/components-data-collection.md) proprio come cambia una regola delle caratteristiche. La generazione rapporti viene aggiornata nella successiva esecuzione rapporti per riflettere tale modifica negli intervalli di date di reporting (1, 7, 14, 30, 60, 90). I numeri dei rapporti precedenti dei giorni precedenti non cambieranno.

## Autorizzazioni RBAC (Role-Based Access Controls) {#role-based-access-controls}

Per le aziende che utilizzano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), i tuoi utenti con il [!UICONTROL RBAC] Le autorizzazioni di sono in grado di modificare l&#39;origine dati associata al [!UICONTROL folder trait]. Un utente deve appartenere a un gruppo con una delle seguenti caratteristiche:

* `READ` e `WRITE` raggruppare le autorizzazioni per un&#39;origine dati delle caratteristiche.
* `VIEW_ALL_TRAITS` e `EDIT_ALL_TRAITS` autorizzazioni wild card per le origini dati delle caratteristiche.

Scopri come assegnare [!UICONTROL RBAC] autorizzazioni in [documentazione di amministrazione](../../features/administration/administration-overview.md#create-group).

## Limiti e altre considerazioni {#limits}

| Elemento | Descrizione |
|---|---|
| Tipo di caratteristica | [!UICONTROL Onboarded traits] e [!UICONTROL algorithmic traits] contribuire al massimo 1 realizzazione a un [!UICONTROL folder trait]Frequenza di. |
| Spostamento di caratteristiche tra cartelle | Lo spostamento di una caratteristica da una cartella a un’altra squalifica tale caratteristica dalla prima caratteristica della cartella e la qualifica per la seconda [!UICONTROL folder trait]. Ciò significa che se elimini o sposti una caratteristica dalla cartella, gli utenti nella popolazione della caratteristica verranno rimossi dai segmenti utilizzando la caratteristica cartella come espressione del segmento. <br> Quando mappi segmenti o suite di rapporti di Adobe Analytics nell’organizzazione di Experienci Cloud, Audience Manager crea automaticamente segmenti e caratteristiche nuovi e corrispondenti di sola lettura. Non puoi modificare o modificare la posizione di archiviazione di queste caratteristiche da Audience Manager. Tuttavia, qualsiasi modifica eseguita sui segmenti o sulle suite di rapporti di Adobe Analytics mappati si riflette in Audience Manager. |
| Variabili di sistema | [!UICONTROL Folder traits] non può essere realizzato nelle chiamate evento che utilizzano `d_sid` parametro. |
| Generazione di report | [!UICONTROL Folder traits] sono caratteristiche calcolate automaticamente e non vengono visualizzate in **[!UICONTROL Overlap Reports]**. |
