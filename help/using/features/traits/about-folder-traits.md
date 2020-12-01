---
description: Le caratteristiche delle cartelle consentono di aggregare automaticamente le caratteristiche che risiedono nella stessa cartella e tutte le cartelle figlie in un segmento di targeting.
keywords: segment size estimator;sse
seo-description: Le caratteristiche delle cartelle consentono di aggregare automaticamente le caratteristiche che risiedono nella stessa cartella e tutte le cartelle figlie in un segmento di targeting.
seo-title: Caratteristiche delle cartelle Informazioni
solution: Audience Manager
title: Caratteristiche delle cartelle Informazioni
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---


# Informazioni sulle caratteristiche cartella {#folder-traits-about}

[!UICONTROL Folder traits] consente di aggregare automaticamente le caratteristiche che risiedono nella stessa cartella e tutte le cartelle figlie in un segmento di targeting.

## Vantaggi dell&#39;utilizzo delle caratteristiche delle cartelle {#benefits}

Un elemento [!UICONTROL folder trait] contiene tutte le caratteristiche presenti in una cartella principale e nelle relative cartelle figlie associate. Questo consente di segmentare e indirizzare automaticamente gli utenti a diversi livelli di cartella. Ad esempio, supponiamo che la struttura delle cartelle sia simile alla seguente:

`*` Elettronica (principale)

    `*` Laptop (figlio)

        `*` Marchi (nipote)

[!UICONTROL Folder traits] qualificate tutti gli utenti in queste cartelle in un file creato automaticamente  [!DNL Electronics] [!UICONTROL Folder Trait] (in base al nome della cartella principale). E questo processo si ripete mentre si sposta verso il basso la struttura del file. In questo caso, le caratteristiche delle cartelle acquisiscono tutti gli utenti nelle cartelle Laptop e Brands in un notebook creato automaticamente [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sono selezionabili nelle espressioni di segmento. La selezione di [!UICONTROL folder trait] equivale a selezionare tutte le caratteristiche all&#39;interno di tale cartella e delle relative sottocartelle con un raggruppamento [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Realizzazione caratteristiche cartella - Recency e frequenza {#folder-traits-realization}

Il conteggio delle frequenze di una caratteristica della cartella è la somma delle realizzazioni delle caratteristiche presenti nella cartella e nelle relative cartelle figlie. L&#39;illustrazione seguente mostra le caratteristiche A, B e C, presenti nella cartella Automobile. Considerate che ciascuna caratteristica presenta le seguenti realizzazioni:

* Caratteristica A: 5
* Caratteristiche B: 1
* Caratteristiche C: 1

In questo caso, il [!DNL Automobile Folder Trait] ha 7 realizzazioni.

![](assets/folder_traits_rollup_border.png)

## Report caratteristiche cartella {#folder-traits-reporting}

[!UICONTROL Folder traits] acquisite tutti gli utenti dalle caratteristiche nella struttura di cartelle sottostante. Se si sposta una caratteristica da una cartella a un&#39;altra, la modifica viene propagata ai nostri [server di raccolta dati](../../reference/system-components/components-data-collection.md) esattamente come una modifica della regola di caratteristica. Gli aggiornamenti dei report nel report successivo vengono eseguiti per riflettere questa modifica tra gli intervalli di date dei rapporti (1, 7, 14, 30, 60, 90). I vecchi numeri di reporting dei giorni precedenti non verranno modificati.

## Autorizzazioni per controlli di accesso basati sul ruolo (RBAC) {#role-based-access-controls}

Per le aziende che utilizzano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), gli utenti con le autorizzazioni [!UICONTROL RBAC] appropriate possono modificare l&#39;origine dati associata al [!UICONTROL folder trait]. Un utente deve appartenere a un gruppo con una delle seguenti caratteristiche:

* `READ` e autorizzazioni  `WRITE` di gruppo per un&#39;origine dati di caratteristiche.
* `VIEW_ALL_TRAITS` e autorizzazioni  `EDIT_ALL_TRAITS` con caratteri jolly per le origini dati caratteristiche.

Scopri come assegnare le autorizzazioni [!UICONTROL RBAC] nella nostra [documentazione di amministrazione](../../features/administration/administration-overview.md#create-group).

## Limiti e altre considerazioni {#limits}

| Elemento | Descrizione |
|---|---|
| Tipo di caratteristica | [!UICONTROL Onboarded traits] e  [!UICONTROL algorithmic traits] contribuire al massimo 1 realizzazione alla frequenza  [!UICONTROL folder trait]di un |
| Spostamento delle caratteristiche tra le cartelle | Se si sposta una caratteristica da una cartella a un&#39;altra, la caratteristica specificata verrà rimossa dalla prima caratteristica della cartella e classificata per la seconda [!UICONTROL folder trait]. Questo significa che se eliminate o spostate una caratteristica dalla cartella, gli utenti nella popolazione della caratteristica verranno separati dai segmenti utilizzando la caratteristica della cartella come espressione di segmento. <br> Quando si esegue la mappatura  segmenti Adobe Analytics o suite di rapporti alla propria organizzazione  Experience Cloud,  Audience Manager crea automaticamente nuovi segmenti e caratteristiche di sola lettura corrispondenti. Non è possibile modificare o modificare la posizione di memorizzazione di queste caratteristiche dal  Audience Manager. Tuttavia, qualsiasi modifica eseguita sui segmenti Adobe Analytics  mappati o sulle suite di rapporti si riflette in  Audience Manager. |
| Variabili di sistema | [!UICONTROL Folder traits] non può essere eseguito nelle chiamate di eventi utilizzando il  `d_sid` parametro. |
| Generazione di report | [!UICONTROL Folder traits] sono caratteristiche create automaticamente e non vengono visualizzate in  **[!UICONTROL Overlap Reports]**. |