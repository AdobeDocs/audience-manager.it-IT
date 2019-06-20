---
description: Le caratteristiche della cartella consentono di aggregare automaticamente le caratteristiche residenti all'interno della stessa cartella e di tutte le cartelle secondarie in un segmento targabile.
keywords: stima della dimensione del segmento; sse
seo-description: Le caratteristiche della cartella consentono di aggregare automaticamente le caratteristiche residenti all'interno della stessa cartella e di tutte le cartelle secondarie in un segmento targabile.
seo-title: Caratteristiche della cartella
solution: Audience Manager
title: Caratteristiche della cartella
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Caratteristiche cartella: Informazioni {#folder-traits-about}

[!UICONTROL Folder traits] consente di aggregare automaticamente le caratteristiche residenti all&#39;interno della stessa cartella e di tutte le cartelle secondarie in un segmento in grado di essere targabile.

## Vantaggi delle caratteristiche della cartella {#benefits}

A [!UICONTROL folder trait] contiene tutte le caratteristiche in una cartella principale e nelle relative cartelle secondarie associate. Questo consente di segmentare e indirizzare automaticamente gli utenti a diversi livelli di cartella. Ad esempio, supponiamo che tu abbia una struttura di cartelle come questa:

`*` Electronics (parent)

`*` Laptop (figlio)

`*` Marchi (inferiori)

[!UICONTROL Folder traits] qualifica tutti gli utenti in queste cartelle in una creazione automatica [!DNL Electronics][!UICONTROL Folder Trait] (in base al nome della cartella principale). Questo processo si ripete quando si sposta verso il basso la struttura del file. In questo caso, le caratteristiche della cartella acquisiscono tutti gli utenti nelle cartelle Laptop e Marchi in un laptop [!UICONTROL Folder Trait]automaticamente creato.

[!UICONTROL Folder traits] sono selezionabili nelle espressioni del segmento. Selezionando un [!UICONTROL folder trait] equivale a selezionare tutte le caratteristiche all&#39;interno della cartella e le relative sottocartelle con un [!UICONTROL OR] raggruppamento.

![](assets/folder-traits-compare-border.jpg)

## Rappresentazione delle caratteristiche della cartella - Recency e frequenza {#folder-traits-realization}

Il conteggio frequenza di una caratteristica di una cartella è la somma delle rappresentazioni delle caratteristiche nella sua cartella e nelle relative cartelle figlie. L&#39;illustrazione seguente mostra le caratteristiche A, B e C, che risiedono nella cartella Automobile. Considerate che ciascuna caratteristica dispone delle seguenti realizzazioni:

* Caratteristica A: 5
* Caratteristica B: 1
* Caratteristica C: 1

In questo caso, l&#39; [!DNL ]automobile [!UICONTROL Folder Trait] ha 7 realizzazioni.

![](assets/folder_traits_rollup_border.png)

## Generazione di rapporti sulle caratteristiche {#folder-traits-reporting}

[!UICONTROL Folder traits] acquisire tutti gli utenti dalle caratteristiche nella struttura di cartelle sottostante. Se spostate una caratteristica da una cartella a un&#39;altra cartella, la modifica viene propagata ai [nostri server](../../reference/system-components/components-data-collection.md) di raccolta dati come una modifica regola caratteristica. Gli aggiornamenti di reporting nel report successivo vengono eseguiti per riflettere questa modifica tra gli intervalli di date del rapporto (1, 7, 14, 30, 60, 90, lifetime). I vecchi numeri di reporting dei giorni precedenti non cambieranno.

## Autorizzazioni RBAC (basate su ruoli) autorizzate {#role-based-access-controls}

Per le aziende che usano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), gli utenti con le autorizzazioni appropriate [!UICONTROL RBAC] sono in grado di modificare l&#39;origine dati associata all &#39; [!UICONTROL folder trait]. Un utente deve appartenere a un gruppo con uno dei seguenti elementi:

* `READ` e `WRITE` le autorizzazioni del gruppo a un&#39;origine dati caratteristica.
* `VIEW_ALL_TRAITS` e `EDIT_ALL_TRAITS` autorizzazioni wild card per le origini dati delle caratteristiche.

Scopri come assegnare [!UICONTROL RBAC] le autorizzazioni nella nostra documentazione [sull&#39;amministrazione](../../features/administration/administration-overview.md#create-group).

## Limiti e altre considerazioni {#limits}

| Elemento | Descrizione |
|---|---|
| Tipo caratteristica | [!UICONTROL Onboarded traits] e [!UICONTROL algorithmic traits] contribuisce al massimo 1 realizzazione alla frequenza di una [!UICONTROL folder trait]. |
| Spostamento delle caratteristiche tra le cartelle | Se si sposta una caratteristica da una cartella all&#39;altra, la caratteristica viene ignorata dalla prima caratteristica della cartella e la si qualifica per la seconda [!UICONTROL folder trait]. Questo significa che se eliminate o spostate una caratteristica dalla cartella, gli utenti nella popolazione della caratteristica saranno non segmentati dai segmenti utilizzando la caratteristica di cartella come espressione di segmento. |
| Variabili di sistema | [!UICONTROL Folder traits] non può essere realizzata nelle chiamate dell&#39;evento utilizzando il `d_sid` parametro. |
| Generazione di rapporti   | [!UICONTROL Folder traits] are autocalculated traits and do not appear in **[!UICONTROL Overlap Reports]**. |