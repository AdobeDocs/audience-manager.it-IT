---
description: In questo documento viene illustrato come i dati dei clienti vengono gestiti in Audience Manager.
seo-description: Questo documento spiega come i dati dei clienti vengono gestiti in Audience Manager.
seo-title: Governance dei dati
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Governance dei dati
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# Governance dei dati

## Panoramica {#overview}

La governance dei dati in Audience Manager si riferisce al ciclo di vita dei dati dei clienti in Audience Manager e include la [raccolta e l'offuscamento di indirizzi](data-governance.md#collecting-ip-addresses)IP, la conservazione [dei](data-governance.md#data-retention)dati e i trasferimenti [di dati](data-governance.md#data-transfers)transfrontalieri.

## Raccolta di indirizzi IP e offuscamento indirizzi IP {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** Metodologia di offuscamento IP: In base ai principi di "Privacy By Design", Adobe Audience Manager consente ai clienti di abilitare l’ [!DNL IP] offuscamento dall’interfaccia utente, sia a livello globale che in tutte le aree geografiche o per specifici paesi. Quando abilitate questa impostazione, l’ultimo ottetto (l’ultima parte) dell’ [!DNL IP] indirizzo viene eliminato immediatamente quando l’ [!DNL IP] indirizzo viene assimilato in Audience Manager. Audience Manager elimina questa parte dell' [!DNL IP] indirizzo prima dell'elaborazione (inclusa la prima di qualsiasi ricerca geografica facoltativa o registrazione dell' [!DNL IP] indirizzo). Ad esempio:

* Prima: `255.255.255.255`
* Dopo: `255.255.255.0`

>[!NOTE]
>
>Consulta [IP Address Obfuscation](../../features/administration/ip-obfuscation.md) (Oscuramento degli indirizzi IP) per informazioni su come abilitare l'offuscamento degli [!DNL IP] indirizzi nell'interfaccia utente di Audience Manager.

Guardate il video seguente per comprendere come funziona l'offuscamento [!DNL IP] degli indirizzi in Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=ita)

**** Segmentazione geografica: Se abilitate l'offuscamento [!DNL IP] dell'indirizzo, gli ottetti rimanenti dell' [!DNL IP] indirizzo possono ancora essere utilizzati per la segmentazione geografica e il reporting in Audience Manager. Se non abilitate l'offuscamento [!DNL IP] degli indirizzi, Audience Manager utilizza l' [!DNL IP] indirizzo completo. È possibile utilizzare la funzione di segmentazione geografica che consente di identificare una [!DNL IP] posizione per area geografica in entrambi i casi, ma con una leggera perdita di precisione quando si utilizza [!DNL IP] l'offuscamento. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. L'ottenimento di informazioni a livello di regione e di paese dovrebbe essere influenzato solo leggermente. I dati di segmentazione geografica sono granulari solo a livello di città o codice postale, e non a livello individuale. Ulteriori informazioni sul [geotargeting](../../features/traits/trait-geotarget-keys.md) e su come impostare caratteristiche con variabili geografiche.

## Conservazione dei dati in Audience Manager {#data-retention}

L'applicazione di criteri di conservazione dei dati appropriati, sicuri e tempestivi ai dati è una parte importante del rispetto delle normative sulla privacy dei dati. I clienti di Audience Manager possono impostare periodi di conservazione personalizzati su caratteristiche e segmenti definendo il TTL (ora di vivere) richiesto. Per ulteriori informazioni sui periodi di conservazione, consulta Domande frequenti [sulla conservazione dei](../../faq/faq-privacy.md) dati.

## Trasferimenti di dati transfrontalieri {#data-transfers}

Quando Audience Manager trasferisce dati personali dai clienti oltre i confini nazionali, Audience Manager lo fa in conformità con la legge applicabile. Per ulteriori informazioni, visitare l' [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) .