---
description: Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che è possibile creare per un conto. I limiti si applicano a questi elementi, siano essi creati nell’interfaccia utente o a livello di programmazione tramite metodi API. I limiti di utilizzo aiutano a proteggere gli Audienci Manager da processi automatizzati che potrebbero tentare di compromettere le nostre API o l’interfaccia utente.
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: Limiti di utilizzo
keywords: Mappatura ID, mappature ID, mappature cookie
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 7%

---

# Limiti di utilizzo {#usage-limits}

Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che è possibile creare per un conto. I limiti si applicano a questi elementi, siano essi creati nell’interfaccia utente o a livello di programmazione tramite [!DNL API] metodi. I limiti di utilizzo aiutano a proteggere gli Audienci Manager da processi automatizzati che potrebbero compromettere il nostro [!DNL API]s o dell’interfaccia utente.

## Limiti di mappatura degli ID {#id-mapping-limits}

La tabella seguente elenca [Mappatura ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limiti per gli ID dispositivo. Quando un ID raggiunge uno dei limiti seguenti, Audience Manager aggiunge nuove mappature ID basate su una logica FIFO (first in, first out), rimuovendo la mappatura ID memorizzata più vecchia e aggiungendo la nuova. Fai riferimento a [Indice degli ID](../../reference/ids-in-aam.md) in Audience Manager per dettagli sugli ID supportati da Audience Manager.

| Mappatura ID | Limite massimo |
|-----------|-------------- |
| ID Device Advertising ([DAID](../../reference/ids-in-aam.md)) a ID multi-dispositivo ([DPUUID](../../reference/ids-in-aam.md)) | 100 ID Device Advertising ([DAID](../../reference/ids-in-aam.md)) a 1 ID multi-dispositivo ([DPUUID](../../reference/ids-in-aam.md)) |
| ID multi-dispositivo ([DPUUID](../../reference/ids-in-aam.md)) all&#39;ID Device Advertising ([DAID](../../reference/ids-in-aam.md)) | 10 ID multi-dispositivo ([DPUUID](../../reference/ids-in-aam.md)) a 1 ID Device Advertising ([DAID](../../reference/ids-in-aam.md)), per ogni [DPID](../../reference/ids-in-aam.md) |
| Cookie/ID browser per cookie/ID browser | 1000 ID cookie/browser per 1 ID cookie/browser |

## Limiti elemento {#item-limits}

Nelle tabelle sono elencati i limiti correnti per tipo di elemento. Non puoi creare nuove caratteristiche, segmenti, destinazioni o [!UICONTROL Algorithmic Models] se si raggiunge un limite specifico per uno di questi elementi. Se si raggiunge un limite, è necessario eliminare un elemento precedente prima di poterne creare uno nuovo.

### Limiti delle caratteristiche

| Tipo di caratteristica | Limite massimo |
| -------------------------- | ------------------------------------- |
| Caratteristiche totali | 100,000 |
| Qualifiche caratteristiche totali | 150,000. Per ulteriori informazioni sulla qualifica delle caratteristiche, consulta Limite di qualificazione delle caratteristiche in [Riferimento per le qualifiche delle caratteristiche](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algoritmica | 50 |
| Basato su regole | 100,000 |
| Onboarded | 100,000 |
| Caratteristiche cartella | 2,000 |

### Limiti dei segmenti

| Tipo di segmento | Limite massimo |
| -------------- | ------------- |
| Segmenti totali | 20,000 |

### Limiti di destinazione

| Tipo di destinazione | Limite massimo |
| ------------------ | ------------- |
| Destinazioni totali | 1,000 |
| Cookie | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Limiti modello algoritmico

| Elemento | Limite massimo |
| -------- | ----- |
| Attivo [!UICONTROL Look-Alike Models] | 20. Conteggi solo Audience Manager *attivo* modelli algoritmici rispetto al limite. |
| [!UICONTROL Look-Alike Models] dimensione massima del pubblico | 25,000,000.  Tieni presente che questo limite non può essere aumentato. Puoi diminuire le dimensioni del pubblico selezionando meno origini dati per il modello o una finestra di lookback più breve. |
| Numero massimo di caratteristiche escluse per un [!UICONTROL Look-Alike Model] | 500. Consulta [Esclusione di caratteristiche nella modellazione algoritmica](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Massimo [!UICONTROL Predictive Audiences Models] | 10 |
| Numero massimo di utenti tipo previsti per [!UICONTROL Predictive Audiences Models] | 50 |

### Limiti cartelle

| Elemento | Limite massimo |
| ------------- | ------------------ |
| Cartelle delle caratteristiche | 2,000.  La struttura delle cartelle può avere una profondità massima di 5 livelli. |

### Limiti dei segnali derivati

| Elemento | Limite massimo |
| --------------- | ------------- |
| Segnali derivati | 50,000. |

### Limite account utente società

| Elemento | Limite massimo |
| ----------- | ------------- |
| Numero massimo di account utente per una società | 1,000. |

## Monitorare l’utilizzo {#monitor-usage}

Puoi vedere l’utilizzo e i limiti per il tuo account andando in **[!UICONTROL Administration > Limits]**. Per accedere a è necessario disporre di autorizzazioni di amministratore.

![immagine limiti di utilizzo](assets/usage-limits.png)

## Aumentare i limiti degli elementi {#increase-item-limits}

I limiti predefiniti qui elencati dovrebbero fornire una capacità sufficiente per le tue esigenze aziendali. Se l’organizzazione raggiunge regolarmente questi limiti, contatta il rappresentante del tuo account per discutere di un aumento.
