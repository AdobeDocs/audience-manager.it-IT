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
source-wordcount: '1001'
ht-degree: 2%

---

# Indice degli ID in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Panoramica {#overview}

[!DNL Audience Manager] utilizza più ID per identificare e gestire i dati inviati. Fare riferimento a questo articolo per l&#39;elenco completo degli ID [!DNL Audience Manager], con esempi dei prefissi da utilizzare con.

## Prefisso ID {#prefixing}

Sebbene sia possibile fare riferimento alla maggior parte di questi ID con i relativi nomi autonomi, la maggior parte di essi è destinata all&#39;utilizzo con vari prefissi durante il passaggio di dati attraverso chiamate [!DNL DCS]. Alcuni di questi ID sono utilizzati da [!DNL Audience Manager] senza essere esposti agli utenti, mentre altri sono visibili anche nell&#39;interfaccia utente.

Per informazioni sui prefissi utilizzati negli esempi seguenti, vedere [Attributi supportati per le chiamate API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] elenco di ID {#id-list}

| ID | Nome e descrizione | Utilizzo ed esempi | Posizione interfaccia utente |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], noto anche come [!UICONTROL Device ID]. Un ID dispositivo numerico di 38 cifre che [!DNL Audience Manager] associa a ogni dispositivo con cui interagisce. Pensa a questo ID ogni volta che vedi una menzione di utenti univoci nell&#39;interfaccia utente [!DNL Audience Manager]. Audience Manager salva questo ID come [!DNL cookie] nel dominio di terze parti `demdex.net`. | Nelle chiamate di [!DNL DCS], `uuid` è preceduto dal prefisso `d_`. <br>Esempio: `d_uuid = 07955261652886032950143702505894272138` | È possibile filtrare [!DNL traits] per [!UICONTROL Device ID] durante la creazione di [Modelli lookalike](../features/algorithmic-models/create-model.md) e [la creazione di segmenti](../features/segments/segment-builder.md). È inoltre possibile filtrare i risultati per [!UICONTROL Device ID] quando si eseguono [Report generali per caratteristiche](../reporting/general-reports.md) e [Report tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Questo è l&#39;ID fornito a un&#39;azienda al momento della registrazione a un account [!DNL Experience Cloud]. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Non visibile nell&#39;interfaccia utente di [!DNL Audience Manager]. Per scoprire come trovare il [!DNL Organization ID] della tua azienda, leggi [Trova il tuo ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. [!DNL PID] è un ID società in [!DNL Audience Manager]. Audience Manager associa [!DNL imsOrgId] a [!DNL PID]. | `1352` | Non visibile nell&#39;interfaccia utente di [!DNL Audience Manager]. |
| [!DNL ECID], [!DNL MID] | ID [!DNL Experience Cloud]. L&#39;ID [!DNL Experience Cloud] ([!DNL ECID], abbreviazioni legacy [!DNL MID] o [!DNL MCID]) deriva matematicamente da [!DNL Organization ID] e [!DNL Audience Manager] [!UICONTROL Unique User ID]. Finché questi ID rimangono costanti, generare il [!DNL ECID] corretto per un utente specifico è semplicemente un problema matematico. Con gli stessi [!DNL Organization ID] e [!DNL Audience Manager] [!DNL UUID] si ottiene ogni volta lo stesso valore [!DNL ECID]. Per ulteriori informazioni su [!DNL ECID], consulta la documentazione di [Cookie e Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17). | `mid = 08382830887934830189014177072406221371` | Non visibile nell&#39;interfaccia utente di [!DNL Audience Manager]. |
| [!DNL SID] | [!UICONTROL Trait ID]. [!UICONTROL Trait ID] identifica in modo univoco [!DNL traits] nell&#39;ambiente [!DNL Audience Manager]. | Nelle chiamate di [!DNL DCS], `SID` è preceduto dal prefisso `d_`. <br>Esempio `d_sid=289983`. | A ogni [!UICONTROL Trait ID] viene assegnato un [!DNL trait], visibile nell&#39;interfaccia utente, nella pagina [Caratteristiche](../features/traits/trait-details-page.md). |
| [!DNL SID] | [!UICONTROL Segment ID]. [!UICONTROL Segment ID] identifica in modo univoco [!DNL segments] nell&#39;ambiente [!DNL Audience Manager]. | Nelle chiamate di [!DNL DCS], `SID` è preceduto dal prefisso `d_`. <br>Esempio `d_sid=4798574`. | A ogni [!UICONTROL Segment ID] viene assegnato un [!DNL segment], visibile nell&#39;interfaccia utente, nella pagina [Segmenti](../features/segments/segment-summary-view.md). |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Questo ID identifica in modo univoco i segmenti nell&#39;ambiente [!DNL Audience Manager]. | `741232` | A ogni segmento viene assegnato un [!UICONTROL Legacy Segment ID], visibile nell&#39;interfaccia utente, nella pagina [Segmenti](../features/segments/segment-summary-view.md). |
| [!DNL destID] | [!UICONTROL Destination ID]. [!UICONTROL Destination ID] identifica in modo univoco [!DNL destinations] nell&#39;ambiente [!DNL Audience Manager]. A ogni [!DNL destination] nell&#39;interfaccia utente viene assegnato un ID. | `2523` | A ogni [!UICONTROL Destination ID] viene assegnato un [!DNL destination], visibile nell&#39;interfaccia utente, nella pagina [Destinazioni](../features/destinations/destinations-home.md). |
| [!DNL DPID] | [!UICONTROL Data Source ID] (indicato anche come [!UICONTROL Data Provider ID]). [!UICONTROL Data Source ID] è uno spazio dei nomi per gli ID o [!DNL traits]. A ogni [!DNL data source] (provider dati) nell&#39;interfaccia utente viene assegnato un ID. | Nelle chiamate di [!DNL DCS], `dpid` è preceduto dal prefisso `d_`. <br>Esempio: `d_dpid=39217`. | A ogni [!UICONTROL Data Provider ID] viene assegnato un [!DNL data source], visibile nell&#39;interfaccia utente, nella pagina [Origini dati](../features/datasources-list-and-settings.md). |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], indicato anche come [!DNL CRM ID] o [!UICONTROL Cross-Device ID]. Un ID di terze parti. Questo è l&#39;ID con cui si identificano gli utenti finali nel proprio sistema [!DNL CRM]. È possibile sincronizzare [!DNL DPUUIDs] con [!DNL Audience Manager] [!DNL UUIDs] e sincronizzare [!DNL DPUUIDs] dai diversi [!UICONTROL Data Sources] ([!DNL DPIDs]) nel processo di sincronizzazione ID. | Nelle chiamate [!DNL DCS], `dpuuid` è preceduto dal prefisso `d_`. <br> Esempio `d_dpuuid=2132-3423vn-343fds-3432r`. | È possibile filtrare [!DNL traits] per [!UICONTROL Cross-Device ID] durante la creazione di [Modelli lookalike](../features/algorithmic-models/create-model.md) e [la creazione di segmenti](../features/segments/segment-builder.md). È inoltre possibile filtrare i risultati per [!UICONTROL Cross-Device ID] quando si eseguono [Report generali per caratteristiche](../reporting/general-reports.md) e [Report tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Vedere `DPUUID`. | Vedere `DPUUID`. | Vedere `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Le coppie chiave-valore [!DNL CID] e [!DNL CID_IC] sostituiscono [!DNL DPID] e [!DNL DPUUID]. Forniscono le stesse funzioni di [!DNL DPID] e [!DNL DPUUID], ma sono più efficienti perché includono l&#39;ID del provider di dati e l&#39;ID utente (o il codice di integrazione) in una singola coppia chiave-valore. | Nelle chiamate di [!DNL DCS], questi ID sono preceduti dal prefisso `d_`. <br>Esempio: `d_cid_ic=39217_myIntegrationCode`. | Vedere `DPID` e `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Un ID univoco per ogni dispositivo hardware, da utilizzare a scopi pubblicitari. Di solito fornito dal produttore del dispositivo o del sistema operativo del dispositivo. | Vedi [ID dispositivo globali](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Gli ID dispositivo globali sono ID pubblicitari del dispositivo, univoci per ciascun dispositivo, forniti dal produttore del dispositivo o dal sistema operativo. La tabella seguente spiega cosa sono questi ID e quale è il loro formato. Per ulteriori informazioni sugli ID dispositivo globali e su come utilizzarli in [!DNL Audience Manager], leggere [Global Data Sources](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Nome e descrizione | Esempio |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID sono identificatori di dispositivi mobili, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono il sistema operativo [!DNL iOS]. | Il formato è rigorosamente costituito da 32 cifre esadecimali maiuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri.<br> Esempio: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID] sono identificatori di dispositivi mobili forniti dai produttori di dispositivi Android. Questi ID rappresentano i dispositivi che eseguono il sistema operativo [!DNL Android]. | Il formato è rigorosamente costituito da 32 cifre esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] rappresentano [!DNL Roku] dispositivi di streaming. | Il formato è rigorosamente costituito da 32 cifre esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID] sono identificatori di dispositivo generati da [!DNL Windows 10] per dispositivo e per utente. | [!DNL MAID] sono formattati come stringhe alfanumeriche. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] sono identificatori di dispositivo forniti da [!DNL Samsung] Smart TV. | [!DNL Samsung] [!DNL TIFA] ID formattati come stringhe alfanumeriche. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificatori di dispositivo che rappresentano i dispositivi che eseguono il sistema operativo [!DNL Fire OS]. | Il formato è rigorosamente costituito da 32 cifre esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | Identificatori di dispositivo che rappresentano i dispositivi che eseguono il sistema operativo [!DNL LG webOS]. | Il formato è rigorosamente costituito da 32 cifre esadecimali minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Identificatori di dispositivo che rappresentano dispositivi che eseguono il sistema operativo Vizio smart TV. | [!DNL Vizio IFA] ID formattati come stringhe alfanumeriche. <br>Esempio: `7XCBNROQJQPYW`. |
