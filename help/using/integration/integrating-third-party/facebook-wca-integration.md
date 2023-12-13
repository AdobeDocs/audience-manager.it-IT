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

# [!DNL Facebook WCA] Integrazione {#facebook-wca-integration}

Questa pagina illustra il processo di creazione di [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixel allo scopo di inviare dati basati su Web [!DNL Audience Manager] segmenti di pubblico a [!DNL Facebook], per il targeting di annunci online con maggiore trasparenza.

>[!IMPORTANT]
>
>Questa non è un’integrazione prodotta tra Audienci Manager e Facebook.

## Panoramica {#overview}

[Pubblico personalizzato sito web facebook (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) consente di creare un elenco di persone che hanno visitato determinate pagine o intrapreso azioni particolari sul sito web. [!DNL Audience Manager] abilita l&#39;attivazione in [!DNL WCA] utilizzo [!DNL URL] destinazioni, con cui puoi configurare un’integrazione personalizzata basata su pixel per inviare un pubblico basato su web a [!DNL Facebook] per il targeting.

![Integrazione di Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Questa funzionalità richiede la selezione di [!UICONTROL Website] opzione pubblico per piattaforme social in [Destinazioni URL](/help/using/features/destinations/create-url-destination.md). Le piattaforme social richiedono che le informazioni del referente vengano smascherate quando vengono inviate alla loro piattaforma. Tieni presente che la piattaforma/il partner di destinazione sarà in grado di visualizzare le informazioni nel referrer [!DNL URL].

## Prerequisiti {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmenti, pronti per l’assegnazione al nuovo [!DNL Facebook] destinazione. Ecco [come creare un segmento](/help/using/features/segments/segment-builder.md) nel [!DNL Audience Manager] UI.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versione 4.1.0 o successiva. Scarica la versione più recente **[qui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versione 9.0 o successiva, scaricabile da **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. In alternativa, se utilizzi [Server-Side Forwarding (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) per importare dati in [!DNL Audience Manager], è necessario utilizzare la versione 2.12 o successiva di AppMeasurement. Scarica [!DNL AppMeasurement] utilizzando [Gestione codici di Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

È consigliabile installare o aggiornare le librerie nei passaggi 3 e 4 utilizzando [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Passaggio 1: creare un [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Crea un nuovo [!UICONTROL URL Destination] in [!DNL Audience Manager] e denominalo [!DNL Facebook Website Custom Audiences]. Utilizza le impostazioni seguenti per creare la destinazione. È inoltre possibile fare riferimento al [Configurare una destinazione URL](/help/using/features/destinations/create-url-destination.md) pagina.

### Informazioni di base

* **[!UICONTROL Category]**: Personalizzato
* **[!UICONTROL Type]**: [!DNL URL]
* Seleziona la **[!UICONTROL Auto-fill Destination Mapping]** , quindi seleziona **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Seleziona l’opzione **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Questa etichetta di esportazione impedisce l’inclusione di dati di terze parti e di dati derivati da grafici dei dispositivi nei segmenti.

### Configurazione

* **[!UICONTROL URL type]**: Seleziona **[!UICONTROL Website audience for social platforms]**. Selezionando questo [!UICONTROL URL Type] opzione, [!DNL Audience Manager] non oscura il referente [!DNL URL] quando si attiva una [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Seleziona **[!UICONTROL Enable]**.
* In **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]** , immettere il [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL] esempio: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Esempio di pixel attivato dalla pagina. Questo esempio mostra un utente idoneo per tre [!DNL Audience Manager] segmenti, con gli ID 3401321, 2993399 e 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parametro | Descrizione |
|---------|----------|
| `id` | Il tuo [!DNL Facebook] ID pixel, disponibile nella sezione [!DNL Facebook Ad Manager] durante la creazione di pixel per il pubblico. |
| `ev` | Evento. Si tratta di un valore arbitrario che verrà visualizzato nel [!DNL Facebook Ad Manager] una volta che il pixel inizia a essere attivato sul sito. Consulta la [!UICONTROL Include] elemento in [Passaggio 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), per ulteriori informazioni. |
| `cd[segID]` | Un parametro aggiuntivo, che inizierà a essere popolato all&#39;interno del [!DNL Facebook Ad Manager] una volta che il pixel inizia a essere attivato sul sito. `segID` è anche arbitrario. |
| `%ALIAS%` | Un [!DNL Audience Manager] macro, che verrà sostituita dinamicamente con la [!DNL Audience Manager] [!UICONTROL segment] ID idonei per il visitatore del sito, delimitati da virgole , |

Il tuo [!UICONTROL URL destination] La configurazione deve essere simile a quella riportata di seguito:

![Configurazione di destinazione](/help/using/integration/assets/facebook-wca.png)

Salva il [!UICONTROL destination]. Quindi, puoi passare alla sezione **Mappature dei segmenti** passaggio.

## Passaggio 2: mappature dei segmenti - mappatura del segmento alla destinazione {#step-2-segment-mappings}

In [Configurare la destinazione URL](/help/using/features/destinations/create-url-destination.md) flusso di lavoro, mappa il segmento applicabile sul nuovo segmento creato [!UICONTROL destination]. Nota che il valore di mappatura viene compilato automaticamente con [!DNL Audience Manager] [!UICONTROL segment ID].

Inserire una data di fine, se applicabile, altrimenti lasciare vuoto per non specificare alcuna data di fine.

## Passaggio 3: creare un [!UICONTROL Audience] entro [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulta [Creare un pubblico personalizzato per il sito web](https://www.facebook.com/business/help/666509013483225) nel [!DNL Facebook] documentazione della guida. Seleziona la [!UICONTROL Create Audience] nella tabella seguente:

| Elemento | Descrizione |
|---------|----------|
| Traffico del sito web | Combinazione personalizzata |
| Includi | <ul><li>Seleziona **[!UICONTROL Event]** > Seleziona **[!UICONTROL Adobe-Audience-Manager-Segment]**. Questo era il valore del `ev` nel pixel di esempio nel passaggio 1. Se il pixel non è ancora stato attivato, **[!UICONTROL Event]** opzione o **[!UICONTROL Adobe-Audience-Manager-Segment]** potrebbe non essere visualizzato nel [!DNL Facebook] dell&#39;utente.</li><li>Aggiungi un parametro: Seleziona `segID`.</li><li><p>Seleziona la **contiene** operatore.</p><p>Questo è importante, considerando che i visitatori possono qualificarsi per più segmenti, possono esserci più [!UICONTROL segment IDs] nel parametro pixel. Utilizzo di è uguale a (`=`) potrebbe non qualificare i visitatori per il pubblico e si osserverà un volume inferiore.</p></li><li>Aggiungi un valore: immetti il valore [!DNL Audience Manager] ID segmento.</li></ul> |
| Aggiungi nuova condizione | Impostazione facoltativa. |
| Nell&#39;ultimo/a | Impostazione facoltativa. |
| Nome pubblico | Si consiglia di utilizzare lo stesso [!DNL Audience Manager] nome del segmento per coerenza, a meno che tu non aggiunga condizioni aggiuntive a questo pubblico. |

## Passaggio 4: assegnare il [!UICONTROL Audience] a un [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Dopo aver creato [!DNL Custom Audience], assegnalo a una campagna pubblicitaria. Crea una nuova campagna o modificane una esistente e il pubblico appena creato sarà elencato in [!DNL Facebook] dell&#39;utente. La tua campagna pubblicitaria è indirizzata agli utenti che hanno visto il pixel acceso sul browser quando visitano il sito, se [!DNL Audience Manager] li include nel segmento.

## Riepilogo {#summary}

Ora che hai assegnato il tuo [!DNL Audience Manager] segmento al [!DNL Facebook WCA] destinazione, [!DNL Audience Manager] attiverà selettivamente il [!DNL Facebook WCA] agli utenti di un dato segmento con il rispettivo ID segmento nel pixel per compilare il [!DNL Facebook Audience]. Ciò si traduce in un aumento graduale della [!DNL Facebook Audience] più il tag viene attivato per il pubblico applicabile sul sito.

>[!NOTE]
>
> Se un utente esce dal [!DNL Audience Manager] segmento, al momento non è possibile: [!DNL Audience Manager] per informare [!DNL Facebook] per rimuovere l&#39;utente da [!DNL Custom Audience].
>
