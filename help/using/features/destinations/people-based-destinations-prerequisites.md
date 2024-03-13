---
description: Leggi di seguito per una panoramica dei requisiti dei clienti che devi soddisfare prima di iscriverti a Destinazioni basate su persone.
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Prerequisiti e considerazioni
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: 2b823855994f394261a66e896ef7de7bb7a5450f
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 2%

---


# Prerequisiti e considerazioni {#prerequisites-considerations}

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

Leggi di seguito per una panoramica dei requisiti del cliente che è necessario soddisfare prima di iscriversi a [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leggi attentamente questo articolo prima di passare alla fase di implementazione.

## Registrazione per [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] è una funzionalità premium che migliora l’esperienza di Audience Manager consentendo di attivare i segmenti di pubblico primario in ambienti basati sulle persone, indirizzando il pubblico con offerte personalizzate sui social network o tramite l’e-mail marketing.

Contatta il tuo rappresentante di Adobe per approfittare di questa funzionalità premium.

## Prerequisiti specifici per i partner {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Prima di usare [!UICONTROL People-Based Destinations] per inviare il pubblico di prime parti [!UICONTROL segments] a [!DNL Facebook], assicurati di soddisfare i seguenti requisiti:

1. Il tuo [!DNL Facebook] l&#39;account utente deve avere **Gestire le campagne** Autorizzazione abilitata per l’account annuncio che intendi utilizzare.
2. Aggiungi il **Adobe Experience Cloud** account aziendale come partner pubblicitario nel [!DNL Facebook Ad Account]. Utilizza `business ID=206617933627973`. Consulta [Aggiunta di partner a Business Manager](https://www.facebook.com/business/help/1717412048538897) per i dettagli.

   >[!IMPORTANT]
   >Durante la configurazione delle autorizzazioni per Adobe Experience Cloud, devi abilitare **Gestire le campagne** autorizzazione. Questa è richiesta per l’integrazione di [!UICONTROL People-Based Destinations].

3. Leggi e firma la [!DNL Facebook Custom Audiences] Termini di servizio. Per fare questo, vai su `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dove `accountID` è il tuo [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Prima di usare [!UICONTROL People-Based Destinations] per inviare i segmenti di pubblico di prime parti a [!DNL LinkedIn], assicurati che le [!DNL LinkedIn Campaign Manager] l&#39;account ha [!DNL Creative Manager] o un livello di autorizzazione più elevato.

Per scoprire come modificare il [!DNL LinkedIn Campaign Manager] autorizzazioni utente, consulta [Aggiungere, modificare e rimuovere le autorizzazioni utente sugli account Advertising](https://www.linkedin.com/help/lms/answer/5753) nella documentazione di LinkedIn.

Consulta [Informazioni e configurazione della destinazione LinkedIn basata sulle persone](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) per istruzioni video.

### [!DNL Google Customer Match] {#gcm}

Prima di usare [!UICONTROL People-Based Destinations] per inviare i segmenti di pubblico primario a una [!DNL Google Customer Match] destinazione, assicurati di leggere e rispettare i criteri di Google per l&#39;utilizzo di [!DNL Customer Match], delineato nella [Documentazione di supporto Google](https://support.google.com/google-ads/answer/6299717).

Quindi, assicurati che il tuo [!DNL Google] l’account è configurato per [!DNL Standard] o un livello di autorizzazione più elevato. Consulta la [Documentazione di Google Ads](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) per i dettagli.

I clienti con account conformi vengono inseriti automaticamente nell’elenco Consentiti da Google.

## Onboarding dei dati {#data-onboarding}

>[!IMPORTANT]
>
>Tutti i clienti Audienci Manager possono acquisire e-mail con hash senza registrarsi a [!UICONTROL People-Based Destinations].

Acquisizione dei dati per [!UICONTROL People-Based Destinations] attualmente supporta fino a 10 indirizzi e-mail con hash collegati a un ID cliente ([!DNL CRM ID]), per trasferimento batch.

Il caricamento di più di 10 indirizzi e-mail con hash collegati a un ID cliente in più trasferimenti batch fa sì che Audienci Manager mantenga gli ultimi 10 indirizzi e-mail aggiunti.

Per acquisire gli identificatori con hash, [creare un’origine dati multi-dispositivo per gli identificatori con hash](../create-data-source-hashed-emails.md) e abilita **[!UICONTROL Share associated cross-device IDs in people-based destinations and/or hashed email workflows]** opzione.

![Audience Manager di immagine dell’interfaccia utente che mostra l’opzione per condividere gli ID multi-dispositivo associati nelle destinazioni basate su persone e/o nei flussi di lavoro e-mail con hash](assets/data-source-share-ids.png)

## Privacy dei dati {#data-privacy}

Anche se [!UICONTROL People-Based Destinations] consenti di eseguire il targeting dei tipi di pubblico in base a indirizzi e-mail con hash che hai caricato. non puoi caricare in Audienci Manager informazioni sui visitatori direttamente identificabili. Nella fase di onboarding dei dati, devi assicurarti che gli indirizzi e-mail che intendi utilizzare abbiano l’hash con [!DNL SHA256] algoritmo. In caso contrario, non potrai utilizzarli in [!UICONTROL People-Based Destinations].

## Hashing dei dati e crittografia {#data-hashing-encryption}

La crittografia è una funzione bidirezionale. È inoltre possibile decrittografare qualsiasi informazione crittografata utilizzando la chiave di decrittografia corretta. La cifratura dei dati nel contesto dell&#39;Audience Manager comporta gravi rischi, in quanto qualsiasi forma cifrata di informazioni personali può anche essere decifrata. A differenza della crittografia, [!UICONTROL People-Based Destinations] sono progettati per funzionare con dati con hash.

L’hashing è una funzione unidirezionale che scompone l’input per produrre un risultato univoco. Utilizzando algoritmi di hashing appropriati, come [!DNL SHA256], non è possibile invertire la funzione di hashing e visualizzare le informazioni non codificate. Gli indirizzi e-mail che effettuerai l’onboarding dell’Audience Manager devono essere con hash con [!DNL SHA256] algoritmo. In questo modo, puoi assicurarti che nessun indirizzo e-mail senza hash raggiunga Audienci Manager.

## Requisiti di hashing {#hashing-requirements}

Quando esegui l’hashing degli indirizzi e-mail, assicurati di soddisfare i seguenti requisiti:

* Taglia tutti gli spazi iniziali e finali dalla stringa e-mail; ad esempio: `johndoe@example.com`, non `<space>johndoe@example.com<space>`;
* Quando esegui l’hashing delle stringhe e-mail, assicurati di eseguire l’hashing della stringa in minuscolo;
   * Esempio: `example@email.com`, non `EXAMPLE@EMAIL.COM`;
* Assicurati che la stringa con hash sia tutta in minuscolo
   * Esempio: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, non `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Non salare la corda.

Guarda il video seguente per comprendere i requisiti di hashing di [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud consente di eseguire l&#39;hashing degli ID cliente tramite [!DNL Adobe Experience Platform Identity Service (ECID)]. Consulta [Supporto di hashing SHA-256 per setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) per informazioni dettagliate su come utilizzare ECID per eseguire l’hashing degli ID cliente.

## Ottenimento delle autorizzazioni utente {#obtaining-user-permission}

Da [!UICONTROL People-Based Destinations] ti consente di attivare i dati sul pubblico di prime parti nei canali basati sulle persone, è tua responsabilità informare e ottenere dai clienti i consensi necessari su come utilizzerai i loro dati per scopi pubblicitari o di altro tipo.

Prima di iscriverti a [!UICONTROL People-Based Destinations], assicurati di ottenere il consenso dei clienti prima di utilizzare le loro informazioni a scopo pubblicitario.

Nel caso in cui i clienti desiderino rinunciare alle campagne pubblicitarie, consulta [Gestione degli opt-out](../../overview/data-security-and-privacy/data-privacy-requests.md) per informazioni su come interrompere ulteriormente la raccolta dei dati da parte di Audienci Manager.

## Applicazione dell’attivazione dei dati di prime parti {#enforcing-first-party-activation}

Quando si utilizza [!UICONTROL People-Based Destinations], puoi utilizzare solo dati di prime parti per attivare segmenti di pubblico in canali basati sulle persone. Non puoi utilizzare dati di seconde o terze parti per l’attivazione del pubblico nei canali basati sulle persone.

Quando si utilizza [!UICONTROL People-Based Destinations], utilizza [Controlli sull’esportazione dei dati](../data-export-controls.md) per etichettare [!UICONTROL data sources] e [!UICONTROL destinations] in base alle linee guida e ai requisiti delle piattaforme di destinazione e dei fornitori di dati.

## Onboarding degli ID con hash autenticati tramite Declared ID Targeting {#onboard-authenticated-declared-id}

Esistono due modi per trasferire i dati offline in Audience Manager per [!UICONTROL People-Based Destinations].

* [Inviare dati batch](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) ad Audience Manager per acquisire indirizzi e-mail con hash. Con questo metodo, puoi scegliere di utilizzare gli indirizzi e-mail con hash del tuo [!DNL CRM] database in [!UICONTROL People-Based Destinations]. Inoltre, quando utilizzi questo metodo, puoi anche qualificare gli indirizzi e-mail con hash per [caratteristiche onboarded](../traits/trait-and-segment-qualification-reference.md).
* Utilizzare [ID dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando si trasmettono gli ID cliente autenticati. Quando si utilizza questo metodo, ad Audience Manager, per tuo conto, invia solo a [!UICONTROL People-Based Destinations] gli indirizzi e-mail con hash degli utenti che si sono autenticati online. Gli indirizzi e-mail attivati tramite i canali basati sulle persone sono solo quelli nelle chiamate all’evento degli ID dichiarati. Gli altri indirizzi e-mail associati all’ID cliente non vengono inviati in tempo reale.
