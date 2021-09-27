---
description: Utilizza Global Data Sources per importare gli ID pubblicitari dei dispositivi.
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

Le origini dati globali sono accessibili da tutti i clienti di Audience Manager e contengono gli ID pubblicità dei dispositivi generati da produttori di dispositivi come [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] e [!DNL Android] produttori di dispositivi. Questi ID sono resi disponibili dai produttori per scopi pubblicitari. I clienti di Audience Manager possono utilizzare le origini dati globali per sincronizzare gli ID dispositivo e importare o esportare i dati in base a tali mappature.

Nella tabella seguente sono descritte le origini dati globali supportate da Audience Manager.

| ID origine dati | Descrizione |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** gli ID rappresentano i dispositivi che eseguono il sistema  [!DNL Android] operativo. |
| 20915 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** gli ID rappresentano i dispositivi che eseguono il sistema  [!DNL iOS] operativo. |
| 121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** gli ID rappresentano i dispositivi  [!DNL Roku] in streaming. |
| 389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** gli ID rappresentano i dispositivi che eseguono il sistema  [!DNL Windows 10] operativo. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** gli ID rappresentano le  [!DNL Samsung] smart TV. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** rappresentano i dispositivi in esecuzione  [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** -  **[!DNL LGUDID]** rappresenta i dispositivi che utilizzano il sistema  [!DNL LG webOS] operativo. |
| 1171489 | **[!DNL Vizio ID for Advertising]** -  **[!DNL IFA]** rappresentano i dispositivi con sistemi operativi Vizio Smart TV. |

## Importazione di dati da origini dati globali

È possibile importare ID dispositivo da origini dati globali tramite sia [trasferimento dati in tempo reale](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) che [trasferimento dati batch](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Quando invii dati ad Audience Manager utilizzando un ID dispositivo globale, assicurati di utilizzare l’origine dati corrispondente per l’ID dispositivo in questione. Esempio: per importare i dati per [!DNL Apple IDFA], utilizza l&#39;ID origine dati 20915.

## Limitazioni

Sui dispositivi con sistemi operativi [!DNL iOS] e [!DNL Android], solo le applicazioni native possono recuperare e utilizzare gli ID pubblicitari dei dispositivi ([!UICONTROL DAID]s). Le applicazioni web in esecuzione nei browser mobili non hanno accesso agli ID pubblicitari dei dispositivi.

## Convalida ID dispositivo globale

Audience Manager convalida gli ID pubblicitari del dispositivo ([!UICONTROL DAID]) importati dai clienti, in base al formato, per garantire che corrispondano al formato standard indicato dai produttori dei dispositivi. Consulta [Indice degli ID in Audience Manager](../reference/ids-in-aam.md) per una mappatura dettagliata degli ID dei dispositivi per annunci pubblicitari alle sorgenti di dati globali e il formato corretto per ciascun ID. Assicurati di importare gli ID dispositivo nel formato corretto, in base al tipo di dispositivo. L&#39;Audience Manager rifiuta gli ID dispositivo che non soddisfano il formato corretto e restituisce un messaggio di errore per indicare che l&#39;ID è stato rifiutato.

* La messaggistica di errore per i trasferimenti di dati in batch è descritta qui: [Termini e definizioni dei rapporti sullo stato di onboarding](../reporting/onboarding-status-report.md#report-terms-conditions).
* La messaggistica di errore per i trasferimenti di dati in tempo reale è descritta qui: [Codici errore DCS, messaggi ed esempi](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Criteri di scadenza ID dispositivo

Ad Audience Manager, gli ID pubblicitari dei dispositivi vengono eliminati automaticamente dopo 120 giorni di inattività, in modo analogo a [AAM UUID](../faq/faq-privacy.md)s.

## Richiesta di nuove origini dati globali

Per richiedere l’aggiunta ad Audience Manager di nuove origini dati globali, contatta Adobe Consulting o Adobe Customer Care e fornisci informazioni dettagliate sulle origini dati richieste:

* il nome della piattaforma richiesta (ad esempio [!UICONTROL Apple IDFA]);
* il nome della società/organizzazione che gestisce la piattaforma (ad esempio, [!UICONTROL Apple Inc.]);
* Collegamenti alle specifiche tecniche per lo spazio dei nomi dell&#39;ID del dispositivo pubblicitario (ad esempio, [Documentazione AdSupport](https://developer.apple.com/documentation/adsupport)).
