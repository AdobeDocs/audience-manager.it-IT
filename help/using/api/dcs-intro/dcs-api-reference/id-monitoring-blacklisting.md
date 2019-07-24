---
description: Il DCS monitora gli ID ricevuti e blacklist quelli che vengono inviati a un tasso di tempo elevato per un breve periodo di tempo.
keywords: id; monitoring; blacklist; dcs
seo-description: Il DCS monitora gli ID ricevuti e blacklist quelli che vengono inviati a un tasso di tempo elevato per un breve periodo di tempo.
seo-title: Monitoraggio ID e Blacklisting
solution: Audience Manager
title: Monitoraggio ID e Blacklisting
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Monitoraggio ID e Blacklisting

The [!UICONTROL DCS] monitors the IDs it receives and blacklists those that are being sent at an unusually high rate over a short period of time.

## Panoramica

To protect the Audience Manager infrastructure against malicious activity, the [!UICONTROL DCS] uses an advanced algorithm to monitor the IDs it receives. These can be [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), or [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). See [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) for detailed explanations of the IDs supported by Audience Manager.

The [!UICONTROL DCS] monitors the frequency at which it receives these IDs to detect potential malicious activity. When the [!UICONTROL DCS] detects an unusually large amount of [!UICONTROL DCS] requests for any given ID in a short amount of time, that ID is blacklisted.

## Codici di errore

You can identify blacklisted IDs by the error codes received from the [!UICONTROL DCS]. I codici di errore che possono essere ricevuti sono:

* 303: ID cliente bloccato;
* 306: ID dispositivo dichiarato bloccato;
* 307: Operazione di profilo bloccata per ID.

See [DCS Error Codes, Messages, and Examples](dcs-error-codes.md) for details on the error codes that you may receive.

## Non in blacklist

Gli ID in lista nera non devono essere utilizzati in richieste future, perché generano rapporti di dati errati. The [!UICONTROL DCS] does not support un-blacklisting of IDs.

## Impatto sulla sincronizzazione ID

[!UICONTROL DCS] le chiamate possono includere uno o più tipi di ID. Le chiamate contenenti un singolo ID vengono ignorate completamente se tale ID viene inserito in blacklist e non si verifica alcuna sincronizzazione ID in questa situazione.

When a multiple ID call also includes a blacklisted ID, the [!UICONTROL DCS] disregards the blacklisted ID and only uses the remaining, non-blacklisted IDs for synchronization.

## Cause e problemi risolti per l'elenco in blacklist ID

La causa più frequente degli ID in lista nera è quella errata tra l'infrastruttura dei clienti e Audience Manager. Quando identificate un ID in lista nera, assicuratevi di rivedere accuratamente le integrazioni di Audience Manager. See **Implementation and Integration Guides** for detailed explanations of how you should configure Audience Manager to work with other Experience Cloud solutions or external systems.

Another frequent cause of blacklisted IDs are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!UICONTROL DCS] multiple times. Se identificate l'indicizzazione dei bot come motivo per l'inserimento in blacklist degli ID, limitate l'accesso bot al sito Web.

Se riscontrate un tempo difficile per identificare i problemi di integrazione, non esitate a contattare l'Assistenza clienti. Prior to opening a support request, make sure to keep the `.har` `HTTP` archive of your browser ready. Questo archivio aiuta il team di supporto a identificare perché si è verificato un blacklist ID.