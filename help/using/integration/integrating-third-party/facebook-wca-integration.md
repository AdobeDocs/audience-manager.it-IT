---
description: Questa pagina illustra il processo di creazione dei pixel del pubblico personalizzato del sito Web Facebook (WCA) allo scopo di inviare a Facebook segmenti di pubblico Audience Manager basati sul Web, per il targeting di annunci online con una migliore trasparenza.
seo-description: Questa pagina illustra il processo di creazione dei pixel del pubblico personalizzato del sito Web Facebook (WCA) allo scopo di inviare a Facebook segmenti di pubblico Audience Manager basati sul Web, per il targeting di annunci online con una migliore trasparenza.
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

Questa pagina illustra il processo di creazione di [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixel per l’invio di segmenti di [!DNL Audience Manager] pubblico basati sul Web a [!DNL Facebook], per il targeting di annunci online con maggiore trasparenza.

## Panoramica {#overview}

[Il sito Web di Facebook Custom Audiences (WCA)](https://www.facebook.com/business/help/449542958510885) consente di creare un elenco di persone che hanno visitato determinate pagine o che hanno effettuato particolari azioni sul sito Web. [!DNL Audience Manager] abilita l&#39;attivazione utilizzando [!DNL WCA] le [!DNL URL] destinazioni, con cui puoi configurare un&#39;integrazione personalizzata basata su pixel per inviare audience basate sul Web [!DNL Facebook] per il targeting.

![Integrazione di Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Questa funzionalità richiede la selezione dell&#39;opzione [!UICONTROL Website] audience per le piattaforme social nelle destinazioni [](/help/using/features/destinations/create-url-destination.md)URL. Le piattaforme social richiedono che le informazioni sul referente vengano smascherate quando inviate alla propria piattaforma. Questo significa che la piattaforma/il partner di destinazione sarà in grado di visualizzare le informazioni nel referente [!DNL URL].

## Prerequisiti {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmenti, pronti per essere assegnati alla nuova [!DNL Facebook] destinazione. Questo è [come creare un segmento](/help/using/features/segments/segment-builder.md) nell&#39; [!DNL Audience Manager] interfaccia utente.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versione 4.1.0 o successiva. Scarica la versione più recente **[qui](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versione 9.0 o successiva, scaricabile da **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. In alternativa, se per importare i dati in un file SSF ([Server-Side Forwarding)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)[!DNL Audience Manager]utilizzate la versione 2.12 o successiva di AppMeasurement, devi usare la versione 2.12 o successiva. Download[!DNL AppMeasurement]using the[Analytics Code Manager](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/code-manager-admin.html).

È consigliabile installare o aggiornare le librerie nei passaggi 3 e 4 tramite [Launch](https://docs.adobelaunch.com/) Adobe Experience Platform o Gestione [tag dinamica](https://docs.adobe.com/content/help/it-IT/dtm/using/dtm-home.html)Adobe.

## Passaggio 1 - Creazione di un [!UICONTROL Facebook Destination] componente [!DNL Audience Manager] {#step-1-create-facebook-destination}

Create un nuovo [!UICONTROL URL Destination] in [!DNL Audience Manager] e denominatelo [!DNL Facebook Website Custom Audiences]. Durante la creazione della destinazione, usate le impostazioni riportate di seguito. Potete anche fare riferimento alla pagina [Configura una destinazione](/help/using/features/destinations/create-url-destination.md) URL.

### Informazioni di base

* **[!UICONTROL Category]**: Personalizzato
* **[!UICONTROL Type]**: [!DNL URL]
* Selezionare la **[!UICONTROL Auto-fill Destination Mapping]** casella di controllo, quindi selezionare **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selezionate l’opzione **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Questa etichetta di esportazione impedisce l&#39;inclusione nei segmenti di dati e dati di terze parti derivati dai grafici dei dispositivi.

### Configurazione

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. Selezionando questa [!UICONTROL URL Type] opzione, [!DNL Audience Manager] non oscura le [!DNL URL] informazioni del referente quando si attiva un [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* Nel campo **[!UICONTROL Base URL]** e **[!UICONTROL Secure URL]** , inserite il [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Esempio [!DNL URL] di base: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Esempio di pixel generato dalla pagina. Questo esempio mostra un utente idoneo per tre [!DNL Audience Manager] segmenti, con gli ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parametro | Descrizione |
---------|----------|
| `id` | L’ID [!DNL Facebook] pixel, che potete trovare nell’interfaccia [!DNL Facebook Ad Manager] utente quando create i pixel del pubblico. |
| `ev` | Event.     Si tratta di un valore arbitrario, che verrà visualizzato nell&#39;interfaccia [!DNL Facebook Ad Manager] utente quando il pixel inizia a essere attivato sul sito. Per ulteriori informazioni, vedi [!UICONTROL Include] l&#39;elemento nel [Passaggio 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Un parametro aggiuntivo, che inizierà a essere popolato all&#39;interno dell&#39;interfaccia [!DNL Facebook Ad Manager] utente una volta che il pixel inizia a essere attivato sul sito. `segID` è anche arbitrario. |
| `%ALIAS%` | Una [!DNL Audience Manager] macro, che verrà sostituita dinamicamente con gli [!DNL Audience Manager] ID [!UICONTROL segment] idonei per il visitatore del sito, delimitata da virgola , |

La [!UICONTROL URL destination] configurazione dovrebbe essere simile a quella dell&#39;immagine seguente:

![Configurazione della destinazione](/help/using/integration/assets/facebook-wca.png)

Salva il [!UICONTROL destination]. Quindi, puoi procedere al passaggio **Mappature** segmenti.

## Passaggio 2 - Mappature segmento - Mappa segmento a destinazione {#step-2-segment-mappings}

Nel flusso di lavoro [Configura destinazione](/help/using/features/destinations/create-url-destination.md) URL, mappate il segmento applicabile al segmento appena creato [!UICONTROL destination]. Il valore di mappatura viene popolato automaticamente con il [!DNL Audience Manager][!UICONTROL segment ID].

Se applicabile, inserire una data di fine. In caso contrario lasciare vuoto il campo per nessuna data di fine.

## Passaggio 3 - Creare un [!UICONTROL Audience] interno [!DNL Facebook Ads Manager] {#step-3-create-audience}

Consultate [Creare un pubblico](https://www.facebook.com/business/help/666509013483225) personalizzato per il sito Web nella documentazione dell&#39; [!DNL Facebook] Aiuto. Selezionare le [!UICONTROL Create Audience] opzioni nella tabella seguente:

| Elemento | Descrizione |
---------|----------|
| Traffico sito Web | Combinazione personalizzata |
| Includi | <ul><li>Selezionare **[!UICONTROL Event]** > Seleziona **[!UICONTROL Adobe-Audience-Manager-Segment]**. Questo era il valore del `ev` parametro nel pixel di esempio nel passaggio 1. Notate che se il pixel deve ancora essere attivato, l&#39; **[!UICONTROL Event]** opzione o **[!UICONTROL Adobe-Audience-Manager-Segment]** non viene visualizzata nell&#39;interfaccia [!DNL Facebook] utente.</li><li>Aggiungete un parametro: Selezionare `segID`.</li><li><p>Selezionare l&#39;operatore **contains** .</p><p>Ciò è importante, poiché i visitatori possono essere idonei per più segmenti, il parametro pixel può contenere più [!UICONTROL segment IDs] elementi. L&#39;utilizzo dell&#39;operatore equals (`=`) potrebbe non essere idoneo dai visitatori per il pubblico, e si noterà un volume inferiore.</p></li><li>Aggiungete un valore: Immettete l’ID del [!DNL Audience Manager] segmento.</li></ul> |
| Aggiungi nuova condizione | Impostazione opzionale. |
| Nell&#39;ultimo | Impostazione opzionale. |
| Nome audience | È consigliabile utilizzare lo stesso nome di [!DNL Audience Manager] segmento per coerenza, a meno che non vengano aggiunte condizioni aggiuntive a questo pubblico. |

## Passaggio 4 - Assegna [!UICONTROL Audience] a un [!UICONTROL Campaign] pollici [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Dopo aver creato il [!DNL Custom Audience], assegnatelo a una campagna pubblicitaria. Crea una nuova campagna o ne modifichi una esistente e troverai che il pubblico appena creato è elencato nell&#39;interfaccia [!DNL Facebook] utente. La campagna pubblicitaria verrà indirizzata agli utenti che hanno visto l’attivazione dei pixel nel browser durante la visita al sito, se [!DNL Audience Manager] li include nel segmento.

## Riepilogo {#summary}

Dopo aver assegnato il [!DNL Audience Manager] segmento alla [!DNL Facebook WCA] destinazione, [!DNL Audience Manager] attiva selettivamente il [!DNL Facebook WCA] pixel per gli utenti di un dato segmento con il rispettivo ID di segmento nel pixel per la compilazione [!DNL Facebook Audience]. Ciò comporta un aumento graduale [!DNL Facebook Audience] quanto più il tag viene trasmesso al pubblico applicabile sul sito.

>[!NOTE]
>
> Se un utente non rientra nel [!DNL Audience Manager] segmento, al momento non è possibile [!DNL Audience Manager] informare [!DNL Facebook] per rimuovere l&#39;utente dal [!DNL Custom Audience].

