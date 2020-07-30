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
source-git-commit: 7d2f4b45ac3e45c9b4fcaffa4b5c5324ff03e683
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 6%

---


# Limiti di utilizzo {#usage-limits}

 Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che è possibile creare per un account. Limiti si applicano a questi elementi, sia che siano creati nell&#39;interfaccia utente, sia che siano impostati in modo programmatico tramite [!DNL API] metodi. I limiti di utilizzo contribuiscono a proteggere  Audience Manager dai processi automatizzati che potrebbero tentare di compromettere la nostra interfaccia [!DNL API]o quella dell&#39;utente.

## Limiti di mappatura degli ID {#id-mapping-limits}

Nella tabella seguente sono elencati i limiti di mappatura [](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) degli ID per gli ID dispositivo. Quando un ID raggiunge uno dei limiti riportati di seguito,  Audience Manager aggiunge nuove mappature ID basate su una logica [!DNL FIFO] (primo in, primo out), rimuovendo la mappatura ID memorizzata più vecchia e aggiungendo la nuova mappatura. Per informazioni sugli ID supportati da  Audience Manager, consultate [Indice degli ID](../../reference/ids-in-aam.md) in  Audience Manager.

| Mappatura ID | Limite massimo |
|-----------|-------------- |
| Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) to Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) | 100 Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) to 1 Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) |
| ID cross-device ([DPUUID](../../reference/ids-in-aam.md)) per Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) | 10 ID cross-device ([DPUUID](../../reference/ids-in-aam.md)) a 1 ID pubblicitario dispositivo ([DAID](../../reference/ids-in-aam.md)), per ogni [DPID](../../reference/ids-in-aam.md) |
| Cookie/ID browser per cookie/ID browser | 1000 cookie/ID browser a 1 cookie/ID browser |

## Limiti elemento {#item-limits}

Le tabelle elencano i limiti correnti per tipo di articolo. Non puoi creare nuove caratteristiche, segmenti, destinazioni o [!UICONTROL Algorithmic Models] se raggiungi un limite specifico per uno di questi elementi. Se raggiungete un limite, dovete eliminare un elemento precedente prima di poterne creare uno nuovo.

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
| Attivo [!UICONTROL Look-Alike Models] | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| [!UICONTROL Look-Alike Models] dimensione massima del pubblico | 25,000,000.  Tenete presente che questo limite non può essere aumentato. Potete ridurre le dimensioni del pubblico selezionando meno origini dati per il modello o selezionando una finestra di look-back più breve. |
| Numero massimo di caratteristiche escluse per un [!UICONTROL Look-Alike Model] | 500. Consulta Esclusione [caratteristica in Modellazione](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)algoritmica. |
| Num [!UICONTROL Predictive Audiences Models] | 10 |
| Numero massimo di figure della linea di base per [!UICONTROL Predictive Audiences Models] | 50 |

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