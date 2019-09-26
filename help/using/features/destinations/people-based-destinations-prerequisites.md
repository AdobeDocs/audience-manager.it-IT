---
description: 'Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.  '
seo-description: 'Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.  '
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Prerequisites and Considerations
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# Prerequisites and Considerations {#prerequisites-considerations}

Read below for an overview of customer requirements that you need to meet before signing up for [!DNL People-Based Destinations].

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

## Onboarding dei dati {#data-onboarding}

L'assimilazione dei dati per [!DNL People-Based Destinations] ora supporta fino a 10 indirizzi e-mail con hash collegati a un ID cliente ([!DNL CRM ID]), per trasferimento batch. Il caricamento di più di 10 indirizzi e-mail con hash collegati a un ID cliente causa l’inserimento di 10 indirizzi da parte di Audience Manager, senza un ordine specifico.

Se si caricano più di 10 indirizzi e-mail con hash collegati a un ID cliente in più trasferimenti batch, Audience Manager conserva gli ultimi 10 indirizzi e-mail aggiunti.

## Privacy dei dati {#data-privacy}

Anche se [!DNL People-Based Destinations] consentite di eseguire il targeting dei tipi di pubblico in base agli indirizzi e-mail con hash caricati dall'utente, non potete caricare in Audience Manager eventuali informazioni sui visitatori direttamente identificabili. Nella fase di onboarding dei dati, devi accertarti che gli indirizzi e-mail che intendi utilizzare siano crittografati con l' [!DNL SHA256] algoritmo. In caso contrario, non potrai utilizzarli in [!DNL People-Based Destinations].

## Hashing dati contro crittografia {#data-hashing-encryption}

La crittografia è una funzione bidirezionale. È inoltre possibile decrittografare qualsiasi informazione crittografata utilizzando la chiave di decrittazione corretta. La cifratura dei dati nel contesto di Audience Manager comporta seri rischi, poiché è possibile decifrare anche qualsiasi forma crittografata di informazioni personali. Invece della cifratura, [!DNL People-Based Destinations] sono progettati per funzionare con dati con hash.

Hashing è una funzione unidirezionale che scorre l'input per produrre un risultato unico. Utilizzando gli algoritmi di hashing appropriati, come [!DNL SHA256], non c'è modo di invertire la funzione di hashing e rivelare le informazioni non scorrevoli. Gli indirizzi e-mail che si desidera inserire in Audience Manager devono essere crittografati con l’ [!DNL SHA256] algoritmo. This way, you can ensure that no unhashed email addresses reach Audience Manager.

## Requisiti di hash {#hashing-requirements}

When hashing the email addresses, make sure to comply with the following requirements:

* Trim all leading and trailing spaces from the email string; example: , not ;`johndoe@example.com``<space>johndoe@example.com<space>`
* Make sure the hashed string is all lowercase; example: , not ;`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149``55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`
* Do not salt the string.

Adobe Experience Cloud gives you the option to hash customer IDs through the Experience Cloud ID Service. See SHA256 Hashing Support for setCustomerIDs for detailed information on how to use ECID to hash customer IDs.[](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html)

## Obtaining User Permission {#obtaining-user-permission}

Since  helps you activate first-party audience data in people-based channels, it is your responsibility to inform and obtain any necessary consents from your customers of how you will use their data for advertising or other purposes.[!DNL People-Based Destinations]

Before you sign up for , make sure to obtain your customers' consent before using their information for advertising purposes.[!DNL People-Based Destinations]

In case your customers wish to opt-out of advertising campaigns, see Opt-out Management for details on how to stop Audience Manager from collecting data any further.[](../../overview/data-security-and-privacy/opt-out-management.md)

## Enforcing First-Party Data Activation {#enforcing-first-party-activation}

When using , you can only use first-party data to activate audience segments in people-based channels. [!DNL People-Based Destinations] Non potete utilizzare dati di seconda o terza parte per l'attivazione dell'audience nei canali basati sulle persone.

## Onboard Authenticated Hashed IDs through Declared ID Targeting {#onboard-authenticated-declared-id}

There are two ways you can bring your offline data to Audience Manager for .[!DNL People-Based Destinations]

* [Invia dati](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) batch ad Audience Manager per il caricamento di indirizzi e-mail con hash. Con questo metodo, potete scegliere di utilizzare gli indirizzi e-mail con hash del [!DNL CRM] database in [!DNL People-Based Destinations]. Inoltre, quando utilizzate questo metodo, potete anche qualificare gli indirizzi e-mail con hash per le caratteristiche [registrate](../traits/trait-qualification-reference.md).
* Usate gli ID [dichiarati](../declared-ids.md) per dichiarare gli indirizzi e-mail con hash quando trasmettete gli ID cliente autenticati. Quando si utilizza questo metodo, Audience Manager, per vostro conto, invia solo agli indirizzi e-mail con [!DNL People-Based Destinations] hash degli utenti che hanno eseguito l'autenticazione online. Gli indirizzi e-mail attivati attraverso i canali basati sulle persone sono solo quelli nelle chiamate dell'evento ID dichiarate. Gli altri indirizzi e-mail associati all'ID cliente non vengono inviati in tempo reale.
