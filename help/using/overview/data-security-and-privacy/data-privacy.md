---
description: Descrive l’integrazione di Audience Manager e la conformità alle best practice generalmente accettate relative alla privacy dei consumatori e alle procedure di rinuncia.
seo-description: Descrive l’integrazione di Audience Manager e la conformità alle best practice generalmente accettate relative alla privacy dei consumatori e alle procedure di rinuncia.
seo-title: Panoramica sulla privacy dei dati
solution: Audience Manager
title: Panoramica sulla privacy dei dati
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 78%

---


# Panoramica sulla privacy dei dati {#data-privacy}

## Panoramica

The Data Privacy documentation describes [!DNL Audience Manager] integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

[!DNL Audience Manager] riconosce l’importanza della relazione tra i consumatori e i brand online con cui interagiscono. Entrambe le parti beneficiano dello scambio trasparente di dati pseudonimi:

* I consumatori ricevono contenuti personalizzati, offerte di prodotti scontati ed esperienze utente semplificate.
* I brand ricevono flussi di entrate fondamentali che supportano più modelli di business online.

In our continuing support of this model, [!DNL Audience Manager] remains committed to providing you with the tools to help support your ability to provide  transparency and control to your consumers, while delivering personalized ads subject to the [Online Behavioral Advertising (OBA) Self-Regulatory Principles](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

Il [Regolamento generale sulla protezione dei dati (RGPD)](https://eugdpr.org/) ha introdotto diversi nuovi diritti riguardanti la privacy dei dati per i membri dell’Unione europea, tra cui il **diritto di accesso** e il **diritto all’oblio**. This means that any [!DNL EU] citizen whose personal data has been collected by your business can request to access or delete their data at any time. Il mancato rispetto di queste richieste può comportare multe di milioni di dollari per la tua organizzazione.

To comply with [!DNL GDPR], [!DNL Audience Manager] supports data access and delete [requests](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

Il [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), entrato in vigore il 1° gennaio 2020, conferisce ai residenti californiani nuovi diritti in merito alle loro informazioni personali e impone responsabilità in materia di protezione dei dati a determinate entità che conducono attività commerciali in California.

[!DNL CCPA]Il fornisce nuovi diritti sulla privacy dei dati ai residenti della California, compreso il diritto di accesso e cancellazione dei propri dati personali e di sapere se essi sono venduti o divulgati (e a chi). To comply with [!DNL CCPA], [!DNL Audience Manager] supports [!DNL CCPA] access and delete [requests](data-privacy-requests.md).

Per ulteriori informazioni, consulta il [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy/opt-out.html).

## Rispetto delle normative {#compliance}

[!DNL Audience Manager] ti aiuta a rispettare gli obblighi derivanti da determinate normative sulla privacy attraverso strumenti per la privacy, come l’[Adobe Experience Platform Privacy Service](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html) per le richieste di accesso e cancellazione dei dati.

Questo servizio fornisce una [!DNL RESTful API] e un’interfaccia utente che facilitano la gestione delle richieste dei clienti relative ai dati. Tramite il [Privacy Service](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html), puoi inviare richieste di accesso e cancellazione dei dati in base a una richiesta di un singolo consumatore, in modo da automatizzare questa parte degli obblighi di conformità.

Mentre le richieste di accesso e cancellazione dei dati vengono gestite tramite [Privacy Service](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html), le [richieste di rinuncia](data-privacy-requests.md#opt-out-requests) sono attualmente supportate tramite l’[API DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Per ulteriori informazioni, consulta [Data Privacy Requests](data-privacy-requests.md).

## Concetti correlati {#related-concepts}

* [Data Privacy Requests](data-privacy-requests.md)
* [Consent Management](data-privacy-consent.md)
* [Audience Manager Plug-in for IAB TCF](aam-iab-plugin.md)
* [Audience Manager Identifiers](data-privacy-ids.md)
* [CCPA Glossary](aam-ccpa-glossary.md)
* [RGPD Glossary](aam-gdpr-glossary.md)
* [RGPD Considerations for Destinations](aam-gdpr-partners.md)
* [RGPD Readiness Guidance for Audience Manager Customers](aam-gdpr-readiness.md)
* [Data Governance](data-governance.md)
* [Privacy and Data Retention FAQ](../../faq/faq-privacy.md)