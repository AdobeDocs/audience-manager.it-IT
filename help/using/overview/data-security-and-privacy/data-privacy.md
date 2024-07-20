---
description: Descrive l’integrazione di Audience Manager e la conformità alle best practice generalmente accettate relative alla privacy dei consumatori e alle procedure di rinuncia.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: Panoramica sulla privacy dei dati
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 52%

---

# Panoramica sulla privacy dei dati {#data-privacy}

## Panoramica

La documentazione sulla Privacy dei dati descrive l&#39;integrazione di [!DNL Audience Manager] e la conformità alle best practice generalmente accettate relative alla privacy dei consumatori e alle procedure di rinuncia.

[!DNL Audience Manager] riconosce l&#39;importanza della relazione tra i consumatori e i brand online con cui interagiscono. Entrambe le parti beneficiano dello scambio trasparente di dati pseudonimi:

* I consumatori ricevono contenuti personalizzati, offerte di prodotti scontati ed esperienze utente semplificate.
* I brand ricevono flussi di entrate fondamentali che supportano più modelli di business online.

In linea con il nostro continuo supporto di questo modello, [!DNL Audience Manager] si impegna a fornirti gli strumenti per aiutarti a offrire trasparenza e controllo ai tuoi consumatori e al tempo stesso proporre annunci personalizzati nel rispetto dei [principi di autoregolamentazione di Online Behavioral Advertising (OBA)](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

Il [Regolamento generale sulla protezione dei dati (RGPD)](https://gdpr.eu/data-privacy/) ha introdotto diversi nuovi diritti riguardanti la privacy dei dati per i membri dell’Unione europea, tra cui il **diritto di accesso** e il **diritto all’oblio**. Ciò significa che qualsiasi cittadino di [!DNL EU] i cui dati personali sono stati raccolti dalla tua azienda può richiedere l&#39;accesso o la cancellazione dei propri dati in qualsiasi momento. Il mancato rispetto di queste richieste può comportare multe di milioni di dollari per la tua organizzazione.

Per rispettare [!DNL GDPR], [!DNL Audience Manager] supporta l&#39;accesso ai dati e l&#39;eliminazione di [richieste](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

Il [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), entrato in vigore il 1° gennaio 2020, conferisce ai residenti californiani nuovi diritti in merito alle loro informazioni personali e impone responsabilità in materia di protezione dei dati a determinate entità che conducono attività commerciali in California.

[!DNL CCPA] offre nuovi diritti sulla privacy dei dati ai residenti della California, incluso il diritto di accesso e cancellazione dei propri dati personali e di sapere se i propri dati personali vengono venduti o divulgati (e a chi). Per rispettare [!DNL CCPA], [!DNL Audience Manager] supporta l&#39;accesso [!DNL CCPA] e l&#39;eliminazione di [richieste](data-privacy-requests.md).

Per ulteriori informazioni, consulta il [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy/opt-out.html).

## Conformità alle normative {#compliance}

[!DNL Audience Manager] ti aiuta a rispettare gli obblighi derivanti da determinate normative sulla privacy, attraverso strumenti per la privacy come [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) per le richieste di accesso e cancellazione dei dati.

Questo servizio fornisce una [!DNL RESTful API] e un’interfaccia utente che facilitano la gestione delle richieste dei clienti relative ai dati. Tramite il [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en), puoi inviare richieste di accesso e cancellazione dei dati in base a una richiesta di un singolo consumatore, in modo da automatizzare questa parte degli obblighi di conformità.

Mentre le richieste di accesso e di eliminazione dei dati vengono gestite tramite Privacy Service, [le richieste di rinuncia](data-privacy-requests.md#opt-out-requests) sono attualmente supportate tramite l&#39;API [DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Per ulteriori informazioni, consulta [Data Privacy Requests](data-privacy-requests.md).

## Concetti correlati {#related-concepts}

* [Richieste sulla privacy dei dati](data-privacy-requests.md)
* [Gestione del consenso](data-privacy-consent.md)
* [Plug-in di Audience Manager per IAB TCF](aam-iab-plugin.md)
* [Identificatori Audience Manager](data-privacy-ids.md)
* [Glossario CCPA](aam-ccpa-glossary.md)
* [Glossario RGPD](aam-gdpr-glossary.md)
* [Considerazioni sul RGPD per le destinazioni](aam-gdpr-partners.md)
* [Guida di preparazione al RGPD per i clienti di Audience Manager](aam-gdpr-readiness.md)
* [Governance dei dati](data-governance.md)
* [Domande frequenti sulla privacy e sulla conservazione dei dati](../../faq/faq-privacy.md)
