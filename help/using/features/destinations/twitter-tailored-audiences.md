---
description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-title: Configurare l'audience personalizzata di Twitter come destinazione autonoma basata su dispositivo
solution: Audience Manager
title: Configurare l'audience personalizzata di Twitter come destinazione autonoma basata su dispositivo
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 1%

---


# Configurare [!DNL Twitter Tailored Audiences] come destinazione autonoma basata su dispositivo {#configure-twitter}

Questo articolo spiega come configurare un&#39;integrazione con audience [personalizzate per](https://business.twitter.com/en/targeting/tailored-audiences.html)Twitter.

## Prerequisiti {#prerequisites}

Prima di configurare la [!DNL Twitter Tailored Audiences] destinazione, accertatevi di verificare i seguenti prerequisiti Twitter da soddisfare.

1. Il tuo [!DNL Twitter Ads] account deve essere idoneo per la pubblicità. I nuovi [!DNL Twitter Ads] account non sono ammessi alla pubblicità nelle prime due settimane dopo la loro creazione.
2. L&#39;account [!DNL Twitter] utente per il quale hai autorizzato l&#39;accesso in  Audience Manager deve avere l&#39;autorizzazione [Partner Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) abilitata.
3. Quando crei la prima [!DNL Twitter Tailored Audiences] destinazione nell&#39;istanza di Audience Manager , contatta il servizio di consulenza Adobe o l&#39;Assistenza clienti per abilitare la sincronizzazione [!DNL Twitter] ID (ID origine dati = 1123) per il tuo account. Questo è necessario per la corretta sincronizzazione tra  Audience Manager e [!DNL Twitter].

## Aggiungi una nuova [!DNL Twitter Tailored Audiences] destinazione {#add-new-twitter-destination}

Questa sezione descrive i passaggi da seguire per configurare una nuova destinazione basata su dispositivo per [!DNL Twitter Tailored Audiences]. Questo scenario presuppone che non sia configurata alcuna [!DNL Twitter Tailored Audiences] destinazione tramite il consulente Adobe o l&#39;Assistenza clienti.

### Passaggio 1: Autenticazione con [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Prima di poter aggiungere la destinazione basata sul dispositivo, è necessario collegare  Audience Manager e il [!DNL Twitter Tailored Audiences] proprio account. Come procedere:

1. Accedete al vostro account Audience Manager  e andate a **[!DNL Administration > Integrated Accounts]**. Se disponete di un&#39;integrazione configurata in precedenza con una piattaforma di destinazione, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
1. Clic **[!DNL Add Account]**.
1. Selezionate [!DNL Twitter Tailored Audiences] e fate clic **[!DNL Confirm]** per reindirizzare la pagina di autenticazione.                     ![piattaforme integrate](assets/dbd-integrated-platforms.png)
1. Dopo l&#39;autenticazione, verrete reindirizzati a  Audience Manager dove dovrebbero essere visualizzati gli account dell&#39;inserzionista associato. Selezionate l’account dell’inserzionista da usare e fate clic su **[!DNL Confirm]**.

### Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2-create-new-destination}

Dopo aver collegato  Audience Manager e l&#39; [!DNL Twitter Tailored Audiences], potete creare la nuova destinazione. Come procedere:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione esistente basata su dispositivo. Assicuratevi di fornire un nome che vi aiuterà a identificare correttamente la destinazione.

1. Accedete al vostro account Audience Manager , andate a **[!DNL Audience Data > Destinations]** e fate clic su **[!DNL Create Destination]**.
1. Nella **[!DNL Basic Information]** sezione, immettete un **[!DNL Name]** e **[!DNL Description]** per la nuova destinazione e utilizzate le impostazioni seguenti: ![setup](assets/dbd-new-basic.png)
1. Clic **[!DNL Next]**.
1. Scegliere le etichette [di esportazione](/help/using/features/data-export-controls.md#controls-labels) dati da impostare per questa destinazione.
1. Clic **[!DNL Save]**.
1. Nella **[!DNL Segment Mappings]** sezione, selezionate i segmenti di pubblico che desiderate inviare a questa destinazione.
1. Salva la destinazione.

## Considerazioni sulla mappatura dei segmenti {#segment-mapping-considerations}

Quando mappate i segmenti di pubblico su [!UICONTROL Twitter], accertatevi di soddisfare i seguenti requisiti di denominazione dei segmenti:

* Fornisci nomi di mappatura dei segmenti leggibili dall’utente. È consigliabile utilizzare lo stesso nome utilizzato per i segmenti Audience Manager .
* Non utilizzare caratteri speciali (`,``%` `:``;` `@``/``=` `?` `$`) nei nomi di mappatura segmenti e segmenti. Se il nome  segmento Audience Manager contiene questi caratteri, rimuoverli prima di mappare il segmento a una [!UICONTROL Twitter] destinazione.

### Esempio 

* Correggi il nome del segmento o della mappatura: &quot;Acquirenti statunitensi ed europei&quot;;
* Nome segmento o mappatura errato: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Non è possibile modificare i nomi dei segmenti già mappati.  Audience Manager utilizza i nomi dei segmenti per identificare correttamente i segmenti nell&#39;integrazione.

## Considerazioni sui tassi di corrispondenza {#match-rates-considerations}

* Quando si utilizza [!UICONTROL Twitter Tailored Audiences], le [!UICONTROL Segment Addressable Audience] metriche e quelle [!UICONTROL Segment Match Rate] della pagina di destinazione non visualizzeranno alcun valore. Si tratta di un comportamento normale, in quanto l&#39;audience che corrisponde con le percentuali di corrispondenza per questa destinazione viene gestita e ospitata da [!UICONTROL Twitter], non da Adobe.
* L&#39;integrazione tra  Audience Manager e [!UICONTROL Twitter Tailored Audiences] supporta i backfill storici del pubblico. Tutte le qualifiche del segmento vengono inviate al [!UICONTROL Twitter] momento della creazione della destinazione.
