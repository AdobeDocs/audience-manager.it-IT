---
description: Questo documento spiega come funziona la gestione del consenso in Audience Manager.
seo-description: Questo documento spiega come funziona la gestione del consenso in Audience Manager.
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
ht-degree: 100%

---


# Gestione del consenso

## Panoramica {#overview}

Nei casi in cui è necessario il consenso per determinate attività di marketing, i clienti di Audience Manager devono determinare l’ambito e se è necessario aggiornare alcuni consensi per poter continuare a utilizzare i dati in futuro.

Audience Manager offre strumenti che ti consentono di ottenere il consenso necessario dagli utenti, in modo da poter fornire loro esperienze personalizzate su tutti i canali.

>[!IMPORTANT]
>
> Il contenuto di questo documento non rappresenta e non intende sostituirsi a una consulenza legale.
>
> In qualità di responsabile del trattamento dei dati, Adobe non è in grado di fornire consulenza legale sull’ottenimento del consenso. Puoi anche valutare la possibilità di lavorare con un provider di soluzioni per la gestione del consenso, come [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) o [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), e consultare l’ufficio legale della tua azienda per consigli su consenso e pratiche al momento della configurazione dell’implementazione del consenso.

## Servizio Opt-in di Experience Cloud

Il [Servizio Opt-in di Experience Cloud](https://docs.adobe.com/content/help/it-IT/id-service/using/implementation/opt-in-service/optin-overview.html) ti consente di configurare i protocolli per il visitatore per aiutarti a identificare se è possibile impostare un cookie sul dispositivo o sul browser del singolo utente quando visita il tuo sito.

Si tratta di un’estensione del [!DNL Experience Cloud ID (ECID) Service], progettata per consentirti di controllare eventuali soluzioni Experience Cloud che possono creare cookie sulle pagine web per i visitatori prima che l’utente dia il consenso.

Il [Servizio Opt-in di Experience Cloud](https://docs.adobe.com/content/help/it-IT/id-service/using/implementation/opt-in-service/optin-overview.html) ti consente inoltre di impostare i protocolli da integrare con la piattaforma di gestione dei contenuti (CMP, Consent Management Platform) e i sistemi esistenti come parte di un tuo progetto più ampio.

## Gestione e ottenimento del consenso

I clienti di Audience Manager possono memorizzare il consenso degli utenti per vari casi d’uso, ad esempio pubblicità o personalizzazione come caratteristiche in Audience Manager. I segmenti che crei con queste caratteristiche includeranno quindi solo gli utenti che forniscono il rispettivo consenso per ciascuno di questi casi di utilizzo. L’utilizzo di questo approccio non interrompe la raccolta dei dati, ma influisce solo sull’utilizzo dei dati quando invii segmenti per l’attivazione. Quando gli utenti revocano il loro consenso, puoi rimuovere queste caratteristiche dal profilo utente utilizzando il [processo batch in entrata](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) di Audience Manager o il processo di rinuncia di Audience Manager come descritto di seguito.

## Gestione della rinuncia e del ritiro del consenso

La rinuncia può essere gestita per Adobe Experience Cloud tramite la pagina relativa alle [scelte sulla privacy](https://www.adobe.com/it/privacy/opt-out.html#customeruse). Le funzionalità con 1 clic consentono agli utenti finali di controllare e rinunciare alla raccolta di dati da parte delle soluzioni pubblicitarie Adobe Experience Cloud (incluso Audience Manager). Nello specifico, consulta la [sezione per i clienti aziendali](https://www.adobe.com/it/privacy/opt-out.html#customeruse) della pagina relativa alle scelte sulla privacy. Per i browser che non supportano i cookie di terze parti, consulta [Declared ID targeting](../../features/declared-ids.md#declared-id-targeting). Per i dispositivi mobili, recupera gli identificatori pertinenti di Audience Manager e chiama le API di rinuncia di Audience Manager come indicato in [Declared ID Opt-Out examples](../../features/declared-ids.md#opt-out-examples). In seguito, puoi interrompere la raccolta di dati per tali utenti con le API di rinuncia dall’SDK di Mobile (consulta [Dispositivi Android](https://docs.adobe.com/content/help/it-IT/mobile-services/android/gdpr-privacy-android/privacy.html) e [Dispositivi iOS](https://docs.adobe.com/content/help/it-IT/mobile-services/ios/privacy-gdpr-ios/privacy.html)). Ulteriori informazioni sulla rinuncia sono disponibili nella [Data Privacy Requests Documentation](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Gestione del consenso per i partner di seconde parti

I partner di seconde parti sono in genere anche titolari del trattamento dei dati e dispongono del processo per ottenere il consenso necessario da parte dell’interessato per condividere i dati con i partner di dati di seconde parti. È tua responsabilità, in qualità di cliente di Audience Manager, determinare se il partner di seconda parte ha ottenuto il consenso necessario per il tuo caso d’uso. Ulteriori dettagli su come ottenere il consenso sono forniti sopra.

## Gestione del consenso per i partner di terze parti di Audience Marketplace

I partner di terze parti di Audience Marketplace sono anche titolari del trattamento dei dati e dispongono del loro processo per ottenere il consenso e gestire le richieste di accesso/cancellazione/correzione. Adobe sta chiedendo in modo proattivo ai partner di terze parti di Audience Marketplace di aggiornare le informazioni sul profilo aziendale in [Adobe Audience Finder](https://www.adobe-audience-finder.com/) con informazioni aggiuntive sulla raccolta dei dati utente. Le informazioni verranno fornite dai partner di terze parti di Audience Marketplace e sono aggiornate regolarmente. Tuttavia, spetta a ciascun cliente di Audience Manager assicurarsi che il partner di terze parti di Audience Marketplace abbia ottenuto il consenso necessario per il proprio caso di utilizzo. Adobe non fornisce alcuna dichiarazione sull’ambito o sulla validità del consenso ottenuto o segnalato da un partner di terze parti di Audience Marketplace per un dato caso di utilizzo.
