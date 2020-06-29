---
description: Aggiungi il modulo di gestione dell'audience ad Adobe  Analytics AppMeasurement per inoltrare  dati Analytics ad  Audience Manager invece di far sì che il codice  Audience Manager Data Integration Library (DIL) invii un pixel dalla pagina.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Aggiungi il modulo di gestione dell'audience ad Adobe  Analytics AppMeasurement per inoltrare  dati Analytics ad  Audience Manager invece di far sì che il codice  Audience Manager Data Integration Library (DIL) invii un pixel dalla pagina.
seo-title: Implementazione del modulo Gestione dell'audience
solution: Audience Manager
title: Implementazione del modulo Gestione dell'audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 1%

---


# Come inoltrare i dati da [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Seguite i passaggi di questa esercitazione per inoltrare [!DNL Analytics] i dati [!DNL Audience Manager] anziché far sì che il [!DNL Audience Manager] codice ( [!UICONTROL Data Integration Library][!DNL DIL]) invii un pixel dalla pagina.

>[!TIP]
>
>È consigliabile utilizzare [!DNL Adobe Experience Platform Launch] per inoltrare [!UICONTROL Analytics] i dati in [!DNL Audience Manager]. Utilizzando [!UICONTROL Launch], non è necessario copiare manualmente il codice in [!DNL AppMeasurement], come mostrato in questa pagina.

## Prerequisiti {#prereqs}

Oltre ad abilitare le estensioni o implementare il codice descritto in questo documento, è anche necessario:

* Implementa il [Servizio](https://docs.adobe.com/content/help/en/id-service/using/home.html)identità Adobe Experience Platform.
* Abilita [inoltro](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) lato server per le suite di rapporti in [!UICONTROL Adobe Analytics Admin Console].

## Implementazione {#implementation}

Esistono due metodi per implementare l&#39;inoltro dei dati da [!DNL Adobe Analytics] a [!DNL Audience Manager], a seconda della soluzione di gestione dei tag utilizzata.

### Implementazione tramite [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] consiglia di utilizzare l&#39;estensione [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) per lo strumento [!DNL Adobe Analytics] e [!DNL Audience Manager] le proprietà. In questo caso, non è necessario copiare manualmente alcun codice. È invece necessario abilitare la condivisione dei dati nell&#39; [!DNL Analytics Launch] estensione, come illustrato nell&#39;immagine seguente. Consultate anche la documentazione di [Adobe  Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Se installate l&#39; [!DNL Adobe Analytics] estensione, *non* installate anche l&#39; [!DNL Audience Manager] estensione. L’inoltro di dati dall’ [!DNL Analytics] estensione sostituisce la funzionalità di [!DNL Audience Manager] estensione.

![Come abilitare la condivisione dei dati dall’estensione Adobe  Analytics a  Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementazione tramite [!DNL Adobe Digital Tag Management (DTM)] o qualsiasi altra soluzione di gestione tag

>[!WARNING]
>
>[!DNL Adobe] ha rilasciato piani per il tramonto [!DNL DTM] entro la fine del 2020. Per ulteriori informazioni e pianificazioni, consultate [!DNL DTM] Piani per un tramonto nei forum [della community di](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)Adobe.

Per implementare [!UICONTROL Audience Management Module] utilizzando [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) o un&#39;altra soluzione di gestione tag:

1. Scarica [!UICONTROL AppMeasurement] utilizzando [Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html) (richiede la versione 1.5 o successiva).
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
>La `audienceManagement.setup` funzione condivide i parametri con la [!DNL Audience Manager] `DIL.create` funzione, che è possibile configurare in questo codice. Per ulteriori informazioni su questi parametri, consultate [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Elementi di codice definiti {#code-elements-defined}

La tabella seguente definisce variabili importanti nell’esempio di codice.

| Parametro | Descrizione |
|--- |--- |
| `partner` | Obbligatorio. Questo è un nome di partner assegnato da [!DNL Adobe]. Talvolta viene definito sottodominio [!UICONTROL partner ID] o sottodominio partner.  Contatta il tuo [!DNL Adobe] consulente o l&#39;Assistenza [](https://helpx.adobe.com/marketing-cloud/contact-support.html) clienti se non conosci il nome del tuo partner. |
| `containerNSID` | Obbligatorio. La maggior parte dei clienti può semplicemente impostare `"containerNSID":0` . Tuttavia, se la società deve personalizzare le sincronizzazioni ID con un contenitore diverso, puoi specificare tale ID contenitore in questo campo. |
| `uuidCookie` | Facoltativo. Questa configurazione consente di impostare un [!DNL Adobe] cookie nel dominio di prime parti. Contiene [!DNL cookie] l’ [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obbligatorio. Il `namespace` parametro è richiesto se utilizzate il [!DNL AudienceManagement] modulo fornito con la [!UICONTROL AppMeasurement] versione 2.10 o successiva. Questo [!UICONTROL AudienceManagement] modulo richiede l&#39;utilizzo di [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o successivo. <br><br>L’ID [!UICONTROL Experience Cloud Organization ID] è fornito da una società al momento della registrazione per l’ [!UICONTROL Experience Cloud]. Scopri l&#39;ID organizzazione della tua società in [Organizzazioni e collegamento](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)account. |

## Risultati: Inoltro dati a [!DNL Audience Manager] {#results-data-forwarding}

L&#39; [!DNL Analytics] implementazione invia i dati a [!DNL Audience Manager] dopo che hai:

* Abilitato [!UICONTROL Server-Side Forwarding] (consultare il consulente in merito a questa funzione);
* Attuato il [!DNL Adobe Experience Platform Identity Service];
* Seguito i passaggi di implementazione in questa esercitazione.

Questo processo invia dati a [!DNL Audience Manager]:

* Chiamate sulla visualizzazione di pagina;
* Da collegamenti tracciati;
* Dalle viste video milestone e heartbeat.

>[!NOTE]
>
>Le variabili inviate a [!DNL Audience Manager] da [!DNL Analytics] utilizzano prefissi speciali. È necessario comprendere e tenere conto di questi prefissi quando si creano [!DNL Audience Manager] caratteristiche. Per ulteriori informazioni su questi prefissi, consultate Requisiti di [prefisso per le variabili](../../features/traits/trait-variable-prefixes.md)chiave.
