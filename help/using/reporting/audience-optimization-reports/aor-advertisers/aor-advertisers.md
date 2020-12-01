---
description: ' Audience Optimization per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per i segmenti  Audience Manager nelle campagne multimediali a pagamento. Questi rapporti combinano dati sulle prestazioni delle campagne a livello di registro con metriche  segmento di Audience Manager per informare le ottimizzazioni incentrate sui segmenti e un mix efficace di canali.'
seo-description: ' Audience Optimization per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per i segmenti  Audience Manager nelle campagne multimediali a pagamento. Questi rapporti combinano dati sulle prestazioni delle campagne a livello di registro con metriche  segmento di Audience Manager per informare le ottimizzazioni incentrate sui segmenti e un mix efficace di canali.'
seo-title: Audience Optimization per gli inserzionisti
solution: Audience Manager
title: Audience Optimization per gli inserzionisti
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---


# [!UICONTROL Audience Optimization] per inserzionisti{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] per gli inserzionisti è possibile identificare potenziali opportunità di prestazioni per segmenti  Audience Manager nelle campagne multimediali a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con  metriche di Audience Manager [!UICONTROL segment] per informare le ottimizzazioni incentrate sui segmenti e un mix efficace di canali.

## Metodi di inserimento dati {#data-ingestion-methods}

È possibile inviare i dati a [!DNL Audience Manager] per l&#39;utilizzo in questi rapporti tramite uno di questi metodi. A volte, i clienti inviano i dati in base a entrambi i metodi. In questo modo i rapporti contengono le informazioni più complete e precise su un visitatore. Per utilizzare i rapporti [!UICONTROL Audience Optimization], le chiamate dell&#39;evento devono includere *all* dei parametri elencati nella documentazione [Panoramica e mappature per i file di metadati](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md). Puoi inviare i dati tramite i seguenti metodi elencati di seguito.

* Chiamate in pixel: Per passare i parametri di metadati richiesti a [!DNL Audience Manager] vedere [Acquisizione dei dati di clic sulla campagna tramite Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) e [Acquisizione dei dati di impressione campagna tramite Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md).

* File di dati: Se desiderate utilizzare questi rapporti per analizzare i vostri dati o dati da un&#39;origine che non è integrata con [!DNL Audience Manager], dovete creare e caricare i dati e i file di metadati per tali dati. Per ulteriori informazioni, vedere [File di dati per  report di Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) e [File di dati e metadati per  report di Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

Il tipo di report che puoi visualizzare dipende dal gruppo [!UICONTROL RBAC] a cui sei assegnato. Per ulteriori informazioni, vedere [Amministrazione](../../../features/administration/administration-overview.md) e [Crea un gruppo](../../../features/administration/administration-overview.md#create-group).

[!UICONTROL RBAC] per visualizzare i  [!UICONTROL Audience Optimization] rapporti, è necessario impostare alcune origini dati. Il consulente [!DNL Audience Manager] configurerà questi [!UICONTROL data sources] per voi. Più [!UICONTROL data sources] in ciascun [!UICONTROL RBAC] gruppo di utenti, più dati saranno accessibili a tali membri del gruppo. Come minimo, il consulente configurerà almeno uno dei seguenti [!UICONTROL data sources]:

* Inserzionista [!UICONTROL data source ]
* Brand (Marchio)[!UICONTROL data source]
* Piattaforma [!UICONTROL data source]

Gli utenti che appartengono a più di un [!UICONTROL RBAC] gruppo di utenti possono passare dalla visualizzazione di ciascun gruppo a quella di ciascun gruppo. I dati visualizzati si aggiorneranno per rispettare il gruppo selezionato. Se la società non utilizza [!UICONTROL RBAC], tutti gli utenti avranno privilegi di amministratore e accesso a tutti i [!UICONTROL data sources] (gruppi di conversione).

## Gruppi di conversione {#conversion-groups}

Nei report [!UICONTROL Audience Optimization], **[!UICONTROL Conversion Groups]** sono sinonimi di [!UICONTROL data sources] che contengono almeno una caratteristica di conversione. [!UICONTROL Data sources] che non contengono almeno una caratteristica di conversione non viene visualizzata nei  [!UICONTROL Audience Optimization] rapporti. È possibile visualizzare le caratteristiche di conversione per i gruppi di conversione nel report [Caratteristiche di conversione segnalate](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
