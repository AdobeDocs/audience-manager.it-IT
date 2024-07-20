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
source-wordcount: '533'
ht-degree: 0%

---

# Caratteristiche cartella: informazioni {#folder-traits-about}

[!UICONTROL Folder traits] ti consente di aggregare automaticamente in un segmento di destinazione le caratteristiche che risiedono nella stessa cartella e tutte le cartelle secondarie.

## Vantaggi dell’utilizzo delle caratteristiche della cartella {#benefits}

Un [!UICONTROL folder trait] contiene tutte le caratteristiche di una cartella padre e delle relative cartelle figlio associate. Questo consente di segmentare e indirizzare automaticamente gli utenti a diversi livelli di cartella. Ad esempio, supponiamo che tu abbia una struttura di cartelle come questa:

Elettronica `*` (padre)

    `*` notebook (figlio)

        `*` marchi (nipote)

[!UICONTROL Folder traits] qualifica tutti gli utenti di queste cartelle in un [!DNL Electronics] [!UICONTROL Folder Trait] creato automaticamente (in base al nome della cartella principale). Questo processo si ripete man mano che ci si sposta verso il basso nella struttura del file. In questo caso, le caratteristiche della cartella acquisiscono tutti gli utenti nelle cartelle dei notebook e dei marchi in un notebook creato automaticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sono selezionabili nelle espressioni di segmento. La selezione di un [!UICONTROL folder trait] equivale alla selezione di tutte le caratteristiche all&#39;interno della cartella e delle relative sottocartelle con un raggruppamento [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Realizzazione delle caratteristiche della cartella - Attualità e frequenza {#folder-traits-realization}

Il conteggio della frequenza di una caratteristica della cartella è la somma delle realizzazioni delle caratteristiche nella sua cartella e nelle sue cartelle secondarie. L’illustrazione seguente mostra le caratteristiche A, B e C, presenti nella cartella Automobile. Considera che ciascuna delle caratteristiche ha le seguenti realizzazioni:

* Caratteristica A: 5
* Caratteristica B: 1
* Caratteristica C: 1

In questo caso, [!DNL Automobile Folder Trait] ha 7 realizzazioni.

![](assets/folder_traits_rollup_border.png)

## Generazione rapporti sulle caratteristiche delle cartelle {#folder-traits-reporting}

[!UICONTROL Folder traits] acquisisce tutti gli utenti dalle caratteristiche nella struttura di cartelle al di sotto di essi. Se sposti una caratteristica da una cartella a un&#39;altra cartella, la modifica si propaga ai nostri [server di raccolta dati](../../reference/system-components/components-data-collection.md) proprio come una modifica della regola della caratteristica. La generazione rapporti viene aggiornata nella successiva esecuzione rapporti per riflettere tale modifica negli intervalli di date di reporting (1, 7, 14, 30, 60, 90). I numeri dei rapporti precedenti dei giorni precedenti non cambieranno.

## Autorizzazioni RBAC (Role-Based Access Controls) {#role-based-access-controls}

Per le aziende che utilizzano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), gli utenti con le autorizzazioni [!UICONTROL RBAC] appropriate possono modificare l&#39;origine dati associata a [!UICONTROL folder trait]. Un utente deve appartenere a un gruppo con una delle seguenti caratteristiche:

* Autorizzazioni di gruppo `READ` e `WRITE` per un&#39;origine dati delle caratteristiche.
* Autorizzazioni con caratteri jolly `VIEW_ALL_TRAITS` e `EDIT_ALL_TRAITS` per origini dati caratteristiche.

Scopri come assegnare le autorizzazioni [!UICONTROL RBAC] nella [documentazione di amministrazione](../../features/administration/administration-overview.md#create-group).

## Limiti e altre considerazioni {#limits}

| Elemento | Descrizione |
|---|---|
| Tipo di caratteristica | [!UICONTROL Onboarded traits] e [!UICONTROL algorithmic traits] contribuiscono al massimo 1 realizzazione alla frequenza di [!UICONTROL folder trait]. |
| Spostamento di caratteristiche tra cartelle | Se si sposta una caratteristica da una cartella a un&#39;altra, tale caratteristica non sarà più valida per la prima caratteristica della cartella e sarà idonea per la seconda [!UICONTROL folder trait]. Ciò significa che se elimini o sposti una caratteristica dalla cartella, gli utenti nella popolazione della caratteristica verranno rimossi dai segmenti utilizzando la caratteristica cartella come espressione del segmento. <br> Quando si mappano segmenti o suite di rapporti di Adobe Analytics nell&#39;organizzazione Experience Cloud, Audience Manager crea automaticamente segmenti e caratteristiche nuovi e corrispondenti di sola lettura. Non puoi modificare o modificare la posizione di archiviazione di queste caratteristiche da Audience Manager. Tuttavia, qualsiasi modifica eseguita sui segmenti o sulle suite di rapporti di Adobe Analytics mappati si riflette in Audience Manager. |
| Variabili di sistema | Impossibile realizzare [!UICONTROL Folder traits] nelle chiamate evento che utilizzano il parametro `d_sid`. |
| Generazione di rapporti   | [!UICONTROL Folder traits] sono caratteristiche calcolate automaticamente e non vengono visualizzate in **[!UICONTROL Overlap Reports]**. |
