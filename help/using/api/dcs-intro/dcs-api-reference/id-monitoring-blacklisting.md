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

Il [!UICONTROL DCS] monitoraggio degli ID riceve e nera quelli che vengono inviati a un tasso di tempo elevato per un breve periodo di tempo.

## Panoramica

Per proteggere l&#39;infrastruttura Audience Manager contro attività dannose, viene [!UICONTROL DCS] utilizzato un algoritmo avanzato per monitorare gli ID ricevuti. Possono trattarsi [!UICONTROL Data Provider Unique User ID]di s/[!UICONTROL CRM ID]s, [!UICONTROL Audience Manager Unique User ID][!UICONTROL AAM UUID]s o [!UICONTROL Experience Cloud ID][!UICONTROL ECID]s. Consulta [Indice degli ID in Audience Manager](../../../reference/ids-in-aam.md) per informazioni dettagliate sugli ID supportati da Audience Manager.

Il [!UICONTROL DCS] monitoraggio della frequenza in cui riceve questi ID per rilevare potenziali attività dannose. Quando l&#39;utente [!UICONTROL DCS] rileva una quantità di [!UICONTROL DCS] richieste insolitamente elevata per un determinato ID in un breve lasso di tempo, tale ID viene inserito in blacklist.

## Codici di errore

Puoi identificare gli ID in blacklist dai codici di errore ricevuti dal [!UICONTROL DCS]. I codici di errore che possono essere ricevuti sono:

* 303: ID cliente bloccato;
* 306: ID dispositivo dichiarato bloccato;
* 307: Operazione di profilo bloccata per ID.

Per [informazioni sui codici di errore che potresti ricevere, consulta Codici di errore DCS, Messaggi ed Esempi](dcs-error-codes.md) .

## Non in blacklist

Gli ID in lista nera non devono essere utilizzati in richieste future, perché generano rapporti di dati errati. Non [!UICONTROL DCS] supporta l&#39;inserimento in blacklist di ID.

## Impatto sulla sincronizzazione ID

[!UICONTROL DCS] le chiamate possono includere uno o più tipi di ID. Le chiamate contenenti un singolo ID vengono ignorate completamente se tale ID viene inserito in blacklist e non si verifica alcuna sincronizzazione ID in questa situazione.

Quando una chiamata ID multipla include anche un ID in lista nera, ignora [!UICONTROL DCS] l&#39;ID in lista nera e usa solo gli ID non inseriti in blacklist rimanenti per la sincronizzazione.

## Cause e problemi risolti per l&#39;elenco in blacklist ID

La causa più frequente degli ID in lista nera è quella errata tra l&#39;infrastruttura dei clienti e Audience Manager. Quando identificate un ID in lista nera, assicuratevi di rivedere accuratamente le integrazioni di Audience Manager. Consulta **Implementazione e guide all&#39;integrazione** per informazioni dettagliate su come configurare Audience Manager per lavorare con altre soluzioni Experience Cloud o con sistemi esterni.

Un&#39;altra causa frequente degli ID in blacklist consiste nell&#39;indicizzazione di bot (cracker Web), che in genere causano aumenti del traffico, con conseguente invio degli stessi [!UICONTROL DCS] ID a più volte. Se identificate l&#39;indicizzazione dei bot come motivo per l&#39;inserimento in blacklist degli ID, limitate l&#39;accesso bot al sito Web.

Se riscontrate un tempo difficile per identificare i problemi di integrazione, non esitate a contattare l&#39;Assistenza clienti. Prima di aprire una richiesta di supporto, assicuratevi di mantenere pronto `.har``HTTP` l&#39;archivio del browser. Questo archivio aiuta il team di supporto a identificare perché si è verificato un blacklist ID.