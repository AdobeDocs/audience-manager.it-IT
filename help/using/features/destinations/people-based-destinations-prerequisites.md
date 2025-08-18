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

Di seguito è riportata una panoramica dei requisiti del cliente che è necessario soddisfare prima di iscriversi a [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Leggi attentamente questo articolo prima di passare alla fase di implementazione.

## Registrazione per [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] è una funzionalità premium che migliora la tua esperienza di Audience Manager consentendoti di attivare i segmenti di pubblico di prime parti in ambienti basati sulle persone, indirizzando il tuo pubblico con offerte personalizzate sui social network o tramite l&#39;e-mail marketing.

Contatta il tuo rappresentante Adobe per approfittare di questa funzionalità premium.

## Prerequisiti specifici per i partner {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare il pubblico di prime parti [!UICONTROL segments] a [!DNL Facebook], assicurati di soddisfare i seguenti requisiti:

1. L&#39;account utente [!DNL Facebook] deve avere l&#39;autorizzazione **Gestisci campagne** abilitata per l&#39;account annuncio che intendi utilizzare.
2. Aggiungi l&#39;account aziendale **Adobe Experience Cloud** come partner pubblicitario nel tuo [!DNL Facebook Ad Account]. Utilizza `business ID=206617933627973`. Per informazioni dettagliate, consulta [Aggiungere partner al tuo Business Manager](https://www.facebook.com/business/help/1717412048538897).

   >[!IMPORTANT]
   >Durante la configurazione delle autorizzazioni per Adobe Experience Cloud, devi abilitare l&#39;autorizzazione **Gestisci campagne**. Questa è richiesta per l’integrazione di [!UICONTROL People-Based Destinations].

3. Leggi e firma le Condizioni per l&#39;utilizzo di [!DNL Facebook Custom Audiences]. Per fare questo, vai su `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, dove `accountID` è il tuo [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare i segmenti di pubblico di prime parti a [!DNL LinkedIn], assicurati che il tuo account di [!DNL LinkedIn Campaign Manager] disponga del livello di autorizzazione [!DNL Creative Manager] o superiore.

Per informazioni su come modificare le autorizzazioni utente di [!DNL LinkedIn Campaign Manager], consulta [Aggiungere, modificare e rimuovere le autorizzazioni utente sugli account Advertising](https://www.linkedin.com/help/lms/answer/5753) nella documentazione di LinkedIn.

Per istruzioni video, consulta [Informazioni e configurazione della destinazione LinkedIn basata sulle persone](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html?lang=it).

### [!DNL Google Customer Match] {#gcm}

Prima di poter utilizzare [!UICONTROL People-Based Destinations] per inviare i segmenti di pubblico di prime parti a una destinazione [!DNL Google Customer Match], assicurati di leggere e rispettare i criteri di Google per l&#39;utilizzo di [!DNL Customer Match], descritti nella [documentazione di supporto Google](https://support.google.com/google-ads/answer/6299717).

Verificare quindi che l&#39;account [!DNL Google] sia configurato per un livello di autorizzazione [!DNL Standard] o superiore. Per informazioni dettagliate, consulta la [documentazione di Google Ads](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&rd=1).

I clienti con account conformi vengono inseriti automaticamente nell’elenco Consentiti da Google.

## Onboarding dei dati {#data-onboarding}

>[!IMPORTANT]
>
>Tutti i clienti Audience Manager possono acquisire e-mail con hash senza registrarsi a [!UICONTROL People-Based Destinations].

L&#39;acquisizione dei dati per [!UICONTROL People-Based Destinations] attualmente supporta fino a 10 indirizzi e-mail con hash collegati a un ID cliente ([!DNL CRM ID]) per trasferimento batch.

Il caricamento di più di 10 indirizzi e-mail con hash collegati a un ID cliente in più trasferimenti batch fa sì che Audience Manager mantenga gli ultimi 10 indirizzi e-mail aggiunti.

Per acquisire gli identificatori con hash, [crea un&#39;origine dati cross-device per gli identificatori con hash](../create-data-source-hashed-emails.md) e abilita l&#39;opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations and/or hashed email workflows]**.

![Immagine dell&#39;interfaccia utente di Audience Manager con l&#39;opzione di condividere gli ID multi-dispositivo associati nelle destinazioni basate su persone e/o nei flussi di lavoro e-mail con hash](assets/data-source-share-ids.png)

## Privacy dei dati {#data-privacy}

Anche se [!UICONTROL People-Based Destinations] ti consente di eseguire il targeting dei tipi di pubblico in base agli indirizzi e-mail con hash che hai caricato, non puoi caricare in Audience Manager informazioni sui visitatori direttamente identificabili. Nella fase di onboarding dei dati, devi assicurarti che l’hashing degli indirizzi e-mail che intendi utilizzare sia eseguito con l’algoritmo [!DNL SHA256]. In caso contrario, non potrai utilizzarli in [!UICONTROL People-Based Destinations].

## Hashing dei dati e crittografia {#data-hashing-encryption}

La crittografia è una funzione bidirezionale. È inoltre possibile decrittografare qualsiasi informazione crittografata utilizzando la chiave di decrittografia corretta. La crittografia dei dati nel contesto di Audience Manager comporta seri rischi, in quanto può essere decrittografata anche qualsiasi forma crittografata di informazioni personali identificabili. A differenza della crittografia, [!UICONTROL People-Based Destinations] sono progettati per funzionare con dati con hash.

L’hashing è una funzione unidirezionale che scompone l’input per produrre un risultato univoco. Utilizzando gli algoritmi di hashing appropriati, come [!DNL SHA256], non è possibile invertire la funzione di hashing e visualizzare le informazioni non codificate. Gli indirizzi e-mail che effettuerai l&#39;onboarding in Audience Manager devono essere con hash con l&#39;algoritmo [!DNL SHA256]. In questo modo, puoi assicurarti che nessun indirizzo e-mail senza hash raggiunga Audience Manager.

## Requisiti di hashing {#hashing-requirements}

Quando esegui l’hashing degli indirizzi e-mail, assicurati di soddisfare i seguenti requisiti:

* Taglia tutti gli spazi iniziali e finali dalla stringa e-mail. Esempio: `johndoe@example.com`, non `<space>johndoe@example.com<space>`;
* Quando esegui l’hashing delle stringhe e-mail, assicurati di eseguire l’hashing della stringa in minuscolo;
   * Esempio: `example@email.com`, non `EXAMPLE@EMAIL.COM`;
* Assicurati che la stringa con hash sia tutta in minuscolo
   * Esempio: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, non `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Non salare la corda.

Il video seguente illustra i requisiti di hashing di [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud consente di eseguire l&#39;hashing degli ID cliente tramite [!DNL Adobe Experience Platform Identity Service (ECID)]. Per informazioni dettagliate su come utilizzare ECID per eseguire l&#39;hashing degli ID cliente, consulta il supporto di hashing [SHA256 per setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html?lang=it).

## Ottenimento delle autorizzazioni utente {#obtaining-user-permission}

Poiché [!UICONTROL People-Based Destinations] ti consente di attivare i dati del pubblico di prime parti nei canali basati sulle persone, è tua responsabilità informare e ottenere il consenso necessario dai tuoi clienti su come userai i loro dati per scopi pubblicitari o altri scopi.

Prima di iscriverti a [!UICONTROL People-Based Destinations], assicurati di ottenere il consenso dei clienti prima di utilizzare le loro informazioni a scopo pubblicitario.

Se i tuoi clienti desiderano rinunciare alle campagne pubblicitarie, consulta [Gestione delle rinunce](../../overview/data-security-and-privacy/data-privacy-requests.md) per informazioni su come impedire ad Audience Manager di raccogliere ulteriori dati.

## Applicazione dell’attivazione dei dati di prime parti {#enforcing-first-party-activation}

Quando si utilizza [!UICONTROL People-Based Destinations], è possibile utilizzare solo dati di prime parti per attivare segmenti di pubblico in canali basati sulle persone. Non puoi utilizzare dati di seconde o terze parti per l’attivazione del pubblico nei canali basati sulle persone.

Quando utilizzi [!UICONTROL People-Based Destinations], utilizza [Controlli sull&#39;esportazione dei dati](../data-export-controls.md) per etichettare [!UICONTROL data sources] e [!UICONTROL destinations] in base alle linee guida e ai requisiti delle piattaforme di destinazione e dei provider di dati.

## Onboarding degli ID con hash autenticati tramite Declared ID Targeting {#onboard-authenticated-declared-id}

Esistono due modi per trasferire i dati offline in Audience Manager per [!UICONTROL People-Based Destinations].

* [Invia dati batch](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) ad Audience Manager per acquisire indirizzi e-mail con hash. Con questo metodo, puoi scegliere di utilizzare gli indirizzi e-mail con hash del tuo database [!DNL CRM] in [!UICONTROL People-Based Destinations]. Inoltre, quando utilizzi questo metodo, puoi anche qualificare gli indirizzi e-mail con hash per [caratteristiche onboarded](../traits/trait-and-segment-qualification-reference.md).
* Utilizza [ID dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmetti gli ID cliente autenticati. Quando si utilizza questo metodo, Audience Manager, per tuo conto, invia a [!UICONTROL People-Based Destinations] solo gli indirizzi e-mail con hash degli utenti che hanno eseguito l&#39;autenticazione online. Gli indirizzi e-mail attivati tramite i canali basati sulle persone sono solo quelli nelle chiamate all’evento degli ID dichiarati. Gli altri indirizzi e-mail associati all’ID cliente non vengono inviati in tempo reale.
