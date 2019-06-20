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


# Implementazione del modulo Gestione dell&#39;audience {#implement-the-audience-management-module}

Aggiungi i [!UICONTROL Audience Management Module] dati a [!DNL Adobe Analytics][!UICONTROL AppMeasurement][!DNL Analytics] Audience Manager invece di fare in modo che il codice Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) invii un pixel dalla pagina.

## Prerequisiti {#prereqs}

Oltre a implementare il codice descritto in questo documento, devi anche:

* Implementazione del [servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Abilita [!UICONTROL Server-Side Forwarding] per suite [!UICONTROL Adobe Analytics Admin Console]di rapporti.

## Implementazione {#implementation}

Per implementare [!UICONTROL Audience Management Module]:

1. Scarica [!UICONTROL AppMeasurement] utilizzando [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (richiede la versione 1.5 o successiva).
1. Aggiornate [!UICONTROL AppMeasurement] il codice alla versione inclusa nel file ZIP scaricato.
1. Copiate tutto il codice dal `AppMeasurement_Module_AudienceManagement.js` file zip. Incolla nel `appMeasurement.js` file appena sopra il testo, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Aggiungi il codice, `s.loadModule("AudienceManagement");`appena sopra il `AppMeasurement_Module_AudienceManagement.js` codice appena aggiunto nel passaggio precedente.
1. Aggiornate e copiate il codice seguente e aggiungetelo alla `doPlugins` funzione del `AppMeasurement.js` file.

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
>La `audienceManagement.setup` funzione condivide i parametri con `DIL.create` la funzione Audience Manager, che potete configurare in questo codice. For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Elementi di codice definiti {#code-elements-defined}

Nella tabella seguente sono definite le variabili importanti nell&#39;esempio di codice.

| Parametro | Descrizione |
|--- |--- |
| `partner` | Obbligatorio. Questo è un nome partner assegnato da Adobe. Talvolta viene denominato &quot;partner partner&quot; o &quot;sottodominio partner&quot;. Contatta il tuo consulente Adobe o [l&#39;Assistenza clienti](https://helpx.adobe.com/marketing-cloud/contact-support.html) se non conosci il nome del tuo partner. |
| `containerNSID` | Obbligatorio. La maggior parte dei clienti può semplicemente impostare `"containerNSID":0` . Tuttavia, se la società deve personalizzare le sincronizzazioni ID con un contenitore diverso, potete specificare tale ID contenitore. |
| `uuidCookie` | Facoltativo. Questa configurazione consente di impostare un cookie Adobe nel dominio di prime parti. Questo cookie contiene l&#39; [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obbligatorio. Il `namespace` parametro è richiesto se utilizzate il modulo audiencemanagement fornito con [!UICONTROL AppMeasurement] la versione 2.10 o successiva. Questo [!UICONTROL AudienceManagement] modulo richiede che sia utilizzato il valore [!UICONTROL Experience Cloud ID Service] 3.3 o successivo. <br> The [!UICONTROL Experience Cloud Organization ID] is the ID that a company is provided with upon signing up for the [!UICONTROL Experience Cloud]. Individua l&#39;ID organizzazione della tua società in [Organizzazioni e collegamento account](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Risultati: Inoltro dati ad Audience Manager {#results-data-forwarding}

L [!DNL Analytics] &#39;implementazione invia dati ad Audience Manager dopo che hai:

* Attivato [!UICONTROL Server-Side Forwarding] (parla con il tuo consulente su questa funzione);
* Implementato il servizio ID;
* Installed the [!UICONTROL Audience Management Module].

Questo processo invia i dati a [!DNL Audience Manager]:

* Nelle chiamate di visualizzazione della pagina;
* Dai collegamenti tracciati;
* Da video milestone and heartbeat video.

>[!NOTE]
>
>Le variabili inviate ad Audience Manager utilizzano [!DNL Analytics] i prefissi speciali. È necessario comprendere e prendere in considerazione questi prefissi al momento della creazione delle caratteristiche di Audience Manager. Per ulteriori informazioni su questi prefissi, consultate [Prefisso requisiti per variabili chiave](../../features/traits/trait-variable-prefixes.md).