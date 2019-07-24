---
description: Le caratteristiche della cartella consentono di aggregare automaticamente le caratteristiche residenti all'interno della stessa cartella e di tutte le cartelle secondarie in un segmento targabile.
keywords: stima della dimensione del segmento; sse
seo-description: Le caratteristiche della cartella consentono di aggregare automaticamente le caratteristiche residenti all'interno della stessa cartella e di tutte le cartelle secondarie in un segmento targabile.
seo-title: Caratteristiche della cartella
solution: Audience Manager
title: Caratteristiche della cartella
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Folder Traits: About {#folder-traits-about}

[!UICONTROL Folder traits] consente di aggregare automaticamente le caratteristiche residenti all'interno della stessa cartella e di tutte le cartelle secondarie in un segmento in grado di essere targabile.

## Benefits of Using Folder Traits {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. Questo consente di segmentare e indirizzare automaticamente gli utenti a diversi livelli di cartella. Ad esempio, supponiamo che tu abbia una struttura di cartelle come questa:

`*` Electronics (parent)

`*` Laptop (figlio)

`*` Marchi (inferiori)

[!UICONTROL Folder traits] qualifica tutti gli utenti in queste cartelle in una creazione automatica [!DNL Electronics][!UICONTROL Folder Trait] (in base al nome della cartella principale). Questo processo si ripete quando si sposta verso il basso la struttura del file. In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sono selezionabili nelle espressioni del segmento. Selecting a [!UICONTROL folder trait] is equivalent to selecting all the traits within that folder and its subfolders with an [!UICONTROL OR] grouping.

![](assets/folder-traits-compare-border.jpg)

## Folder Traits Realization - Recency and Frequency {#folder-traits-realization}

Il conteggio frequenza di una caratteristica di una cartella è la somma delle rappresentazioni delle caratteristiche nella sua cartella e nelle relative cartelle figlie. L'illustrazione seguente mostra le caratteristiche A, B e C, che risiedono nella cartella Automobile. Considerate che ciascuna caratteristica dispone delle seguenti realizzazioni:

* Caratteristica A: 5
* Caratteristica B: 1
* Caratteristica C: 1

In this case, the [!DNL ]Automobile [!UICONTROL Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] acquisire tutti gli utenti dalle caratteristiche nella struttura di cartelle sottostante. If you move a trait from a folder to another folder, the change propagates to our [data collection servers](../../reference/system-components/components-data-collection.md) just like a trait rule change. Gli aggiornamenti di reporting nel report successivo vengono eseguiti per riflettere questa modifica tra gli intervalli di date del rapporto (1, 7, 14, 30, 60, 90, lifetime). I vecchi numeri di reporting dei giorni precedenti non cambieranno.

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), your users with the appropriate [!UICONTROL RBAC] permissions are able to change the data source associated to the [!UICONTROL folder trait]. Un utente deve appartenere a un gruppo con uno dei seguenti elementi:

* `READ` e `WRITE` le autorizzazioni del gruppo a un'origine dati caratteristica.
* `VIEW_ALL_TRAITS` e `EDIT_ALL_TRAITS` autorizzazioni wild card per le origini dati delle caratteristiche.

Learn how to assign [!UICONTROL RBAC] permissions in our [administration documentation](../../features/administration/administration-overview.md#create-group).

## Limits and Other Considerations {#limits}

| Elemento | Descrizione |
|---|---|
| Tipo caratteristica | [!UICONTROL Onboarded traits] e [!UICONTROL algorithmic traits] contribuisce al massimo 1 realizzazione alla frequenza di una [!UICONTROL folder trait]. |
| Spostamento delle caratteristiche tra le cartelle | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second [!UICONTROL folder trait]. Questo significa che se eliminate o spostate una caratteristica dalla cartella, gli utenti nella popolazione della caratteristica saranno non segmentati dai segmenti utilizzando la caratteristica di cartella come espressione di segmento. <br> Quando mappatura di segmenti Adobe Analytics o suite di rapporti alla tua organizzazione Experience Cloud, Audience Manager crea automaticamente nuovi segmenti e caratteristiche di sola lettura. Non puoi modificare o modificare il percorso di archiviazione di queste caratteristiche da Audience Manager. Tuttavia, qualsiasi modifica eseguita sui segmenti mappati di Adobe Analytics o sulle suite di rapporti si riflette in Audience Manager. |
| Variabili di sistema | [!UICONTROL Folder traits] non può essere realizzata nelle chiamate dell'evento utilizzando il `d_sid` parametro. |
| Generazione di rapporti   | [!UICONTROL Folder traits] sono caratteristiche autocalcate e non sono visualizzate.**[!UICONTROL Overlap Reports]** |