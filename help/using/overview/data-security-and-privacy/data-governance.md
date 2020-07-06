---
description: Questo documento spiega come i dati dei clienti vengono gestiti in Audience Manager.
seo-description: Questo documento spiega come i dati dei clienti vengono gestiti in Audience Manager.
seo-title: Governance dei dati
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Governance dei dati
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 96%

---


# Governance dei dati

## Panoramica {#overview}

La governance dei dati in Audience Manager si riferisce al ciclo di vita dei dati dei clienti in Audience Manager e include la [raccolta e offuscamento di indirizzi IP](data-governance.md#collecting-ip-addresses), la [conservazione dei dati](data-governance.md#data-retention) e i [trasferimenti di dati transfrontalieri](data-governance.md#data-transfers).

## Raccolta e offuscamento di indirizzi IP {#collecting-ip-addresses}

L’indirizzo [!DNL IP] di un visitatore di un sito web del cliente viene trasmesso a un [!DNL Data Processing Center] di Adobe ([!DNL DPC]), dove l’indirizzo [!DNL IP] può essere archiviato. In base alla configurazione di rete per il visitatore, l’indirizzo [!DNL IP] non rappresenta necessariamente l’indirizzo [!DNL IP] del computer del visitatore. Ad esempio, l’indirizzo [!DNL IP] potrebbe essere l’indirizzo [!DNL IP] esterno di un firewall con NAT (Network Address Translation), di un proxy [!DNL HTTP] o di un gateway Internet.

**Metodologia di offuscamento dell’IP:** in base ai principi di “Privacy By Design”, Adobe Audience Manager consente ai clienti di abilitare l’offuscamento dell’[!DNL IP] dall’interfaccia utente, sia a livello globale in tutte le aree geografiche che per specifici paesi. Quando abiliti questa impostazione, l’ultimo ottetto (l’ultima parte) dell’indirizzo [!DNL IP] viene eliminato immediatamente quando l’indirizzo [!DNL IP] viene acquisito in Audience Manager. Audience Manager elimina questa parte dell’indirizzo [!DNL IP] prima dell’elaborazione (incluso prima di qualsiasi ricerca geografica facoltativa o registrazione dell’indirizzo [!DNL IP]). Ad esempio:

* Prima: `255.255.255.255`
* Dopo: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](../../features/administration/ip-obfuscation.md) to learn how to enable [!DNL IP] address obfuscation in the Audience Manager user interface.

Guarda il video seguente per comprendere come funziona l’offuscamento degli indirizzi [!DNL IP] in Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Segmentazione geografica:** se abiliti l’offuscamento dell’indirizzo [!DNL IP], gli ottetti rimanenti dell’ indirizzo [!DNL IP] possono ancora essere utilizzati per la segmentazione geografica e il reporting in Audience Manager. Se non abiliti l’offuscamento dell’indirizzo [!DNL IP], Audience Manager utilizza l’indirizzo [!DNL IP] completo. Puoi utilizzare la funzione di segmentazione geografica, che ti consente di identificare una posizione [!DNL IP] per area geografica in entrambi i casi, ma con una leggera perdita di precisione quando utilizzi [!DNL IP] l’offuscamento. L’ottenimento di informazioni a livello di città sarà probabilmente influenzato in modo significativo dall’offuscamento dell’indirizzo [!DNL IP]. L’ottenimento di informazioni a livello di area geografica e nazione dovrebbe essere influenzato solo leggermente. I dati di segmentazione geografica sono granulari solo a livello di città o di codice postale e non a livello di singoli utenti. Leggi di più sul [geotargeting](../../features/traits/trait-geotarget-keys.md) e su come impostare caratteristiche con variabili geografiche.

## Conservazione dei dati in Audience Manager {#data-retention}

L’applicazione di policy di conservazione dei dati appropriate, sicure e tempestive ai tuoi dati è una parte importante del rispetto delle normative sulla privacy dei dati. I clienti di Audience Manager possono impostare periodi di conservazione personalizzati per caratteristiche e segmenti definendo il TTL (time-to-live) richiesto. Per ulteriori informazioni sui periodi di conservazione, consulta [Data Retention FAQ](../../faq/faq-privacy.md).

## Trasferimenti di dati transfrontalieri {#data-transfers}

Quando Audience Manager trasferisce dati personali dai clienti oltre i confini nazionali, lo fa in conformità alla legge applicabile. Per ulteriori informazioni, visita il [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy/eudatatransfers.html).