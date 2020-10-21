---
description: Consultare questo documento per l'elenco completo degli ID Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consultare questo documento per l'elenco completo degli ID Adobe Audience Manager.
seo-title: Indice degli ID in Audience Manager
solution: Audience Manager
title: Indice degli ID in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: reference
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 5%

---


# Index of IDs in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Panoramica {#overview}

[!DNL Audience Manager] utilizza più ID per identificare e gestire i dati inviati. Consultate questo articolo per l’elenco completo degli [!DNL Audience Manager] ID, insieme ad esempi dei prefissi con cui utilizzarli.

## Prefisso ID {#prefixing}

Anche se potete fare riferimento alla maggior parte di questi ID con i loro nomi standalone, la maggior parte di essi è destinata a essere utilizzata con vari prefissi, quando trasmettete i dati tramite [!DNL DCS] chiamate. Alcuni di questi ID vengono utilizzati [!DNL Audience Manager] senza essere esposti agli utenti, mentre altri sono visibili anche nell’interfaccia utente.

Per comprendere i prefissi utilizzati negli esempi seguenti, vedi Attributi [supportati per le chiamate](../api/dcs-intro/dcs-api-reference/dcs-keys.md)API DCS.

## [!DNL Audience Manager] Elenco di ID {#id-list}

| ID | Nome e descrizione | Utilizzo ed esempi | Posizione interfaccia utente |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], anche noto come [!UICONTROL Device ID]. Un ID dispositivo numerico a 38 cifre che [!DNL Audience Manager] si associa a ciascun dispositivo con cui interagisce. Considerate questo ID ogni volta che viene visualizzato un riferimento a utenti univoci nell’ [!DNL Audience Manager] interfaccia utente.  Audience Manager salva questo ID come [!DNL cookie] nel dominio di `demdex.net` terze parti. | Nelle [!DNL DCS] chiamate, `uuid` è preceduto dal `d_` prefisso. <br>Esempio: `d_uuid = 07955261652886032950143702505894272138` | Potete filtrare [!DNL traits] in base [!UICONTROL Device ID] alla creazione di modelli [simili a](../features/algorithmic-models/create-model.md)look e alla [creazione di segmenti](../features/segments/segment-builder.md). È inoltre possibile filtrare i risultati [!UICONTROL Device ID] eseguendo Rapporti [generali per caratteristiche](../reporting/general-reports.md) e Report [tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Questo è l&#39;ID fornito da una società al momento della registrazione per un [!DNL Experience Cloud] account. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Non visibile nell&#39;interfaccia [!DNL Audience Manager] utente. Per informazioni su come trovare l&#39; [!DNL Organization ID]azienda, leggi [Trova il tuo ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)organizzazione. |
| [!DNL PID] | [!DNL Partner ID]. L&#39;ID [!DNL PID] è di una società in [!DNL Audience Manager].  Audience Manager associa un [!DNL imsOrgId] utente a un [!DNL PID]. | `1352` | Non visibile nell&#39;interfaccia [!DNL Audience Manager] utente. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. L’ [!DNL Experience Cloud] ID ([!DNL ECID], abbreviazioni legacy [!DNL MID] o [!DNL MCID]) viene derivato matematicamente dall’ [!DNL Organization ID] ID e dall’ [!DNL Audience Manager] [!UICONTROL Unique User ID]ID. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. Con lo stesso [!DNL Organization ID] e [!DNL Audience Manager] [!DNL UUID] si ottiene lo stesso [!DNL ECID] valore ogni volta. Per maggiori informazioni, consulta [!DNL ECID] la documentazione [Cookie e ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) Experience Cloud. | `mid = 08382830887934830189014177072406221371` | Non visibile nell&#39;interfaccia [!DNL Audience Manager] utente. |
| [!DNL SID] | [!UICONTROL Trait ID]. L&#39; [!UICONTROL Trait ID] identificazione univoca [!DNL traits] nell&#39; [!DNL Audience Manager] ambiente. | Nelle [!DNL DCS] chiamate, `SID` è preceduto dal `d_` prefisso. <br>Esempio `d_sid=289983`. | Una [!UICONTROL Trait ID] viene assegnata a ciascuna [!DNL trait], e visibile nell&#39;interfaccia utente, nella pagina [Caratteristiche](../features/traits/trait-details-page.md) . |
| [!DNL SID] | [!UICONTROL Segment ID]. L&#39; [!UICONTROL Segment ID] identificazione univoca [!DNL segments] nell&#39; [!DNL Audience Manager] ambiente. | Nelle [!DNL DCS] chiamate, `SID` è preceduto dal `d_` prefisso. <br>Esempio `d_sid=4798574`. | Un [!UICONTROL Segment ID] elemento è assegnato a ciascun elemento [!DNL segment], visibile nell’interfaccia utente, nella pagina [Segmenti](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Questo ID identifica in modo univoco i segmenti nell&#39; [!DNL Audience Manager] ambiente. | `741232` | A [!UICONTROL Legacy Segment ID] viene assegnato un segmento, visibile nell’interfaccia utente, nella pagina [Segmenti](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | [!UICONTROL Destination ID]. L&#39; [!UICONTROL Destination ID] identificazione univoca [!DNL destinations] nell&#39; [!DNL Audience Manager] ambiente. Un ID è assegnato a ciascuno [!DNL destination] nell&#39;interfaccia utente. | `2523` | Una [!UICONTROL Destination ID] viene assegnata a ciascuna [!DNL destination], e visibile nell&#39;interfaccia utente, nella pagina [Destinazioni](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | [!UICONTROL Data Source ID] (detto anche [!UICONTROL Data Provider ID]). Spazio dei nomi [!UICONTROL Data Source ID] per ID o [!DNL traits]. Un ID viene assegnato a ciascun [!DNL data source] (provider di dati) nell&#39;interfaccia utente. | Nelle [!DNL DCS] chiamate, `dpid` è preceduto dal `d_` prefisso. <br>Esempio: `d_dpid=39217`. | Un [!UICONTROL Data Provider ID] oggetto è assegnato a ogni [!DNL data source], e visibile nell&#39;interfaccia utente, nella pagina Origini [](../features/datasources-list-and-settings.md) dati. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], denominati anche [!DNL CRM ID] o [!UICONTROL Cross-Device ID]. Un ID di terze parti. Si tratta dell’ID con il quale si identificano gli utenti finali nel proprio [!DNL CRM] sistema. Puoi eseguire la sincronizzazione [!DNL DPUUIDs] con [!DNL Audience Manager] [!DNL UUIDs] e puoi eseguire la sincronizzazione [!DNL DPUUIDs] dai diversi [!UICONTROL Data Sources] ([!DNL DPIDs]) nel processo di sincronizzazione ID. | Nelle [!DNL DCS] chiamate, `dpuuid` è preceduto dal `d_` prefisso. <br> Esempio `d_dpuuid=2132-3423vn-343fds-3432r`. | Potete filtrare [!DNL traits] in base [!UICONTROL Cross-Device ID] alla creazione di modelli [simili a](../features/algorithmic-models/create-model.md)look e alla [creazione di segmenti](../features/segments/segment-builder.md). È inoltre possibile filtrare i risultati [!UICONTROL Cross-Device ID] eseguendo Rapporti [generali per caratteristiche](../reporting/general-reports.md) e Report [tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulta `DPUUID`. | Consulta `DPUUID`. | Consulta `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Le coppie [!DNL CID] e chiave-valore [!DNL CID_IC] sostituiscono [!DNL DPID] e [!DNL DPUUID]. Forniscono le stesse funzioni di [!DNL DPID] e [!DNL DPUUID], ma sono più efficienti perché includono l&#39;ID provider di dati e l&#39;ID utente (o codice di integrazione) in una singola coppia chiave-valore. | Nelle [!DNL DCS] chiamate, questi ID sono preceduti dal `d_` prefisso. <br>Esempio: `d_cid_ic=39217_myIntegrationCode`. | Vedere `DPID` e `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Un ID univoco per ogni dispositivo hardware, da utilizzare a scopi pubblicitari. Generalmente fornito dal fabbricante del dispositivo o del sistema operativo del dispositivo. | Consulta ID dispositivo [globali](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Gli ID dispositivo globali sono ID pubblicità dispositivo, univoci per ciascun dispositivo, forniti dal produttore del dispositivo o dal sistema operativo. Nella tabella seguente sono illustrati gli ID e il relativo formato. Per ulteriori informazioni sugli ID dispositivo globali e su come utilizzarli in [!DNL Audience Manager], consulta [Origini](/help/using/features/global-data-sources.md)dati globali.

| ID | [!DNL Global Data Source ID] | Nome e descrizione | Esempio |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Gli ID sono identificatori del dispositivo mobile, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono il sistema [!DNL iOS] operativo. | Il formato è composto rigorosamente da 32 cifre esadecimali in caratteri maiuscoli, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri.<br> Esempio: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sono identificatori di dispositivi mobili forniti dai produttori di dispositivi Android. Questi ID rappresentano i dispositivi che eseguono il sistema [!DNL Android] operativo. | Il formato è composto rigorosamente da 32 cifre esadecimali in lettere minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] rappresentano i dispositivi [!DNL Roku] di streaming. | Il formato è composto rigorosamente da 32 cifre esadecimali in lettere minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sono identificatori di dispositivo generati da [!DNL Windows 10] per dispositivo, per utente. | [!DNL MAID]s sono formattati come stringhe alfanumeriche. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] sono identificatori dei dispositivi forniti da [!DNL Samsung] Smart TV. | [!DNL Samsung] [!DNL TIFA] Gli ID sono formattati come stringhe alfanumeriche. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificatori del dispositivo che rappresentano i dispositivi in esecuzione nel sistema [!DNL Fire OS] operativo. | Il formato è composto rigorosamente da 32 cifre esadecimali in lettere minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |