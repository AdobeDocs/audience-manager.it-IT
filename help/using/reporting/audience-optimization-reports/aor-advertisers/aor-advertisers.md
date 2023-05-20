---
description: Un Audience Optimization per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per segmenti di Audience Manager nelle campagne a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche dei segmenti Audience Manager per informare ottimizzazioni incentrate sui segmenti e un mix di canali efficace.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization per gli inserzionisti
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 1%

---

# [!UICONTROL Audience Optimization] per gli inserzionisti{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per segmenti di Audience Manager nelle campagne a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con Audience Manager [!UICONTROL segment] metriche per fornire ottimizzazioni incentrate sui segmenti e un mix di canali efficace.

## Metodi di acquisizione dei dati {#data-ingestion-methods}

Puoi inviare dati a [!DNL Audience Manager] da utilizzare in questi rapporti con uno di questi metodi. A volte, i clienti inviano i dati con entrambi i metodi. In questo modo i rapporti contengono informazioni più complete e accurate su un visitatore. Per utilizzare [!UICONTROL Audience Optimization] rapporti, le chiamate dell’evento devono includere *tutto* dei parametri elencati nella [Panoramica e mappature dei file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) documentazione. Puoi inviare i dati tramite i seguenti metodi elencati di seguito.

* Chiamate pixel: per trasmettere i parametri di metadati richiesti a [!DNL Audience Manager] vedi [Acquisizione dei dati di clic delle campagne tramite chiamate pixel](../../../integration/media-data-integration/click-data-pixels.md) e [Acquisizione dei dati di impression delle campagne attraverso chiamate pixel](../../../integration/media-data-integration/impression-data-pixels.md).

* File di dati: se desideri utilizzare questi rapporti per analizzare i tuoi dati o i dati provenienti da un’origine che non è integrata con [!DNL Audience Manager], devi creare e caricare i dati e i file di metadati per tali dati. Per ulteriori informazioni, consulta [File di dati per report di Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) e [File di dati e metadati per report Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Il tipo di rapporti che puoi visualizzare dipende da [!UICONTROL RBAC] gruppo a cui sei assegnato. Consulta [Amministrazione](../../../features/administration/administration-overview.md) e [Creare un gruppo](../../../features/administration/administration-overview.md#create-group) per ulteriori informazioni.

[!UICONTROL RBAC] i gruppi devono avere alcune origini dati impostate per visualizzare [!UICONTROL Audience Optimization] rapporti. Il tuo [!DNL Audience Manager] il consulente configurerà questi [!UICONTROL data sources] per te. Più [!UICONTROL data sources] in ogni [!UICONTROL RBAC] gruppo di utenti, maggiore sarà il numero di dati a cui i membri del gruppo avranno accesso. Il tuo consulente configurerà almeno uno di questi [!UICONTROL data sources]:

* Inserzionista [!UICONTROL data source ]
* Brand (Marchio)[!UICONTROL data source]
* Piattaforma [!UICONTROL data source]

Utenti che appartengono a più utenti [!UICONTROL RBAC] Il gruppo di utenti può passare dalla visualizzazione di ciascun gruppo a quella di altri. I dati visualizzati verranno aggiornati in modo da rispettare il gruppo selezionato. Se l’azienda non utilizza [!UICONTROL RBAC], tutti gli utenti avranno privilegi di amministratore e accesso a tutte le [!UICONTROL data sources] (gruppi di conversione).

## Gruppi di conversione {#conversion-groups}

In [!UICONTROL Audience Optimization] rapporti, **[!UICONTROL Conversion Groups]** sono sinonimo di [!UICONTROL data sources] che contengono almeno una caratteristica di conversione. [!UICONTROL Data sources] che non contengono almeno una caratteristica di conversione non vengono visualizzate nel [!UICONTROL Audience Optimization] rapporti. Puoi visualizzare le caratteristiche di conversione per i gruppi di conversione in [Rapporto di caratteristiche di conversione](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) rapporto.
