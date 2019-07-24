---
description: Aggiungi il modulo Gestione dell'audience ad Adobe Analytics appmeasurement per inoltrare i dati Analytics ad Audience Manager invece di fare in modo che il codice DIL (Audience Manager Data Integration Library) invii un pixel dalla pagina.
keywords: analisi dell'audience; analisi; ssf; inoltro lato server
seo-description: Aggiungi il modulo Gestione dell'audience ad Adobe Analytics appmeasurement per inoltrare i dati Analytics ad Audience Manager invece di fare in modo che il codice DIL (Audience Manager Data Integration Library) invii un pixel dalla pagina.
seo-title: Implementazione del modulo Gestione dell'audience
solution: Audience Manager
title: Implementazione del modulo Gestione dell'audience
uuid: 08846427-def 3-4 a 15-88 e 5-08882 d 8 d 57 ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Implement the Audience Management Module {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## Prerequisiti {#prereqs}

Oltre a implementare il codice descritto in questo documento, devi anche:

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## Implementazione {#implementation}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. Update your [!UICONTROL AppMeasurement] code to the version included in the downloaded zip file.
1. Copy all of the code from `AppMeasurement_Module_AudienceManagement.js` from the zip file. Paste it into the `appMeasurement.js` file just above the text, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Add the code, `s.loadModule("AudienceManagement");`, just above the `AppMeasurement_Module_AudienceManagement.js` code you just added in the previous step.
1. Update and copy the code below and add it to the `doPlugins` function in your `AppMeasurement.js` file.

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>The `audienceManagement.setup` function shares parameters with the Audience Manager `DIL.create` function, which you can configure in this code. For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code Elements Defined {#code-elements-defined}

Nella tabella seguente sono definite le variabili importanti nell'esempio di codice.

| Parametro | Descrizione |
|--- |--- |
| `partner` | Obbligatorio. Questo è un nome partner assegnato da Adobe. Talvolta viene denominato "partner partner" o "sottodominio partner". Contact your Adobe consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don't know your partner name. |
| `containerNSID` | Obbligatorio. Most customers can just set  `"containerNSID":0` . Tuttavia, se la società deve personalizzare le sincronizzazioni ID con un contenitore diverso, potete specificare tale ID contenitore. |
| `uuidCookie` | Facoltativo. Questa configurazione consente di impostare un cookie Adobe nel dominio di prime parti. This cookie contains the [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obbligatorio. The `namespace` parameter is required if you use the AudienceManagement module bundled with [!UICONTROL AppMeasurement] version 2.10 or newer. This [!UICONTROL AudienceManagement] module requires that you use [!UICONTROL Experience Cloud ID Service] 3.3 or newer. <br>Si tratta [!UICONTROL Experience Cloud Organization ID] dell'ID fornito da una società dopo la registrazione. [!UICONTROL Experience Cloud] Find out your company's Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Results: Data Forwarding to Audience Manager {#results-data-forwarding}

Your [!DNL Analytics] implementation sends data to Audience Manager after you have:

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* Implementato il servizio ID;
* Installed the [!UICONTROL Audience Management Module].

This process sends data to [!DNL Audience Manager]:

* Nelle chiamate di visualizzazione della pagina;
* Dai collegamenti tracciati;
* Da video milestone and heartbeat video.

>[!NOTE]
>
>The variables sent to Audience Manager from [!DNL Analytics] use special prefixes. È necessario comprendere e prendere in considerazione questi prefissi al momento della creazione delle caratteristiche di Audience Manager. For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md).