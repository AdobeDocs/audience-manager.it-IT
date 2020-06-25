---
description: Questo documento spiega come funziona la gestione del consenso in  Audience Manager.
seo-description: Questo documento spiega come funziona la gestione del consenso in  Audience Manager.
seo-title: Gestione del consenso
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Gestione del consenso
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---


# Gestione del consenso

## Panoramica {#overview}

Nei casi in cui è necessario il consenso per determinate attività di marketing,  clienti Audience Manager devono determinare l&#39;ambito e se è necessario aggiornare alcuni assetti per poter continuare a utilizzare i dati in futuro.

 Audience Manager offre strumenti che consentono di ottenere il consenso richiesto dagli utenti, in modo da offrire loro esperienze personalizzate su tutti i canali.

>[!IMPORTANT]
>
> Il contenuto del presente documento non è un parere giuridico e non è destinato a sostituire la consulenza legale.
>
> In qualità di titolare del trattamento, Adobe non è in grado di fornire consulenza legale per ottenere il consenso. Puoi anche considerare la possibilità di lavorare con un provider di soluzioni per la gestione del consenso, come [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) o [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), e consultare l&#39;ufficio legale della tua azienda per consigli su consenso e pratiche al momento della configurazione dell&#39;implementazione di consenso.

##  servizio di consenso Experience Cloud

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) lets you set up protocols for the visitor to assist you in determining if you can set a cookie on the individual&#39;s device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

Il [servizio](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) di consenso Experience Cloud consente inoltre di impostare i protocolli da integrare con il Platform (CMP) di gestione dei contenuti e con i sistemi esistenti nel progetto più ampio.

## Gestione del consenso/ottenimento del consenso

 clienti Audience Manager possono memorizzare il consenso degli utenti per vari casi d’uso, ad esempio pubblicità o personalizzazione come caratteristiche in  Audience Manager. I segmenti creati con queste caratteristiche includeranno quindi solo gli utenti che forniscono il rispettivo consenso per ciascuno di questi casi di utilizzo. L&#39;utilizzo di questo approccio non interrompe la raccolta dei dati, ma influisce solo sull&#39;utilizzo dei dati quando invii segmenti per l&#39;attivazione. Quando gli utenti ritirano il loro consenso, potete rimuovere queste caratteristiche dal profilo utente utilizzando il processo [batch di](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) ingresso di Audience Manager  o  processo di rifiuto di Audience Manager come descritto di seguito.

## Gestione del rifiuto/ritiro del consenso

Il rifiuto può essere gestito per Adobe Experience Cloud tramite la pagina [delle scelte](https://www.adobe.com/privacy/opt-out.html#customeruse) sulla privacy. Le funzioni con un solo clic consentono agli utenti finali di controllare e rifiutare la raccolta di dati da parte delle soluzioni pubblicitarie Adobe Experience Cloud (incluso  Audience Manager). Nello specifico, consulta la sezione [del cliente](https://www.adobe.com/privacy/opt-out.html#customeruse) aziendale della pagina Privacy Choices. Per i browser che non supportano i cookie di terze parti, consulta Destinazione [ID](../../features/declared-ids.md#declared-id-targeting)dichiarato. Per i dispositivi mobili, recuperate gli identificatori  Audience Manager pertinenti e chiamate le API di rifiuto  Audience Manager come indicato negli esempi [di rifiuto ID](../../features/declared-ids.md#opt-out-examples)dichiarato. Di conseguenza, puoi interrompere la raccolta di dati per tali utenti con le API di rifiuto dall&#39;SDK di Mobile. Consulta Dispositivi [](https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html) Android e dispositivi [](https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html)iOS. Puoi trovare ulteriori dettagli per l’opzione di rifiuto nella Documentazione [sulle richieste di privacy dei](../../overview/data-security-and-privacy/data-privacy-requests.md)dati.

## Gestione del consenso per i partner di seconda parte

I partner di seconda parte sono in genere anche soggetti incaricati del trattamento dei dati e possiedono la procedura per ottenere il consenso necessario da parte dell&#39;interessato per condividere i dati con i partner di dati di seconda parte. È responsabilità dell&#39;utente, in quanto cliente Audience Manager , determinare se il partner di seconda parte ha ottenuto il consenso necessario per il caso d&#39;uso. Ulteriori dettagli su come ottenere il consenso sono trattati sopra.

## Gestione del consenso per  partner di terze parti Audience Marketplace

 partner di Audience Marketplace di terze parti sono anche i Controllori dati e possiedono il proprio processo per ottenere il consenso e gestire le richieste di accesso/eliminazione/correzione. Adobe richiede in modo proattivo che  partner di Audience Marketplace di terze parti aggiornino le informazioni sul profilo aziendale all&#39;interno di [Adobe Audience Finder](https://www.adobe-audience-finder.com/) con informazioni aggiuntive sulla raccolta dei dati utente. Le informazioni verranno fornite dai  partner Audience Marketplace di terze parti e saranno aggiornate regolarmente. Tuttavia, spetta a ciascun  cliente Audience Manager determinare che il  partner di terze parti Audience Marketplace ha ottenuto il consenso necessario per il caso di utilizzo del cliente. Adobe non esprime osservazioni sull&#39;ambito o sulla validità del consenso ottenuto o segnalato da un  partner di Audience Marketplace di terze parti per un dato caso di utilizzo.
