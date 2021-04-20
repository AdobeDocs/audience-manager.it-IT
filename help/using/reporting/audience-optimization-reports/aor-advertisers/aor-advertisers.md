---
description: Un Audience Optimization per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per segmenti di Audience Manager nelle campagne pubblicitarie a pagamento. Questi rapporti combinano dati sulle prestazioni delle campagne a livello di registro con metriche dei segmenti di Audience Manager per informare le ottimizzazioni incentrate sui segmenti e un efficace mix di canali.
seo-description: Un Audience Optimization per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per segmenti di Audience Manager nelle campagne pubblicitarie a pagamento. Questi rapporti combinano dati sulle prestazioni delle campagne a livello di registro con metriche dei segmenti di Audience Manager per informare le ottimizzazioni incentrate sui segmenti e un efficace mix di canali.
seo-title: Audience Optimization per gli inserzionisti
solution: Audience Manager
title: Audience Optimization per gli inserzionisti
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 2%

---

# [!UICONTROL Audience Optimization] per gli inserzionisti{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] gli inserzionisti possono aiutarti a identificare potenziali opportunità di prestazioni per segmenti di Audience Manager nelle campagne a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche di Audience Manager [!UICONTROL segment] per informare le ottimizzazioni incentrate sui segmenti e un efficace mix di canali.

## Metodi di acquisizione dei dati {#data-ingestion-methods}

Puoi inviare dati a [!DNL Audience Manager] per l’utilizzo in questi rapporti in uno di questi metodi. A volte, i clienti inviano i dati con entrambi i metodi. In questo modo puoi garantire che i rapporti contengano le informazioni più complete e accurate su un visitatore. Per utilizzare i rapporti [!UICONTROL Audience Optimization], le chiamate evento devono includere *all* dei parametri elencati nella documentazione [Panoramica e mappature per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) . Puoi inviare dati tramite i seguenti metodi elencati di seguito.

* Chiamate pixel: Per trasmettere i parametri di metadati richiesti a [!DNL Audience Manager] consulta [Acquisizione dei dati di clic delle campagne tramite chiamate pixel](../../../integration/media-data-integration/click-data-pixels.md) e [Acquisizione dei dati di impression delle campagne tramite chiamate pixel](../../../integration/media-data-integration/impression-data-pixels.md).

* File di dati: Se desideri utilizzare questi rapporti per analizzare i tuoi dati o dati da un’origine non integrata con [!DNL Audience Manager], devi creare e caricare file di dati e metadati per tali dati. Per ulteriori informazioni, consulta [File di dati per rapporti di Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) e [File di dati e metadati per rapporti di Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

Il tipo di report che puoi visualizzare dipende dal gruppo [!UICONTROL RBAC] a cui sei assegnato. Per ulteriori informazioni, consulta [Amministrazione](../../../features/administration/administration-overview.md) e [Creare un gruppo](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] per visualizzare i  [!UICONTROL Audience Optimization] rapporti è necessario che nei gruppi siano configurate alcune origini dati. Il tuo [!DNL Audience Manager] consulente configurerà questi [!UICONTROL data sources] per te. Maggiore è il numero di [!UICONTROL data sources] in ciascun gruppo di utenti [!UICONTROL RBAC], maggiori saranno i dati a cui i membri del gruppo avranno accesso. Come minimo, il tuo consulente configurerà almeno uno di questi [!UICONTROL data sources]:

* Inserzionista [!UICONTROL data source ]
* Brand (Marchio)[!UICONTROL data source]
* Piattaforma [!UICONTROL data source]

Gli utenti che appartengono a più di un gruppo di utenti [!UICONTROL RBAC] possono passare dalla visualizzazione di ciascun gruppo a quella di ciascun gruppo. I dati visualizzati verranno aggiornati per rispettare il gruppo selezionato. Se la tua azienda non utilizza [!UICONTROL RBAC], tutti gli utenti disporranno di privilegi di amministratore e di accesso a tutti i [!UICONTROL data sources] (gruppi di conversione).

## Gruppi di conversione {#conversion-groups}

Nei rapporti [!UICONTROL Audience Optimization] , **[!UICONTROL Conversion Groups]** sono sinonimi di [!UICONTROL data sources] che contengono almeno una caratteristica di conversione. [!UICONTROL Data sources] che non contengono almeno una caratteristica di conversione non viene visualizzata nei  [!UICONTROL Audience Optimization] rapporti. Puoi visualizzare le caratteristiche di conversione per i gruppi di conversione nel rapporto [Caratteristiche di conversione segnalate](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) .
