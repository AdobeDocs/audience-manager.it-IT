---
description: Questo documento spiega come funziona la gestione del consenso in Audience Manager.
seo-description: Questo documento spiega come funziona la gestione del consenso in Audience Manager.
seo-title: Gestione del consenso
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Gestione del consenso
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: fbe4e8c912093c495f27ca887a44ac31d394811a

---


# Gestione del consenso

## Panoramica {#overview}

Nei casi in cui è necessario il consenso per determinate attività di marketing, il consenso dei consumatori deve essere attivo (ad esempio, non devono essere sottoposte a pre-controllo o a silenzio per consenso), disaggregato e le offerte di servizi non possono essere subordinate al consenso dell'interessato. Potrebbero addirittura verificarsi casi in cui è necessario aggiornare alcuni assetti per poter continuare a utilizzare i dati in corso di elaborazione.

Audience Manager offre gli strumenti necessari per ottenere il consenso richiesto dagli utenti, in modo da poter fornire loro esperienze personalizzate tra i canali.

>[!IMPORTANT]
>
> Il contenuto del presente documento non è un parere giuridico e non è destinato a sostituire la consulenza legale.
>
> In qualità di titolare del trattamento, Adobe non è in grado di fornire consulenza legale per ottenere il consenso. Consigliamo di lavorare con un provider di soluzioni per la gestione del consenso, come [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) o [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), per ricevere le migliori raccomandazioni e di consultare l'ufficio legale della tua azienda per consigli su consenso e pratiche al momento della configurazione dell'implementazione di consenso.

## Servizio di consenso Experience Cloud

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) service lets you set up protocols for the visitor to determine if you can set a cookie on the user's device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

Il servizio [di consenso di](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) Experience Cloud consente inoltre di impostare i protocolli da integrare con la piattaforma di gestione dei contenuti (CMP) e i sistemi esistenti come parte di un progetto più ampio.

## Gestione del consenso/ottenimento del consenso

I clienti di Audience Manager possono memorizzare il consenso degli utenti per vari casi d’uso, ad esempio pubblicità o personalizzazione come caratteristiche in Audience Manager. La creazione di segmenti con queste caratteristiche includerà quindi solo gli utenti che forniscono il rispettivo consenso per ciascuno di questi casi d'uso. L'utilizzo di questo approccio non interrompe la raccolta dei dati, ma influisce solo sull'utilizzo dei dati quando invii segmenti per l'attivazione. Quando gli utenti revocano il loro consenso, puoi rimuovere queste caratteristiche dal profilo utente utilizzando il processo [batch in](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) entrata di Audience Manager o il processo di rifiuto di Audience Manager come descritto di seguito.

## Gestione del rifiuto/ritiro del consenso

Il rifiuto può essere gestito per Adobe Experience Cloud tramite la pagina [delle scelte](https://www.adobe.com/privacy/opt-out.html#customeruse) sulla privacy. Le funzioni con 1 clic consentono agli utenti finali di controllare e rifiutare la raccolta di dati da parte delle soluzioni pubblicitarie Adobe Experience Cloud (incluso Audience Manager). Nello specifico, consulta la sezione [del cliente](https://www.adobe.com/privacy/opt-out.html#customeruse) aziendale della pagina Privacy Choices. Per i browser che non supportano i cookie di terze parti, consulta Destinazione [ID](../../features/declared-ids.md#declared-id-targeting)dichiarato. Per i dispositivi mobili, recuperate i pertinenti identificatori di Audience Manager e chiamate le API di rifiuto di Audience Manager come indicato negli esempi [di rifiuto](../../features/declared-ids.md#opt-out-examples)con ID dichiarato. Di conseguenza, puoi interrompere la raccolta di dati per tali utenti con le API di rifiuto dall'SDK di Mobile. Consulta Dispositivi [](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) Android e dispositivi [](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)iOS. Puoi trovare ulteriori dettagli per l’opzione di rifiuto nella Documentazione [sulle richieste di privacy dei](../../overview/data-security-and-privacy/data-privacy-requests.md)dati.

## Gestione del consenso per provider di dati di seconda parte

I provider di dati di seconda parte sono generalmente anche i soggetti incaricati del trattamento dei dati e possiedono la procedura per ottenere il consenso necessario da parte dell'interessato per condividere i dati con i loro partner di dati di seconda parte. È responsabilità dell'utente, in qualità di cliente Audience Manager, determinare se il fornitore di dati di seconda parte ha ottenuto il consenso necessario per il caso d'uso. Ulteriori dettagli su come ottenere il consenso sono trattati sopra.

## Gestione del consenso per provider di dati di terze parti

I provider di dati di terze parti sono anche i Controllori di dati e possiedono il proprio processo per ottenere il consenso e gestire le richieste di accesso/eliminazione/correzione. Adobe richiede in modo proattivo che i provider di dati aggiornino le informazioni sul profilo aziendale in [Adobe Audience Finder](https://www.adobe-audience-finder.com/) con informazioni aggiuntive sulla raccolta di dati utente. Le informazioni verranno fornite dai provider dei dati e saranno aggiornate regolarmente. Tuttavia, spetta a ciascun cliente Audience Manager determinare che il fornitore di dati di terze parti ha ottenuto il consenso necessario per il caso di utilizzo del cliente. Adobe non presenta osservazioni sull'ambito o sulla validità del consenso ottenuto o segnalato da un fornitore di dati di terze parti per un dato caso di utilizzo.
