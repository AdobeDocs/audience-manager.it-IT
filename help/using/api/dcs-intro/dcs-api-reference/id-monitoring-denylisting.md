---
description: Il DCS controlla gli ID ricevuti e aggiunge a un elenco Bloccati  quelli inviati a un tasso eccezionalmente elevato in un breve periodo di tempo.
keywords: id;monitoring;dcs
seo-description: Il DCS controlla gli ID ricevuti e aggiunge a un elenco Bloccati  quelli inviati a un tasso eccezionalmente elevato in un breve periodo di tempo.
seo-title: Monitoraggio e Inserire nell'elenco Bloccati ID
solution: Audience Manager
title: Monitoraggio e Inserire nell'elenco Bloccati ID
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Monitoraggio e Inserire nell&#39;elenco Bloccati ID

Il [!DNL DCS] controlla gli ID ricevuti e aggiunge a un elenco Bloccati  quelli inviati a un tasso insolitamente elevato in un breve periodo di tempo.

## Panoramica

Per proteggere l&#39;infrastruttura del Audience Manager  da attività dannose, [!DNL DCS] utilizza un algoritmo avanzato per monitorare gli ID ricevuti. Possono essere [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulta [Indice degli ID in  Audience Manager](../../../reference/ids-in-aam.md) per informazioni dettagliate sugli ID supportati dal Audience Manager .

Il [!DNL DCS] controlla la frequenza con cui riceve questi ID per rilevare eventuali attività dannose. Quando [!DNL DCS] rileva una quantità insolitamente elevata di [!DNL DCS] richieste per un dato ID in poco tempo, tale ID viene aggiunto a un elenco Bloccati .

## Codici di errore

È possibile identificare gli ID aggiunti a un elenco Bloccati  dai codici di errore ricevuti da [!DNL DCS]. I codici di errore che potresti ricevere sono:

* 303: ID cliente bloccato;
* 306: ID dispositivo dichiarato bloccato;
* 307: Operazione profilo bloccato per ID.

Per informazioni dettagliate sui codici di errore che possono essere ricevuti, vedere [Codici di errore DCS, messaggi ed esempi](dcs-error-codes.md).

## Rimozione di ID da  elenchi Bloccati

Gli ID che sono stati aggiunti  elenchi Bloccati non devono essere utilizzati in richieste future, in quanto porteranno a una segnalazione di dati errata. La [!DNL DCS] non supporta la rimozione degli ID da  elenchi Bloccati.

## Impatto sulla sincronizzazione ID

[!DNL DCS] le chiamate possono includere uno o più tipi di ID. Le chiamate contenenti un singolo ID vengono ignorate completamente se l’ID viene aggiunto a un elenco Bloccati  e in questa situazione non viene eseguita la sincronizzazione ID.

Quando una chiamata ID multipla include anche un ID inserita nell&#39;elenco Bloccati, l&#39; [!DNL DCS] ignora l&#39;ID negato e utilizza solo gli ID consentiti rimanenti per la sincronizzazione.

## Cause e problemi risolti per l’Inserire nell&#39;elenco Bloccati ID

La causa più frequente di ID aggiunti ai elenchi Bloccati  è l&#39;errata integrazione tra l&#39;infrastruttura del cliente e  Audience Manager. Quando identificate un ID inserita nell&#39;elenco Bloccati, accertatevi di controllare accuratamente le integrazioni del Audience Manager . Per informazioni dettagliate su come configurare  Audience Manager per l&#39;utilizzo con altre soluzioni  Experienci Cloud o sistemi esterni, vedere **Guide all&#39;implementazione e all&#39;integrazione**.

Un&#39;altra causa frequente di ID che vengono aggiunti agli elenchi Bloccati  sono i bot di indicizzazione (web crawler), che in genere causano un aumento del traffico, portando gli stessi ID a essere inviati più volte a [!DNL DCS]. Se identificate i bot di indicizzazione come il motivo per cui gli ID vengono aggiunti  elenchi Bloccati, dovete limitare l&#39;accesso ai bot al sito Web.

In caso di problemi di integrazione, non esitate a contattare l&#39;Assistenza clienti. Prima di aprire una richiesta di assistenza, accertatevi di tenere pronto l&#39;archivio `.har` `HTTP` del browser. Questo archivio aiuta il team di assistenza a identificare il motivo per cui l’ID è stato aggiunto a un elenco Bloccati .