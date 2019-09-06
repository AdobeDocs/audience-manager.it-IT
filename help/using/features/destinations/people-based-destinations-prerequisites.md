---
description: 'Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di registrarti per Destinazioni basate su persone.  '
seo-description: 'Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di registrarti per Destinazioni basate su persone.  '
seo-title: Prerequisiti e considerazioni sulle destinazioni basate sulle persone
solution: Audience Manager
title: Prerequisiti e considerazioni
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Prerequisiti e considerazioni {#prerequisites-considerations}

Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di registrarti [!DNL People-Based Destinations].

>[!IMPORTANT]
> Leggete attentamente questo articolo prima di passare alla fase di implementazione.

## Registrazione per destinazioni basate su persone {#signing-up}

[!DNL People-Based Destinations] è una funzionalità premium che migliora l'esperienza di Audience Manager consentendo di attivare segmenti di pubblico di prime parti in ambienti basati su persone, indirizzando il pubblico con offerte personalizzate sui social network o tramite l'e-mail marketing.

Contattate il rappresentante vendite Adobe per informazioni su come registrarvi [!DNL People-Based Destinations].

## Prerequisiti specifici per partner {#partner-prerequisites}

### [!DNL Facebook]

Prima di poter utilizzare [!DNL People-Based Destinations] per inviare segmenti di pubblico, [!DNL Facebook]assicurati di soddisfare i seguenti requisiti:

1. L'account [!DNL Facebook] utente deve disporre dell'autorizzazione **Gestisci campagna** abilitata per l'account Annuncio che intendi utilizzare.
1. Aggiungi l'account aziendale **Adobe Experience Cloud** come partner pubblicitario. [!DNL Facebook Ad Account] Utilizza gli `business ID=206617933627973`. Per ulteriori informazioni, consultate [Aggiungere partner al vostro Business Manager](https://www.facebook.com/business/help/708679622611131) .
   >[!IMPORTANT]
   > Quando configuri le autorizzazioni per Adobe Experience Cloud, devi abilitare **l'autorizzazione Gestisci campagna** . Questa funzione è necessaria per l' [!DNL People-Based Destinations] integrazione.
1. Leggere e firmare [!DNL Facebook Custom Audiences] i Termini di servizio. A questo scopo, vai a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dove `accountID`[!DNL Facebook Ad Account ID]è.

## Onboarding dei dati {#data-onboarding}

L'assimilazione dei dati per [!DNL People-Based Destinations] il momento supporta fino a 10 indirizzi e-mail con hash collegati a un ID cliente ([!DNL CRM ID]), per trasferimento in batch. Il caricamento di più di 10 indirizzi e-mail con hash collegati a un ID cliente causa l'assimilazione di 10 di queste, in nessun ordine specifico.

Se si caricano più di 10 indirizzi e-mail con hash collegati a un ID cliente in più trasferimenti in batch, Audience Manager consente di conservare gli ultimi 10 indirizzi e-mail aggiunti.

## Privacy dei dati {#data-privacy}

Anche se ti [!DNL People-Based Destinations] consente di eseguire il targeting delle audience in base agli indirizzi e-mail, non sono disponibili informazioni di visitatori identificabili direttamente raggiungendo Audience Manager. Nella fase di registrazione dei dati, dovete verificare che gli indirizzi e-mail che pianificate di utilizzare vengano hash con l' [!DNL SHA256] algoritmo. In caso contrario, non potrete utilizzarli [!DNL People-Based Destinations]in.

## Hashing dei dati e cifratura {#data-hashing-encryption}

La crittografia è una funzione bidirezionale. Anche tutte le informazioni crittografate possono essere decifrate utilizzando la chiave di decrittazione corretta. La crittografia dei dati nel contesto di Audience Manager pone un rischio sulla privacy grave, in quanto qualsiasi informazione crittografata può essere decifrata, rivelando dati cliente sensibili. Invece di cifrare, [!DNL People-Based Destinations] sono progettati per lavorare con dati con hash, proteggendo i dati dei clienti utilizzati per il targeting.

L'hash è una funzione unidirezionale che riduce l'input per produrre un risultato univoco. Utilizzando gli algoritmi di hash corretti, come [!DNL SHA256], non è possibile invertire la funzione di hash e rivelare le informazioni senza scrupoli. Gli indirizzi e-mail che si trovano su Audience Manager devono essere hash con l' [!DNL SHA256] algoritmo. In questo modo, nessuna informazione personale raggiunge Audience Manager, mantenendo al sicuro i dati del cliente.

## Requisiti hash {#hashing-requirements}

Quando si hash gli indirizzi e-mail, è necessario rispettare i seguenti requisiti:

* Rifilare tutti gli spazi iniziali e finali dalla stringa e-mail; esempio: `johndoe@example.com`, not `<space>johndoe@example.com<space>`;
* Accertatevi che la stringa hash sia minuscola; esempio: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, not `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Non aggiungete la stringa.

Adobe Experience Cloud vi offre l'opzione di hash ID cliente tramite il servizio Experience Cloud ID. Per informazioni dettagliate sull'utilizzo ECID per hash degli ID cliente, consulta [SHA 256 Hashing Support for setcustomerids](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Ottenimento dell'autorizzazione utente {#obtaining-user-permission}

Poiché [!DNL People-Based Destinations] ti aiuta ad attivare dati di audience di prime parti nei canali basati su persone, è la tua responsabilità informare i clienti di come utilizzerai i loro dati a scopi pubblicitari.

Prima di effettuare l'accesso [!DNL People-Based Destinations], assicuratevi di ottenere il consenso dei clienti prima di utilizzare le informazioni a scopi pubblicitari.

Se i clienti desiderano rinunciare alle campagne pubblicitarie, consulta [Gestione della rinuncia](../../overview/data-security-and-privacy/opt-out-management.md) per informazioni su come arrestare Audience Manager dalla raccolta di dati.

## Attivazione dell'attivazione dei dati di prime parti {#enforcing-first-party-activation}

Quando usi [!DNL People-Based Destinations], puoi usare solo dati di prime parti per attivare i segmenti di pubblico nei canali basati sulle persone. Non puoi usare dati di secondo o terze parti per l'attivazione dell'audience nei canali basati sulle persone.

## Onboard ID con hash autenticati tramite targeting ID dichiarato {#onboard-authenticated-declared-id}

Esistono due modi per trasferire i dati offline ad Audience Manager.[!DNL People-Based Destinations]

* [Inviate dati batch](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) ad Audience Manager per assimilare indirizzi e-mail con hash. Con questo metodo, potete utilizzare tutti gli indirizzi e-mail con hash dal [!DNL CRM] database in. [!DNL People-Based Destinations] Inoltre, quando si utilizza questo metodo, è possibile qualificare gli indirizzi e-mail con hash per [le caratteristiche caricate](../traits/trait-qualification-reference.md).
* Utilizzare [ID dichiarati](../declared-ids.md) per dichiarare indirizzi e-mail con hash durante il passaggio in ID cliente autenticati. Quando si utilizza questo metodo, Audience Manager invia solo agli [!DNL People-Based Destinations] indirizzi e-mail con hash da utenti che hanno eseguito l'autenticazione online. Gli indirizzi e-mail attivati tramite Facebook sono solo quelli nelle chiamate degli eventi ID dichiarati. Altri indirizzi e-mail associati all'ID cliente non vengono inviati in tempo reale.
