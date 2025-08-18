---
description: Audience Optimization per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per i segmenti Audience Manager nelle campagne multimediali a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche dei segmenti di Audience Manager per informare ottimizzazioni incentrate sui segmenti e un mix di canali efficace.
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
ht-degree: 0%

---

# [!UICONTROL Audience Optimization] per gli inserzionisti{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per i segmenti Audience Manager nelle tue campagne multimediali a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche di Audience Manager [!UICONTROL segment] per fornire ottimizzazioni incentrate sui segmenti e un mix di canali efficace.

## Metodi di acquisizione dei dati {#data-ingestion-methods}

È possibile inviare dati a [!DNL Audience Manager] per l&#39;utilizzo in questi report utilizzando uno di questi metodi. A volte, i clienti inviano i dati con entrambi i metodi. In questo modo i rapporti contengono informazioni più complete e accurate su un visitatore. Per utilizzare i report [!UICONTROL Audience Optimization], le chiamate evento devono includere *tutti* i parametri elencati nella documentazione [Panoramica e mappature per file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md). Puoi inviare i dati tramite i seguenti metodi elencati di seguito.

* Chiamate pixel: per passare i parametri di metadati richiesti a [!DNL Audience Manager], vedi [Acquisizione dei dati di clic delle campagne tramite chiamate pixel](../../../integration/media-data-integration/click-data-pixels.md) e [Acquisizione dei dati di impression delle campagne tramite chiamate pixel](../../../integration/media-data-integration/impression-data-pixels.md).

* File di dati: se si desidera utilizzare questi report per analizzare i propri dati o dati da un&#39;origine non integrata con [!DNL Audience Manager], è necessario creare e caricare i file di dati e metadati per tali dati. Per ulteriori informazioni, vedere [File di dati per report Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) e [File di dati e metadati per report Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Il tipo di report visualizzabile dipende dal gruppo [!UICONTROL RBAC] a cui sei assegnato. Per ulteriori informazioni, vedere [Amministrazione](../../../features/administration/administration-overview.md) e [Crea gruppo](../../../features/administration/administration-overview.md#create-group).

[!UICONTROL RBAC] gruppi devono avere alcune origini dati impostate per visualizzare i report [!UICONTROL Audience Optimization]. Il tuo consulente [!DNL Audience Manager] configurerà [!UICONTROL data sources] per te. Più [!UICONTROL data sources] in ogni gruppo di utenti [!UICONTROL RBAC], più dati avranno accesso i membri del gruppo. Il tuo consulente configurerà almeno uno di questi [!UICONTROL data sources]:

* Inserzionista [!UICONTROL data source]
* Marchio [!UICONTROL data source]
* Piattaforma [!UICONTROL data source]

Gli utenti che appartengono a più di un gruppo di utenti [!UICONTROL RBAC] possono passare da una visualizzazione all&#39;altra di ciascun gruppo. I dati visualizzati verranno aggiornati in modo da rispettare il gruppo selezionato. Se la società non utilizza [!UICONTROL RBAC], tutti gli utenti avranno privilegi di amministratore e accesso a tutti i [!UICONTROL data sources] (gruppi di conversione).

## Gruppi di conversione {#conversion-groups}

Nei report [!UICONTROL Audience Optimization], **[!UICONTROL Conversion Groups]** è sinonimo di [!UICONTROL data sources] che contengono almeno una caratteristica di conversione. [!UICONTROL Data sources] che non contengono almeno una caratteristica di conversione non vengono visualizzati nei report [!UICONTROL Audience Optimization]. Puoi visualizzare le caratteristiche di conversione per i gruppi di conversione nel rapporto [Caratteristiche di conversione segnalate](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
