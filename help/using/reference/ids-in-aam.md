---
description: Consulta questo documento per l’elenco completo degli ID di Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid
seo-description: Consulta questo documento per l’elenco completo degli ID di Adobe Audience Manager.
seo-title: Indice degli ID in Audience Manager
solution: Audience Manager
title: Indice degli ID in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 5%

---

# Indice degli ID in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Panoramica {#overview}

[!DNL Audience Manager] utilizza più ID per identificare e gestire i dati inviati. Consulta questo articolo per l’elenco completo degli ID [!DNL Audience Manager] , insieme ad esempi dei prefissi con cui devi usarli.

## Prefisso ID {#prefixing}

Anche se puoi fare riferimento alla maggior parte di questi ID con i loro nomi autonomi, la maggior parte di essi è destinata a essere utilizzata con vari prefissi, quando trasmetti i dati tramite chiamate [!DNL DCS] . Alcuni di questi ID vengono utilizzati da [!DNL Audience Manager] senza essere esposti agli utenti, mentre altri sono visibili anche nell&#39;interfaccia utente.

Per comprendere i prefissi utilizzati nei seguenti esempi, consulta [Attributi supportati per le chiamate API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Elenco di ID {#id-list}

| ID | Nome e descrizione | Utilizzo ed esempi | Posizione interfaccia utente |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], noto anche come  [!UICONTROL Device ID]. ID dispositivo numerico a 38 cifre associato a ciascun dispositivo con cui interagisce. [!DNL Audience Manager] Considera questo ID ogni volta che vedi un riferimento a utenti univoci nell&#39; [!DNL Audience Manager] interfaccia utente. Audience Manager salva questo ID come [!DNL cookie] nel dominio di terze parti `demdex.net` . | Nelle chiamate [!DNL DCS] , `uuid` è preceduto dal prefisso `d_` . <br>Esempio: `d_uuid = 07955261652886032950143702505894272138` | Puoi filtrare [!DNL traits] in base a [!UICONTROL Device ID] durante la creazione di [modelli lookalike](../features/algorithmic-models/create-model.md) e [la creazione di segmenti](../features/segments/segment-builder.md). Puoi anche filtrare i risultati per [!UICONTROL Device ID] quando esegui [Rapporti generali per caratteristiche](../reporting/general-reports.md) e [Rapporti sulle tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Questo è l&#39;ID fornito a una società al momento della registrazione per un account [!DNL Experience Cloud]. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Non visibile nell&#39;interfaccia utente [!DNL Audience Manager]. Per scoprire come trovare il [!DNL Organization ID] della tua azienda, leggi [Trova il tuo ID organizzazione](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. Il [!DNL PID] è l&#39;ID di una società in [!DNL Audience Manager]. Audience Manager associa un [!DNL imsOrgId] a un [!DNL PID]. | `1352` | Non visibile nell&#39;interfaccia utente [!DNL Audience Manager]. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. L&#39; [!DNL Experience Cloud] ID ([!DNL ECID], le abbreviazioni legacy [!DNL MID] o [!DNL MCID]) viene derivato matematicamente dal [!DNL Organization ID] e dal [!DNL Audience Manager] [!UICONTROL Unique User ID]. Fintanto che questi ID rimangono costanti, la generazione del codice [!DNL ECID] corretto per un utente specifico è semplicemente un problema matematico. Con gli stessi [!DNL Organization ID] e [!DNL Audience Manager] [!DNL UUID] ottieni sempre lo stesso valore [!DNL ECID]. Per ulteriori informazioni su [!DNL ECID], consulta la documentazione [Cookie e Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Non visibile nell&#39;interfaccia utente [!DNL Audience Manager]. |
| [!DNL SID] | [!UICONTROL Trait ID]. L’ [!UICONTROL Trait ID] identifica in modo univoco [!DNL traits] nell’ambiente [!DNL Audience Manager]. | Nelle chiamate [!DNL DCS] , `SID` è preceduto dal prefisso `d_` . <br>Esempio `d_sid=289983`. | A [!UICONTROL Trait ID] viene assegnato un [!DNL trait] e visibile nell&#39;interfaccia utente nella pagina [Caratteristiche](../features/traits/trait-details-page.md). |
| [!DNL SID] | [!UICONTROL Segment ID]. L’ [!UICONTROL Segment ID] identifica in modo univoco [!DNL segments] nell’ambiente [!DNL Audience Manager]. | Nelle chiamate [!DNL DCS] , `SID` è preceduto dal prefisso `d_` . <br>Esempio `d_sid=4798574`. | A [!UICONTROL Segment ID] viene assegnato un [!DNL segment] e visibile nell&#39;interfaccia utente nella pagina [Segmenti](../features/segments/segment-summary-view.md). |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Questo ID identifica in modo univoco i segmenti nell&#39;ambiente [!DNL Audience Manager]. | `741232` | Un [!UICONTROL Legacy Segment ID] viene assegnato a ciascun segmento e visibile nell&#39;interfaccia utente nella pagina [Segmenti](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | [!UICONTROL Destination ID]. L’ [!UICONTROL Destination ID] identifica in modo univoco [!DNL destinations] nell’ambiente [!DNL Audience Manager]. A ogni elemento [!DNL destination] dell’interfaccia utente viene assegnato un ID. | `2523` | A [!UICONTROL Destination ID] viene assegnato un elemento [!DNL destination] visibile nell&#39;interfaccia utente nella pagina [Destinazioni](../features/destinations/destinations-home.md). |
| [!DNL DPID] | [!UICONTROL Data Source ID] (indicato anche come  [!UICONTROL Data Provider ID]). Il [!UICONTROL Data Source ID] è uno spazio dei nomi per gli ID o [!DNL traits]. A ogni [!DNL data source] (provider di dati) nell&#39;interfaccia utente viene assegnato un ID. | Nelle chiamate [!DNL DCS] , `dpid` è preceduto dal prefisso `d_` . <br>Esempio: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] viene assegnato un [!DNL data source] e visibile nell&#39;interfaccia utente nella pagina [Origini dati](../features/datasources-list-and-settings.md). |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], anche denominato  [!DNL CRM ID] o  [!UICONTROL Cross-Device ID]. Un ID di terze parti. Questo è l&#39;ID con cui identificare gli utenti finali nel proprio sistema [!DNL CRM]. È possibile sincronizzare [!DNL DPUUIDs] con [!DNL Audience Manager] [!DNL UUIDs] e sincronizzare [!DNL DPUUIDs] dai diversi [!UICONTROL Data Sources] ([!DNL DPIDs]) nel processo di sincronizzazione ID. | Nelle chiamate [!DNL DCS] , `dpuuid` è preceduto dal prefisso `d_` . <br> Esempio `d_dpuuid=2132-3423vn-343fds-3432r`. | Puoi filtrare [!DNL traits] in base a [!UICONTROL Cross-Device ID] durante la creazione di [modelli lookalike](../features/algorithmic-models/create-model.md) e [la creazione di segmenti](../features/segments/segment-builder.md). Puoi anche filtrare i risultati per [!UICONTROL Cross-Device ID] quando esegui [Rapporti generali per caratteristiche](../reporting/general-reports.md) e [Rapporti sulle tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulta `DPUUID`. | Consulta `DPUUID`. | Consulta `DPUUID`. |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Le coppie chiave-valore [!DNL CID] e [!DNL CID_IC] sostituiscono [!DNL DPID] e [!DNL DPUUID]. Forniscono le stesse funzioni delle [!DNL DPID] e [!DNL DPUUID], ma sono più efficienti perché includono l&#39;ID del provider di dati e l&#39;ID utente (o il codice di integrazione) in un&#39;unica coppia chiave-valore. | Nelle chiamate [!DNL DCS] , questi ID sono preceduti dal prefisso `d_` . <br>Esempio: `d_cid_ic=39217_myIntegrationCode`. | Vedere `DPID` e `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Un ID univoco per ogni dispositivo hardware, da utilizzare a scopi pubblicitari. Di solito fornito dal fabbricante del dispositivo o del sistema operativo del dispositivo. | Consulta [ID dispositivo globale](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Gli ID dispositivo globale sono ID per dispositivi pubblicitari, univoci per ciascun dispositivo, forniti dal produttore del dispositivo o dal sistema operativo. La tabella seguente spiega cosa sono questi ID e quale è il loro formato. Per ulteriori informazioni sugli ID dispositivo globali e su come utilizzarli in [!DNL Audience Manager], consulta [Fonti di dati globali](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Nome e descrizione | Esempio |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Gli ID sono identificatori dei dispositivi mobili, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono il sistema operativo [!DNL iOS]. | Il formato è composto rigorosamente da 32 cifre esadecimali in maiuscolo, visualizzate in cinque gruppi e separate da trattini, nel formato 8-4-4-4-12, per un totale di 36 caratteri.<br> Esempio: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sono identificatori per dispositivi mobili forniti dai produttori di dispositivi Android. Questi ID rappresentano i dispositivi che eseguono il sistema operativo [!DNL Android]. | Il formato è composto rigorosamente da 32 cifre esadecimali in minuscolo, visualizzate in cinque gruppi e separate da trattini, nel formato 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] rappresentano dispositivi  [!DNL Roku] in streaming. | Il formato è composto rigorosamente da 32 cifre esadecimali in minuscolo, visualizzate in cinque gruppi e separate da trattini, nel formato 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sono identificatori di dispositivo generati da  [!DNL Windows 10] per dispositivo, per utente. | [!DNL MAID]s sono formattati come stringhe alfanumeriche. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] sono identificatori dei dispositivi forniti da  [!DNL Samsung] Smart TV. | [!DNL Samsung] [!DNL TIFA] Gli ID vengono formattati come stringhe alfanumeriche. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificatori dei dispositivi che rappresentano i dispositivi con il sistema operativo [!DNL Fire OS]. | Il formato è composto rigorosamente da 32 cifre esadecimali in minuscolo, visualizzate in cinque gruppi e separate da trattini, nel formato 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
