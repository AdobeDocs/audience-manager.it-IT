---
description: ' Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che è possibile creare per un account. Limiti si applicano a questi elementi, sia che siano creati nell''interfaccia utente, sia che siano stati impostati in modo programmatico tramite i metodi API. I limiti di utilizzo contribuiscono a proteggere  Audience Manager dai processi automatizzati che potrebbero tentare di compromettere le nostre API o interfaccia utente.'
seo-description: ' Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che è possibile creare per un account. Limiti si applicano a questi elementi, sia che siano creati nell''interfaccia utente, sia che siano stati impostati in modo programmatico tramite i metodi API. I limiti di utilizzo contribuiscono a proteggere  Audience Manager dai processi automatizzati che potrebbero tentare di compromettere le nostre API o interfaccia utente.'
seo-title: Limiti di utilizzo
solution: Audience Manager
title: Limiti di utilizzo
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 6%

---


# Limiti di utilizzo {#usage-limits}

Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through [!DNL API] methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our [!DNL API]s or user interface.

## Limiti di mappatura degli ID {#id-mapping-limits}

The table below lists the [ID mapping](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limits for device IDs. Once an ID reaches any of the limits below, Audience Manager adds new ID mappings based on a [!DNL FIFO] (first in, first out) logic, by removing the oldest stored ID mapping, and adding the new one. Refer to [Index of IDs](../../reference/ids-in-aam.md) in Audience Manager for details on the IDs supported by Audience Manager.

| ID Mapping | Limite massimo |
|-----------|-------------- |
| Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) to Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) | 100 Device Advertising IDs ([DAID](../../reference/ids-in-aam.md)) to 1 Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) |
| Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) to Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) | 10 Cross-device IDs ([DPUUID](../../reference/ids-in-aam.md)) to 1 Device Advertising ID ([DAID](../../reference/ids-in-aam.md)), per each [DPID](../../reference/ids-in-aam.md) |
| Cookie/browser ID to cookie/browser ID | 1000 cookie/browser  IDs to 1 cookie/browser ID |

## Item Limits {#item-limits}

The tables list the current limits by item type. You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. Se raggiungete un limite, dovete eliminare un elemento precedente prima di poterne creare uno nuovo.

### Limiti di caratteristiche

| Tipo di caratteristica | Limite massimo |
| -------------------------- | ------------------------------------- |
| Caratteristiche totali | 100,000 |
| Totale qualifiche caratteristiche | 150,000. Per ulteriori informazioni sulla qualificazione delle caratteristiche, vedere Limite di qualifica delle caratteristiche in Riferimento [alle qualifiche](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)delle caratteristiche. |
| Algoritmo | 50 |
| Basato su regola | 100,000 |
| Onboard | 100,000 |
| Caratteristiche delle cartelle | 2,000 |

### Limiti segmento

| Tipo segmento | Limite massimo |
| -------------- | ------------- |
| Segmenti totali | 20,000 |

### Limiti di destinazione

| Tipo di destinazione | Limite massimo |
| ------------------ | ------------- |
| Totale destinazioni | 1,000 |
| Cookie | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limiti dei modelli algoritmici

| Elemento | Limite massimo |
| -------- | ----- |
| Modelli algoritmici attivi | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| Algorithmic Models dimensione massima del pubblico | 25,000,000.  Tenete presente che questo limite non può essere aumentato. Potete ridurre le dimensioni del pubblico selezionando meno origini dati per il modello o selezionando una finestra di look-back più breve. |
| Numero massimo di caratteristiche escluse per un modello | 500. Consulta Esclusione [caratteristica in Modellazione](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)algoritmica. |

### Limiti cartella

| Elemento | Limite massimo |
| ------------- | ------------------ |
| Cartelle caratteristiche | 2,000.  La struttura delle cartelle può avere una profondità massima di 5 livelli. |

### Limiti dei segnali derivati

| Elemento | Limite massimo |
| --------------- | ------------- |
| Segnali derivati | 50,000. |

### Limite account utente società

| Elemento | Limite massimo |
| ----------- | ------------- |
| Numero massimo di account utente per una società | 1,000. |

## Utilizzo monitor {#monitor-usage}

Potete visualizzare l&#39;utilizzo e i limiti dell&#39;account andando **[!UICONTROL Administration > Limits]**. L&#39;accesso richiede autorizzazioni dell&#39;amministratore.

![immagine con limiti di utilizzo](assets/usage-limits.png)

## Aumenta limiti articolo {#increase-item-limits}

I limiti predefiniti elencati qui dovrebbero fornire capacità sufficiente per le vostre esigenze aziendali. Se la vostra organizzazione raggiunge regolarmente questi limiti, contattate il rappresentante commerciale di riferimento per discutere di un aumento.