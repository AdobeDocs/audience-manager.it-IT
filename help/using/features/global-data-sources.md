---
description: Utilizzate Origini dati globali per importare ID pubblicitari per dispositivi.
seo-description: Utilizzate Origini dati globali per importare ID pubblicitari per dispositivi.
seo-title: Sorgenti di dati globali
solution: Audience Manager
title: Sorgenti di dati globali
feature: Data Sources
translation-type: tm+mt
source-git-commit: cb84f95d52c2e851cb0c016cb25f408f2d79d01b
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 6%

---


# Sorgenti di dati globali {#global-data-sources}

## Panoramica

Le origini dati globali sono accessibili a tutti i clienti  Audience Manager e contengono ID pubblicitari per dispositivi generati dai produttori di dispositivi quali [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] e [!DNL Android] produttori di dispositivi. Questi ID sono resi disponibili dai produttori per scopi pubblicitari.  clienti di Audience Manager possono utilizzare origini dati globali per sincronizzare gli ID dispositivo e importare o esportare dati con chiave da tali mappature.

Nella tabella seguente sono descritte le origini dati globali supportate da  Audience Manager.

| ID origine dati | Descrizione |
|---|---|
| 2014 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** Gli ID rappresentano i dispositivi che eseguono il sistema  [!DNL Android] operativo. |
| 2015 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** Gli ID rappresentano i dispositivi che eseguono il sistema  [!DNL iOS] operativo. |
| 121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** Gli ID rappresentano i dispositivi  [!DNL Roku] in streaming. |
| 389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** Gli ID rappresentano i dispositivi che eseguono il sistema  [!DNL Windows 10] operativo. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** gli ID rappresentano  [!DNL Samsung] smart TV. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** rappresenta i dispositivi in esecuzione  [!DNL Amazon Fire OS] |

## Importazione di dati da origini dati globali

È possibile importare ID dispositivo da origini dati globali tramite il trasferimento di dati in tempo reale [](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) e il trasferimento di dati in batch [](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Quando invii dati a  Audience Manager utilizzando un ID dispositivo globale, accertati di utilizzare l&#39;origine dati corrispondente per l&#39;ID dispositivo in questione. Esempio: per importare dati per [!DNL Apple IDFA], utilizzare l&#39;ID origine dati 2015.

## Limitazioni

Sui dispositivi con sistemi operativi [!DNL iOS] e [!DNL Android], solo le applicazioni native possono recuperare e utilizzare gli ID pubblicitari dei dispositivi ([!UICONTROL DAID]s). Le applicazioni Web in esecuzione nei browser mobili non hanno accesso agli ID pubblicitari dei dispositivi.

## Convalida ID dispositivo globale

 Audience Manager convalida gli ID pubblicitari del dispositivo ([!UICONTROL DAID]) importati dai clienti, in base al loro formato, per assicurarsi che corrispondano al formato standard indicato dai produttori di dispositivi. Consulta [Indice degli ID in  Audience Manager](../reference/ids-in-aam.md) per una mappatura dettagliata degli ID pubblicitari dei dispositivi alle origini dati globali e il formato corretto per ciascun ID. Accertatevi di importare gli ID dispositivo nel formato corretto, in base al tipo di dispositivo.  Audience Manager rifiuta gli ID dispositivo che non soddisfano il formato corretto e restituisce un messaggio di errore per indicare che l&#39;ID è stato rifiutato.

* I messaggi di errore per i trasferimenti di dati batch sono descritti di seguito: [Termini e definizioni del rapporto sullo stato di onboarding](../reporting/onboarding-status-report.md#report-terms-conditions).
* I messaggi di errore per i trasferimenti di dati in tempo reale sono descritti di seguito: [Codici errore DCS, messaggi ed esempi](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Criteri di scadenza ID dispositivo

 Audience Manager elimina automaticamente gli ID pubblicitari dei dispositivi dopo 120 giorni di inattività, in modo simile a [AAM UUID](../faq/faq-privacy.md)s.

## Richiesta di nuove origini dati globali

Per richiedere l&#39;aggiunta di nuove origini dati globali al Audience Manager , contattare  Consulenza del Adobe o  Assistenza clienti Adobe e fornire informazioni dettagliate sulle origini dati richieste:

* il nome della piattaforma richiesta (ad esempio, [!UICONTROL Apple IDFA]);
* Nome della società/organizzazione che gestisce la piattaforma (ad esempio, [!UICONTROL Apple Inc.]);
* Collegamenti alle specifiche tecniche per lo spazio dei nomi ID pubblicità dispositivo (ad esempio, [Documentazione AdSupport](https://developer.apple.com/documentation/adsupport)).