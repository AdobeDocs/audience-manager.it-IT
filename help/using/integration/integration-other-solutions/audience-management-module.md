---
description: Aggiungi il modulo Gestione dell'audience a  Adobe Analytics AppMeasurement per inoltrare i dati di Analytics a  Audience Manager invece di far sì che il codice  Data Integration Library Audience Manager (DIL) invii un pixel dalla pagina.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Aggiungi il modulo Gestione dell'audience a  Adobe Analytics AppMeasurement per inoltrare i dati di Analytics a  Audience Manager invece di far sì che il codice  Data Integration Library Audience Manager (DIL) invii un pixel dalla pagina.
seo-title: Implementazione del modulo Gestione dell'audience
solution: Audience Manager
title: Implementazione del modulo Gestione dell'audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 5%

---


# Come inoltrare i dati da [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Seguite i passaggi in questa esercitazione per inoltrare i dati [!DNL Analytics] a [!DNL Audience Manager] invece di fare in modo che il codice [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) invii un pixel dalla pagina.

>[!TIP]
>
>È consigliabile utilizzare [!DNL Adobe Experience Platform Launch] per inoltrare i dati [!UICONTROL Analytics] in [!DNL Audience Manager]. Utilizzando [!UICONTROL Launch], non è necessario copiare manualmente il codice in [!DNL AppMeasurement], come mostrato in questa pagina.

## Prerequisiti {#prereqs}

Oltre ad abilitare le estensioni o implementare il codice descritto in questo documento, è anche necessario:

* Implementa il [Servizio identità Adobe Experience Platform](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html).
* Abilitare [inoltro lato server](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) per le suite di rapporti in [!UICONTROL Adobe Analytics Admin Console].

## Implementazione {#implementation}

Esistono due metodi per implementare l&#39;inoltro dei dati da [!DNL Adobe Analytics] a [!DNL Audience Manager], a seconda della soluzione di gestione dei tag utilizzata.

### Implementazione tramite [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] consiglia di utilizzare l&#39;estensione  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) di avvio per lo strumento  [!DNL Adobe Analytics] e  [!DNL Audience Manager] le proprietà. In questo caso, non è necessario copiare manualmente alcun codice. È invece necessario abilitare la condivisione dei dati nell&#39;estensione [!DNL Analytics Launch], come illustrato nell&#39;immagine seguente. Vedere anche la documentazione di [ Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager).

>[!TIP]
>
>Se installate l&#39;estensione [!DNL Adobe Analytics], *non* installare anche l&#39;estensione [!DNL Audience Manager]. L&#39;inoltro di dati dall&#39;estensione [!DNL Analytics] sostituisce la funzionalità di estensione [!DNL Audience Manager].

![Come abilitare la condivisione dei dati dall&#39;estensione Adobe Analytics  al Audience Manager ](/help/using/integration/assets/analytics-to-aam.png)

### Implementazione tramite [!DNL Adobe Digital Tag Management (DTM)] o qualsiasi altra soluzione di gestione tag

>[!WARNING]
>
>[!DNL Adobe] ha rilasciato piani per il tramonto  [!DNL DTM] entro la fine del 2020. Per ulteriori informazioni e pianificazioni, vedi [!DNL DTM] Piani per un tramonto nei [ forum della community di Adobi](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

Per implementare [!UICONTROL Audience Management Module] utilizzando [ Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) o un&#39;altra soluzione di gestione tag:

1. Scarica [!UICONTROL AppMeasurement] utilizzando [Analytics Code Manager](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/code-manager-admin.html) (richiede la versione 1.5 o successiva).
1. Aggiornate il codice [!UICONTROL AppMeasurement] alla versione inclusa nel file zip scaricato.
1. Copiate tutto il codice da `AppMeasurement_Module_AudienceManagement.js` dal file zip. Incollatela nel file `appMeasurement.js` appena sopra il testo, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Aggiungete il codice `s.loadModule("AudienceManagement");` appena sopra il codice `AppMeasurement_Module_AudienceManagement.js` appena aggiunto nel passaggio precedente.
1. Aggiornate e copiate il codice seguente e aggiungetelo alla funzione `doPlugins` nel file `AppMeasurement.js`.

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
>La funzione `audienceManagement.setup` condivide i parametri con la funzione [!DNL Audience Manager] `DIL.create`, che è possibile configurare in questo codice. Per ulteriori informazioni su questi parametri, vedere [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Elementi di codice definiti {#code-elements-defined}

La tabella seguente definisce variabili importanti nell’esempio di codice.

| Parametro | Descrizione |
|--- |--- |
| `partner` | Obbligatorio. Si tratta di un nome di partner assegnato da [!DNL Adobe]. Talvolta viene definito [!UICONTROL partner ID] o sottodominio partner.  Contatta il tuo [!DNL Adobe] consulente o [Assistenza clienti](https://helpx.adobe.com/it/marketing-cloud/contact-support.html) se non conosci il nome del tuo partner. |
| `containerNSID` | Obbligatorio. La maggior parte dei clienti può semplicemente impostare `"containerNSID":0` . Tuttavia, se la società deve personalizzare le sincronizzazioni ID con un contenitore diverso, puoi specificare tale ID contenitore in questo campo. |
| `uuidCookie` | Facoltativo. Questa configurazione consente di impostare un cookie [!DNL Adobe] nel dominio di prime parti. Questo [!DNL cookie] contiene il [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obbligatorio. Il parametro `namespace` è richiesto se si utilizza il modulo [!DNL AudienceManagement] fornito con [!UICONTROL AppMeasurement] versione 2.10 o successiva. Questo modulo [!UICONTROL AudienceManagement] richiede l&#39;utilizzo di [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o successivo. <br><br>L’ID  [!UICONTROL Experience Cloud Organization ID] è fornito da una società al momento della registrazione per l’ [!UICONTROL Experience Cloud]. Scopri l&#39;ID organizzazione della tua società in [Organizzazioni e collegamento account](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Risultati: Inoltro dei dati a [!DNL Audience Manager] {#results-data-forwarding}

L&#39;implementazione [!DNL Analytics] invia i dati a [!DNL Audience Manager] dopo che:

* Abilitato [!UICONTROL Server-Side Forwarding] (consultare il consulente in merito a questa funzione);
* Implementato il [!DNL Adobe Experience Platform Identity Service];
* Seguito i passaggi di implementazione in questa esercitazione.

Questo processo invia dati a [!DNL Audience Manager]:

* Chiamate sulla visualizzazione di pagina;
* Da collegamenti tracciati;
* Dalle viste video milestone e heartbeat.

>[!NOTE]
>
>Le variabili inviate a [!DNL Audience Manager] da [!DNL Analytics] utilizzano prefissi speciali. È necessario comprendere e tenere conto di questi prefissi quando si creano caratteristiche [!DNL Audience Manager]. Per ulteriori informazioni su questi prefissi, vedere [Prefissi obbligatori per variabili chiave](../../features/traits/trait-variable-prefixes.md).
