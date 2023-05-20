---
description: Per l'elenco completo degli ID Adobe Audience Manager, consulta questo documento.
keywords: DPID; DPUUID; CID; UUID; uuid; uuuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuuid, uuuid, uuid, uuuid, uuuid, uuuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Indice degli ID in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 5%

---

# Indice degli ID in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Panoramica {#overview}

[!DNL Audience Manager] utilizza più ID per identificare e gestire i dati che gli invii. Per l’elenco completo delle opzioni disponibili, consulta questo articolo. [!DNL Audience Manager] ID, insieme ad esempi dei prefissi che dovresti utilizzare con.

## Prefisso ID {#prefixing}

Anche se è possibile fare riferimento alla maggior parte di questi ID con i loro nomi autonomi, la maggior parte di essi deve essere utilizzata con vari prefissi, quando si trasmettono i dati tramite [!DNL DCS] chiamate. Alcuni di questi ID sono utilizzati da [!DNL Audience Manager] senza essere esposti agli utenti, mentre altri sono visibili anche nell’interfaccia utente (UI).

Per informazioni sui prefissi utilizzati negli esempi seguenti, vedere [Attributi supportati per le chiamate API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Elenco di ID {#id-list}

| ID | Nome e descrizione | Utilizzo ed esempi | Posizione interfaccia utente |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], noto anche come [!UICONTROL Device ID]. Un ID dispositivo numerico di 38 cifre che [!DNL Audience Manager] viene associato a ogni dispositivo con cui interagisce. Pensa a questo ID ogni volta che vedi una menzione di utenti univoci nel [!DNL Audience Manager] UI. Audience Manager salva questo ID come [!DNL cookie] nel `demdex.net` Dominio di terze parti. | In entrata [!DNL DCS] chiamate, `uuid` è preceduto da `d_` prefisso. <br>Esempio: `d_uuid = 07955261652886032950143702505894272138` | Puoi filtrare [!DNL traits] da [!UICONTROL Device ID] durante la creazione [Modelli looklike](../features/algorithmic-models/create-model.md), e [creazione di segmenti](../features/segments/segment-builder.md). Puoi anche filtrare i risultati per [!UICONTROL Device ID] durante l’esecuzione [Rapporti generali sulle caratteristiche](../reporting/general-reports.md) e [Rapporti sulle tendenze per le caratteristiche](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Questo è l’ID che viene fornito a un’azienda al momento della registrazione per un [!DNL Experience Cloud] account. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Non visibile in [!DNL Audience Manager] dell&#39;utente. Per scoprire come trovare i [!DNL Organization ID], leggi [Ricerca dell&#39;ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. Il [!DNL PID] è l’ID di un’azienda in [!DNL Audience Manager]. Audience Manager associa un [!DNL imsOrgId] a un [!DNL PID]. | `1352` | Non visibile in [!DNL Audience Manager] dell&#39;utente. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. Il [!DNL Experience Cloud] ID ([!DNL ECID], abbreviazioni legacy [!DNL MID] o [!DNL MCID]) è derivato matematicamente dal [!DNL Organization ID] e [!DNL Audience Manager] [!UICONTROL Unique User ID]. Finché questi ID rimangono costanti, generando il [!DNL ECID] per un utente specifico è semplicemente un problema matematico. Con lo stesso [!DNL Organization ID] e [!DNL Audience Manager] [!DNL UUID] lo stesso [!DNL ECID] ogni volta. Ulteriori informazioni sulla funzione [!DNL ECID] nel [Cookie e ID Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) documentazione. | `mid = 08382830887934830189014177072406221371` | Non visibile in [!DNL Audience Manager] dell&#39;utente. |
| [!DNL SID] | [!UICONTROL Trait ID]. Il [!UICONTROL Trait ID] identifica in modo univoco [!DNL traits] nel [!DNL Audience Manager] ambiente. | In entrata [!DNL DCS] chiamate, `SID` è preceduto da `d_` prefisso. <br>Esempio `d_sid=289983`. | A [!UICONTROL Trait ID] è assegnato a ciascuno [!DNL trait], e visibile nell&#39;interfaccia utente, nella [Caratteristiche](../features/traits/trait-details-page.md) pagina. |
| [!DNL SID] | [!UICONTROL Segment ID]. Il [!UICONTROL Segment ID] identifica in modo univoco [!DNL segments] nel [!DNL Audience Manager] ambiente. | In entrata [!DNL DCS] chiamate, `SID` è preceduto da `d_` prefisso. <br>Esempio `d_sid=4798574`. | A [!UICONTROL Segment ID] è assegnato a ciascuno [!DNL segment], e visibile nell&#39;interfaccia utente, nella [Segmenti](../features/segments/segment-summary-view.md) pagina. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Questo ID identifica in modo univoco i segmenti nel [!DNL Audience Manager] ambiente. | `741232` | A [!UICONTROL Legacy Segment ID] è assegnato a ciascun segmento ed è visibile nell’interfaccia utente, nella [Segmenti](../features/segments/segment-summary-view.md) pagina. |
| [!DNL destID] | [!UICONTROL Destination ID]. Il [!UICONTROL Destination ID] identifica in modo univoco [!DNL destinations] nel [!DNL Audience Manager] ambiente. A ogni viene assegnato un ID [!DNL destination] nell’interfaccia utente di. | `2523` | A [!UICONTROL Destination ID] è assegnato a ciascuno [!DNL destination], e visibile nell&#39;interfaccia utente, nella [Destinazioni](../features/destinations/destinations-home.md) pagina. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (denominati anche [!UICONTROL Data Provider ID]). Il [!UICONTROL Data Source ID] è uno spazio dei nomi per gli ID o [!DNL traits]. A ogni viene assegnato un ID [!DNL data source] (provider di dati) nell’interfaccia utente. | In entrata [!DNL DCS] chiamate, `dpid` è preceduto da `d_` prefisso. <br>Esempio: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] è assegnato a ciascuno [!DNL data source], e visibile nell&#39;interfaccia utente, nella [Origini dati](../features/datasources-list-and-settings.md) pagina. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], anche denominati [!DNL CRM ID] o [!UICONTROL Cross-Device ID]. Un ID di terze parti. Questo è l’ID tramite il quale si identificano gli utenti finali nel proprio [!DNL CRM] di rete. Puoi sincronizzare [!DNL DPUUIDs] con [!DNL Audience Manager] [!DNL UUIDs] e puoi sincronizzare [!DNL DPUUIDs] dal tuo diverso [!UICONTROL Data Sources] ([!DNL DPIDs]) nel processo di sincronizzazione ID. | In entrata [!DNL DCS] chiamate, `dpuuid` è preceduto da `d_` prefisso. <br> Esempio `d_dpuuid=2132-3423vn-343fds-3432r`. | Puoi filtrare [!DNL traits] da [!UICONTROL Cross-Device ID] durante la creazione [Modelli looklike](../features/algorithmic-models/create-model.md), e [creazione di segmenti](../features/segments/segment-builder.md). Puoi anche filtrare i risultati per [!UICONTROL Cross-Device ID] durante l’esecuzione [Rapporti generali sulle caratteristiche](../reporting/general-reports.md) e [Rapporti sulle tendenze per le caratteristiche](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulta `DPUUID`. | Consulta `DPUUID`. | Consulta `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Il [!DNL CID] e [!DNL CID_IC] coppie chiave-valore sostituite [!DNL DPID] e [!DNL DPUUID]. Offrono le stesse funzioni del [!DNL DPID] e [!DNL DPUUID], ma sono più efficienti perché includono l’ID del provider di dati e l’ID utente (o il codice di integrazione) in una singola coppia chiave-valore. | In entrata [!DNL DCS] chiamate, questi ID sono preceduti dalla `d_` prefisso. <br>Esempio: `d_cid_ic=39217_myIntegrationCode`. | Consulta `DPID` e `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Un ID univoco per ogni dispositivo hardware, da utilizzare a scopi pubblicitari. Di solito fornito dal produttore del dispositivo o del sistema operativo del dispositivo. | Consulta [ID dispositivo globali](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Gli ID dispositivo globali sono ID pubblicitari del dispositivo, univoci per ciascun dispositivo, forniti dal produttore del dispositivo o dal sistema operativo. La tabella seguente spiega cosa sono questi ID e quale è il loro formato. Per ulteriori informazioni sugli ID dispositivo globali e su come utilizzarli in [!DNL Audience Manager], leggi [Fonti di dati globali](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Nome e descrizione | Esempio |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Gli ID sono identificatori di dispositivi mobili, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono [!DNL iOS] sistema operativo. | Il formato è rigorosamente costituito da 32 cifre esadecimali maiuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri.<br> Esempio: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sono gli identificatori dei dispositivi mobili forniti dai produttori di dispositivi Android. Questi ID rappresentano i dispositivi che eseguono [!DNL Android] sistema operativo. | Il formato è rigorosamente costituito da 32 cifre esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] rappresentare [!DNL Roku] dispositivi di streaming. | Il formato è rigorosamente costituito da 32 cifre esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sono identificatori di dispositivo generati da [!DNL Windows 10] per dispositivo e per utente. | [!DNL MAID]s sono formattate come stringhe alfanumeriche. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] gli identificatori del dispositivo sono forniti da [!DNL Samsung] Smart TV. | [!DNL Samsung] [!DNL TIFA] Gli ID sono formattati come stringhe alfanumeriche. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificatori di dispositivo che rappresentano dispositivi su cui è in esecuzione [!DNL Fire OS] sistema operativo. | Il formato è rigorosamente costituito da 32 cifre esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | Identificatori di dispositivo che rappresentano dispositivi su cui è in esecuzione [!DNL LG webOS] sistema operativo. | Il formato è rigorosamente costituito da 32 cifre esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Identificatori di dispositivo che rappresentano dispositivi che eseguono il sistema operativo Vizio smart TV. | [!DNL Vizio IFA] Gli ID sono formattati come stringhe alfanumeriche. <br>Esempio: `7XCBNROQJQPYW`. |
