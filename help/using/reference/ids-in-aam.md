---
description: Consulta questo documento per l’elenco completo degli ID di Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uid, uid, uuid, uid, uid, uid, uuid, uuid, uuid, uuid, uuid, uid, uid, uid, uid, uid, uuid, uuid, uid, uuid
seo-description: Consulta questo documento per l’elenco completo degli ID di Adobe Audience Manager.
seo-title: Indice degli ID in Audience Manager
solution: Audience Manager
title: Indice degli ID in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 7d168c754a9b99dfd88718a0c27c34f3c1dc61d5

---


# Indice degli ID in Audience Manager{#index-of-ids-in-audience-manager}

Consulta questo documento per l’elenco completo degli ID di Adobe Audience Manager.

| ID | Nome e descrizione | Esempio  |
|---|---|---|
| [!DNL AAM UUID] | ID utente univoco di Audience Manager. Un ID dispositivo numerico a 38 cifre associato da Audience Manager a ciascun dispositivo con cui interagisce. Pensa a questo ID ogni volta che viene indicato un riferimento a utenti univoci nell’interfaccia utente di Audience Manager. Audience Manager salva questo ID come cookie nel dominio di `demdex.net` terze parti. L'UUID di Audience Manager viene inviato nelle chiamate dell'evento come `d_uuid` segnale. | `demdex = 07955261652886032950143702505894272138` |
| [!DNL ImsOrgId] | ID organizzazione. Questo è l'ID fornito da una società al momento della registrazione a Experience Cloud. Per scoprire come trovare l'ID organizzazione della società, leggi [Trova il tuo ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)organizzazione. | `5DC5123F5245B1D20A490D46@AdobeOrg` |
| PID | ID partner. Il PID è l'ID di una società in Audience Manager. Audience Manager associa un [!DNL imsOrgId] utente a un [!DNL PID]. | `1352` |
| [!DNL ECID], [!DNL MID] | Experience Cloud ID. L’ID Experience Cloud ([!DNL ECID], abbreviazioni precedenti [!DNL MID] o [!DNL MCID]) viene derivato matematicamente dall’ID organizzazione e dall’ID utente univoco di Audience Manager. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. Per ulteriori informazioni sull’ECID, consulta la documentazione [Cookies and Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) . | `mid = 08382830887934830189014177072406221371` |
| [!DNL SID] | ID caratteristica. L’ID caratteristica identifica in modo univoco le caratteristiche nell’ambiente Audience Manager. A ogni caratteristica dell’interfaccia utente (interfaccia utente) viene assegnato un ID caratteristica. | `289983` |
| SID | ID segmento. L’ID segmento identifica in modo univoco i segmenti nell’ambiente Audience Manager. Un ID segmento viene assegnato a ciascun segmento nell’interfaccia utente. | `4798574` |
| [!DNL csegID] | ID segmento legacy. Questo ID identifica in modo univoco i segmenti nell'ambiente Audience Manager. A ogni segmento dell’interfaccia utente viene assegnato un ID segmento legacy. | `741232` |
| [!DNL destID] | ID destinazione. L’ID di destinazione identifica in modo univoco le destinazioni nell’ambiente Audience Manager. Un ID è assegnato a ciascuna destinazione nell’interfaccia utente. | `2523` |
| [!DNL DPID] | ID origine dati (altrimenti denominato ID provider dati). L'ID origine dati è uno spazio dei nomi per ID o caratteristiche. Un ID viene assegnato a ogni origine dati (provider di dati) nell'interfaccia utente. | `39217` |
| [!DNL DPUUID] | ID utente univoco provider di dati (detto anche [!DNL CRM ID]). Un ID di terze parti. Si tratta dell’ID con cui identificare gli utenti finali nel proprio [!DNL CRM] sistema. Puoi eseguire la sincronizzazione [!DNL DPUUIDs] con Audience Manager [!DNL UUIDs] e puoi eseguire la sincronizzazione [!DNL DPUUIDs] da diverse Origini dati ([!DNL DPIDs]) nel processo di sincronizzazione ID. | `2132-3423vn-343fds-3432r` |
| [!DNL CRM ID] | Consulta DPUUID. | `2132-3423vn-343fds-3432r` |
| [!DNL CID], [!DNL CID_IC] | ID cliente, Codice integrazione ID cliente. Le coppie [!DNL CID] e chiave-valore sostituiscono [!DNL CID_IC] e [!DNL DPID] [!DNL DPUUID]. Forniscono le stesse funzioni di [!DNL DPID] e [!DNL DPUUID], ma sono più efficienti perché includono l'ID provider di dati e l'ID utente (o codice di integrazione) in una singola coppia chiave-valore. |  |
| [!DNL DAID] | Device Advertising ID. Un ID univoco per ogni dispositivo hardware, da utilizzare a scopi pubblicitari. Generalmente fornito dal fabbricante del dispositivo o del sistema operativo del dispositivo. | Consulta ID dispositivo [globali](#global-device-ids). |

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
