---
description: Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che puoi creare per un account. I limiti si applicano a questi elementi sia creati nell'interfaccia utente sia mediante metodi API. I limiti di utilizzo aiutano a proteggere Audience Manager dai processi automatizzati che possono tentare di compromettere le nostre API o l'interfaccia utente.
seo-description: Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che puoi creare per un account. I limiti si applicano a questi elementi sia creati nell'interfaccia utente sia mediante metodi API. I limiti di utilizzo aiutano a proteggere Audience Manager dai processi automatizzati che possono tentare di compromettere le nostre API o l'interfaccia utente.
seo-title: Limiti di utilizzo
solution: Audience Manager
title: Limiti di utilizzo
keywords: Mappatura ID, mappature ID, mappature cookie
uuid: 50 ca 4647-0 b 5 c -409 c -89 fa -4 fa 1799 b 3222
translation-type: tm+mt
source-git-commit: d893998e9e59dbce64195a167e267c6f7ed16f90

---


# Limiti di utilizzo {#usage-limits}

Audience Manager imposta un limite massimo per il numero di caratteristiche, segmenti, destinazioni e modelli algoritmici che puoi creare per un account. I limiti si applicano a questi elementi sia per l'interfaccia utente che per quelli mediante [!DNL API] metodi. I limiti di utilizzo aiutano a proteggere Audience Manager dai processi automatizzati che potrebbero tentare di compromettere l'interfaccia [!DNL API]utente o l'interfaccia utente.

## Limiti di mappatura degli ID {#id-mapping-limits}

La tabella seguente elenca i [limiti di mappatura](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) ID per gli ID dispositivo. Una volta raggiunto un qualsiasi limite di seguito, Audience Manager aggiunge nuove mappature ID basate su una [!DNL FIFO] logica (first in, first out), rimuovendo la mappatura ID memorizzata meno recente e aggiunge quella nuova. Fai riferimento [all'indice degli ID](../../reference/ids-in-aam.md) in Audience Manager per informazioni sugli ID supportati da Audience Manager.

| Mappatura ID | Limite massimo |
|-----------|-------------- |
| Device Advertising ID (DAID) to Cross-Device ID (CRM ID) | 100 ID pubblicitari dispositivo (daids) a 1 ID cross-device (CRM ID) |
| ID cross-device (CRM ID) to Device Advertising ID (DAID) | 10 ID cross-device (CRM ID) a 1 Device Advertising ID (DAID) |
| ID cookie/browser per cookie/ID browser | 1000 ID/browser browser to 1 cookie/browser ID |

## Limiti elemento {#item-limits}

Le tabelle indicano i limiti correnti per tipo di elemento. Non puoi creare nuove caratteristiche, segmenti, destinazioni o [!UICONTROL Algorithmic Models] se raggiungere un limite specifico per uno di questi elementi. Se raggiungete un limite, dovete eliminare un elemento precedente prima di crearne uno nuovo.

### Limiti caratteristiche

| Tipo caratteristica | Limite massimo |
| -------------------------- | ------------------------------------- |
| Totale caratteristiche | 100,000 |
| Totale caratteristiche caratteristiche | 150,000. Per ulteriori informazioni sulla qualifica delle caratteristiche, consulta Limite delle qualifiche caratteristiche in [Riferimento alle caratteristiche caratteristiche](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
| Algoritmo | 50 |
| Basate sulla regola | 100,000 |
| Caricati | 100,000 |
| Caratteristiche cartella | 2,000 |

### Limiti segmento

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

### Limiti del modello algoritmici

| Elemento | Limite massimo |
| -------- | ----- |
| Modelli algoritmici attivi | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| Dimensioni massime dei modelli algoritmici | 25,000,000.  Tenete presente che questo limite non può essere aumentato. Puoi diminuire le dimensioni del pubblico selezionando un numero inferiore di origini dati per il modello o selezionando una finestra di look-back più breve. |
| Numero massimo di caratteristiche escluse per un modello | 500. Consultate [Esclusione caratteristica in Modellazione algoritmica](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

### Limiti cartella

| Elemento | Limite massimo |
| ------------- | ------------------ |
| Cartelle caratteristiche | 2,000.  La struttura delle cartelle può avere un livello massimo di 5 livelli. |

### Limiti segnali derivati

| Elemento | Limite massimo |
| --------------- | ------------- |
| Segnali derivati | 50,000. |

### Limite account utente società

| Elemento | Limite massimo |
| ----------- | ------------- |
| Numero massimo di account utente per una società | 1,000. |

## Utilizzo del monitor {#monitor-usage}

Puoi visualizzare l'utilizzo e i limiti per il tuo account. **[!UICONTROL Administration > Limits]** L'accesso richiede autorizzazioni amministratore.

![l'immagine limita l'utilizzo](assets/usage-limits.png)

## Aumenta limiti elemento {#increase-item-limits}

I limiti predefiniti elencati qui devono fornire una capacità sufficiente per le esigenze aziendali. Se la vostra organizzazione raggiunge in modo coerente questi limiti, contattate il rappresentante commerciale di riferimento per discutere di un aumento.