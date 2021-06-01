---
description: Il DCS controlla gli ID ricevuti e aggiunge ad un elenco Bloccati quelli che vengono inviati con una frequenza insolitamente alta in un breve periodo di tempo.
keywords: id;monitoraggio;dcs
seo-description: Il DCS controlla gli ID ricevuti e aggiunge ad un elenco Bloccati quelli che vengono inviati con una frequenza insolitamente alta in un breve periodo di tempo.
seo-title: Monitoraggio ID e Inserire nell'elenco Bloccati
solution: Audience Manager
title: Monitoraggio ID e Inserire nell'elenco Bloccati
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# Monitoraggio ID e Inserire nell&#39;elenco Bloccati

Il [!DNL DCS] controlla gli ID ricevuti e aggiunge ad un elenco Bloccati quelli che vengono inviati con una frequenza insolitamente alta in un breve periodo di tempo.

## Panoramica

Per proteggere l&#39;infrastruttura Audience Manager da attività dannose, il [!DNL DCS] utilizza un algoritmo avanzato per monitorare gli ID ricevuti. Possono essere [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) o [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Consulta [Indice degli ID in Audience Manager](../../../reference/ids-in-aam.md) per spiegazioni dettagliate sugli ID supportati dall&#39;Audience Manager.

Il [!DNL DCS] controlla la frequenza con cui riceve questi ID per rilevare potenziali attività dannose. Quando [!DNL DCS] rileva una quantità insolitamente elevata di richieste [!DNL DCS] per un determinato ID in un breve periodo di tempo, tale ID viene aggiunto a un elenco Bloccati.

## Codici di errore

Puoi identificare gli ID aggiunti a un elenco Bloccati dai codici di errore ricevuti da [!DNL DCS]. I codici di errore che potresti ricevere sono:

* 303 ID cliente bloccato;
* 306 ID dispositivo dichiarato bloccato;
* 307 Operazione di profilo bloccata per l&#39;ID.

Per informazioni dettagliate sui codici di errore che possono essere ricevuti, consulta [Codici di errore DCS, messaggi ed esempi](dcs-error-codes.md) .

## Rimozione di ID dagli elenchi Bloccati

Gli ID aggiunti agli elenchi Bloccati non devono essere utilizzati in richieste future, in quanto porteranno a segnalazioni di dati errate. Il [!DNL DCS] non supporta la rimozione degli ID dagli elenchi Bloccati.

## Impatto sulla sincronizzazione ID

[!DNL DCS] Le chiamate possono includere uno o più tipi di ID. Le chiamate contenenti un singolo ID vengono completamente ignorate se tale ID viene aggiunto a un elenco Bloccati e in questa situazione non si verifica alcuna sincronizzazione ID.

Quando una chiamata ID multipla include anche un ID inserita nell&#39;elenco Bloccati, [!DNL DCS] ignora l&#39;ID negato e utilizza solo gli ID consentiti rimanenti per la sincronizzazione.

## Cause e problemi risolti per la  Inserire nell&#39;elenco Bloccati ID

La causa più frequente dell’aggiunta degli ID agli elenchi Bloccati è l’integrazione errata tra l’infrastruttura del cliente e l’Audience Manager. Quando identifichi un ID inserita nell&#39;elenco Bloccati, assicurati di controllare accuratamente le integrazioni di Audience Manager. Consulta **Guide all&#39;implementazione e all&#39;integrazione** per spiegazioni dettagliate su come configurare Audience Manager per l&#39;utilizzo con altre soluzioni o sistemi esterni di Experience Cloud.

Un’altra causa frequente dell’aggiunta degli ID agli elenchi Bloccati sono i bot di indicizzazione (web crawler), che generalmente causano un aumento del traffico, e questo causa l’invio degli stessi ID a [!DNL DCS] più volte. Se identifichi i bot di indicizzazione come motivo per cui gli ID vengono aggiunti agli elenchi Bloccati, devi limitare l’accesso ai bot al tuo sito web.

In caso di problemi nell’identificazione dei problemi di integrazione, non esitare a contattare l’Assistenza clienti. Prima di aprire una richiesta di supporto, assicurati di tenere a portata di mano l’ archivio `.har` `HTTP` del browser. Questo archivio consente al team di supporto di identificare il motivo per cui l’ID è stato aggiunto a un elenco Bloccati.
