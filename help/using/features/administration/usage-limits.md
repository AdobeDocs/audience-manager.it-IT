---
description: Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che è possibile creare per un account. I limiti si applicano a questi elementi, creati nell’interfaccia utente o a livello di programmazione tramite i metodi API. I limiti di utilizzo proteggono gli Audienci Manager dai processi automatizzati che possono tentare di compromettere le nostre API o l’interfaccia utente.
seo-description: Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che è possibile creare per un account. I limiti si applicano a questi elementi, creati nell’interfaccia utente o a livello di programmazione tramite i metodi API. I limiti di utilizzo proteggono gli Audienci Manager dai processi automatizzati che possono tentare di compromettere le nostre API o l’interfaccia utente.
seo-title: Limiti di utilizzo
solution: Audience Manager
title: Limiti di utilizzo
keywords: Mappatura ID, mappature ID, mappature cookie
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Utilizzo e fatturazione
translation-type: tm+mt
source-git-commit: a696bc03e430e25e2752d84905009645c625d762
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 6%

---


# Limiti di utilizzo {#usage-limits}

Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che è possibile creare per un account. I limiti si applicano a questi elementi, creati nell’interfaccia utente o a livello di programmazione tramite i metodi [!DNL API] . I limiti di utilizzo proteggono gli Audienci Manager dai processi automatizzati che possono tentare di compromettere la nostra [!DNL API]s o l&#39;interfaccia utente.

## Limiti di mappatura degli ID {#id-mapping-limits}

La tabella seguente elenca i limiti [della mappatura ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) per gli ID dispositivo. Una volta raggiunto uno dei limiti seguenti, Audience Manager aggiunge nuove mappature ID basate su una logica FIFO (primo in, primo out), rimuovendo la mappatura ID memorizzata più vecchia e aggiungendo quella nuova. Per informazioni sugli ID supportati dall&#39;Audience Manager, fai riferimento a [Indice degli ID](../../reference/ids-in-aam.md) nell&#39;Audience Manager .

| Mappatura ID | Limite massimo |
|-----------|-------------- |
| Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) to Cross-device ID ([DPUUID](../../reference/ids-in-aam.md)) | 100 ID pubblicità dispositivo ([DAID](../../reference/ids-in-aam.md)) a 1 ID multi-dispositivo ([DPUUID](../../reference/ids-in-aam.md)) |
| ID multi-dispositivo ([DPUUID](../../reference/ids-in-aam.md)) in ID pubblicità dispositivo ([DAID](../../reference/ids-in-aam.md)) | 10 ID multi-dispositivo ([DPUUID](../../reference/ids-in-aam.md)) a 1 ID pubblicità dispositivo ([DAID](../../reference/ids-in-aam.md)), per ogni [DPID](../../reference/ids-in-aam.md) |
| ID cookie/browser per cookie/ID browser | 1000 cookie/ID browser a 1 cookie/ID browser |

## Limiti degli elementi {#item-limits}

Nelle tabelle sono elencati i limiti correnti per tipo di elemento. Non puoi creare nuove caratteristiche, segmenti, destinazioni o [!UICONTROL Algorithmic Models] se raggiungi un limite specifico per uno di questi elementi. Se raggiungi un limite, devi eliminare un elemento precedente prima di poterne creare uno nuovo.

### Limiti delle caratteristiche

| Tipo di caratteristica | Limite massimo |
| -------------------------- | ------------------------------------- |
| Caratteristiche totali | 100.000 |
| Qualifiche totali delle caratteristiche | 150.000. Per ulteriori informazioni sulla qualifica delle caratteristiche, consulta Limite di qualifica delle caratteristiche in [Riferimento delle qualifiche delle caratteristiche](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algoritmica | 50 |
| Basato su regole | 100.000 |
| Onboarded | 100.000 |
| Caratteristiche cartella | 2.000 |

### Limiti dei segmenti

| Tipo di segmento | Limite massimo |
| -------------- | ------------- |
| Segmenti totali | 20.000 |

### Limiti di destinazione

| Tipo di destinazione | Limite massimo |
| ------------------ | ------------- |
| Destinazioni totali | 1.000 |
| Cookie | 1.000 |
| URL | 1.000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limiti dei modelli algoritmici

| Elemento | Limite massimo |
| -------- | ----- |
| Attivo [!UICONTROL Look-Alike Models] | 20. L&#39;Audience Manager conta solo i modelli algoritmici *attivi* rispetto al limite. |
| [!UICONTROL Look-Alike Models] dimensione massima del pubblico | 25.000.000.  Tieni presente che questo limite non può essere aumentato. È possibile ridurre le dimensioni del pubblico selezionando meno origini dati per il modello o selezionando un intervallo di look-back più breve. |
| Numero massimo di caratteristiche escluse per un [!UICONTROL Look-Alike Model] | 500. Consulta [Esclusione delle caratteristiche nella modellazione algoritmica](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Massimo [!UICONTROL Predictive Audiences Models] | 10 |
| Numero massimo di persone della linea di base per [!UICONTROL Predictive Audiences Models] | 50 |

### Limiti cartella

| Elemento | Limite massimo |
| ------------- | ------------------ |
| Cartelle delle caratteristiche | 2.000.  La struttura delle cartelle può avere una profondità massima di 5 livelli. |

### Limiti dei segnali derivati

| Elemento | Limite massimo |
| --------------- | ------------- |
| Segnali derivati | 50.000. |

### Limite account utente aziendali

| Elemento | Limite massimo |
| ----------- | ------------- |
| Numero massimo di account utente per una società | 1.000. |

## Utilizzo monitor {#monitor-usage}

Puoi visualizzare l’utilizzo e i limiti dell’account andando a **[!UICONTROL Administration > Limits]**. L&#39;accesso richiede le autorizzazioni di amministratore.

![immagine dei limiti di utilizzo](assets/usage-limits.png)

## Aumenta i limiti degli elementi {#increase-item-limits}

I limiti predefiniti qui elencati dovrebbero fornire una capacità sufficiente per le tue esigenze aziendali. Se la tua organizzazione raggiunge regolarmente questi limiti, contatta il rappresentante del tuo account per discutere di un aumento.