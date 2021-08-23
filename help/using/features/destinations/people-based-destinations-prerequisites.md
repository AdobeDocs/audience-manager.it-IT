---
description: 'Di seguito trovi una panoramica dei requisiti dei clienti che devono essere soddisfatti prima di registrarti alle destinazioni basate su persone.  '
seo-description: 'Di seguito trovi una panoramica dei requisiti dei clienti che devono essere soddisfatti prima di registrarti alle destinazioni basate su persone.  '
seo-title: Prerequisiti e considerazioni sulle destinazioni basate su persone
solution: Audience Manager
title: Prerequisiti e considerazioni
feature: Destinazioni basate su persone
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1013'
ht-degree: 3%

---

# Prerequisiti e considerazioni {#prerequisites-considerations}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

Di seguito trovi una panoramica dei requisiti dei clienti che devono essere soddisfatti prima di iscriversi a [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leggi attentamente questo articolo prima di passare alla fase di implementazione.

## Iscriviti a [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] è una funzionalità premium che migliora l’esperienza Audience Manager consentendoti di attivare i segmenti di pubblico primario in ambienti basati sulle persone, indirizzando il pubblico con offerte personalizzate sui social network o tramite il marketing e-mail.

Contatta il tuo rappresentante Adobe per sfruttare questa funzionalità premium.

## Prerequisiti specifici per i partner {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare il pubblico di prime parti [!UICONTROL segments] a [!DNL Facebook], assicurati di soddisfare i seguenti requisiti:

1. L&#39;account utente [!DNL Facebook] deve disporre dell&#39;autorizzazione **Gestisci campagne** abilitata per l&#39;account annuncio che intendi utilizzare.
2. Aggiungi l&#39;account aziendale **Adobe Experience Cloud** come partner pubblicitario nel tuo [!DNL Facebook Ad Account]. Utilizza `business ID=206617933627973`. Per ulteriori informazioni, consulta [Aggiungi partner al tuo Business Manager](https://www.facebook.com/business/help/1717412048538897) .
   >[!IMPORTANT]
   > Quando configuri le autorizzazioni per Adobe Experience Cloud, devi abilitare l&#39;autorizzazione **Gestisci campagne**. Questa è richiesta per l’integrazione di [!UICONTROL People-Based Destinations].
3. Leggi e firma i termini del servizio [!DNL Facebook Custom Audiences]. Per fare questo, vai su `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dove `accountID` è il tuo [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare i segmenti di pubblico di prime parti a [!DNL LinkedIn], assicurati che il tuo account [!DNL LinkedIn Campaign Manager] disponga del livello di autorizzazione [!DNL Creative Manager] o superiore.

Per informazioni su come modificare le autorizzazioni utente [!DNL LinkedIn Campaign Manager], consulta [Aggiungere, modificare e rimuovere le autorizzazioni utente sugli account pubblicitari](https://www.linkedin.com/help/lms/answer/5753) nella documentazione di LinkedIn.

Per istruzioni video, consulta [Informazioni e configurazione della destinazione LinkedIn basata sulle persone](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) .

### [!DNL Google Customer Match] {#gcm}

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare i segmenti di pubblico di prime parti a una destinazione [!DNL Google Customer Match], è obbligatorio che [!DNL Google] ti aggiunga al loro elenco consentiti.

Contatta il tuo [!DNL Google] rappresentante e segui le istruzioni di elenco consentiti descritte in [Utilizza i partner di Customer Match per caricare i tuoi dati](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google] documentazione.

Una volta completato questo processo, puoi creare il tuo [!UICONTROL People-Based Destination].

## Onboarding dei dati {#data-onboarding}

L’acquisizione dei dati per [!UICONTROL People-Based Destinations] supporta attualmente fino a 10 indirizzi e-mail con hash collegati a un ID cliente ([!DNL CRM ID]) per trasferimento batch. Il caricamento di più di 10 indirizzi e-mail con hash collegati a un ID cliente causa l’inserimento di 10 indirizzi, senza un ordine specifico.

Il caricamento di più di 10 indirizzi e-mail con hash collegati a un ID cliente in più trasferimenti batch fa sì che Audience Manager mantenga gli ultimi 10 indirizzi e-mail aggiunti.

## Privacy dei dati {#data-privacy}

Anche se [!UICONTROL People-Based Destinations] ti consente di eseguire il targeting dei tipi di pubblico in base a indirizzi e-mail con hash caricati dall’utente, ti è impedito di caricare in Audience Manager eventuali informazioni sui visitatori direttamente identificabili. Nella fase di onboarding dei dati, devi assicurarti che gli indirizzi e-mail che intendi utilizzare siano contraddistinti dall’algoritmo [!DNL SHA256]. In caso contrario, non potrai utilizzarli in [!UICONTROL People-Based Destinations].

## Hashing dati contro crittografia {#data-hashing-encryption}

La codifica è una funzione bidirezionale. Qualsiasi informazione crittografata può anche essere decrittografata, utilizzando la chiave di decrittografia corretta. La cifratura dei dati nel contesto dell&#39;Audience Manager comporta gravi rischi, in quanto anche qualsiasi forma crittografata di informazioni personali identificabili può essere decrittografata. Invece della crittografia, [!UICONTROL People-Based Destinations] è progettato per funzionare con dati con hash.

L&#39;hashing è una funzione unidirezionale che scorre l&#39;input per produrre un risultato univoco. Utilizzando gli algoritmi di hashing appropriati, come [!DNL SHA256], non c&#39;è modo di invertire la funzione di hashing e di rivelare le informazioni non sottoposte a scansione. Gli indirizzi e-mail da integrare nell’Audience Manager devono essere contraddistinti dall’algoritmo [!DNL SHA256] . In questo modo, puoi assicurarti che nessun indirizzo e-mail senza hash raggiunga un Audience Manager.

## Requisiti di hashing {#hashing-requirements}

Quando esegui l’hashing degli indirizzi e-mail, assicurati di rispettare i seguenti requisiti:

* Taglia tutti gli spazi iniziali e finali dalla stringa e-mail; esempio: `johndoe@example.com`, non `<space>johndoe@example.com<space>`;
* Quando esegui l’hashing delle stringhe e-mail, assicurati di utilizzare l’hash della stringa in minuscolo;
   * Esempio: `example@email.com`, non `EXAMPLE@EMAIL.COM`;
* Assicurati che la stringa con hash sia tutto minuscola
   * Esempio: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, non `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Non saldare la stringa.

Guarda il video seguente per comprendere i requisiti di hashing di [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud ti offre la possibilità di aggiungere hash agli ID cliente tramite [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulta [Supporto di hashing SHA-256 per setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) per informazioni dettagliate su come utilizzare ECID per aggiungere hash agli ID cliente.

## Ottenimento dell&#39;autorizzazione utente {#obtaining-user-permission}

Poiché [!UICONTROL People-Based Destinations] consente di attivare i dati del pubblico di prime parti nei canali basati sulle persone, è tua responsabilità informare e ottenere dai clienti il consenso necessario su come utilizzerai i loro dati per scopi pubblicitari o di altro tipo.

Prima di iscriverti a [!UICONTROL People-Based Destinations], assicurati di ottenere il consenso dei tuoi clienti prima di utilizzare le loro informazioni a scopo pubblicitario.

Nel caso in cui i clienti desiderino rinunciare alle campagne pubblicitarie, consulta [Gestione rinuncia](../../overview/data-security-and-privacy/data-privacy-requests.md) per informazioni su come impedire ad Audience Manager di raccogliere ulteriori dati.

## Applicazione dell’attivazione dei dati di prime parti {#enforcing-first-party-activation}

Quando utilizzi [!UICONTROL People-Based Destinations], puoi utilizzare solo dati di prime parti per attivare segmenti di pubblico nei canali basati sulle persone. Non puoi utilizzare dati di seconde o terze parti per l’attivazione del pubblico nei canali basati sulle persone.

Quando utilizzi [!UICONTROL People-Based Destinations], utilizza [Controlli sull&#39;esportazione dei dati](../data-export-controls.md) per etichettare i [!UICONTROL data sources] e [!UICONTROL destinations] in base alle linee guida e ai requisiti delle piattaforme di destinazione e dei fornitori di dati.

## ID autenticati a bordo tramite targeting degli ID dichiarati {#onboard-authenticated-declared-id}

Esistono due modi per trasferire i dati offline in Audience Manager per [!UICONTROL People-Based Destinations].

* [Invia Audience Manager ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) dati batch per l’acquisizione di indirizzi e-mail con hash. Con questo metodo, puoi scegliere di utilizzare gli indirizzi e-mail con hash dal database [!DNL CRM] in [!UICONTROL People-Based Destinations]. Inoltre, quando utilizzi questo metodo, puoi anche qualificare gli indirizzi e-mail con hash per [caratteristiche onboarded](../traits/trait-and-segment-qualification-reference.md).
* Utilizza [ID dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmetti gli ID cliente autenticati. Quando utilizzi questo metodo, ad Audience Manager, invia per tuo conto solo a [!UICONTROL People-Based Destinations] gli indirizzi e-mail con hash dagli utenti che hanno eseguito l’autenticazione online. Gli indirizzi e-mail attivati tramite canali basati sulle persone sono solo quelli nelle chiamate dell&#39;evento ID dichiarato. Gli altri indirizzi e-mail associati all’ID cliente non vengono inviati in tempo reale.
