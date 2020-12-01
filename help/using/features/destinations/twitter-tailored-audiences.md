---
description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-description: Questo articolo spiega come configurare l'audience personalizzata per Twitter per le integrazioni nuove ed esistenti.
seo-title: Configurare pubblici personalizzati di Twitter come una destinazione self-service basata su dispositivi
solution: Audience Manager
title: Configurare pubblici personalizzati di Twitter come una destinazione self-service basata su dispositivi
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 8ff76decc1cbd7f7babd619dd1ce9fe047541337
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 4%

---


# Configurare [!DNL Twitter Tailored Audiences] come destinazione autonoma basata su dispositivo {#configure-twitter}

Questo articolo spiega come configurare un&#39;integrazione con [Pubblico personalizzato su Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html).

## Prerequisiti {#prerequisites}

Prima di configurare la destinazione [!DNL Twitter Tailored Audiences], accertatevi di verificare i seguenti prerequisiti Twitter da soddisfare.

1. Il tuo account [!DNL Twitter Ads] deve essere idoneo per la pubblicità. I nuovi account [!DNL Twitter Ads] non sono ammessi alla pubblicità nelle prime due settimane successive alla creazione.
2. L&#39;account [!DNL Twitter] per il quale avete autorizzato l&#39;accesso nel  Audience Manager deve avere l&#39;autorizzazione [Partner Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) abilitata.
3. Quando crei la prima [!DNL Twitter Tailored Audiences] destinazione nell&#39;istanza  Audience Manager, contatta  Consulente di Adobe o l&#39;Assistenza clienti per abilitare la sincronizzazione ID [!DNL Twitter] (ID origine dati = 1123) per il tuo account. Questo è necessario per la corretta sincronizzazione tra  Audience Manager e [!DNL Twitter].

## Aggiungere una nuova [!DNL Twitter Tailored Audiences] destinazione {#add-new-twitter-destination}

Questa sezione descrive i passaggi da seguire per configurare una nuova destinazione basata su dispositivo per [!DNL Twitter Tailored Audiences]. In questo scenario si presuppone che non esista una [!DNL Twitter Tailored Audiences] destinazione configurata tramite il consulente del Adobe  o l&#39;Assistenza clienti.

### Passaggio 1: Autenticazione con [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Prima di poter aggiungere la destinazione basata sul dispositivo, è necessario collegare  Audience Manager e l&#39;account [!DNL Twitter Tailored Audiences]. Come procedere:

1. Accedete al vostro account  Audience Manager e andate a **[!DNL Administration > Integrated Accounts]**. Se disponete di un&#39;integrazione configurata in precedenza con una piattaforma di destinazione, visualizzatela in questa pagina. In caso contrario, la pagina è vuota.
1. Clic **[!DNL Add Account]**.
1. Selezionare [!DNL Twitter Tailored Audiences] e fare clic su **[!DNL Confirm]** per reindirizzare la pagina di autenticazione.                     ![piattaforme integrate](assets/dbd-integrated-platforms.png)
1. Dopo l&#39;autenticazione, verrete reindirizzati  Audience Manager in cui dovrebbero essere visualizzati gli account dell&#39;inserzionista associato. Selezionate l&#39;account dell&#39;inserzionista che desiderate utilizzare e fate clic su **[!DNL Confirm]**.

### Passaggio 2: Creare una nuova destinazione basata su dispositivo {#step2-create-new-destination}

Dopo aver collegato  Audience Manager e il [!DNL Twitter Tailored Audiences], potete creare la nuova destinazione. Come procedere:

>[!NOTE]
>
>Non è possibile modificare il nome di una destinazione esistente basata su dispositivo. Assicuratevi di fornire un nome che vi aiuterà a identificare correttamente la destinazione.

1. Accedete al vostro account  Audience Manager, andate a **[!DNL Audience Data > Destinations]** e fate clic su **[!DNL Create Destination]**.
1. Nella sezione **[!DNL Basic Information]**, immettete un **[!DNL Name]** e un **[!DNL Description]** per la nuova destinazione e utilizzate le impostazioni seguenti: ![setup](assets/dbd-new-basic.png)
1. Clic **[!DNL Next]**.
1. Scegliere le [Etichette esportazione dati](/help/using/features/data-export-controls.md#controls-labels) che si desidera impostare per questa destinazione.
1. Clic **[!DNL Save]**.
1. Nella sezione **[!DNL Segment Mappings]**, selezionate i segmenti di pubblico che desiderate inviare a questa destinazione.
1. Salva la destinazione.

## Considerazioni sulla mappatura dei segmenti {#segment-mapping-considerations}

Quando mappate i segmenti di pubblico su [!UICONTROL Twitter], accertatevi di soddisfare i seguenti requisiti di denominazione dei segmenti:

* Fornisci nomi di mappatura dei segmenti leggibili dall’utente. È consigliabile utilizzare lo stesso nome utilizzato per i segmenti di Audience Manager .
* Non utilizzare caratteri speciali (`,` `%` `:` `;` `@` `/` `=` `?` &lt;a7/> `$`) nei nomi di mappatura segmenti e segmenti. Se il nome del segmento di Audience Manager  contiene questi caratteri, rimuoverli prima di mappare il segmento a una destinazione [!UICONTROL Twitter].

### Esempio

* Correggi il nome del segmento o della mappatura: &quot;Acquirenti statunitensi ed europei&quot;;
* Nome segmento o mappatura errato: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Non è possibile modificare i nomi dei segmenti già mappati.  Audience Manager utilizza i nomi dei segmenti per identificare correttamente i segmenti nell&#39;integrazione.

## Considerazioni sui tassi di corrispondenza {#match-rates-considerations}

* L&#39;integrazione tra  Audience Manager e [!UICONTROL Twitter Tailored Audiences] supporta i backfill storici del pubblico. Tutte le qualifiche del segmento vengono inviate a [!UICONTROL Twitter] al momento della creazione della destinazione.
