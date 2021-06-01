---
description: Questa pagina illustra il processo di creazione dei pixel di Facebook Website Custom Audiences (WCA) allo scopo di inviare segmenti di pubblico di Audience Manager basati su web a Facebook, per il targeting di annunci online con una maggiore trasparenza.
seo-description: Questa pagina illustra il processo di creazione dei pixel di Facebook Website Custom Audiences (WCA) allo scopo di inviare segmenti di pubblico di Audience Manager basati su web a Facebook, per il targeting di annunci online con una maggiore trasparenza.
seo-title: Integrazione di Facebook WCA
solution: Audience Manager
title: Integrazione di Facebook WCA
feature: Integrazione di terze parti
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 5%

---

# [!DNL Facebook WCA] Integrazione {#facebook-wca-integration}

Questa pagina illustra il processo di creazione di [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixel allo scopo di inviare segmenti di pubblico basati sul Web [!DNL Audience Manager] a [!DNL Facebook], per il targeting di annunci online con una maggiore trasparenza.

## Panoramica {#overview}

[Il sito Web di facebook con tipi di pubblico personalizzati (WCA, Custom Audiences) ](https://www.facebook.com/business/help/449542958510885)  consente di creare un elenco di persone che hanno visitato determinate pagine o effettuato particolari azioni sul sito web. [!DNL Audience Manager] abilita l’attivazione in  [!DNL WCA] utilizzando  [!DNL URL] le destinazioni, con le quali puoi configurare un’integrazione personalizzata basata su pixel per l’invio di tipi di pubblico basati sul Web  [!DNL Facebook] per il targeting.

![Integrazione di Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Questa funzionalità richiede la selezione dell&#39;opzione [!UICONTROL Website] pubblico per piattaforme social in [Destinazioni URL](/help/using/features/destinations/create-url-destination.md). Le piattaforme social richiedono che le informazioni sui referenti vengano smascherate quando inviate alla loro piattaforma. Tieni presente che ciò significa che la piattaforma/partner di destinazione sarà in grado di visualizzare le informazioni nel referente [!DNL URL].

## Prerequisiti {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmenti, pronti per l’assegnazione alla nuova  [!DNL Facebook] destinazione. Ecco [come creare un segmento](/help/using/features/segments/segment-builder.md) nell’ interfaccia utente [!DNL Audience Manager] .
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versione 4.1.0 o successiva. Scarica la versione più recente **[qui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versione 9.0 o successiva, scaricabile da  **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. In alternativa, se utilizzi [Server-Side Forwarding (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) per importare dati in [!DNL Audience Manager], devi utilizzare AppMeasurement versione 2.12 o successiva. Scarica [!DNL AppMeasurement] utilizzando [Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

È consigliabile installare o aggiornare le librerie nei passaggi 3 e 4 utilizzando [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html).

## Passaggio 1: creare un [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Crea un nuovo [!UICONTROL URL Destination] in [!DNL Audience Manager] e denominalo [!DNL Facebook Website Custom Audiences]. Utilizza le impostazioni seguenti durante la creazione della destinazione. Puoi anche fare riferimento alla pagina [Configura una destinazione URL](/help/using/features/destinations/create-url-destination.md) .

### Informazioni di base

* **[!UICONTROL Category]**: Personalizzato
* **[!UICONTROL Type]**: [!DNL URL]
* Selezionare la casella di controllo **[!UICONTROL Auto-fill Destination Mapping]**, quindi selezionare **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selezionare l&#39;opzione **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Questa etichetta di esportazione impedisce l’inclusione nei segmenti di dati e dati di terze parti derivati da grafici dei dispositivi.

### Configurazione

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Selezionando questa opzione [!UICONTROL URL Type], [!DNL Audience Manager] non nasconde le informazioni del referente [!DNL URL] quando si attiva un pixel [!DNL Facebook WCA].
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Nel campo **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]**, immetti il pixel [!DNL Facebook WCA].
* **[!UICONTROL Delimiter]**:  `,`

Esempio di base [!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Esempio di pixel generati dalla pagina. Questo esempio mostra un utente idoneo per tre segmenti [!DNL Audience Manager] con ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parametro | Descrizione |
---------|----------|
| `id` | Il tuo [!DNL Facebook] pixel ID, che puoi trovare nell’ interfaccia utente [!DNL Facebook Ad Manager] durante la creazione di pixel per il pubblico. |
| `ev` | Event.     Si tratta di un valore arbitrario che verrà visualizzato nell&#39;interfaccia utente [!DNL Facebook Ad Manager] una volta che il pixel inizia ad attivarsi sul sito. Per ulteriori informazioni, consulta la voce [!UICONTROL Include] in [Passaggio 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience) . |
| `cd[segID]` | Un parametro aggiuntivo, che inizierà a popolarsi all&#39;interno dell&#39;interfaccia utente [!DNL Facebook Ad Manager] una volta che il pixel inizia ad attivarsi sul sito. `segID` è anche arbitrario. |
| `%ALIAS%` | Una macro [!DNL Audience Manager] che verrà sostituita dinamicamente con gli ID [!DNL Audience Manager] [!UICONTROL segment] idonei per il visitatore del sito, delimitati da virgole , |

La configurazione [!UICONTROL URL destination] deve essere simile a quella dell&#39;immagine seguente:

![Configurazione della destinazione](/help/using/integration/assets/facebook-wca.png)

Salva il [!UICONTROL destination]. Quindi, puoi procedere al passaggio **Mapping segmento** .

## Passaggio 2 - Mappature dei segmenti - Mappare il segmento sulla destinazione {#step-2-segment-mappings}

Nel flusso di lavoro [Configura destinazione URL](/help/using/features/destinations/create-url-destination.md) , mappa il segmento applicabile al tuo [!UICONTROL destination] appena creato. Il valore di mappatura viene compilato automaticamente con [!DNL Audience Manager] [!UICONTROL segment ID].

Inserisci una data di fine, se applicabile, altrimenti lascia vuoto per nessuna data di fine.

## Passaggio 3: creare un [!UICONTROL Audience] all&#39;interno di [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consulta [Creare un pubblico personalizzato per un sito web](https://www.facebook.com/business/help/666509013483225) nella documentazione dell&#39;Aiuto [!DNL Facebook]. Seleziona le opzioni [!UICONTROL Create Audience] nella tabella seguente:

| Elemento | Descrizione |
---------|----------|
| Traffico sito web | Combinazione personalizzata |
| Includi | <ul><li>Seleziona **[!UICONTROL Event]** > Seleziona **[!UICONTROL Adobe-Audience-Manager-Segment]**. Questo era il valore del parametro `ev` nel pixel di esempio nel passaggio 1. Nota che se il pixel non è ancora attivo, l&#39;opzione **[!UICONTROL Event]** o **[!UICONTROL Adobe-Audience-Manager-Segment]** potrebbe non essere visualizzata nell&#39;interfaccia utente [!DNL Facebook].</li><li>Aggiungi un parametro: Selezionare `segID`.</li><li><p>Selezionare l&#39;operatore **contiene**.</p><p>Questo è importante, dato che i visitatori possono qualificarsi per più segmenti, ci possono essere più [!UICONTROL segment IDs] nel parametro pixel. L’utilizzo dell’operatore è uguale a (`=`) potrebbe non essere adatto ai visitatori per il pubblico e si noterà un volume inferiore.</p></li><li>Aggiungi un valore: Immetti l’ID del segmento [!DNL Audience Manager] .</li></ul> |
| Aggiungi nuova condizione | Impostazione opzionale. |
| Nell&#39;ultimo | Impostazione opzionale. |
| Nome del pubblico | È consigliabile utilizzare lo stesso nome di segmento [!DNL Audience Manager] per coerenza, a meno che non si stiano aggiungendo condizioni aggiuntive a questo pubblico. |

## Passaggio 4: assegna il [!UICONTROL Audience] a un [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Dopo aver creato il [!DNL Custom Audience], assegnalo a una campagna pubblicitaria. Crea una nuova campagna o modificane una esistente e il pubblico appena creato viene elencato nell’ interfaccia utente [!DNL Facebook] . La campagna pubblicitaria verrà indirizzata agli utenti che hanno visto l’attivazione dei pixel sul loro browser quando visitano il tuo sito, se [!DNL Audience Manager] li include nel segmento.

## Riepilogo {#summary}

Dopo aver assegnato il segmento [!DNL Audience Manager] alla destinazione [!DNL Facebook WCA], [!DNL Audience Manager] attiverà selettivamente il pixel [!DNL Facebook WCA] per gli utenti di un dato segmento con il rispettivo ID segmento nel pixel per compilare il [!DNL Facebook Audience]. Questo comporta un aumento graduale del [!DNL Facebook Audience] quanto più il tag viene inviato al pubblico applicabile sul sito.

>[!NOTE]
>
> Se un utente non rientra nel segmento [!DNL Audience Manager], attualmente non esiste modo per [!DNL Audience Manager] di informare [!DNL Facebook] di rimuovere l&#39;utente dal [!DNL Custom Audience].

