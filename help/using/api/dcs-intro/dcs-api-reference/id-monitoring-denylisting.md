---
description: Il DCS monitora gli ID ricevuti e aggiunge a un elenco Bloccati quelli che vengono inviati con una frequenza insolitamente alta in un breve periodo di tempo.
keywords: id;monitoraggio;dcs;id;monitoring;dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: Monitoraggio degli ID e Inserisce nell'elenco Bloccati dei
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Monitoraggio degli ID e Inserisce nell&#39;elenco Bloccati dei

[!DNL DCS] controlla gli ID ricevuti e aggiunge a un elenco Bloccati quelli che vengono inviati con una frequenza insolitamente alta in un breve periodo di tempo.

## Panoramica

Per proteggere l&#39;infrastruttura Audience Manager da attività dannose, [!DNL DCS] utilizza un algoritmo avanzato per monitorare gli ID ricevuti. Possono essere [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Per informazioni dettagliate sugli ID supportati da Audience Manager, consulta [Indice degli ID in Audience Manager](../../../reference/ids-in-aam.md).

[!DNL DCS] controlla la frequenza con cui riceve questi ID per rilevare potenziali attività dannose. Quando [!DNL DCS] rileva una quantità insolitamente elevata di [!DNL DCS] richieste per un determinato ID in un breve periodo di tempo, tale ID viene aggiunto a un elenco Bloccati.

## Codici errore

È possibile identificare gli ID aggiunti a un elenco Bloccati dai codici di errore ricevuti da [!DNL DCS]. I codici di errore che potresti ricevere sono:

* 303: ID cliente bloccato;
* 306: ID dispositivo dichiarato bloccato;
* 307: operazione profilo bloccata per ID.

Consulta [Codici errore DCS, messaggi ed esempi](dcs-error-codes.md) per informazioni dettagliate sui codici di errore che potresti ricevere.

## Rimozione degli ID dagli elenchi Bloccati

Gli ID che sono stati aggiunti agli elenchi Bloccati non devono essere utilizzati in eventuali richieste future, in quanto porteranno a una segnalazione di dati errata. [!DNL DCS] non supporta la rimozione degli ID dagli elenchi Bloccati.

## Impatto sulla sincronizzazione ID

[!DNL DCS] chiamate possono includere uno o più tipi di ID. Le chiamate contenenti un singolo ID vengono completamente ignorate se tale ID viene aggiunto a un elenco Bloccati e in questa situazione non si verifica alcuna sincronizzazione ID.

Inserire nell&#39;elenco Bloccati Quando una chiamata ID multipla include anche un ID, [!DNL DCS] ignora l&#39;ID negato e utilizza solo gli ID consentiti rimanenti per la sincronizzazione.

## Cause e correzioni per la Inserisce nell&#39;elenco Bloccati dell’ID di

La causa più frequente dell’aggiunta degli ID agli elenchi Bloccati è l’integrazione non corretta tra l’infrastruttura del cliente e Audience Manager. Inserire nell&#39;elenco Bloccati Quando identifichi un ID, assicurati di rivedere attentamente le integrazioni Audience Manager. Consulta **Guide all&#39;implementazione e all&#39;integrazione** per informazioni dettagliate su come configurare Audience Manager per l&#39;utilizzo con altre soluzioni Experience Cloud o con sistemi esterni.

Un&#39;altra causa frequente di aggiunta degli ID agli elenchi Bloccati sono i bot di indicizzazione (crawler web), che in genere causano un aumento del traffico e portano all&#39;invio degli stessi ID a [!DNL DCS] più volte. Se identifichi nei bot di indicizzazione il motivo per cui gli ID vengono aggiunti agli elenchi Bloccati, devi limitare l’accesso dei bot al sito web.

Se hai difficoltà a identificare i problemi di integrazione, non esitare a contattare l’Assistenza clienti. Prima di aprire una richiesta di supporto, assicurarsi di mantenere pronto l&#39;archivio `.har` `HTTP` del browser. Questo archivio aiuta il team di supporto a identificare il motivo per cui l’ID è stato aggiunto a un elenco Bloccati.
