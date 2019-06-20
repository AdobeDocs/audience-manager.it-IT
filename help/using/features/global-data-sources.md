---
description: Usa origini dati globali per importare ID pubblicitari del dispositivo.
seo-description: Usa origini dati globali per importare ID pubblicitari del dispositivo.
seo-title: Fonti di dati globali
solution: Audience Manager
title: Fonti di dati globali
uuid: null
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Fonti di dati globali {#global-data-sources}

## Panoramica

Le origini dati globali sono accessibili da tutti i clienti Audience Manager e contengono ID pubblicitari del dispositivo generati dai produttori di dispositivi come [!DNL Apple][!DNL Samsung][!DNL Microsoft], e [!DNL Roku]i produttori [!DNL Android] di dispositivi. Questi ID sono resi disponibili dai produttori per scopi pubblicitari. I clienti di Audience Manager possono utilizzare origini dati globali per sincronizzare gli ID dispositivo e importare o esportare dati estesi da tali mappature.

Nella tabella seguente sono descritte le origini dati globali supportate da Audience Manager.

| ID origine dati | Descrizione |
|---|---|
| 20914 | **Google Advertising ID** - **gaid** rappresentano i dispositivi che eseguono il sistema operativo Android. |
| 20915 | **Apple ID for Advertising** - **idfas** rappresenta i dispositivi che eseguono il sistema operativo iOS. |
| 121963 | **Roku ID for Advertising** - **ridas** rappresenta i dispositivi di streaming Roku. |
| 389146 | **ID pubblicità Microsoft** - **Maid** rappresenta i dispositivi con sistema operativo Windows 10. |
| 404660 | **Samsung DUIDS** rappresenta i smart TVS smart Samsung. |

## Importazione di dati da origini dati globali

Puoi importare ID dispositivo da origini dati globali tramite trasferimento dati [in tempo reale](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) e [trasferimento di dati in batch](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Quando inviate dati ad Audience Manager utilizzando un ID dispositivo globale, accertatevi di utilizzare l&#39;origine dati corrispondente per l&#39;ID dispositivo in questione. Esempio: per importare dati per [!DNL Apple IDFA], utilizzare l&#39;ID di origine dati 20915.

## Limitazioni

Sui dispositivi in esecuzione [!DNL iOS] e [!DNL Android] sui sistemi operativi, solo le applicazioni native possono recuperare e utilizzare ID pubblicitari del dispositivo[!UICONTROL DAID]. Le applicazioni Web eseguite nei browser mobili non hanno accesso agli ID pubblicitari del dispositivo.

## Convalida ID dispositivo globale

Audience Manager convalida gli ID pubblicitari del dispositivo ([!UICONTROL DAID]) importati dai clienti, in base al loro formato, per assicurare che corrispondano al formato standard delineato dai produttori di dispositivi. Consulta [Indice degli ID in Audience Manager](../reference/ids-in-aam.md) per una mappatura dettagliata degli ID pubblicitari dispositivo a origini dati globali e il formato corretto per ogni ID. Accertatevi di importare ID dispositivo nel formato corretto, in base al tipo di dispositivo. Audience Manager rifiuta gli ID dispositivo che non soddisfano il formato corretto e restituiscono un messaggio di errore per indicare che l&#39;ID è stato rifiutato.

* I messaggi di errore per i trasferimenti di dati in batch sono descritti qui: [Termini e definizioni dei report sullo stato di iscrizione](../reporting/onboarding-status-report.md#report-terms-conditions).
* I messaggi di errore per trasferimenti di dati in tempo reale sono descritti qui: [Codici di errore, messaggi ed esempi DCS](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Criterio di scadenza ID dispositivo

Audience Manager elimina automaticamente gli ID pubblicitari del dispositivo dopo 120 giorni di inattività, simile a [AAM UUID](../faq/faq-privacy.md).

## Richiesta di nuove origini dati globali

Per richiedere l&#39;aggiunta di nuove origini dati globali ad Audience Manager, contatta Adobe Consulting o l&#39;Assistenza clienti Adobe e fornisci informazioni dettagliate sulle origini dati richieste:

* Nome della piattaforma richiesta (ad es. [!UICONTROL Apple IDFA],);
* Nome della società/organizzazione che gestisce la piattaforma (ad es. [!UICONTROL Apple Inc.],);
* Collegamenti alle specifiche tecniche dello spazio nomi ID pubblicitario dispositivo (ad es. Documentazione [di adsupport](https://developer.apple.com/documentation/adsupport)).