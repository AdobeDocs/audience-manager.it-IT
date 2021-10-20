---
description: 'Di seguito trovi una panoramica dei requisiti dei clienti che devono essere soddisfatti prima di registrarti alle destinazioni basate su persone.  '
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Prerequisiti e considerazioni
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# Prerequisiti e considerazioni {#prerequisites-considerations}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

Leggi qui di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leggi attentamente questo articolo prima di passare alla fase di implementazione.

## Iscriviti [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] è una funzionalità premium che migliora l’esperienza Audience Manager consentendoti di attivare i segmenti di pubblico primario in ambienti basati sulle persone, indirizzando il pubblico con offerte personalizzate sui social network o tramite il marketing e-mail.

Contatta il tuo rappresentante Adobe per sfruttare questa funzionalità premium.

## Prerequisiti specifici per i partner {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Prima di utilizzare [!UICONTROL People-Based Destinations] per inviare il pubblico di prime parti [!UICONTROL segments] a [!DNL Facebook], assicurati di soddisfare i seguenti requisiti:

1. Le [!DNL Facebook] l&#39;account utente deve avere **Gestire le campagne** autorizzazione abilitata per l’account annuncio che intendi utilizzare.
2. Aggiungi il **Adobe Experience Cloud** account aziendale come partner pubblicitario nel tuo [!DNL Facebook Ad Account]. Utilizza `business ID=206617933627973`. Vedi [Aggiungi i partner al tuo Business Manager](https://www.facebook.com/business/help/1717412048538897) per i dettagli.
   >[!IMPORTANT]
   > Quando configuri le autorizzazioni per Adobe Experience Cloud, devi abilitare il **Gestire le campagne** autorizzazione. Questa è richiesta per l’integrazione di [!UICONTROL People-Based Destinations].
3. Leggi e firma i [!DNL Facebook Custom Audiences] Termini di servizio Per fare questo, vai su `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dove `accountID` è il tuo [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Prima di utilizzare [!UICONTROL People-Based Destinations] per inviare i segmenti di pubblico di prime parti a [!DNL LinkedIn], assicurati che [!DNL LinkedIn Campaign Manager] l&#39;account [!DNL Creative Manager] o livello di autorizzazione superiore.

Per scoprire come modificare il [!DNL LinkedIn Campaign Manager] autorizzazioni utente, vedi [Aggiungere, modificare e rimuovere le autorizzazioni utente sugli account pubblicitari](https://www.linkedin.com/help/lms/answer/5753) nella documentazione di LinkedIn.

Vedi [Informazioni e configurazione della destinazione LinkedIn basata sulle persone](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) per istruzioni video.

### [!DNL Google Customer Match] {#gcm}

Prima di utilizzare [!UICONTROL People-Based Destinations] per inviare i segmenti di pubblico di prime parti a un [!DNL Google Customer Match] assicurati di leggere e rispettare i criteri di Google per l&#39;utilizzo di [!DNL Customer Match], descritti nella [Documentazione di supporto per Google](https://support.google.com/google-ads/answer/6299717).

Successivamente, assicurati che [!DNL Google] account configurato per un [!DNL Standard] o livello di autorizzazione superiore. Consulta la sezione [Documentazione di Google Ads](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) per i dettagli.

I clienti con account conformi vengono automaticamente inseriti nell’elenco Consentiti da Google.

## Onboarding dei dati {#data-onboarding}

Acquisizione dati per [!UICONTROL People-Based Destinations] attualmente supporta fino a 10 indirizzi e-mail con hash collegati a un ID cliente ([!DNL CRM ID]), per trasferimento batch. Il caricamento di più di 10 indirizzi e-mail con hash collegati a un ID cliente causa l’inserimento di 10 indirizzi, senza un ordine specifico.

Il caricamento di più di 10 indirizzi e-mail con hash collegati a un ID cliente in più trasferimenti batch fa sì che Audience Manager mantenga gli ultimi 10 indirizzi e-mail aggiunti.

## Privacy dei dati {#data-privacy}

Nonostante [!UICONTROL People-Based Destinations] ti consente di eseguire il targeting dei tipi di pubblico in base agli indirizzi e-mail con hash caricati dall’utente, ti viene impedito di caricare in Audience Manager eventuali informazioni sui visitatori direttamente identificabili. Nella fase di onboarding dei dati, devi accertarti che gli indirizzi e-mail che intendi utilizzare siano con hash con [!DNL SHA256] algoritmo. In caso contrario, non potrai utilizzarli in [!UICONTROL People-Based Destinations].

## Hashing dati contro crittografia {#data-hashing-encryption}

La codifica è una funzione bidirezionale. Qualsiasi informazione crittografata può anche essere decrittografata, utilizzando la chiave di decrittografia corretta. La cifratura dei dati nel contesto dell&#39;Audience Manager comporta gravi rischi, in quanto anche qualsiasi forma crittografata di informazioni personali identificabili può essere decrittografata. Contrariamente alla cifratura, [!UICONTROL People-Based Destinations] sono invece progettati per funzionare con dati con hash.

L&#39;hashing è una funzione unidirezionale che scorre l&#39;input per produrre un risultato univoco. Utilizzando gli algoritmi di hashing appropriati, come [!DNL SHA256], non c&#39;è modo di invertire la funzione di hashing e rivelare le informazioni non sottoposte a scansione. Gli indirizzi e-mail che verranno inseriti nell’Audience Manager devono essere contraddistinti da un hash [!DNL SHA256] algoritmo. In questo modo, puoi assicurarti che nessun indirizzo e-mail senza hash raggiunga un Audience Manager.

## Requisiti di hashing {#hashing-requirements}

Quando esegui l’hashing degli indirizzi e-mail, assicurati di rispettare i seguenti requisiti:

* Taglia tutti gli spazi iniziali e finali dalla stringa e-mail; esempio: `johndoe@example.com`, not `<space>johndoe@example.com<space>`;
* Quando esegui l’hashing delle stringhe e-mail, assicurati di utilizzare l’hash della stringa in minuscolo;
   * Esempio: `example@email.com`, not `EXAMPLE@EMAIL.COM`;
* Assicurati che la stringa con hash sia tutto minuscola
   * Esempio: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, not `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Non saldare la stringa.

Guarda il video seguente per comprendere i requisiti di hashing di [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud ti offre la possibilità di aggiungere hash agli ID cliente tramite [!DNL Adobe Experience Platform Identity Service (ECID)]. Vedi [Supporto di hashing SHA-256 per setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) per informazioni dettagliate su come utilizzare ECID per aggiungere hash agli ID cliente.

## Ottenimento dell&#39;autorizzazione utente {#obtaining-user-permission}

Da [!UICONTROL People-Based Destinations] consente di attivare i dati del pubblico di prime parti nei canali basati sulle persone; è tua responsabilità informare e ottenere dai clienti il consenso necessario su come utilizzare i loro dati per scopi pubblicitari o di altro tipo.

Prima di iscriversi [!UICONTROL People-Based Destinations], assicurati di ottenere il consenso dei tuoi clienti prima di utilizzare le loro informazioni a scopo pubblicitario.

Nel caso in cui i clienti desiderino rinunciare alle campagne pubblicitarie, consulta [Gestione delle rinunce](../../overview/data-security-and-privacy/data-privacy-requests.md) per informazioni dettagliate su come impedire ad Audience Manager di raccogliere ulteriori dati.

## Applicazione dell’attivazione dei dati di prime parti {#enforcing-first-party-activation}

Quando utilizzi [!UICONTROL People-Based Destinations], puoi utilizzare solo dati di prime parti per attivare segmenti di pubblico nei canali basati sulle persone. Non puoi utilizzare dati di seconde o terze parti per l’attivazione del pubblico nei canali basati sulle persone.

Quando utilizzi [!UICONTROL People-Based Destinations], utilizza [Controlli sull&#39;esportazione dei dati](../data-export-controls.md) per etichettare [!UICONTROL data sources] e [!UICONTROL destinations] secondo le linee guida e i requisiti delle piattaforme di destinazione e dei fornitori di dati.

## ID autenticati a bordo tramite targeting degli ID dichiarati {#onboard-authenticated-declared-id}

Esistono due modi per trasferire i dati offline in Audience Manager per [!UICONTROL People-Based Destinations].

* [Invia dati batch](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) ad Audience Manager per acquisire indirizzi e-mail con hash. Con questo metodo, puoi scegliere di utilizzare gli indirizzi e-mail con hash dal tuo [!DNL CRM] database in [!UICONTROL People-Based Destinations]. Inoltre, quando utilizzi questo metodo, puoi anche qualificare gli indirizzi e-mail con hash per [caratteristiche onboarded](../traits/trait-and-segment-qualification-reference.md).
* Utilizzo [ID dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando si trasmettono gli ID cliente autenticati. Quando utilizzi questo metodo, ad Audience Manager, invia solo a [!UICONTROL People-Based Destinations] indirizzi e-mail con hash degli utenti che hanno eseguito l’autenticazione online. Gli indirizzi e-mail attivati tramite canali basati sulle persone sono solo quelli nelle chiamate dell&#39;evento ID dichiarato. Gli altri indirizzi e-mail associati all’ID cliente non vengono inviati in tempo reale.
