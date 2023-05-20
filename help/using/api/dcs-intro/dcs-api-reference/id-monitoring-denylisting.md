---
description: Il DCS monitora gli ID ricevuti e aggiunge a un elenco Bloccati quelli che vengono inviati con una frequenza insolitamente alta in un breve periodo di tempo.
keywords: id;monitoraggio;dcs;id;monitoring;dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: Monitoraggio degli ID e Inserisce nell'elenco Bloccati degli ID
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Monitoraggio degli ID e Inserisce nell&#39;elenco Bloccati degli ID

Il [!DNL DCS] monitora gli ID ricevuti e aggiunge a un elenco Bloccati quelli che vengono inviati con una frequenza insolitamente alta in un breve periodo di tempo.

## Panoramica

Per proteggere l&#39;infrastruttura Audience Manager da attività dannose, [!DNL DCS] utilizza un algoritmo avanzato per monitorare gli ID ricevuti. Questi possono essere [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s) [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), oppure [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulta [Indice degli ID in Audience Manager](../../../reference/ids-in-aam.md) per spiegazioni dettagliate degli ID supportati da Audience Manager.

Il [!DNL DCS] monitora la frequenza con cui riceve questi ID per rilevare potenziali attività dannose. Quando [!DNL DCS] rileva una quantità insolitamente elevata di [!DNL DCS] richiede per un determinato ID in un breve periodo di tempo, che viene aggiunto a un elenco Bloccati.

## Codici errore

Puoi identificare gli ID aggiunti a un elenco Bloccati in base ai codici di errore ricevuti dalla [!DNL DCS]. I codici di errore che potresti ricevere sono:

* 303: ID cliente bloccato;
* 306: ID dispositivo dichiarato bloccato;
* 307: operazione profilo bloccata per ID.

Consulta [Codici errore DCS, messaggi ed esempi](dcs-error-codes.md) per informazioni dettagliate sui codici di errore che potresti ricevere.

## Rimozione degli ID dagli elenchi Bloccati

Gli ID che sono stati aggiunti agli elenchi Bloccati non devono essere utilizzati in eventuali richieste future, in quanto porteranno a una segnalazione di dati errata. Il [!DNL DCS] non supporta la rimozione degli ID dagli elenchi Bloccati.

## Impatto sulla sincronizzazione ID

[!DNL DCS] le chiamate possono includere uno o più tipi di ID. Le chiamate contenenti un singolo ID vengono completamente ignorate se tale ID viene aggiunto a un elenco Bloccati e in questa situazione non si verifica alcuna sincronizzazione ID.

Inserita nell&#39;elenco Bloccati Quando una chiamata ID multipla include anche un ID, il [!DNL DCS] ignora l’ID negato e utilizza solo gli ID consentiti rimanenti per la sincronizzazione.

## Cause e correzioni per la Inserisce nell&#39;elenco Bloccati degli ID di

La causa più frequente per cui gli ID vengono aggiunti agli elenchi Bloccati è l’integrazione errata tra l’infrastruttura del cliente e l’Audience Manager. Inserita nell&#39;elenco Bloccati Quando identifichi un ID, accertati di rivedere attentamente le integrazioni dell’Audience Manager. Consulta **Guide all’implementazione e all’integrazione** per spiegazioni dettagliate su come configurare Audience Manager per l’utilizzo con altre soluzioni Experience Cloud o con sistemi esterni.

Un’altra causa frequente per l’aggiunta degli ID agli elenchi Bloccati sono i bot di indicizzazione (web crawler), che in genere causano un aumento del traffico e portano all’invio degli stessi ID al [!DNL DCS] più volte. Se identifichi nei bot di indicizzazione il motivo per cui gli ID vengono aggiunti agli elenchi Bloccati, devi limitare l’accesso dei bot al sito web.

Se hai difficoltà a identificare i problemi di integrazione, non esitare a contattare l’Assistenza clienti. Prima di aprire una richiesta di supporto, assicurati di conservare `.har` `HTTP` archivio del browser pronto. Questo archivio aiuta il team di supporto a identificare il motivo per cui l’ID è stato aggiunto a un elenco Bloccati.
