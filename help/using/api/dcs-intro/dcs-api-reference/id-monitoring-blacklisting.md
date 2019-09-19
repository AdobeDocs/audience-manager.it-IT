---
description: Il DCS controlla gli ID ricevuti ed elenca in blacklist quelli inviati a un tasso insolitamente elevato in un breve periodo di tempo.
keywords: id;monitoraggio;inserimento in blacklist;dcs
seo-description: Il DCS controlla gli ID ricevuti ed elenca in blacklist quelli inviati a un tasso insolitamente elevato in un breve periodo di tempo.
seo-title: Monitoraggio ID e Blacklist
solution: Audience Manager
title: Monitoraggio ID e Blacklist
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Monitoraggio ID e Blacklist

Controlla [!UICONTROL DCS] gli ID ricevuti ed elenca in blacklist quelli inviati a un tasso insolitamente elevato in un breve periodo di tempo.

## Panoramica

Per proteggere l'infrastruttura Audience Manager da attività dannose, il [!UICONTROL DCS] team utilizza un algoritmo avanzato per monitorare gli ID ricevuti. Questi possono essere [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulta [Indice degli ID in Audience Manager](../../../reference/ids-in-aam.md) per una spiegazione dettagliata degli ID supportati da Audience Manager.

Il [!UICONTROL DCS] monitor controlla la frequenza con cui riceve questi ID per rilevare eventuali attività dannose. Quando [!UICONTROL DCS] rileva un numero insolitamente elevato di [!UICONTROL DCS] richieste per un determinato ID in poco tempo, l’ID viene inserito in blacklist.

## Codici di errore

Puoi identificare gli ID inseriti in blacklist in base ai codici di errore ricevuti da [!UICONTROL DCS]. I codici di errore che potresti ricevere sono:

* 303: ID cliente bloccato;
* 306: ID dispositivo dichiarato bloccato;
* 307: Operazione profilo bloccato per ID.

Consulta Codici di errore [DCS, messaggi ed esempi](dcs-error-codes.md) per informazioni dettagliate sui codici di errore che potresti ricevere.

## Senza blacklist

Gli ID inseriti in blacklist non devono essere utilizzati in richieste future, poiché porteranno a una generazione di rapporti di dati errata. L' [!UICONTROL DCS] impostazione non supporta l'eliminazione della blacklist degli ID.

## Impatto sulla sincronizzazione ID

[!UICONTROL DCS] le chiamate possono includere uno o più tipi di ID. Le chiamate contenenti un singolo ID vengono ignorate completamente se l’ID è elencato in blacklist e in questa situazione non si verifica alcuna sincronizzazione ID.

Quando una chiamata ID multipla include anche un ID inserito in blacklist, l’ [!UICONTROL DCS] ID non viene considerato e utilizza solo gli ID rimanenti, non inseriti in blacklist, per la sincronizzazione.

## Cause e problemi risolti per l’inserimento in blacklist degli ID

La causa più frequente di inserimento degli ID nella blacklist è l'errata integrazione tra l'infrastruttura cliente e Audience Manager. Quando identificate un ID inserito in blacklist, accertatevi di controllare accuratamente le integrazioni di Audience Manager. Consulta **Guide** all’implementazione e all’integrazione per informazioni dettagliate su come configurare Audience Manager per l’utilizzo con altre soluzioni Experience Cloud o con sistemi esterni.

Un'altra causa frequente di ID inseriti in blacklist sono i bot di indicizzazione (web crawler), che in genere causano un aumento del traffico, portando gli stessi ID a essere inviati più [!UICONTROL DCS] volte. Se identificate i bot di indicizzazione come il motivo della blacklist degli ID, dovrete limitare l’accesso ai bot al sito Web.

In caso di problemi di integrazione, non esitate a contattare l'Assistenza clienti. Prima di aprire una richiesta di assistenza, accertatevi di tenere pronto l’ `.har``HTTP` archivio del browser. Questo archivio aiuta il team di supporto a identificare il motivo per cui si è verificato l’inserimento in blacklist degli ID.