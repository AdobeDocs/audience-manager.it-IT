---
description: Questa pagina illustra il processo di creazione dei pixel del pubblico personalizzato del sito Web Facebook (WCA) allo scopo di inviare segmenti di pubblico di Audienci Manager basati sul Web a Facebook, per il targeting di annunci online con una migliore trasparenza.
seo-description: Questa pagina illustra il processo di creazione dei pixel del pubblico personalizzato del sito Web Facebook (WCA) allo scopo di inviare segmenti di pubblico di Audienci Manager basati sul Web a Facebook, per il targeting di annunci online con una migliore trasparenza.
seo-title: Integrazione di Facebook WCA
solution: Audience Manager
title: Integrazione di Facebook WCA
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 6%

---


# [!DNL Facebook WCA] Integrazione {#facebook-wca-integration}

Questa pagina illustra il processo di creazione di pixel [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) allo scopo di inviare segmenti di pubblico [!DNL Audience Manager] basati su Web a [!DNL Facebook], per il targeting di annunci online con maggiore trasparenza.

## Panoramica {#overview}

[Il sito Web di Facebook Custom Audiences (WCA) ](https://www.facebook.com/business/help/449542958510885) consente di creare un elenco di persone che hanno visitato determinate pagine o che hanno effettuato particolari azioni sul sito Web. [!DNL Audience Manager] abilita l&#39;attivazione  [!DNL WCA] utilizzando  [!DNL URL] le destinazioni, con le quali puoi configurare un&#39;integrazione personalizzata basata su pixel per l&#39;invio di audience basate sul Web  [!DNL Facebook] per il targeting.

![Integrazione di Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Questa funzionalità richiede la selezione dell&#39;opzione [!UICONTROL Website] audience per le piattaforme social in [destinazioni URL](/help/using/features/destinations/create-url-destination.md). Le piattaforme social richiedono che le informazioni sul referente vengano smascherate quando inviate alla propria piattaforma. Questo significa che la piattaforma/partner di destinazione sarà in grado di visualizzare le informazioni nel referente [!DNL URL].

## Prerequisiti {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmenti, pronti per essere assegnati alla nuova  [!DNL Facebook] destinazione. [come creare un segmento](/help/using/features/segments/segment-builder.md) nell&#39; [!DNL Audience Manager] interfaccia utente.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versione 4.1.0 o successiva. Scarica la versione più recente **[qui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versione 9.0 o successiva, scaricabile da  **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. In alternativa, se per importare i dati in [!DNL Audience Manager] si utilizza [Trasmissione lato server (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html), è necessario utilizzare AppMeasurement versione 2.12 o successiva. Scarica [!DNL AppMeasurement] utilizzando [Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

È consigliabile installare o aggiornare le librerie nei passaggi 3 e 4 utilizzando [ Adobe Experience Platform Launch](https://docs.adobelaunch.com/) o [ Gestione tag dinamica dei Adobi](https://docs.adobe.com/content/help/it-IT/dtm/using/dtm-home.html).

## Passaggio 1 - Crea un [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Create un nuovo [!UICONTROL URL Destination] in [!DNL Audience Manager] e denominatelo [!DNL Facebook Website Custom Audiences]. Durante la creazione della destinazione, usate le impostazioni riportate di seguito. È inoltre possibile fare riferimento alla pagina [Configura una destinazione URL](/help/using/features/destinations/create-url-destination.md).

### Informazioni di base

* **[!UICONTROL Category]**: Personalizzato
* **[!UICONTROL Type]**: [!DNL URL]
* Selezionare la casella di controllo **[!UICONTROL Auto-fill Destination Mapping]**, quindi selezionare **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selezionare l&#39;opzione **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Questa etichetta di esportazione impedisce l&#39;inclusione nei segmenti di dati e dati di terze parti derivati dai grafici dei dispositivi.

### Configurazione

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Selezionando questa opzione [!UICONTROL URL Type], [!DNL Audience Manager] non oscura le informazioni relative al referente [!DNL URL] durante l&#39;attivazione di un pixel [!DNL Facebook WCA].
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Nel campo **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]** immettere il pixel [!DNL Facebook WCA].
* **[!UICONTROL Delimiter]**:  `,`

Esempio di base [!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Esempio di pixel generato dalla pagina. Questo esempio mostra un utente idoneo per tre segmenti [!DNL Audience Manager], con gli ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parametro | Descrizione |
---------|----------|
| `id` | L&#39; [!DNL Facebook] ID pixel, che è possibile trovare nell&#39; [!DNL Facebook Ad Manager] interfaccia utente durante la creazione di pixel per il pubblico. |
| `ev` | Event.     Si tratta di un valore arbitrario che verrà visualizzato nell&#39;interfaccia utente [!DNL Facebook Ad Manager] quando il pixel inizierà a essere attivato sul sito. Per ulteriori informazioni, vedere l&#39;elemento [!UICONTROL Include] in [Passaggio 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Un parametro aggiuntivo, che inizierà a essere popolato all&#39;interno dell&#39;interfaccia utente [!DNL Facebook Ad Manager] quando il pixel inizierà a essere attivato sul sito. `segID` è anche arbitrario. |
| `%ALIAS%` | Una macro [!DNL Audience Manager], che verrà sostituita dinamicamente con gli [!DNL Audience Manager] [!UICONTROL segment] ID idonei per il visitatore del sito, delimitati da virgole , |

La configurazione [!UICONTROL URL destination] deve essere simile a quella dell&#39;immagine seguente:

![Configurazione della destinazione](/help/using/integration/assets/facebook-wca.png)

Salvare il file [!UICONTROL destination]. Quindi, puoi procedere al passaggio **Mappature segmenti**.

## Passaggio 2 - Mappature segmento - Mappa segmento a destinazione {#step-2-segment-mappings}

Nel flusso di lavoro [Configura destinazione URL](/help/using/features/destinations/create-url-destination.md), mappate il segmento applicabile alla [!UICONTROL destination] appena creata. Il valore di mappatura viene popolato automaticamente con [!DNL Audience Manager] [!UICONTROL segment ID].

Se applicabile, inserire una data di fine. In caso contrario lasciare vuoto il campo per nessuna data di fine.

## Passaggio 3 - Creare un [!UICONTROL Audience] all&#39;interno di [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consultate [Create a Website Custom Audience](https://www.facebook.com/business/help/666509013483225) (Creazione di un pubblico personalizzato per il sito Web) nella [!DNL Facebook] documentazione della guida. Selezionare le opzioni [!UICONTROL Create Audience] nella tabella seguente:

| Elemento | Descrizione |
---------|----------|
| Traffico sito Web | Combinazione personalizzata |
| Includi | <ul><li>Selezionare **[!UICONTROL Event]** > Seleziona **[!UICONTROL Adobe-Audience-Manager-Segment]**. Questo è il valore del parametro `ev` nel pixel di esempio nel passaggio 1. Se il pixel deve ancora essere attivato, l&#39;opzione **[!UICONTROL Event]** o **[!UICONTROL Adobe-Audience-Manager-Segment]** potrebbe non essere visualizzata nell&#39;interfaccia utente [!DNL Facebook].</li><li>Aggiungete un parametro: Selezionare `segID`.</li><li><p>Selezionare l&#39;operatore **contains**.</p><p>Ciò è importante, poiché i visitatori possono essere idonei per più segmenti, nel parametro pixel possono essere presenti più [!UICONTROL segment IDs]. L&#39;utilizzo dell&#39;operatore uguale a (`=`) potrebbe non essere idoneo dai visitatori per il pubblico, e si noterà un volume inferiore.</p></li><li>Aggiungete un valore: Immettere l&#39;ID del segmento [!DNL Audience Manager].</li></ul> |
| Aggiungi nuova condizione | Impostazione opzionale. |
| Nell&#39;ultimo | Impostazione opzionale. |
| Nome audience | È consigliabile utilizzare lo stesso nome di segmento [!DNL Audience Manager] per coerenza, a meno che non si stiano aggiungendo condizioni aggiuntive a questo pubblico. |

## Passaggio 4 - Assegnare la [!UICONTROL Audience] a [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Dopo aver creato il [!DNL Custom Audience], assegnatelo a una campagna pubblicitaria. Crea una nuova campagna o ne modifichi una esistente e troverai che il pubblico appena creato è elencato nell&#39;interfaccia [!DNL Facebook] utente. La campagna pubblicitaria verrà indirizzata agli utenti che hanno visto l&#39;attivazione dei pixel nel browser durante la visita del sito, se [!DNL Audience Manager] li include nel segmento.

## Riepilogo {#summary}

Dopo aver assegnato il segmento [!DNL Audience Manager] alla destinazione [!DNL Facebook WCA], [!DNL Audience Manager] attiverà selettivamente il pixel [!DNL Facebook WCA] per gli utenti di un dato segmento con il rispettivo ID segmento nel pixel per compilare il [!DNL Facebook Audience]. Ciò comporta un aumento graduale del [!DNL Facebook Audience], più il tag viene trasmesso al pubblico applicabile sul sito.

>[!NOTE]
>
> Se un utente non rientra nel segmento [!DNL Audience Manager], al momento [!DNL Audience Manager] non è possibile informare [!DNL Facebook] di rimuovere l&#39;utente dal segmento [!DNL Custom Audience].

