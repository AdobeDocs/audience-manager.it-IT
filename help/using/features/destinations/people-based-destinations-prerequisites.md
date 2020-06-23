---
description: 'Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti alle Destinazioni basate sulle persone.  '
seo-description: 'Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti alle Destinazioni basate sulle persone.  '
seo-title: Destinazioni basate su persone Prerequisiti e considerazioni
solution: Audience Manager
title: Prerequisiti e considerazioni
translation-type: tm+mt
source-git-commit: 4d4915b9a99ddcdf321d9f4970321f5f54e057ea
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 0%

---


# Prerequisiti e considerazioni {#prerequisites-considerations}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leggi attentamente questo articolo prima di passare alla fase di implementazione.

## Registrazione [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] è una funzionalità premium che migliora l&#39;esperienza Audience Manager  consentendo di attivare i segmenti di pubblico di prime parti in ambienti basati su persone, rivolgendosi al pubblico con offerte personalizzate sui social network o tramite il marketing e-mail.

Contattate il vostro rappresentante Adobe per sfruttare questa funzione premium.

## Prerequisiti specifici per i partner {#partner-prerequisites}

### [!DNL Facebook]

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare il pubblico di prime parti [!UICONTROL segments] a [!DNL Facebook], accertatevi di soddisfare i seguenti requisiti:

1. Il tuo account [!DNL Facebook] utente deve avere l&#39;autorizzazione **Gestisci campagne** abilitata per l&#39;account annuncio che intendi utilizzare.
2. Aggiungi l&#39;account aziendale di **Adobe Experience Cloud** come partner pubblicitario all&#39;interno dell&#39; [!DNL Facebook Ad Account]azienda. Utilizza gli `business ID=206617933627973`. Per informazioni, consulta [Aggiunta di partner al tuo Business Manager](https://www.facebook.com/business/help/1717412048538897) .
   >[!IMPORTANT]
   > Quando configuri le autorizzazioni per Adobe Experience Cloud, devi abilitare l&#39;autorizzazione **Gestisci campagne** . Questo è richiesto per l&#39; [!UICONTROL People-Based Destinations] integrazione.
3. Leggi e firma le [!DNL Facebook Custom Audiences] Condizioni del servizio. Per fare questo, andate a `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dov&#39; `accountID` è il vostro [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn]

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare segmenti di pubblico di prime parti a [!DNL LinkedIn], accertati che il tuo [!DNL LinkedIn Campaign Manager] account disponga di un livello di autorizzazione [!DNL Creative Manager] o superiore.

Per informazioni su come modificare le autorizzazioni [!DNL LinkedIn Campaign Manager] utente, consulta [Aggiungi, Modifica e Rimuovi autorizzazioni utente sugli account](https://www.linkedin.com/help/lms/answer/5753) pubblicitari nella documentazione di LinkedIn.

## Onboarding dei dati {#data-onboarding}

L&#39;assimilazione dei dati per [!UICONTROL People-Based Destinations] ora supporta fino a 10 indirizzi e-mail con hash collegati a un ID cliente ([!DNL CRM ID]), per trasferimento batch. Se si caricano più di 10 indirizzi e-mail con hash collegati a un ID cliente,  Audience Manager ne acquisirà 10, in nessun ordine specifico.

Se si caricano più di 10 indirizzi e-mail con hash collegati a un ID cliente in più trasferimenti batch,  Audience Manager conserva i 10 indirizzi e-mail aggiunti più di recente.

## Privacy dei dati {#data-privacy}

Anche se [!UICONTROL People-Based Destinations] consentite di eseguire il targeting dei tipi di pubblico basati su indirizzi e-mail con hash caricati dall&#39;utente, non potete caricare in  Audience Manager eventuali informazioni sui visitatori direttamente identificabili. Nella fase di onboarding dei dati, devi accertarti che gli indirizzi e-mail che intendi utilizzare siano crittografati con l&#39; [!DNL SHA256] algoritmo. In caso contrario, non potrai utilizzarli in [!UICONTROL People-Based Destinations].

## Hashing dati contro crittografia {#data-hashing-encryption}

La crittografia è una funzione bidirezionale. È inoltre possibile decrittografare qualsiasi informazione cifrata utilizzando la chiave di decrittazione corretta. La cifratura dei dati nel contesto di  Audience Manager comporta seri rischi, poiché è possibile decifrare anche qualsiasi forma crittografata di informazioni personali. Invece della cifratura, [!UICONTROL People-Based Destinations] sono progettati per funzionare con dati con hash.

Hashing è una funzione unidirezionale che scorre l&#39;input per produrre un risultato unico. Utilizzando gli algoritmi di hashing appropriati, come [!DNL SHA256], non c&#39;è modo di invertire la funzione di hashing e rivelare le informazioni non scorrevoli. Gli indirizzi e-mail che verranno visualizzati su  Audience Manager devono essere collegati all&#39; [!DNL SHA256] algoritmo. In questo modo, potete assicurarvi che nessun indirizzo e-mail senza hash arrivi  Audience Manager.

## Requisiti di hash {#hashing-requirements}

Quando eseguite l&#39;hashing degli indirizzi e-mail, accertatevi di rispettare i seguenti requisiti:

* Rifila tutti gli spazi iniziali e finali dalla stringa e-mail; esempio: `johndoe@example.com`, not `<space>johndoe@example.com<space>`;
* Durante l&#39;hashing delle stringhe e-mail, assicurarsi di eseguire l&#39;hash della stringa minuscola;
   * Esempio: `example@email.com`, not `EXAMPLE@EMAIL.COM`;
* Verificate che la stringa con hash sia in lettere minuscole
   * Esempio: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, not `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Non saldare la stringa.

Guardate il video seguente per comprendere i requisiti di hashing di [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud ti offre la possibilità di far passare gli ID cliente attraverso [!DNL Adobe Experience Platform Identity Service (ECID)]. Per informazioni dettagliate sull’utilizzo di ECID per l’hash degli ID cliente, consultate Supporto hash [SHA256 per setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Ottenimento dell&#39;autorizzazione utente {#obtaining-user-permission}

Poiché [!UICONTROL People-Based Destinations] consente di attivare i dati del pubblico di prime parti nei canali basati sulle persone, è responsabilità dell&#39;utente informare e ottenere dai clienti qualsiasi consenso necessario su come utilizzare i dati per scopi pubblicitari o di altro tipo.

Prima di iscriversi, [!UICONTROL People-Based Destinations]assicuratevi di ottenere il consenso dei clienti prima di utilizzare le loro informazioni a scopo pubblicitario.

Nel caso in cui i clienti desiderino rinunciare alle campagne pubblicitarie, consulta Gestione [del](../../overview/data-security-and-privacy/data-privacy-requests.md) rifiuto per informazioni su come impedire a  Audience Manager di raccogliere i dati.

## Applicazione dell&#39;attivazione dei dati di prime parti {#enforcing-first-party-activation}

Quando si utilizza [!UICONTROL People-Based Destinations], è possibile utilizzare solo dati di prime parti per attivare i segmenti di pubblico nei canali basati sulle persone. Non potete utilizzare dati di seconda o terza parte per l&#39;attivazione dell&#39;audience nei canali basati sulle persone.

Durante l&#39;utilizzo [!UICONTROL People-Based Destinations], utilizzare [Controlli](../data-export-controls.md) sull&#39;esportazione dei dati per etichettare l&#39;utente [!UICONTROL data sources] e [!UICONTROL destinations] in base alle linee guida e ai requisiti delle piattaforme e dei provider di dati di destinazione.

## ID con hash autenticati a bordo tramite targeting ID dichiarato {#onboard-authenticated-declared-id}

Esistono due modi per portare i dati offline  Audience Manager per [!UICONTROL People-Based Destinations].

* [Inviare dati](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) batch a  Audience Manager agli indirizzi e-mail con hash. Con questo metodo, potete scegliere di utilizzare gli indirizzi e-mail con hash del [!DNL CRM] database in [!UICONTROL People-Based Destinations]. Inoltre, quando utilizzate questo metodo, potete anche qualificare gli indirizzi e-mail con hash per le caratteristiche [registrate](../traits/trait-and-segment-qualification-reference.md).
* Usate gli ID [dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmettete gli ID cliente autenticati. Quando si utilizza questo metodo,  Audience Manager, a nome dell&#39;utente, invia solo [!UICONTROL People-Based Destinations] gli indirizzi e-mail con hash degli utenti che hanno eseguito l&#39;autenticazione online. Gli indirizzi e-mail attivati attraverso i canali basati sulle persone sono solo quelli nelle chiamate dell&#39;evento ID dichiarate. Gli altri indirizzi e-mail associati all&#39;ID cliente non vengono inviati in tempo reale.
