---
description: 'Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti alle Destinazioni basate sulle persone.  '
seo-description: 'Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti alle Destinazioni basate sulle persone.  '
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Prerequisiti e considerazioni
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# Prerequisiti e considerazioni {#prerequisites-considerations}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell'utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per assistenza legale.

Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti [!DNL People-Based Destinations].

>[!IMPORTANT]
> Leggi attentamente questo articolo prima di passare alla fase di implementazione.

## Registrazione alle destinazioni basate sulle persone {#signing-up}

[!DNL People-Based Destinations] è una funzionalità premium che migliora l'esperienza di Audience Manager consentendo di attivare i segmenti di pubblico di prime parti in ambienti basati su persone, indirizzando il pubblico con offerte personalizzate sui social network o tramite il marketing e-mail.

Contattate il vostro rappresentante Adobe per sfruttare questa funzione premium.

## Prerequisiti specifici per i partner {#partner-prerequisites}

### [!DNL Facebook]

Prima di poter utilizzare [!DNL People-Based Destinations] per inviare segmenti di pubblico di prime parti a [!DNL Facebook], verifica di soddisfare i seguenti requisiti:

1. Il tuo account [!DNL Facebook] utente deve avere l'autorizzazione **Gestisci campagne** abilitata per l'account annuncio che intendi utilizzare.
1. Aggiungi l'account aziendale **Adobe Experience Cloud** come partner pubblicitario all'interno dell' [!DNL Facebook Ad Account]azienda. Utilizza gli `business ID=206617933627973`. Per informazioni, consulta [Aggiunta di partner al tuo Business Manager](https://www.facebook.com/business/help/708679622611131) .
   >[!IMPORTANT]
   > Quando configuri le autorizzazioni per Adobe Experience Cloud, devi abilitare l'autorizzazione **Gestisci campagne** . Questo è richiesto per l' [!DNL People-Based Destinations] integrazione.
1. Leggi e firma le [!DNL Facebook Custom Audiences] Condizioni del servizio. Per fare questo, andate a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dov' `accountID` è il vostro [!DNL Facebook Ad Account ID].

## Data Onboarding {#data-onboarding}

L'assimilazione dei dati per [!DNL People-Based Destinations] ora supporta fino a 10 indirizzi e-mail con hash collegati a un ID cliente ([!DNL CRM ID]), per trasferimento batch. Il caricamento di più di 10 indirizzi e-mail con hash collegati a un ID cliente causa l’inserimento di 10 indirizzi da parte di Audience Manager, senza un ordine specifico.

Uploading more than 10 hashed email addresses linked to one customer ID in multiple batch transfers causes Audience Manager to retain the most recent 10 email addresses added.

## Privacy dei dati {#data-privacy}

Anche se [!DNL People-Based Destinations] consentite di eseguire il targeting dei tipi di pubblico in base agli indirizzi e-mail con hash caricati dall'utente, non potete caricare in Audience Manager eventuali informazioni sui visitatori direttamente identificabili. Nella fase di onboarding dei dati, devi accertarti che gli indirizzi e-mail che intendi utilizzare siano crittografati con l' [!DNL SHA256] algoritmo. Otherwise, you won't be able to use them in .[!DNL People-Based Destinations]

## Hashing dati contro crittografia {#data-hashing-encryption}

La crittografia è una funzione bidirezionale. Any encrypted information can also be decrypted, using the correct decryption key. La cifratura dei dati nel contesto di Audience Manager comporta seri rischi, poiché è possibile decifrare anche qualsiasi forma crittografata di informazioni personali. Invece della cifratura, [!DNL People-Based Destinations] sono progettati per funzionare con dati con hash.

Hashing è una funzione unidirezionale che scorre l'input per produrre un risultato unico. By using proper hashing algorithms, like , there is no way to reverse the hashing function and reveal the unscrambled information. [!DNL SHA256] The email addresses that you will onboard to Audience Manager must be hashed with the  algorithm. [!DNL SHA256] This way, you can ensure that no unhashed email addresses reach Audience Manager.

## Hashing Requirements {#hashing-requirements}

When hashing the email addresses, make sure to comply with the following requirements:

* Trim all leading and trailing spaces from the email string; example: , not ;`johndoe@example.com``<space>johndoe@example.com<space>`
* When hashing the email strings, make sure to hash the lowercase string;
   * Esempio: , not ;`example@email.com``EXAMPLE@EMAIL.COM`
* Make sure the hashed string is all lowercase
   * Esempio: , not ;`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149``55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`
* Non saldare la stringa.

Adobe Experience Cloud gives you the option to hash customer IDs through the Experience Cloud ID Service. Per informazioni dettagliate sull’utilizzo di ECID per l’hash degli ID cliente, consultate Supporto hash [SHA256 per setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Ottenimento dell'autorizzazione utente {#obtaining-user-permission}

Poiché [!DNL People-Based Destinations] consente di attivare i dati del pubblico di prime parti nei canali basati sulle persone, è responsabilità dell'utente informare e ottenere dai clienti qualsiasi consenso necessario su come utilizzare i dati per scopi pubblicitari o di altro tipo.

Prima di iscriversi, [!DNL People-Based Destinations]assicuratevi di ottenere il consenso dei clienti prima di utilizzare le loro informazioni a scopo pubblicitario.

Nel caso in cui i clienti desiderino rinunciare alle campagne pubblicitarie, consulta Gestione [del](../../overview/data-security-and-privacy/opt-out-management.md) rifiuto per informazioni su come impedire ad Audience Manager di raccogliere ulteriori dati.

## Applicazione dell'attivazione dei dati di prime parti {#enforcing-first-party-activation}

Quando si utilizza [!DNL People-Based Destinations], è possibile utilizzare solo dati di prime parti per attivare i segmenti di pubblico nei canali basati sulle persone. Non potete utilizzare dati di seconda o terza parte per l'attivazione dell'audience nei canali basati sulle persone.

## ID con hash autenticati a bordo tramite targeting ID dichiarato {#onboard-authenticated-declared-id}

Esistono due modi per trasferire i dati offline ad Audience Manager per [!DNL People-Based Destinations].

* [Invia dati](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) batch ad Audience Manager per il caricamento di indirizzi e-mail con hash. Con questo metodo, potete scegliere di utilizzare gli indirizzi e-mail con hash del [!DNL CRM] database in [!DNL People-Based Destinations]. Inoltre, quando utilizzate questo metodo, potete anche qualificare gli indirizzi e-mail con hash per le caratteristiche [registrate](../traits/trait-qualification-reference.md).
* Usate gli ID [dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmettete gli ID cliente autenticati. Quando si utilizza questo metodo, Audience Manager, per vostro conto, invia solo agli indirizzi e-mail con [!DNL People-Based Destinations] hash degli utenti che hanno eseguito l'autenticazione online. Gli indirizzi e-mail attivati attraverso i canali basati sulle persone sono solo quelli nelle chiamate dell'evento ID dichiarate. Gli altri indirizzi e-mail associati all'ID cliente non vengono inviati in tempo reale.
