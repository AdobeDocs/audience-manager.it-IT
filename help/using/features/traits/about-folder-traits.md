---
description: Le caratteristiche delle cartelle consentono di aggregare automaticamente le caratteristiche che risiedono nella stessa cartella e tutte le cartelle figlie in un segmento di targeting.
keywords: stima dimensioni segmento;sse
seo-description: Le caratteristiche delle cartelle consentono di aggregare automaticamente le caratteristiche che risiedono nella stessa cartella e tutte le cartelle figlie in un segmento di targeting.
seo-title: Caratteristiche delle cartelle Informazioni
solution: Audience Manager
title: Caratteristiche delle cartelle Informazioni
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# Caratteristiche cartella: Informazioni {#folder-traits-about}

[!UICONTROL Folder traits] consente di aggregare automaticamente le caratteristiche che risiedono nella stessa cartella e tutte le cartelle figlie in un segmento di targeting.

## Vantaggi dell’utilizzo delle caratteristiche delle cartelle {#benefits}

Una cartella [!UICONTROL folder trait] contiene tutte le caratteristiche presenti in una cartella principale e nelle relative cartelle figlie associate. Questo consente di segmentare e indirizzare automaticamente gli utenti a diversi livelli di cartella. Ad esempio, supponiamo che la struttura delle cartelle sia simile alla seguente:

`*` Elettronica (principale)

    `*` Laptop (bambino)

        `*` Marchi (nipote)

[!UICONTROL Folder traits] qualificate tutti gli utenti in queste cartelle in un file creato automaticamente [!DNL Electronics] (in base al nome della cartella principale) [!UICONTROL Folder Trait] . E questo processo si ripete mentre si sposta verso il basso la struttura del file. In questo caso, le caratteristiche delle cartelle acquisiscono tutti gli utenti nelle cartelle Laptop e Brands in un notebook creato automaticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sono selezionabili nelle espressioni di segmento. La selezione di una cartella [!UICONTROL folder trait] equivale a selezionare tutte le caratteristiche all’interno di tale cartella e delle relative sottocartelle con un [!UICONTROL OR] raggruppamento.

![](assets/folder-traits-compare-border.jpg)

## Realizzazione delle caratteristiche delle cartelle - Recency e frequenza {#folder-traits-realization}

Il conteggio delle frequenze di una caratteristica della cartella è la somma delle realizzazioni delle caratteristiche presenti nella cartella e nelle relative cartelle figlie. L'illustrazione seguente mostra le caratteristiche A, B e C, presenti nella cartella Automobile. Considerate che ciascuna caratteristica presenta le seguenti realizzazioni:

* Caratteristica A: 5
* Caratteristiche B: 1
* Caratteristiche C: 1

In questo caso, l' [!DNL ]Automobile [!UICONTROL Folder Trait] ha 7 realizzazioni.

![](assets/folder_traits_rollup_border.png)

## Report sulle caratteristiche delle cartelle {#folder-traits-reporting}

[!UICONTROL Folder traits] acquisite tutti gli utenti dalle caratteristiche nella struttura di cartelle sottostante. Se si sposta una caratteristica da una cartella a un'altra, la modifica viene propagata ai nostri server [di raccolta](../../reference/system-components/components-data-collection.md) dati esattamente come una modifica della regola delle caratteristiche. Gli aggiornamenti dei report nel report successivo vengono eseguiti per riflettere questa modifica tra gli intervalli di date dei rapporti (1, 7, 14, 30, 60, 90). I vecchi numeri di reporting dei giorni precedenti non verranno modificati.

## Autorizzazioni RBAC (Role Based Access Controls) {#role-based-access-controls}

Per le aziende che utilizzano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), gli utenti con le [!UICONTROL RBAC] autorizzazioni appropriate possono modificare l'origine dati associata al [!UICONTROL folder trait]. Un utente deve appartenere a un gruppo con una delle seguenti caratteristiche:

* `READ` e `WRITE` raggruppare le autorizzazioni per un'origine dati di caratteristiche.
* `VIEW_ALL_TRAITS` e le autorizzazioni per i `EDIT_ALL_TRAITS` caratteri jolly per le origini dati sulle caratteristiche.

Scopri come assegnare [!UICONTROL RBAC] le autorizzazioni nella documentazione [](../../features/administration/administration-overview.md#create-group)di amministrazione.

## Limiti e altre considerazioni {#limits}

| Elemento | Descrizione |
|---|---|
| Tipo di caratteristica | [!UICONTROL Onboarded traits] e [!UICONTROL algorithmic traits] contribuire al massimo 1 realizzazione alla frequenza [!UICONTROL folder trait]di un |
| Spostamento delle caratteristiche tra le cartelle | Se si sposta una caratteristica da una cartella a un’altra, la caratteristica specificata verrà rimossa dalla caratteristica della prima cartella e classificata per la seconda [!UICONTROL folder trait]. Questo significa che se eliminate o spostate una caratteristica dalla cartella, gli utenti nella popolazione della caratteristica verranno separati dai segmenti utilizzando la caratteristica della cartella come espressione di segmento. <br> Quando mappate segmenti o suite di rapporti di Adobe Analytics alla vostra organizzazione Experience Cloud, Audience Manager crea automaticamente nuovi segmenti e caratteristiche di sola lettura corrispondenti. Da Audience Manager non potete modificare o modificare la posizione di archiviazione di queste caratteristiche. Tuttavia, qualsiasi modifica eseguita sui segmenti Adobe Analytics o sulle suite di rapporti mappati viene visualizzata in Audience Manager. |
| Variabili di sistema | [!UICONTROL Folder traits] non può essere eseguito nelle chiamate di eventi utilizzando il `d_sid` parametro. |
| Generazione di rapporti   | [!UICONTROL Folder traits] sono caratteristiche create automaticamente e non vengono visualizzate in **[!UICONTROL Overlap Reports]**. |