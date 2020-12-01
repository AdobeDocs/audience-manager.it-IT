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


# Indice degli ID in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Panoramica {#overview}

[!DNL Audience Manager] utilizza più ID per identificare e gestire i dati inviati. Consultate questo articolo per l&#39;elenco completo degli [!DNL Audience Manager] ID, insieme ad esempi dei prefissi con cui utilizzarli.

## Prefisso ID {#prefixing}

Anche se potete fare riferimento alla maggior parte di questi ID con i relativi nomi standalone, la maggior parte di essi è destinata a essere utilizzata con vari prefissi, quando trasmettete i dati tramite [!DNL DCS] chiamate. Alcuni di questi ID vengono utilizzati da [!DNL Audience Manager] senza essere esposti agli utenti, mentre altri sono visibili anche nell&#39;interfaccia utente.

Per comprendere i prefissi utilizzati negli esempi seguenti, vedere [Attributi supportati per le chiamate API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Elenco di ID {#id-list}

| ID | Nome e descrizione | Utilizzo ed esempi | Posizione interfaccia utente |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], anche noto come  [!UICONTROL Device ID]. Un ID dispositivo numerico a 38 cifre che [!DNL Audience Manager] associa a ciascun dispositivo con cui interagisce. Pensa a questo ID ogni volta che viene indicato un utente univoco nell&#39;interfaccia [!DNL Audience Manager].  Audience Manager salva questo ID come [!DNL cookie] nel `demdex.net` dominio di terze parti. | Nelle chiamate [!DNL DCS], `uuid` è preceduto dal prefisso `d_`. <br>Esempio: `d_uuid = 07955261652886032950143702505894272138` | È possibile filtrare [!DNL traits] per [!UICONTROL Device ID] durante la creazione di [modelli simili a un aspetto](../features/algorithmic-models/create-model.md) e [la creazione di segmenti](../features/segments/segment-builder.md). È inoltre possibile filtrare i risultati in base a [!UICONTROL Device ID] durante l&#39;esecuzione di [Rapporti generali per caratteristiche](../reporting/general-reports.md) e [Report tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Questo è l&#39;ID fornito da una società al momento della registrazione per un account [!DNL Experience Cloud]. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Non visibile nell&#39;interfaccia utente [!DNL Audience Manager]. Per informazioni su come trovare il [!DNL Organization ID] della tua azienda, leggi [Trova il tuo ID organizzazione](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. L&#39; [!DNL PID] è l&#39;ID di una società in [!DNL Audience Manager].  Audience Manager associa un elemento [!DNL imsOrgId] a un elemento [!DNL PID]. | `1352` | Non visibile nell&#39;interfaccia utente [!DNL Audience Manager]. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. L&#39;ID [!DNL Experience Cloud] ([!DNL ECID], abbreviazioni precedenti [!DNL MID] o [!DNL MCID]) viene derivato matematicamente da [!DNL Organization ID] e da [!DNL Audience Manager] [!UICONTROL Unique User ID]. Fintanto che questi ID rimangono costanti, generare il codice [!DNL ECID] giusto per un utente specifico è semplicemente un problema matematico. Con gli stessi [!DNL Organization ID] e [!DNL Audience Manager] [!DNL UUID] si ottiene sempre lo stesso valore [!DNL ECID]. Per ulteriori informazioni su [!DNL ECID], consulta la sezione [Cookie e  ID Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) della documentazione. | `mid = 08382830887934830189014177072406221371` | Non visibile nell&#39;interfaccia utente [!DNL Audience Manager]. |
| [!DNL SID] | [!UICONTROL Trait ID]. L&#39; [!UICONTROL Trait ID] identifica in modo univoco [!DNL traits] nell&#39;ambiente [!DNL Audience Manager]. | Nelle chiamate [!DNL DCS], `SID` è preceduto dal prefisso `d_`. <br>Esempio `d_sid=289983`. | A [!UICONTROL Trait ID] viene assegnato a ciascun [!DNL trait], visibile nell&#39;interfaccia utente, nella pagina [Caratteristiche](../features/traits/trait-details-page.md). |
| [!DNL SID] | [!UICONTROL Segment ID]. L&#39; [!UICONTROL Segment ID] identifica in modo univoco [!DNL segments] nell&#39;ambiente [!DNL Audience Manager]. | Nelle chiamate [!DNL DCS], `SID` è preceduto dal prefisso `d_`. <br>Esempio `d_sid=4798574`. | A [!UICONTROL Segment ID] viene assegnato a ciascun [!DNL segment], visibile nell&#39;interfaccia utente, nella pagina [Segments](../features/segments/segment-summary-view.md). |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Questo ID identifica in modo univoco i segmenti nell&#39;ambiente [!DNL Audience Manager]. | `741232` | A [!UICONTROL Legacy Segment ID] viene assegnato a ciascun segmento, visibile nell&#39;interfaccia utente, nella pagina [Segments](../features/segments/segment-summary-view.md). |
| [!DNL destID] | [!UICONTROL Destination ID]. L&#39; [!UICONTROL Destination ID] identifica in modo univoco [!DNL destinations] nell&#39;ambiente [!DNL Audience Manager]. Un ID viene assegnato a ciascun [!DNL destination] nell&#39;interfaccia utente. | `2523` | A [!UICONTROL Destination ID] viene assegnato a ogni [!DNL destination], visibile nell&#39;interfaccia utente, nella pagina [Destinations](../features/destinations/destinations-home.md). |
| [!DNL DPID] | [!UICONTROL Data Source ID] (detto anche  [!UICONTROL Data Provider ID]). [!UICONTROL Data Source ID] è uno spazio dei nomi per ID o [!DNL traits]. A ciascun [!DNL data source] (provider di dati) nell&#39;interfaccia utente viene assegnato un ID. | Nelle chiamate [!DNL DCS], `dpid` è preceduto dal prefisso `d_`. <br>Esempio: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] viene assegnato a ogni [!DNL data source], visibile nell&#39;interfaccia utente, nella pagina [Origini dati](../features/datasources-list-and-settings.md). |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], denominati anche  [!DNL CRM ID] o  [!UICONTROL Cross-Device ID]. Un ID di terze parti. Si tratta dell&#39;ID con cui si identificano gli utenti finali nel proprio sistema [!DNL CRM]. È possibile sincronizzare [!DNL DPUUIDs] con [!DNL Audience Manager] [!DNL UUIDs] e sincronizzare [!DNL DPUUIDs] da [!UICONTROL Data Sources] diversi &lt;a4/> ([!DNL DPIDs]) nel processo di sincronizzazione ID. | Nelle chiamate [!DNL DCS], `dpuuid` è preceduto dal prefisso `d_`. <br> Esempio `d_dpuuid=2132-3423vn-343fds-3432r`. | È possibile filtrare [!DNL traits] per [!UICONTROL Cross-Device ID] durante la creazione di [modelli simili a un aspetto](../features/algorithmic-models/create-model.md) e [la creazione di segmenti](../features/segments/segment-builder.md). È inoltre possibile filtrare i risultati in base a [!UICONTROL Cross-Device ID] durante l&#39;esecuzione di [Rapporti generali per caratteristiche](../reporting/general-reports.md) e [Report tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulta `DPUUID`. | Consulta `DPUUID`. | Consulta `DPUUID`. |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Le coppie chiave-valore [!DNL CID] e [!DNL CID_IC] sostituiscono [!DNL DPID] e [!DNL DPUUID]. Forniscono le stesse funzioni delle [!DNL DPID] e [!DNL DPUUID], ma sono più efficienti perché includono l&#39;ID provider di dati e l&#39;ID utente (o codice di integrazione) in una singola coppia chiave-valore. | Nelle chiamate [!DNL DCS], questi ID sono preceduti dal prefisso `d_`. <br>Esempio: `d_cid_ic=39217_myIntegrationCode`. | Vedere `DPID` e `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Un ID univoco per ogni dispositivo hardware, da utilizzare a scopi pubblicitari. Generalmente fornito dal fabbricante del dispositivo o del sistema operativo del dispositivo. | Vedere [ID dispositivo globale](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Gli ID dispositivo globali sono ID pubblicità dispositivo, univoci per ciascun dispositivo, forniti dal produttore del dispositivo o dal sistema operativo. Nella tabella seguente sono illustrati gli ID e il relativo formato. Per ulteriori informazioni sugli ID dispositivo globali e su come utilizzarli in [!DNL Audience Manager], consultare [Origini dati globali](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Nome e descrizione | Esempio |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 2015 | [!DNL Identifier for Advertisers] Gli ID sono identificatori del dispositivo mobile, forniti dal produttore del dispositivo. Questi ID rappresentano dispositivi che eseguono il sistema operativo [!DNL iOS]. | Il formato è composto rigorosamente da 32 cifre esadecimali in caratteri maiuscoli, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri.<br> Esempio: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 2014 | [!DNL Google Advertising ID]s sono identificatori di dispositivi mobili forniti dai produttori di dispositivi Android. Questi ID rappresentano dispositivi che eseguono il sistema operativo [!DNL Android]. | Il formato è composto rigorosamente da 32 cifre esadecimali in lettere minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] rappresentano i dispositivi  [!DNL Roku] di streaming. | Il formato è composto rigorosamente da 32 cifre esadecimali in lettere minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sono identificatori di dispositivo generati da  [!DNL Windows 10] per dispositivo, per utente. | [!DNL MAID]s sono formattati come stringhe alfanumeriche. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] sono identificatori dei dispositivi forniti da  [!DNL Samsung] Smart TV. | [!DNL Samsung] [!DNL TIFA] Gli ID sono formattati come stringhe alfanumeriche. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificatori del dispositivo che rappresentano i dispositivi con il sistema operativo [!DNL Fire OS]. | Il formato è composto rigorosamente da 32 cifre esadecimali in lettere minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |