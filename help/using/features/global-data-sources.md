---
description: Utilizza Global Data Sources per importare gli ID per annunci pubblicitari sui dispositivi.
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: Sorgenti di dati globali
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 77daa5bd6545914f65e3e0f19b12c750535244e8
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 6%

---

# Sorgenti di dati globali {#global-data-sources}

## Panoramica

Le origini di dati globali sono accessibili da tutti i clienti Audience Manager e contengono gli ID di pubblicità dei dispositivi generati dai produttori di dispositivi, come [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku], e [!DNL Android] produttori di dispositivi. Questi ID sono resi disponibili dai produttori per scopi pubblicitari. I clienti Audience Manager possono utilizzare origini di dati globali per sincronizzare gli ID dispositivo e importare o esportare dati ricavati da tali mappature.

Nella tabella seguente sono descritte le origini dati globali supportate da Audience Manager.

| ID origine dati | Descrizione |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** Gli ID rappresentano i dispositivi che eseguono [!DNL Android] sistema operativo. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** Gli ID rappresentano i dispositivi che eseguono [!DNL iOS] sistema operativo. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** Gli ID rappresentano [!DNL Roku] dispositivi di streaming. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** Gli ID rappresentano i dispositivi che eseguono [!DNL Windows 10] sistema operativo. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** Gli ID rappresentano [!DNL Samsung] smart TV. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** rappresenta i dispositivi in esecuzione [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** rappresentano i dispositivi che eseguono [!DNL LG webOS] sistema operativo. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** rappresenta i dispositivi che eseguono sistemi operativi Vizio smart TV. |

## Importazione di dati da origini dati globali

Puoi importare gli ID dispositivo da origini dati globali tramite entrambi [trasferimento dati in tempo reale](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) e [trasferimento di dati in batch](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Quando invii dati ad Audience Manager utilizzando un ID dispositivo globale, assicurati di utilizzare l’origine dati corrispondente per l’ID dispositivo in questione. Esempio: per importare dati per [!DNL Apple IDFA], utilizza il 20915 ID dell’origine dati.

## Limitazioni

Sui dispositivi in esecuzione [!DNL iOS] e [!DNL Android] , solo le applicazioni native possono recuperare e utilizzare gli ID dei dispositivi pubblicitari ([!UICONTROL DAID]s). Le applicazioni web in esecuzione nei browser mobili non hanno accesso agli ID per annunci pubblicitari sui dispositivi.

## Convalida ID dispositivo globale

L&#39;Audience Manager convalida gli ID dispositivo advertising ([!UICONTROL DAID]) importati dai clienti, in base al loro formato, per garantire che corrispondano al formato standard indicato dai produttori dei dispositivi. Consulta [Indice degli ID in Audience Manager](../reference/ids-in-aam.md) per una mappatura dettagliata degli ID Device Advertising alle origini dati globali e per il formato corretto di ciascun ID. Assicurati di importare gli ID dispositivo nel formato corretto, in base al tipo di dispositivo. L&#39;Audience Manager rifiuta gli ID dispositivo che non soddisfano il formato corretto e restituisce un messaggio di errore per indicare che l&#39;ID è stato rifiutato.

* I messaggi di errore per i trasferimenti di dati in batch sono descritti qui: [Termini e definizioni del rapporto sullo stato di onboarding](../reporting/onboarding-status-report.md#report-terms-conditions).
* I messaggi di errore per i trasferimenti di dati in tempo reale sono descritti qui: [Codici errore DCS, messaggi ed esempi](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Criteri di scadenza ID dispositivo

Audience Manager elimina automaticamente gli ID di pubblicità del dispositivo dopo 120 giorni di inattività, in modo simile a [UUID AAM](../faq/faq-privacy.md)s.

## Richiesta di nuove origini dati globali

Per richiedere l’aggiunta di nuove origini dati globali ad Audience Manager Adobe, contatta la Consulenza o l’Assistenza clienti Adobe e fornisci informazioni dettagliate sulle origini dati richieste:

* Il nome della piattaforma richiesta (ad es. [!UICONTROL Apple IDFA]);
* Il nome dell’azienda/organizzazione che gestisce la piattaforma (ad esempio, [!UICONTROL Apple Inc.]);
* Collegamenti alle specifiche tecniche per lo spazio dei nomi dell’ID per annunci pubblicitari del dispositivo (ad esempio, [Documentazione di AdSupport](https://developer.apple.com/documentation/adsupport)).
