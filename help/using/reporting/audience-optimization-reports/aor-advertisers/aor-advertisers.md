---
description: L'ottimizzazione audience per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per segmenti Audience Manager tra le campagne multimediali a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche dei segmenti Audience Manager per informare le ottimizzazioni incentrate sul segmento e un mix efficace dei canali.
seo-description: L'ottimizzazione audience per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per segmenti Audience Manager tra le campagne multimediali a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche dei segmenti Audience Manager per informare le ottimizzazioni incentrate sul segmento e un mix efficace dei canali.
seo-title: Ottimizzazione dell'audience per gli inserzionisti
solution: Audience Manager
title: Ottimizzazione dell'audience per gli inserzionisti
uuid: 852 d 550 e -3 c 7 f -4750-9 abc -365 c 3 a 6 f 7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ottimizzazione dell&#39;audience per gli inserzionisti{#audience-optimization-for-advertisers}

L&#39;ottimizzazione audience per gli inserzionisti può aiutarti a identificare potenziali opportunità di prestazioni per segmenti Audience Manager tra le campagne multimediali a pagamento. Questi rapporti combinano i dati sulle prestazioni delle campagne a livello di registro con le metriche dei segmenti Audience Manager per informare le ottimizzazioni incentrate sul segmento e un mix efficace dei canali.

## Metodi di inserimento dati {#data-ingestion-methods}

Potete inviare dati da [!DNL Audience Manager] utilizzare in questi rapporti in base a uno di questi metodi. A volte i clienti inviano dati in base a entrambi i metodi. In questo modo i rapporti possono contenere informazioni più complete e accurate su un visitatore. Per utilizzare i [!UICONTROL Audience Optimization] rapporti, le chiamate agli eventi devono includere *tutti* i parametri elencati nella documentazione [Panoramica e Mappature per i file](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) metadati. Puoi inviare dati tramite i seguenti metodi elencati di seguito.

* Chiamate pixel: Per passare i parametri di metadati richiesti per [!DNL Audience Manager] visualizzare [la funzione di acquisizione dei dati, fate clic su Calls Calls (Chiamate pixel) tramite Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) (Chiamate pixel) e [Capturing Campaign Impression Data Data via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md)(Acquisizione di dati di impression per la campagna tramite chiamate pixel).

* File di dati: Se desideri utilizzare questi rapporti per analizzare dati o dati personalizzati da un&#39;origine non [!DNL Audience Manager]integrata, devi creare e caricare dati e file di metadati per quei dati. Per ulteriori informazioni, vedi [File di dati per report](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) e [dati di ottimizzazione dell&#39;audience e file di metadati per report di ottimizzazione pubblico](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## Controlli di accesso basati su ruolo (RBAC) {#rbac}

Il tipo di rapporti che puoi visualizzare dipende dal [!UICONTROL RBAC] gruppo a cui sei assegnato. Per ulteriori informazioni, consulta [Amministrazione](../../../features/administration/administration-overview.md) e [Crea un gruppo](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] devono avere alcune origini dati configurate per visualizzare [!UICONTROL Audience Optimization] i rapporti. Il [!DNL Audience Manager] tuo consulente conterrà queste origini dati. Più sono le origini dati in ciascun [!UICONTROL RBAC] gruppo di utenti, più dati i membri del gruppo avranno accesso. Come minimo, il consulente conterrà almeno una di queste origini dati:

* Origine dati inserzionista
* Origine dati marchio
* Origine dati piattaforma

Gli utenti che appartengono a più gruppi [!UICONTROL RBAC] possono passare dalla visualizzazione di ciascun gruppo. I dati visualizzati vengono aggiornati per rispettare il gruppo selezionato. Se la società non utilizza [!UICONTROL RBAC], tutti gli utenti avranno privilegi di amministratore e accesso a tutte le origini dati (gruppi di conversione).

## Gruppi di conversione {#conversion-groups}

Nei [!UICONTROL Audience Optimization] report sono **[!UICONTROL Conversion Groups]** sinonimi di origini dati contenenti almeno un trait di conversione. Le origini dati che non contengono almeno un trait di conversione non vengono visualizzate nei [!UICONTROL Audience Optimization] report. Potete visualizzare le caratteristiche di conversione per i gruppi di conversione [nel report Traits](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) di conversione segnalati.
