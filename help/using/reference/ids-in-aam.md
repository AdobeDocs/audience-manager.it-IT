---
description: Fate riferimento a questo documento per l'elenco completo degli ID di Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Fate riferimento a questo documento per l'elenco completo degli ID di Adobe Audience Manager.
seo-title: Indice degli ID in Audience Manager
solution: Audience Manager
title: Indice degli ID in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 723c75e8946c42779b4c27727ff9e6398b5fc9b1

---


# Indice degli ID in Audience Manager{#index-of-ids-in-audience-manager}

## Panoramica {#overview}

Audience Manager utilizza più ID per identificare e gestire i dati inviati. Fate riferimento a questo articolo per l&#39;elenco completo degli ID di Adobe Audience Manager, insieme ad esempi dei prefissi con cui utilizzarli.

## Prefisso ID {#prefixing}

Anche se potete fare riferimento alla maggior parte di questi ID con i loro nomi standalone, la maggior parte di essi è destinata a essere utilizzata con vari prefissi, quando trasmettete i dati tramite chiamate DCS. Alcuni di questi ID vengono utilizzati da Audience Manager senza essere esposti agli utenti, mentre altri sono visibili anche nell’interfaccia utente.

Per comprendere i prefissi utilizzati negli esempi seguenti, vedi Attributi [supportati per le chiamate](../api/dcs-intro/dcs-api-reference/dcs-keys.md)API DCS.

## Elenco degli ID di Audience Manager {#id-list}

| ID | Nome e descrizione | Utilizzo ed esempi | Posizione interfaccia |
|---|---|---|---|
| [!DNL AAM UUID] | ID utente univoco di Audience Manager, noto anche come [!UICONTROL Device ID]. Un ID dispositivo numerico a 38 cifre associato da Audience Manager a ciascun dispositivo con cui interagisce. Pensa a questo ID ogni volta che viene indicato un riferimento a utenti univoci nell’interfaccia utente di Audience Manager. Audience Manager salva questo ID come cookie nel dominio di `demdex.net` terze parti. | Nelle [!DNL DCS] chiamate, `uuid` è preceduto dal `d_` prefisso. <br>Esempio: `d_uuid = 07955261652886032950143702505894272138` | Potete filtrare le caratteristiche in base [!UICONTROL Device ID] alla creazione di modelli [simili a](../features/algorithmic-models/create-model.md)look e alla [creazione di segmenti](../features/segments/segment-builder.md). È inoltre possibile filtrare i risultati [!UICONTROL Device ID] eseguendo Rapporti [generali per caratteristiche](../reporting/general-reports.md) e Report [tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | ID organizzazione. Questo è l&#39;ID fornito da una società al momento della registrazione per un account Experience Cloud. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Non visibile nell’interfaccia di Audience Manager. Per informazioni su come trovare l&#39;ID organizzazione della società, leggi [Trova il tuo ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)organizzazione. |
| PID | ID partner. Il PID è l&#39;ID di una società in Audience Manager. Audience Manager associa un [!DNL imsOrgId] utente a un [!DNL PID]. | `1352` | Non visibile nell’interfaccia di Audience Manager. |
| [!DNL ECID], [!DNL MID] | Experience Cloud ID. L’ID Experience Cloud ([!DNL ECID], abbreviazioni precedenti [!DNL MID] o [!DNL MCID]) viene derivato matematicamente dall’ID organizzazione e dall’ID utente univoco di Audience Manager. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. Per ulteriori informazioni sull’ECID, consulta la documentazione [Cookies and Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Non visibile nell’interfaccia di Audience Manager. |
| [!DNL SID] | ID caratteristica. L’ID caratteristica identifica in modo univoco le caratteristiche nell’ambiente Audience Manager. | Nelle [!DNL DCS] chiamate, `SID` è preceduto dal `d_` prefisso. <br>Esempio `d_sid=289983`. | Un ID caratteristica viene assegnato a ciascuna caratteristica, visibile nell’interfaccia utente, nella pagina [Caratteristiche](../features/traits/trait-details-page.md) . |
| [!DNL SID] | ID segmento. L’ID segmento identifica in modo univoco i segmenti nell’ambiente Audience Manager. | Nelle [!DNL DCS] chiamate, `SID` è preceduto dal `d_` prefisso. <br>Esempio `d_sid=4798574`. | Un ID segmento viene assegnato a ciascun segmento, visibile nell’interfaccia utente, nella pagina [Segmenti](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | ID segmento legacy. Questo ID identifica in modo univoco i segmenti nell&#39;ambiente Audience Manager. | `741232` | Un ID segmento legacy viene assegnato a ciascun segmento, visibile nell’interfaccia utente, nella pagina [Segmenti](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | ID destinazione. L’ID di destinazione identifica in modo univoco le destinazioni nell’ambiente Audience Manager. Un ID è assegnato a ciascuna destinazione nell’interfaccia utente. | `2523` | Un ID di destinazione viene assegnato a ciascuna destinazione, visibile nell’interfaccia utente, nella pagina [Destinazioni](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | ID origine dati (altrimenti denominato ID provider dati). L&#39;ID origine dati è uno spazio dei nomi per ID o caratteristiche. Un ID viene assegnato a ogni origine dati (provider di dati) nell&#39;interfaccia utente. | Nelle [!DNL DCS] chiamate, `dpid` è preceduto dal `d_` prefisso. <br>Esempio: `d_dpid=39217`. | Un ID provider di dati viene assegnato a ogni origine dati, visibile nell&#39;interfaccia utente, nella pagina Origini [](../features/datasources-list-and-settings.md) dati. |
| [!DNL DPUUID] | ID utente univoco del provider di dati, detto anche [!DNL CRM ID] o [!UICONTROL Cross-Device ID]. Un ID di terze parti. Si tratta dell’ID con il quale si identificano gli utenti finali nel proprio [!DNL CRM] sistema. Puoi eseguire la sincronizzazione [!DNL DPUUIDs] con Audience Manager [!DNL UUIDs] e puoi eseguire la sincronizzazione [!DNL DPUUIDs] da diverse Origini dati ([!DNL DPIDs]) nel processo di sincronizzazione ID. | Nelle chiamate DCS, `dpuuid` è preceduto dal `d_` prefisso. <br> Esempio `d_dpuuid=2132-3423vn-343fds-3432r`. | Potete filtrare le caratteristiche in base [!UICONTROL Cross-Device ID] alla creazione di modelli [simili a](../features/algorithmic-models/create-model.md)look e alla [creazione di segmenti](../features/segments/segment-builder.md). È inoltre possibile filtrare i risultati [!UICONTROL Cross-Device ID] eseguendo Rapporti [generali per caratteristiche](../reporting/general-reports.md) e Report [tendenze per caratteristiche](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Consulta `DPUUID`. | Consulta `DPUUID`. | Consulta `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | ID cliente, Codice integrazione ID cliente. Le coppie [!DNL CID] e chiave-valore [!DNL CID_IC] sostituiscono [!DNL DPID] e [!DNL DPUUID]. Forniscono le stesse funzioni di [!DNL DPID] e [!DNL DPUUID], ma sono più efficienti perché includono l&#39;ID provider di dati e l&#39;ID utente (o codice di integrazione) in una singola coppia chiave-valore. | Nelle chiamate DCS, questi ID sono preceduti dal `d_` prefisso. <br>Esempio: `d_cid_ic=39217_myIntegrationCode`. | Vedere `DPID` e `DPUUID`. |
| [!DNL DAID] | Device Advertising ID. Un ID univoco per ogni dispositivo hardware, da utilizzare a scopi pubblicitari. Generalmente fornito dal fabbricante del dispositivo o del sistema operativo del dispositivo. | Consulta ID dispositivo [globali](#global-device-ids). |  |

## ID dispositivo globale {#global-device-ids}

Gli ID dispositivo globali sono ID pubblicità dispositivo, univoci per ciascun dispositivo, forniti dal produttore del dispositivo o dal sistema operativo. Nella tabella seguente sono illustrati gli ID e il relativo formato. Per ulteriori informazioni sugli ID dispositivo globali e su come utilizzarli in Audience Manager, consulta Origini [dati](/help/using/features/global-data-sources.md)globali.

| ID | ID origine dati globale | Nome e descrizione | Esempio  |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Gli ID sono identificatori del dispositivo mobile, forniti dal produttore del dispositivo. Questi ID rappresentano i dispositivi che eseguono il sistema operativo iOS. | Il formato è composto rigorosamente da 32 cifre esadecimali in caratteri maiuscoli, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri.<br> Esempio: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sono identificatori di dispositivi mobili forniti dai produttori di dispositivi Android. Questi ID rappresentano i dispositivi che eseguono il sistema [!DNL Android] operativo. | Il formato è composto rigorosamente da 32 cifre esadecimali in lettere minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] rappresentano i dispositivi [!DNL Roku] di streaming. | Il formato è composto rigorosamente da 32 cifre esadecimali in lettere minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sono identificatori di dispositivo generati da [!DNL Windows 10] per dispositivo, per utente. | [!DNL MAID]s sono formattati come stringhe alfanumeriche. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s sono identificatori di dispositivo forniti da Samsung Smart TV. | I Samsung [!DNL DUID]sono formattati come stringhe alfanumeriche. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identificatori del dispositivo che rappresentano i dispositivi in esecuzione nel sistema [!DNL Fire OS] operativo. | Il formato è composto rigorosamente da 32 cifre esadecimali in lettere minuscole, visualizzate in cinque gruppi e separate da trattini, nella forma 8-4-4-4-12, per un totale di 36 caratteri. <br>Esempio: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

