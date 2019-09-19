---
description: Audience Optimization per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per i segmenti Audience Manager nelle tue campagne multimediali a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche dei segmenti di Audience Manager per informare le ottimizzazioni incentrate sui segmenti e un mix efficace di canali.
seo-description: Audience Optimization per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per i segmenti Audience Manager nelle tue campagne multimediali a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche dei segmenti di Audience Manager per informare le ottimizzazioni incentrate sui segmenti e un mix efficace di canali.
seo-title: Ottimizzazione dell'audience per gli inserzionisti
solution: Audience Manager
title: Ottimizzazione dell'audience per gli inserzionisti
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

Audience Optimization per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per i segmenti Audience Manager nelle tue campagne multimediali a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche dei segmenti di Audience Manager per informare le ottimizzazioni incentrate sui segmenti e un mix efficace di canali.

## Metodi di inserimento dati {#data-ingestion-methods}

È possibile inviare dati [!DNL Audience Manager] per l'utilizzo in questi rapporti tramite uno di questi metodi. A volte, i clienti inviano i dati in base a entrambi i metodi. In questo modo i rapporti contengono le informazioni più complete e precise su un visitatore. Per utilizzare i [!UICONTROL Audience Optimization] rapporti, le chiamate agli eventi devono includere *tutti* i parametri elencati nella documentazione [Panoramica e Mappature per i file](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) di metadati. Puoi inviare i dati tramite i seguenti metodi elencati di seguito.

* Chiamate in pixel: Per trasmettere i parametri di metadati richiesti per [!DNL Audience Manager] vedere [Acquisizione dei dati di clic sulla campagna tramite Pixel Calls (Chiamate pixel) e](../../../integration/media-data-integration/click-data-pixels.md) Acquisizione dei dati di impressione della campagna tramite Pixel Calls (Chiamate pixel) [](../../../integration/media-data-integration/impression-data-pixels.md).

* File di dati: Se desiderate utilizzare questi rapporti per analizzare i vostri dati o dati da un'origine non integrata con [!DNL Audience Manager], dovete creare e caricare i dati e i file di metadati per tali dati. Per ulteriori informazioni, vedi File [di dati per report](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) di ottimizzazione dell'audience e file di [dati e metadati per report](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)di ottimizzazione dell'audience.

## Controlli di accesso basati sul ruolo (RBAC) {#rbac}

Il tipo di rapporti che puoi visualizzare dipende dal [!UICONTROL RBAC] gruppo a cui sei assegnato. Per ulteriori informazioni, consulta [Amministrazione](../../../features/administration/administration-overview.md) e [creazione di un gruppo](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] per visualizzare i [!UICONTROL Audience Optimization] rapporti, è necessario che siano configurate alcune origini dati. Il tuo [!DNL Audience Manager] consulente configurerà queste origini dati per te. Più origini dati in ciascun gruppo di [!UICONTROL RBAC] utenti, più dati saranno accessibili ai membri del gruppo. Come minimo, il consulente configurerà almeno una delle seguenti origini dati:

* Origine dati inserzionista
* Origine dati marchio
* Origine dati piattaforma

Gli utenti appartenenti a più [!UICONTROL RBAC] gruppi di utenti possono passare dalla visualizzazione di ciascun gruppo a quella di appartenenza. I dati visualizzati si aggiorneranno per rispettare il gruppo selezionato. Se la società non utilizza [!UICONTROL RBAC], tutti gli utenti avranno privilegi di amministratore e l'accesso a tutte le origini dati (gruppi di conversione).

## Gruppi di conversione {#conversion-groups}

Nei [!UICONTROL Audience Optimization] rapporti, **[!UICONTROL Conversion Groups]** sono sinonimi di origini dati che contengono almeno una caratteristica di conversione. Le origini dati che non contengono almeno una caratteristica di conversione non vengono visualizzate nei [!UICONTROL Audience Optimization] rapporti. Puoi visualizzare le caratteristiche di conversione per i gruppi di conversione nel rapporto Caratteristiche [conversione](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) segnalate.
