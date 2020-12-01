---
description: 'Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti alle Destinazioni basate sulle persone.  '
seo-description: 'Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti alle Destinazioni basate sulle persone.  '
seo-title: Destinazioni basate su persone Prerequisiti e considerazioni
solution: Audience Manager
title: Prerequisiti e considerazioni
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: d3184195d6a51ff013a3d1fc8526ca9afd3386c2
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 3%

---


# Prerequisiti e considerazioni {#prerequisites-considerations}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti a [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leggi attentamente questo articolo prima di passare alla fase di implementazione.

## Registrazione per [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] è una funzionalità premium che migliora l&#39;esperienza  Audience Manager consentendo di attivare i segmenti di pubblico di prime parti in ambienti basati su persone, indirizzando il pubblico con offerte personalizzate sui social network o tramite il marketing e-mail.

Contattate il rappresentante del Adobe  per sfruttare questa funzionalità premium.

## Prerequisiti specifici per i partner {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare il pubblico di prime parti [!UICONTROL segments] a [!DNL Facebook], assicurarsi di soddisfare i seguenti requisiti:

1. L&#39;account utente [!DNL Facebook] deve avere l&#39;autorizzazione **Gestisci campagne** abilitata per l&#39;account annuncio che intendi utilizzare.
2. Aggiungi l&#39;account **Adobe Experience Cloud** come partner pubblicitario nel tuo [!DNL Facebook Ad Account]. Utilizza `business ID=206617933627973`. Per ulteriori informazioni, vedere [Aggiungi partner al tuo Business Manager](https://www.facebook.com/business/help/1717412048538897).
   >[!IMPORTANT]
   > Durante la configurazione delle autorizzazioni per Adobe Experience Cloud, è necessario abilitare l&#39;autorizzazione **Gestisci campagne**. Questa è richiesta per l’integrazione di [!UICONTROL People-Based Destinations].
3. Leggi e firma le [!DNL Facebook Custom Audiences] Condizioni del servizio. Per fare questo, vai su `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dove `accountID` è il tuo [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare segmenti di pubblico di prime parti a [!DNL LinkedIn], assicurarsi che l&#39;account [!DNL LinkedIn Campaign Manager] disponga di un livello di autorizzazione [!DNL Creative Manager] o superiore.

Per informazioni su come modificare le [!DNL LinkedIn Campaign Manager] autorizzazioni utente, vedere [Aggiungi, Modifica e rimuovi le autorizzazioni utente sugli account pubblicitari](https://www.linkedin.com/help/lms/answer/5753) nella documentazione di LinkedIn.

Per istruzioni video, consultate [Informazioni e configurazione sulla destinazione basata sulle persone di LinkedIn](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html).

### [!DNL Google Customer Match] {#gcm}

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare segmenti di pubblico di prime parti a una [!DNL Google Customer Match] destinazione, è obbligatorio che [!DNL Google] ti aggiunga al loro elenco consentiti .

Contatta il tuo [!DNL Google] rappresentante e segui le istruzioni  elenco consentiti descritte in [Utilizza partner di corrispondenza clienti per caricare i dati](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google].

Una volta completato il processo, è possibile creare il [!UICONTROL People-Based Destination].

## Onboarding dei dati {#data-onboarding}

L&#39;assimilazione dei dati per [!UICONTROL People-Based Destinations] supporta attualmente fino a 10 indirizzi e-mail con hash collegati a un ID cliente ([!DNL CRM ID]), per trasferimento batch. Se si caricano più di 10 indirizzi e-mail con hash collegati a un ID cliente,  Audience Manager ne acquisisce 10, in nessun ordine specifico.

Se si caricano più di 10 indirizzi e-mail con hash collegati a un ID cliente in più trasferimenti batch,  Audience Manager conserva gli ultimi 10 indirizzi e-mail aggiunti.

## Privacy dei dati {#data-privacy}

Sebbene [!UICONTROL People-Based Destinations] consenta di eseguire il targeting dei tipi di pubblico in base agli indirizzi e-mail con hash caricati dall&#39;utente, non è consentito caricare nel Audience Manager le informazioni sui visitatori direttamente identificabili. Nella fase di onboarding dei dati, devi accertarti che gli indirizzi e-mail che intendi utilizzare siano crittografati con l&#39;algoritmo [!DNL SHA256]. In caso contrario, non potrai utilizzarli in [!UICONTROL People-Based Destinations].

## Hashing dati contro crittografia {#data-hashing-encryption}

La crittografia è una funzione bidirezionale. È inoltre possibile decrittografare qualsiasi informazione cifrata utilizzando la chiave di decrittazione corretta. La cifratura dei dati nel contesto di  Audience Manager comporta gravi rischi, poiché è possibile decifrare anche qualsiasi forma crittografata di informazioni personali. Invece della cifratura, [!UICONTROL People-Based Destinations] è progettato per funzionare con i dati con hash.

Hashing è una funzione unidirezionale che scorre l&#39;input per produrre un risultato unico. Utilizzando gli algoritmi di hashing appropriati, come [!DNL SHA256], non c&#39;è modo di invertire la funzione di hashing e rivelare le informazioni non scorrevoli. Gli indirizzi e-mail che si desidera inserire  Audience Manager devono essere crittografati con l&#39;algoritmo [!DNL SHA256]. In questo modo, potete assicurarvi che nessun indirizzo e-mail senza hashing raggiunga  Audience Manager.

## Requisiti di hash {#hashing-requirements}

Quando eseguite l&#39;hashing degli indirizzi e-mail, accertatevi di rispettare i seguenti requisiti:

* Rifila tutti gli spazi iniziali e finali dalla stringa e-mail; esempio: `johndoe@example.com`, non `<space>johndoe@example.com<space>`;
* Durante l&#39;hashing delle stringhe e-mail, assicurarsi di eseguire l&#39;hash della stringa minuscola;
   * Esempio: `example@email.com`, non `EXAMPLE@EMAIL.COM`;
* Verificate che la stringa con hash sia in lettere minuscole
   * Esempio: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, non `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Non saldare la stringa.

Guardate il video seguente per comprendere i requisiti di hashing di [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud ti offre la possibilità di hash degli ID cliente tramite [!DNL Adobe Experience Platform Identity Service (ECID)]. Per informazioni dettagliate sull&#39;utilizzo di ECID per l&#39;hash degli ID cliente, vedere [Supporto hash SHA256 per setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html).

## Ottenimento dell&#39;autorizzazione utente {#obtaining-user-permission}

Poiché [!UICONTROL People-Based Destinations] consente di attivare i dati del pubblico di prime parti nei canali basati sulle persone, è responsabilità dell&#39;utente informare e ottenere dai clienti qualsiasi consenso necessario su come utilizzare i dati per scopi pubblicitari o altri scopi.

Prima di effettuare la registrazione per [!UICONTROL People-Based Destinations], assicurarsi di ottenere il consenso dei clienti prima di utilizzare le informazioni a scopo pubblicitario.

Nel caso in cui i clienti desiderino rinunciare alle campagne pubblicitarie, consultate [Opt-out Management](../../overview/data-security-and-privacy/data-privacy-requests.md) per informazioni su come impedire a  Audience Manager di raccogliere dati in un secondo momento.

## Applicazione dell&#39;attivazione dei dati di prime parti {#enforcing-first-party-activation}

Quando si utilizza [!UICONTROL People-Based Destinations], è possibile utilizzare solo dati di prime parti per attivare i segmenti di pubblico nei canali basati sulle persone. Non potete utilizzare dati di seconda o terza parte per l&#39;attivazione dell&#39;audience nei canali basati sulle persone.

Quando si utilizza [!UICONTROL People-Based Destinations], utilizzare [Controlli sull&#39;esportazione dei dati](../data-export-controls.md) per etichettare [!UICONTROL data sources] e [!UICONTROL destinations] in base alle linee guida e ai requisiti delle piattaforme di destinazione e dei provider di dati.

## ID con hash autenticati a bordo attraverso il targeting con ID dichiarato {#onboard-authenticated-declared-id}

Esistono due modi per trasferire i dati offline in Audience Manager per [!UICONTROL People-Based Destinations].

* [Invia ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) dati batch  Audience Manager agli indirizzi e-mail con hash più intensi. Con questo metodo, potete scegliere di utilizzare gli indirizzi e-mail con hash del database [!DNL CRM] in [!UICONTROL People-Based Destinations]. Inoltre, quando si utilizza questo metodo, è anche possibile qualificare gli indirizzi e-mail con hash per le [caratteristiche registrate](../traits/trait-and-segment-qualification-reference.md).
* Utilizzate gli [ID dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmettete gli ID cliente autenticati. Quando si utilizza questo metodo,  Audience Manager, a nome dell&#39;utente, invia solo a [!UICONTROL People-Based Destinations] gli indirizzi e-mail con hash degli utenti che hanno eseguito l&#39;autenticazione online. Gli indirizzi e-mail attivati attraverso i canali basati sulle persone sono solo quelli nelle chiamate dell&#39;evento ID dichiarate. Gli altri indirizzi e-mail associati all&#39;ID cliente non vengono inviati in tempo reale.
