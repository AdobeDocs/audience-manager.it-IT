---
description: Il DCS controlla gli ID ricevuti e aggiunge a un elenco di negazioni quelli inviati a un tasso insolitamente elevato in un breve periodo di tempo.
keywords: id;monitoring;dcs
seo-description: Il DCS controlla gli ID ricevuti e aggiunge a un elenco di negazioni quelli inviati a un tasso insolitamente elevato in un breve periodo di tempo.
seo-title: Monitoraggio ID e denylist
solution: Audience Manager
title: Monitoraggio ID e denylist
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Monitoraggio ID e denylist

Controlla [!DNL DCS] gli ID ricevuti e aggiunge a un elenco di negazioni quelli inviati a un tasso insolitamente elevato in un breve periodo di tempo.

## Panoramica

Per proteggere l&#39;infrastruttura Audience Manager  da attività dannose, l&#39;utente [!DNL DCS] utilizza un algoritmo avanzato per monitorare gli ID ricevuti. Questi possono essere [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulta [Indice degli ID in  Audience Manager](../../../reference/ids-in-aam.md) per una spiegazione dettagliata degli ID supportati da  Audience Manager.

Il [!DNL DCS] monitor controlla la frequenza con cui riceve questi ID per rilevare eventuali attività dannose. Quando [!DNL DCS] rileva un numero insolitamente elevato di [!DNL DCS] richieste per un determinato ID in un breve lasso di tempo, tale ID viene aggiunto a un elenco di negazioni.

## Codici di errore

È possibile identificare gli ID aggiunti a un elenco di negazioni tramite i codici di errore ricevuti da [!DNL DCS]. I codici di errore che potresti ricevere sono:

* 303: ID cliente bloccato;
* 306: ID dispositivo dichiarato bloccato;
* 307: Operazione profilo bloccato per ID.

Consulta Codici di errore [DCS, messaggi ed esempi](dcs-error-codes.md) per informazioni dettagliate sui codici di errore che potresti ricevere.

## Rimozione di ID dagli elenchi di negazioni

Gli ID che sono stati aggiunti per negare gli elenchi non devono essere utilizzati in richieste future, in quanto porteranno a una segnalazione di dati errata. L&#39;elenco [!DNL DCS] non supporta la rimozione degli ID dagli elenchi degli elenchi degli elenchi degli elenchi degli indirizzi non validi.

## Impatto sulla sincronizzazione ID

[!DNL DCS] le chiamate possono includere uno o più tipi di ID. Le chiamate contenenti un singolo ID vengono ignorate completamente se tale ID viene aggiunto a un elenco di negazioni e in questa situazione non viene eseguita la sincronizzazione ID.

Quando una chiamata con più ID include anche un ID elencato in modo non valido, l’ID [!DNL DCS] viene ignorato e per la sincronizzazione vengono utilizzati solo gli ID consentiti rimanenti.

## Cause e problemi risolti per l’esclusione degli ID

La causa più frequente di ID aggiunti per negare gli elenchi è l&#39;errata integrazione tra l&#39;infrastruttura cliente e  Audience Manager. Quando identificate un ID denylist, accertatevi di controllare accuratamente le integrazioni Audience Manager . Consultate **Guide** all’implementazione e all’integrazione per informazioni dettagliate su come configurare  Audience Manager per l’utilizzo con altre soluzioni  Experience Cloud o con sistemi esterni.

Un&#39;altra causa frequente di ID che vengono aggiunti per negare gli elenchi è rappresentata dai bot di indicizzazione (web crawler), che in genere causano un aumento del traffico e fanno sì che gli stessi ID vengano inviati più [!DNL DCS] volte. Se identificate i bot di indicizzazione come il motivo per cui gli ID vengono aggiunti agli elenchi di negazione, dovrete limitare l&#39;accesso ai bot al sito Web.

In caso di problemi di integrazione, non esitate a contattare l&#39;Assistenza clienti. Prima di aprire una richiesta di assistenza, accertatevi di tenere pronto l’ `.har``HTTP` archivio del browser. Questo archivio aiuta il team di assistenza a identificare il motivo per cui l’ID è stato aggiunto a un elenco di negazioni.