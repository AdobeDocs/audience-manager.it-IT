---
description: In questo documento viene illustrato come i dati del cliente sono gestiti in  Audience Manager.
seo-description: In questo documento viene illustrato come i dati dei clienti vengono gestiti in  Audience Manager.
seo-title: Governance dei dati
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Governance dei dati
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 1%

---


# Governance dei dati

## Panoramica {#overview}

La governance dei dati in  Audience Manager si riferisce al ciclo di vita dei dati dei clienti in  Audience Manager e include la [raccolta e l&#39;offuscamento di indirizzi](data-governance.md#collecting-ip-addresses)IP, la conservazione [dei](data-governance.md#data-retention)dati e i trasferimenti [](data-governance.md#data-transfers)transfrontalieri di dati.

## Raccolta di indirizzi IP e offuscamento indirizzi IP {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**Metodologia dell&#39;offuscamento IP:** In base ai principi di &quot;Privacy By Design&quot;,  Adobe Audience Manager consente ai clienti di abilitare l&#39; [!DNL IP] offuscamento dall&#39;interfaccia utente, sia a livello globale in tutte le aree geografiche che per specifici paesi. Quando attivate questa impostazione, l’ultimo ottetto (l’ultima parte) dell’ [!DNL IP] indirizzo viene eliminato immediatamente quando l’ [!DNL IP] indirizzo viene assimilato  Audience Manager.  Audience Manager scarta questa parte dell&#39; [!DNL IP] indirizzo prima dell&#39;elaborazione (compresa prima di qualsiasi ricerca geografica facoltativa o registrazione dell&#39; [!DNL IP] indirizzo). Ad esempio:

* Prima: `255.255.255.255`
* Dopo: `255.255.255.0`

>[!NOTE]
>
>Consultate [IP Address Obfuscation](../../features/administration/ip-obfuscation.md) (Oscuramento degli indirizzi IP) per apprendere come abilitare l&#39;offuscamento degli [!DNL IP] indirizzi nell&#39;interfaccia utente di Audience Manager .

Guardate il video seguente per comprendere come funziona l&#39;offuscamento [!DNL IP] dell&#39;indirizzo in  Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Segmentazione geografica:** Se abilitate l&#39;offuscamento [!DNL IP] dell&#39;indirizzo, gli ottetti rimanenti dell&#39; [!DNL IP] indirizzo possono ancora essere utilizzati per la segmentazione geografica e il reporting in  Audience Manager. Se non abilitate l&#39;offuscamento [!DNL IP] dell&#39;indirizzo,  Audience Manager utilizza l&#39; [!DNL IP] indirizzo completo. È possibile utilizzare la funzione di segmentazione geografica che consente di identificare una [!DNL IP] posizione per area geografica in entrambi i casi, ma con una leggera perdita di precisione quando si utilizza [!DNL IP] l&#39;offuscamento. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. L&#39;ottenimento di informazioni a livello di regione e di paese dovrebbe essere influenzato solo leggermente. I dati di segmentazione geografica sono granulari solo a livello di città o codice postale, e non a livello individuale. Ulteriori informazioni sul [geotargeting](../../features/traits/trait-geotarget-keys.md) e su come impostare caratteristiche con variabili geografiche.

## Conservazione dei dati in  Audience Manager {#data-retention}

L&#39;applicazione di criteri di conservazione dei dati appropriati, sicuri e tempestivi ai dati è una parte importante del rispetto delle normative sulla privacy dei dati.  clienti Audience Manager possono impostare periodi di conservazione personalizzati su caratteristiche e segmenti definendo il TTL (ora di vita) richiesto. Per ulteriori informazioni sui periodi di conservazione, consulta Domande frequenti [sulla conservazione dei](../../faq/faq-privacy.md) dati.

## Trasferimenti di dati transfrontalieri {#data-transfers}

Quando  Audience Manager trasferisce dati personali da Clienti oltre i confini nazionali,  Audience Manager lo fa in conformità con la legge applicabile. Per ulteriori informazioni, visitare il Centro [per la privacy di](https://www.adobe.com/privacy/eudatatransfers.html) Adobe.