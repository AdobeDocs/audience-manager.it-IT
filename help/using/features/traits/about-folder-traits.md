---
description: Le caratteristiche delle cartelle consentono di aggregare automaticamente le caratteristiche che risiedono nella stessa cartella e tutte le cartelle figlie in un segmento di targeting.
keywords: stima dimensioni segmento;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Caratteristiche delle cartelle Informazioni
solution: Audience Manager
title: Caratteristiche delle cartelle Informazioni
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 9fa5a558c839da89286b1abdf77e835a92747c87

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

## Folder Traits Realization - Recency and Frequency {#folder-traits-realization}

Il conteggio delle frequenze di una caratteristica della cartella è la somma delle realizzazioni delle caratteristiche presenti nella cartella e nelle relative cartelle figlie. L'illustrazione seguente mostra le caratteristiche A, B e C, presenti nella cartella Automobile. Considerate che ciascuna caratteristica presenta le seguenti realizzazioni:

* Caratteristica A: 5
* Trait B: 1
* Caratteristiche C: 1

In questo caso, il [!DNL Automobile Folder Trait] ha 7 realizzazioni.

![](assets/folder_traits_rollup_border.png)

## Report sulle caratteristiche delle cartelle {#folder-traits-reporting}

[!UICONTROL Folder traits] acquisite tutti gli utenti dalle caratteristiche nella struttura di cartelle sottostante. If you move a trait from a folder to another folder, the change propagates to our data collection servers just like a trait rule change. [](../../reference/system-components/components-data-collection.md) The reporting updates in the next reporting run to reflect this change across the reporting date ranges (1, 7, 14, 30, 60, 90). I vecchi numeri di reporting dei giorni precedenti non verranno modificati.

## Autorizzazioni RBAC (Role Based Access Controls) {#role-based-access-controls}

Per le aziende che utilizzano [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), gli utenti con le [!UICONTROL RBAC] autorizzazioni appropriate possono modificare l'origine dati associata al [!UICONTROL folder trait]. A user must belong to a group with either of the following:

* `READ` and  group permissions to a trait data source.`WRITE`
* `VIEW_ALL_TRAITS` and `EDIT_ALL_TRAITS` wild card permissions for trait data sources.

Learn how to assign  permissions in our administration documentation.[!UICONTROL RBAC][](../../features/administration/administration-overview.md#create-group)

## Limits and Other Considerations {#limits}

| Elemento | Descrizione |
|---|---|
| Trait type | [!UICONTROL Onboarded traits] and  contribute at most 1 realization to a 's frequency.[!UICONTROL algorithmic traits][!UICONTROL folder trait] |
| Moving traits between folders | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second . [!UICONTROL folder trait] Questo significa che se eliminate o spostate una caratteristica dalla cartella, gli utenti nella popolazione della caratteristica verranno separati dai segmenti utilizzando la caratteristica della cartella come espressione di segmento. <br> When mapping Adobe Analytics segments or report suites to your Experience Cloud organization, Audience Manager automatically creates new, corresponding, read-only segments and traits. You cannot edit or change the storage location of these traits from Audience Manager. Tuttavia, qualsiasi modifica eseguita sui segmenti Adobe Analytics o sulle suite di rapporti mappati viene visualizzata in Audience Manager. |
| Variabili di sistema | [!UICONTROL Folder traits] non può essere eseguito nelle chiamate di eventi utilizzando il `d_sid` parametro. |
| Generazione di rapporti   | [!UICONTROL Folder traits] sono caratteristiche create automaticamente e non vengono visualizzate in **[!UICONTROL Overlap Reports]**. |