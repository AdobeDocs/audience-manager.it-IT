---
description: Questa pagina illustra il processo di creazione dei pixel di Facebook Website Custom Audiences (WCA) allo scopo di inviare segmenti di pubblico di Audience Manager basati su web a Facebook, per il targeting di annunci online con una maggiore trasparenza.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integrazione di Facebook WCA
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 8780083474d68717fe3bd4dc632d96da89929122
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Facebook WCA] Integrazione {#facebook-wca-integration}

Questa pagina illustra il processo di creazione [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixel per l’invio di dati basati sul web [!DNL Audience Manager] segmenti di pubblico in [!DNL Facebook], per il targeting di annunci online con una maggiore trasparenza.

## Panoramica {#overview}

[Tipi di pubblico personalizzati del sito web facebook (WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) consente di creare un elenco di persone che hanno visitato determinate pagine o che hanno eseguito determinate azioni sul sito web. [!DNL Audience Manager] abilita l&#39;attivazione in [!DNL WCA] utilizzo [!DNL URL] destinazioni con le quali puoi configurare un’integrazione personalizzata basata su pixel per inviare tipi di pubblico basati sul web a [!DNL Facebook] per il targeting.

![Integrazione di Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Questa funzionalità richiede la selezione della [!UICONTROL Website] pubblico per l’opzione piattaforme social in [Destinazioni URL](/help/using/features/destinations/create-url-destination.md). Le piattaforme social richiedono che le informazioni sui referenti vengano smascherate quando inviate alla loro piattaforma. Tieni presente che ciò significa che la piattaforma/il partner di destinazione sarà in grado di visualizzare le informazioni nel referente [!DNL URL].

## Prerequisiti {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmenti, pronti per l’assegnazione al nuovo [!DNL Facebook] destinazione. Qui [come creare un segmento](/help/using/features/segments/segment-builder.md) in [!DNL Audience Manager] Interfaccia utente.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versione 4.1.0 o successiva. Scarica la versione più recente **[qui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versione 9.0 o successiva, scaricabile da **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. In alternativa, se utilizzi [Server-Side Forwarding (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) per importare dati in [!DNL Audience Manager], devi utilizzare AppMeasurement versione 2.12 o successiva. Scarica [!DNL AppMeasurement] utilizzando [Gestione codici di Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

È consigliabile installare o aggiornare le librerie nei passaggi 3 e 4 utilizzando [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Passaggio 1 - Creare un [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Crea un nuovo [!UICONTROL URL Destination] in [!DNL Audience Manager] e denominalo [!DNL Facebook Website Custom Audiences]. Utilizza le impostazioni seguenti durante la creazione della destinazione. Puoi inoltre fare riferimento alla sezione [Configurare una destinazione URL](/help/using/features/destinations/create-url-destination.md) pagina.

### Informazioni di base

* **[!UICONTROL Category]**: Personalizzato
* **[!UICONTROL Type]**: [!DNL URL]
* Seleziona la **[!UICONTROL Auto-fill Destination Mapping]** casella di controllo, quindi selezionare **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Seleziona l’opzione **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Questa etichetta di esportazione impedisce l’inclusione nei segmenti di dati e dati di terze parti derivati da grafici dei dispositivi.

### Configurazione

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Selezionando questa opzione [!UICONTROL URL Type] opzione, [!DNL Audience Manager] non oscura il referente [!DNL URL] informazioni durante l&#39;attivazione di un [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* In **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]** campo , inserisci [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL] esempio: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Esempio di pixel generati dalla pagina. Questo esempio mostra un utente idoneo per tre [!DNL Audience Manager] segmenti, con gli ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parametro | Descrizione |
|---------|----------|
| `id` | Le [!DNL Facebook] ID pixel, che puoi trovare nel [!DNL Facebook Ad Manager] interfaccia utente durante la creazione dei pixel del pubblico. |
| `ev` | Event.   Si tratta di un valore arbitrario, che verrà visualizzato nel [!DNL Facebook Ad Manager] interfaccia utente una volta che il pixel inizia ad attivarsi sul sito. Consulta la sezione [!UICONTROL Include] elemento in [Passaggio 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), per ulteriori informazioni. |
| `cd[segID]` | Un parametro aggiuntivo che inizierà a essere popolato all&#39;interno della [!DNL Facebook Ad Manager] interfaccia utente una volta che il pixel inizia ad attivarsi sul sito. `segID` è anche arbitrario. |
| `%ALIAS%` | Un [!DNL Audience Manager] macro, che verrà sostituita dinamicamente con [!DNL Audience Manager] [!UICONTROL segment] ID idonei per il visitatore del sito, delimitati da virgole , |

Le [!UICONTROL URL destination] La configurazione dovrebbe essere simile a quella dell&#39;immagine seguente:

![Configurazione della destinazione](/help/using/integration/assets/facebook-wca.png)

Salva il [!UICONTROL destination]. Quindi, puoi procedere alla **Mappature dei segmenti** passo.

## Passaggio 2 - Mappature dei segmenti - Mappatura di segmenti su destinazione {#step-2-segment-mappings}

In [Configurare la destinazione URL](/help/using/features/destinations/create-url-destination.md) flusso di lavoro, mappa il segmento applicabile al segmento appena creato [!UICONTROL destination]. Tieni presente che il valore di mappatura viene compilato automaticamente con la variabile [!DNL Audience Manager] [!UICONTROL segment ID].

Inserisci una data di fine, se applicabile, altrimenti lascia vuoto per nessuna data di fine.

## Passaggio 3: creare un [!UICONTROL Audience] entro [!DNL Facebook Ads Manager] {#step-3-create-audience}

Vedi [Creare un pubblico personalizzato per un sito web](https://www.facebook.com/business/help/666509013483225) in [!DNL Facebook] guida. Seleziona la [!UICONTROL Create Audience] nella tabella seguente:

| Elemento | Descrizione |
|---------|----------|
| Traffico sito web | Combinazione personalizzata |
| Includi | <ul><li>Seleziona **[!UICONTROL Event]** > Seleziona **[!UICONTROL Adobe-Audience-Manager-Segment]**. Questo era il valore del `ev` nel pixel di esempio al punto 1. Tieni presente che se il pixel deve ancora attivarsi, il **[!UICONTROL Event]** opzione o **[!UICONTROL Adobe-Audience-Manager-Segment]** potrebbero non essere visualizzati nel [!DNL Facebook] interfaccia utente.</li><li>Aggiungi un parametro: Seleziona `segID`.</li><li><p>Seleziona la **contiene** operatore.</p><p>Questo è importante, poiché i visitatori possono qualificarsi per più segmenti, potrebbero essere presenti più [!UICONTROL segment IDs] nel parametro pixel. Utilizzando &quot;è uguale a&quot; (`=`) potrebbe non essere adatto ai visitatori per il pubblico e si noterà un volume inferiore.</p></li><li>Aggiungi un valore: Inserisci il [!DNL Audience Manager] ID segmento.</li></ul> |
| Aggiungi nuova condizione | Impostazione opzionale. |
| Nell&#39;ultimo | Impostazione opzionale. |
| Nome del pubblico | Si consiglia di utilizzare lo stesso [!DNL Audience Manager] nome del segmento per coerenza, a meno che tu non aggiungi condizioni aggiuntive a questo pubblico. |

## Passaggio 4: assegnare il [!UICONTROL Audience] a [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Dopo aver creato il [!DNL Custom Audience], assegnalo a una campagna pubblicitaria. Crea una nuova campagna o ne modifichi una esistente e il pubblico appena creato viene elencato in [!DNL Facebook] interfaccia utente. La tua campagna pubblicitaria sarà indirizzata agli utenti che hanno visto l’incendio dei pixel sul loro browser quando visitano il tuo sito, se [!DNL Audience Manager] li include nel segmento.

## Riepilogo {#summary}

Ora che hai assegnato il tuo [!DNL Audience Manager] alla [!DNL Facebook WCA] destinazione, [!DNL Audience Manager] attiverà selettivamente il [!DNL Facebook WCA] pixel per gli utenti di un dato segmento con il rispettivo ID segmento nel pixel per popolare il [!DNL Facebook Audience]. Ciò comporta un graduale aumento del [!DNL Facebook Audience] più il tag viene inviato al pubblico applicabile sul sito.

>[!NOTE]
>
> Se un utente non soddisfa le condizioni [!DNL Audience Manager] al momento non è possibile [!DNL Audience Manager] informare [!DNL Facebook] per rimuovere l&#39;utente dalla [!DNL Custom Audience].
