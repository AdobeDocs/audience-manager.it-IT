---
description: Aggiungi il modulo Gestione dell'audience ad Adobe Analytics AppMeasurement per inoltrare i dati di Analytics ad Audience Manager invece di far inviare un pixel dalla pagina al codice DIL (Audience Manager Data Integration Library).
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Aggiungi il modulo Gestione dell'audience ad Adobe Analytics AppMeasurement per inoltrare i dati di Analytics ad Audience Manager invece di far inviare un pixel dalla pagina al codice DIL (Audience Manager Data Integration Library).
seo-title: Implementazione del modulo Gestione dell'audience
solution: Audience Manager
title: Implementazione del modulo Gestione dell'audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 1b7c29c0637432a320b2a7573a3f5a7fb4cdcb81

---


# Implementazione del modulo Gestione dell'audience {#implement-the-audience-management-module}

Aggiungi l’icona [!UICONTROL Audience Management Module] a [!DNL Adobe Analytics][!UICONTROL AppMeasurement] per inoltrare [!DNL Analytics] i dati ad Audience Manager invece di far sì che il codice di Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) invii un pixel dalla pagina.

>[!NOTE]
>
>Le istruzioni riportate in questa pagina fanno riferimento alle implementazioni tramite [Adobe Digital Tag Manager (DTM)](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) o qualsiasi altra soluzione di gestione tag, *ad eccezione* di [Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html). È consigliabile utilizzare Adobe Launch. Utilizzando [!DNL Launch], non è necessario copiare manualmente il codice in [!UICONTROL AppMeasurement], come mostrato in questa pagina.

## Prerequisiti {#prereqs}

Oltre ad implementare il codice descritto in questo documento, è necessario anche:

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Abilitare [!UICONTROL Server-Side Forwarding] per le suite di rapporti nel [!UICONTROL Adobe Analytics Admin Console].

## Implementazione {#implementation}

Per implementare [!UICONTROL Audience Management Module]:

1. Scarica [!UICONTROL AppMeasurement] utilizzando [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (richiede la versione 1.5 o successiva).
1. Aggiornate il [!UICONTROL AppMeasurement] codice alla versione inclusa nel file zip scaricato.
1. Copiate tutto il codice dal file `AppMeasurement_Module_AudienceManagement.js` zip. Incollare il file nel `appMeasurement.js` file appena sopra il testo, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Aggiungi il codice, `s.loadModule("AudienceManagement");`, immediatamente sopra il `AppMeasurement_Module_AudienceManagement.js` codice appena aggiunto nel passaggio precedente.
1. Aggiornate e copiate il codice riportato di seguito e aggiungetelo alla `doPlugins` funzione presente nel `AppMeasurement.js` file.

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
>La `audienceManagement.setup` funzione condivide i parametri con la funzione Audience Manager `DIL.create` , che potete configurare in questo codice. Per ulteriori informazioni su questi parametri, consultate [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Elementi di codice definiti {#code-elements-defined}

La tabella seguente definisce variabili importanti nell’esempio di codice.

| Parametro | Descrizione |
|--- |--- |
| `partner` | Obbligatorio. Questo è un nome di partner assegnato da Adobe. Talvolta viene definito "ID partner" o "sottodominio partner".  Contatta il tuo consulente Adobe o l'Assistenza [](https://helpx.adobe.com/marketing-cloud/contact-support.html) clienti se non conosci il nome del tuo partner. |
| `containerNSID` | Obbligatorio. La maggior parte dei clienti può semplicemente impostare `"containerNSID":0` . Tuttavia, se la società deve personalizzare le sincronizzazioni ID con un contenitore diverso, puoi specificare tale ID contenitore in questo campo. |
| `uuidCookie` | Facoltativo. Questa configurazione consente di impostare un cookie Adobe nel dominio di prime parti. Questo cookie contiene l’ [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obbligatorio. Il `namespace` parametro è richiesto se utilizzate il modulo AudienceManagement fornito con la [!UICONTROL AppMeasurement] versione 2.10 o successiva. Questo [!UICONTROL AudienceManagement] modulo richiede l'utilizzo di [!UICONTROL Experience Cloud ID Service] 3.3 o successivo. <br> L’ID [!UICONTROL Experience Cloud Organization ID] è fornito da una società al momento della registrazione per l’ [!UICONTROL Experience Cloud]. Scopri l'ID organizzazione della tua società in [Organizzazioni e collegamento](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)account. |

## Risultati: Inoltro dei dati ad Audience Manager {#results-data-forwarding}

La tua [!DNL Analytics] implementazione invia i dati ad Audience Manager dopo che hai:

* Abilitato [!UICONTROL Server-Side Forwarding] (consultare il consulente in merito);
* Implementazione del servizio ID;
* Installato il [!UICONTROL Audience Management Module].

Questo processo invia dati a [!DNL Audience Manager]:

* Chiamate sulla visualizzazione di pagina;
* Da collegamenti tracciati;
* Dalle viste video milestone e heartbeat.

>[!NOTE]
>
>Le variabili inviate ad Audience Manager da [!DNL Analytics] utilizzano prefissi speciali. È necessario comprendere e tenere conto di questi prefissi quando si creano caratteristiche di Audience Manager. Per ulteriori informazioni su questi prefissi, consultate Requisiti di [prefisso per le variabili](../../features/traits/trait-variable-prefixes.md)chiave.