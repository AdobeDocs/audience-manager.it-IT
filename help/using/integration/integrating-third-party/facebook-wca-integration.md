---
description: Questa pagina illustra il processo di creazione di pixel WCA (Custom Audiences) per il sito web di Facebook allo scopo di inviare segmenti di pubblico di Audienci Manager basati su web a Facebook, per il targeting di annunci online con una maggiore trasparenza.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integrazione WCA facebook
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# Integrazione di [!DNL Facebook WCA] {#facebook-wca-integration}

In questa pagina viene illustrato il processo di creazione di [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixel allo scopo di inviare segmenti di pubblico [!DNL Audience Manager] basati sul Web a [!DNL Facebook], per il targeting di annunci online con maggiore trasparenza.

>[!IMPORTANT]
>
>Questa non è un’integrazione prodotta tra Audience Manager e Facebook.

## Panoramica {#overview}

[Tipi di pubblico personalizzati del sito Web Facebook (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) consente di creare un elenco di persone che hanno visitato determinate pagine o intrapreso azioni particolari sul sito Web. [!DNL Audience Manager] abilita l&#39;attivazione in [!DNL WCA] utilizzando [!DNL URL] destinazioni, con le quali è possibile configurare un&#39;integrazione personalizzata basata su pixel per inviare tipi di pubblico basati sul Web a [!DNL Facebook] per il targeting.

![Integrazione di Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Questa funzionalità richiede la selezione dell&#39;opzione [!UICONTROL Website] pubblico per piattaforme social in [Destinazioni URL](/help/using/features/destinations/create-url-destination.md). Le piattaforme social richiedono che le informazioni del referente vengano smascherate quando vengono inviate alla loro piattaforma. Tieni presente che la piattaforma/partner di destinazione sarà in grado di visualizzare le informazioni nel referente [!DNL URL].

## Prerequisiti {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmenti, pronti per l&#39;assegnazione alla nuova destinazione [!DNL Facebook]. Ecco [come creare un segmento](/help/using/features/segments/segment-builder.md) nell&#39;interfaccia utente di [!DNL Audience Manager].
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) versione 4.1.0 o successiva. Scarica la versione più recente **[qui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versione 9.0 o successiva, scaricabile da **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. In alternativa, se si utilizza [Server-Side Forwarding (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) per importare dati in [!DNL Audience Manager], è necessario utilizzare AppMeasurement versione 2.12 o successiva. Scarica [!DNL AppMeasurement] utilizzando [Analytics Code Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

È consigliabile installare o aggiornare le librerie nei passaggi 3 e 4 utilizzando [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Passaggio 1 - Creare un [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Creare un nuovo [!UICONTROL URL Destination] in [!DNL Audience Manager] e denominarlo [!DNL Facebook Website Custom Audiences]. Utilizza le impostazioni seguenti per creare la destinazione. È inoltre possibile fare riferimento alla pagina [Configurare una destinazione URL](/help/using/features/destinations/create-url-destination.md).

### Informazioni di base

* **[!UICONTROL Category]**: Personalizzato
* **[!UICONTROL Type]**: [!DNL URL]
* Selezionare la casella di controllo **[!UICONTROL Auto-fill Destination Mapping]**, quindi selezionare **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selezionare l&#39;opzione **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Questa etichetta di esportazione impedisce l’inclusione di dati di terze parti e di dati derivati da grafici dei dispositivi nei segmenti.

### Configurazione

* **[!UICONTROL URL type]**: Selezionare **[!UICONTROL Website audience for social platforms]**. Selezionando questa opzione [!UICONTROL URL Type], [!DNL Audience Manager] non nasconde le informazioni del referente [!DNL URL] durante l&#39;attivazione di un pixel [!DNL Facebook WCA].
* **[!UICONTROL Serialize]**: Selezionare **[!UICONTROL Enable]**.
* Nel campo **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]** immettere il pixel [!DNL Facebook WCA].
* **[!UICONTROL Delimiter]**: `,`

Esempio di base [!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Esempio di pixel attivato dalla pagina. Questo esempio mostra un utente idoneo per tre segmenti [!DNL Audience Manager], con gli ID 3401321, 2993399 e 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parametro | Descrizione |
|---------|----------|
| `id` | L&#39;ID pixel di [!DNL Facebook], che si trova nell&#39;interfaccia utente di [!DNL Facebook Ad Manager] durante la creazione dei pixel del pubblico. |
| `ev` | Evento. Si tratta di un valore arbitrario che verrà visualizzato nell&#39;interfaccia utente [!DNL Facebook Ad Manager] quando il pixel inizia a essere attivato sul sito. Per ulteriori informazioni, vedere l&#39;elemento [!UICONTROL Include] in [Passaggio 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Un parametro aggiuntivo, che inizierà a essere popolato all&#39;interno dell&#39;interfaccia utente [!DNL Facebook Ad Manager] quando il pixel inizierà a essere attivato sul sito. `segID` è anche arbitrario. |
| `%ALIAS%` | Una macro [!DNL Audience Manager], che verrà sostituita dinamicamente con gli ID [!DNL Audience Manager] [!UICONTROL segment] per cui il visitatore del sito è idoneo, delimitati da virgole , |

La configurazione di [!UICONTROL URL destination] deve essere simile a quella nell&#39;immagine seguente:

![Configurazione destinazione](/help/using/integration/assets/facebook-wca.png)

Salva [!UICONTROL destination]. Quindi puoi procedere al passaggio **Mappature segmento**.

## Passaggio 2: mappature dei segmenti - mappatura del segmento alla destinazione {#step-2-segment-mappings}

Nel flusso di lavoro [Configura destinazione URL](/help/using/features/destinations/create-url-destination.md), mappa il segmento applicabile al nuovo [!UICONTROL destination] creato. Il valore di mappatura viene compilato automaticamente con [!DNL Audience Manager] [!UICONTROL segment ID].

Inserire una data di fine, se applicabile, altrimenti lasciare vuoto per non specificare alcuna data di fine.

## Passaggio 3 - Creare un [!UICONTROL Audience] entro [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulta [Creare un pubblico personalizzato per il sito Web](https://www.facebook.com/business/help/666509013483225) nella documentazione di [!DNL Facebook]. Selezionare le opzioni [!UICONTROL Create Audience] nella tabella seguente:

| Elemento | Descrizione |
|---------|----------|
| Traffico del sito web | Combinazione personalizzata |
| Includi | <ul><li>Selezionare **[!UICONTROL Event]** > Seleziona **[!UICONTROL Adobe-Audience-Manager-Segment]**. Questo era il valore del parametro `ev` nel pixel di esempio nel passaggio 1. Se il pixel non è ancora stato attivato, è possibile che l&#39;opzione **[!UICONTROL Event]** o **[!UICONTROL Adobe-Audience-Manager-Segment]** non venga visualizzata nell&#39;interfaccia utente di [!DNL Facebook].</li><li>Aggiungi un parametro: Seleziona `segID`.</li><li><p>Selezionare l&#39;operatore **contains**.</p><p>Questo è importante, considerando che i visitatori possono qualificarsi per più segmenti, ci possono essere più [!UICONTROL segment IDs] nel parametro pixel. L&#39;utilizzo dell&#39;operatore è uguale a (`=`) potrebbe non qualificare i visitatori per il pubblico e si osserverà un volume inferiore.</p></li><li>Aggiungi un valore: immetti l&#39;ID del segmento [!DNL Audience Manager].</li></ul> |
| Aggiungi nuova condizione | Impostazione facoltativa. |
| Nell&#39;ultimo/a | Impostazione facoltativa. |
| Nome pubblico | È consigliabile utilizzare lo stesso nome di segmento [!DNL Audience Manager] per coerenza, a meno che non vengano aggiunte condizioni aggiuntive a questo pubblico. |

## Passaggio 4: assegnare [!UICONTROL Audience] a [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Dopo aver creato [!DNL Custom Audience], assegnalo a una campagna pubblicitaria. Crea una nuova campagna o modificane una esistente. Il pubblico appena creato sarà elencato nell&#39;interfaccia utente di [!DNL Facebook]. La tua campagna pubblicitaria eseguirà il targeting degli utenti che hanno visto il pixel acceso sul browser quando visitano il tuo sito, se [!DNL Audience Manager] li include nel segmento.

## Riepilogo {#summary}

Ora che hai assegnato il segmento [!DNL Audience Manager] alla destinazione [!DNL Facebook WCA], [!DNL Audience Manager] attiverà selettivamente il pixel [!DNL Facebook WCA] per gli utenti di un dato segmento con il rispettivo ID segmento nel pixel per popolare [!DNL Facebook Audience]. Ciò comporta un aumento graduale di [!DNL Facebook Audience] e più il tag viene attivato per il pubblico applicabile sul sito.

>[!NOTE]
>
> Se un utente non rientra nel segmento [!DNL Audience Manager], al momento [!DNL Audience Manager] non ha modo di informare [!DNL Facebook] della rimozione dell&#39;utente da [!DNL Custom Audience].
>
