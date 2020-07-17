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

Controlla [!DNL DCS] gli ID ricevuti e aggiunge a un elenco Bloccati  quelli inviati a un tasso insolitamente elevato in un breve periodo di tempo.

## Panoramica

Per proteggere l&#39;infrastruttura Audience Manager  da attività dannose, l&#39;utente [!DNL DCS] utilizza un algoritmo avanzato per monitorare gli ID ricevuti. Questi possono essere [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulta [Indice degli ID in  Audience Manager](../../../reference/ids-in-aam.md) per una spiegazione dettagliata degli ID supportati da  Audience Manager.

Il [!DNL DCS] monitor controlla la frequenza con cui riceve questi ID per rilevare eventuali attività dannose. Quando [!DNL DCS] rileva un numero insolitamente elevato di [!DNL DCS] richieste per un determinato ID in un breve lasso di tempo, tale ID viene aggiunto a un elenco Bloccati .

## Codici di errore

È possibile identificare gli ID aggiunti a un elenco Bloccati  dai codici di errore ricevuti dall&#39;utente [!DNL DCS]. I codici di errore che potresti ricevere sono:

* 303: ID cliente bloccato;
* 306: ID dispositivo dichiarato bloccato;
* 307: Operazione profilo bloccato per ID.

Consulta Codici di errore [DCS, messaggi ed esempi](dcs-error-codes.md) per informazioni dettagliate sui codici di errore che potresti ricevere.

## Rimozione di ID da  elenchi Bloccati

Gli ID che sono stati aggiunti  elenchi Bloccati non devono essere utilizzati in richieste future, in quanto porteranno a una segnalazione di dati errata. L&#39;impostazione [!DNL DCS] non supporta la rimozione degli ID dai elenchi Bloccati .

## Impatto sulla sincronizzazione ID

[!DNL DCS] le chiamate possono includere uno o più tipi di ID. Le chiamate contenenti un singolo ID vengono ignorate completamente se l’ID viene aggiunto a un elenco Bloccati  e in questa situazione non viene eseguita la sincronizzazione ID.

Quando una chiamata con ID multiplo include anche un ID inserita nell&#39;elenco Bloccati, l’ [!DNL DCS] ID negato viene ignorato e utilizza solo gli ID consentiti rimanenti per la sincronizzazione.

## Cause e problemi risolti per l’Inserire nell&#39;elenco Bloccati ID

La causa più frequente di ID aggiunti ai elenchi Bloccati  è l&#39;errata integrazione tra l&#39;infrastruttura cliente e  Audience Manager. Quando identificate un ID inserita nell&#39;elenco Bloccati, accertatevi di controllare accuratamente le integrazioni Audience Manager . Consultate **Guide** all’implementazione e all’integrazione per informazioni dettagliate su come configurare  Audience Manager per l’utilizzo con altre soluzioni  Experience Cloud o con sistemi esterni.

Un&#39;altra causa frequente di ID che vengono aggiunti agli elenchi Bloccati  sono i bot di indicizzazione (web crawler), che in genere causano un aumento del traffico, portando gli stessi ID a essere inviati più volte [!DNL DCS] . Se identificate i bot di indicizzazione come il motivo per cui gli ID vengono aggiunti  elenchi Bloccati, dovete limitare l&#39;accesso ai bot al sito Web.

In caso di problemi di integrazione, non esitate a contattare l&#39;Assistenza clienti. Prima di aprire una richiesta di assistenza, accertatevi di tenere pronto l’ `.har``HTTP` archivio del browser. Questo archivio aiuta il team di assistenza a identificare il motivo per cui l’ID è stato aggiunto a un elenco Bloccati .