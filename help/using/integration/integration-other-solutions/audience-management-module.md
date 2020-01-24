---
description: Aggiungi il modulo Gestione dell'audience ad Adobe Analytics AppMeasurement per inoltrare i dati di Analytics ad Audience Manager invece di far inviare un pixel dalla pagina al codice DIL (Audience Manager Data Integration Library).
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Aggiungi il modulo Gestione dell'audience ad Adobe Analytics AppMeasurement per inoltrare i dati di Analytics ad Audience Manager invece di far inviare un pixel dalla pagina al codice DIL (Audience Manager Data Integration Library).
seo-title: Implementazione del modulo Gestione dell'audience
solution: Audience Manager
title: Implementazione del modulo Gestione dell'audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: dddc67e80e2b8c2e5e3ec76912a030e52d2206f5

---


# Come inoltrare i dati da Adobe Analytics ad Audience Manager {#implement-the-audience-management-module}

Seguite i passaggi di questa esercitazione per inoltrare [!DNL Analytics] i dati ad Audience Manager invece di far sì che il codice di Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) invii un pixel dalla pagina.

>[!TIP]
>
>È consigliabile utilizzare [!UICONTROL Adobe Launch] per inoltrare [!UICONTROL Analytics] i dati ad Audience Manager. Utilizzando [!UICONTROL Launch], non è necessario copiare manualmente il codice in [!UICONTROL AppMeasurement], come mostrato in questa pagina.

>[!NOTE]
>
>Le istruzioni riportate in questa pagina fanno riferimento alle implementazioni tramite [Adobe Digital Tag Manager (DTM)](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) o qualsiasi altra soluzione di gestione tag, *ad eccezione* di [Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html). È consigliabile utilizzare Adobe Launch. Utilizzando [!DNL Launch], non è necessario copiare manualmente il codice in [!UICONTROL AppMeasurement], come mostrato in questa pagina.

## Prerequisiti {#prereqs}

Oltre ad abilitare le estensioni o implementare il codice descritto in questo documento, è anche necessario:

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Abilita [inoltro](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) lato server per le suite di rapporti in [!UICONTROL Adobe Analytics Admin Console].

## Implementazione {#implementation}

Esistono due metodi per implementare l’inoltro dei dati da Adobe Analytics ad Audience Manager, a seconda della soluzione di gestione dei tag utilizzata.

### Implementazione tramite Adobe Launch

Adobe consiglia di utilizzare l’estensione [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) per utilizzare Adobe Analytics e Audience Manager sulle proprietà. In questo caso, non è necessario copiare manualmente alcun codice. Al contrario, devi abilitare la condivisione dei dati nell&#39;estensione di Analytics Launch, come illustrato nell&#39;immagine seguente. Consultate anche la documentazione di [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Se installate l&#39;estensione Adobe Analytics, *non* installate anche l&#39;estensione Audience Manager. L&#39;inoltro di dati dall&#39;estensione Analytics sostituisce la funzionalità di estensione Audience Manager.

![Come abilitare la condivisione dei dati dall’estensione Adobe Analytics ad Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementazione tramite Adobe Digital Tag Management (DTM) o qualsiasi altra soluzione di gestione tag


>[!WARNING]
>
>Adobe ha rilasciato dei piani per la scadenza di DTM entro la fine del 2020. Per ulteriori informazioni e pianificazioni, consulta Piani DTM per un tramonto nei forum [della community di](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)Adobe.

Per implementare [!UICONTROL Audience Management Module] utilizzando [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) o un&#39;altra soluzione di gestione tag:

1. Scarica [!UICONTROL AppMeasurement] utilizzando [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (richiede la versione 1.5 o successiva).
1. Aggiornate il [!UICONTROL AppMeasurement] codice alla versione inclusa nel file zip scaricato.
1. Copiate tutto il codice dal file `AppMeasurement_Module_AudienceManagement.js` zip. Incollare il file nel `appMeasurement.js` file appena sopra il testo, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Aggiungi il codice, `s.loadModule("AudienceManagement");`, immediatamente sopra il `AppMeasurement_Module_AudienceManagement.js` codice appena aggiunto nel passaggio precedente.
1. Aggiornate e copiate il codice riportato di seguito e aggiungetelo alla `doPlugins` funzione presente nel `AppMeasurement.js` file.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
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
| `partner` | Obbligatorio. Questo è un nome di partner assegnato da Adobe. Talvolta viene definito &quot;ID partner&quot; o &quot;sottodominio partner&quot;.  Contatta il tuo consulente Adobe o l&#39;Assistenza [](https://helpx.adobe.com/marketing-cloud/contact-support.html) clienti se non conosci il nome del tuo partner. |
| `containerNSID` | Obbligatorio. La maggior parte dei clienti può semplicemente impostare `"containerNSID":0` . Tuttavia, se la società deve personalizzare le sincronizzazioni ID con un contenitore diverso, puoi specificare tale ID contenitore in questo campo. |
| `uuidCookie` | Facoltativo. Questa configurazione consente di impostare un cookie Adobe nel dominio di prime parti. Questo cookie contiene l’ [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obbligatorio. Il `namespace` parametro è richiesto se utilizzate il modulo AudienceManagement fornito con la [!UICONTROL AppMeasurement] versione 2.10 o successiva. Questo [!UICONTROL AudienceManagement] modulo richiede l&#39;utilizzo di [!UICONTROL Experience Cloud ID Service] 3.3 o successivo. <br> L’ID [!UICONTROL Experience Cloud Organization ID] è fornito da una società al momento della registrazione per l’ [!UICONTROL Experience Cloud]. Scopri l&#39;ID organizzazione della tua società in [Organizzazioni e collegamento](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)account. |

## Risultati: Inoltro dei dati ad Audience Manager {#results-data-forwarding}

La tua [!DNL Analytics] implementazione invia i dati ad Audience Manager dopo che hai:

* Abilitato [!UICONTROL Server-Side Forwarding] (consultare il consulente in merito);
* implementato il servizio Experience Cloud ID;
* Seguito i passaggi di implementazione in questa esercitazione.

Questo processo invia dati a [!DNL Audience Manager]:

* Chiamate sulla visualizzazione di pagina;
* Da collegamenti tracciati;
* Dalle viste video milestone e heartbeat.

>[!NOTE]
>
>Le variabili inviate ad Audience Manager da [!DNL Analytics] utilizzano prefissi speciali. È necessario comprendere e tenere conto di questi prefissi quando si creano caratteristiche di Audience Manager. Per ulteriori informazioni su questi prefissi, consultate Requisiti di [prefisso per le variabili](../../features/traits/trait-variable-prefixes.md)chiave.