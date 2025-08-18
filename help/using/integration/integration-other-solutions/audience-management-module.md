---
description: Aggiungi il modulo Gestione dell’audience ad Adobe Analytics AppMeasurement per inoltrare i dati di Analytics ad Audience Manager invece di far inviare un pixel dalla pagina dal codice di Audience Manager Data Integration Library (DIL).
keywords: audience analytics; analytics; ssf; inoltro lato server
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementazione del modulo Gestione dell’audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# Inoltrare dati da [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Segui i passaggi descritti in questo tutorial per inoltrare i dati [!DNL Analytics] a [!DNL Audience Manager] invece di inviare un pixel dalla pagina con il codice [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]).

>[!TIP]
>
>È consigliabile utilizzare [!DNL Adobe Experience Platform Tags] per inoltrare [!UICONTROL Analytics] dati a [!DNL Audience Manager]. Utilizzando [!UICONTROL Tags], non è necessario copiare manualmente il codice in [!DNL AppMeasurement], come mostrato in questa pagina.

## Prerequisiti {#prereqs}

Oltre ad abilitare le estensioni o implementare il codice descritto in questo documento, devi anche:

* Implementare il [servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Abilita [Server-Side Forwarding](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) per le suite di rapporti in [!UICONTROL Adobe Analytics Admin Console].

## Implementazione {#implementation}

Esistono due metodi per implementare l&#39;inoltro dati da [!DNL Adobe Analytics] a [!DNL Audience Manager], a seconda della soluzione di gestione tag utilizzata.

### Implementazione tramite [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] consiglia di utilizzare l&#39;estensione [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) per dotare di strumenti [!DNL Adobe Analytics] e [!DNL Audience Manager] le proprietà. In questo caso, non è necessario copiare manualmente alcun codice. È invece necessario abilitare la condivisione dei dati nell&#39;estensione [!DNL Analytics], come illustrato nell&#39;immagine seguente. Consulta anche la documentazione dell&#39;[estensione Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager).

>[!TIP]
>
>Se installi l&#39;estensione [!DNL Adobe Analytics], *non* installa anche l&#39;estensione [!DNL Audience Manager]. L&#39;inoltro dei dati dall&#39;estensione [!DNL Analytics] sostituisce la funzionalità dell&#39;estensione [!DNL Audience Manager].

![Come abilitare la condivisione dei dati dall&#39;estensione Adobe Analytics ad Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Elementi di codice definiti {#code-elements-defined}

La tabella seguente definisce variabili importanti nell’esempio di codice.

| Parametro | Descrizione |
|--- |--- |
| `partner` | Obbligatorio. Questo è un nome di partner assegnato da [!DNL Adobe]. A volte è indicato come [!UICONTROL partner ID] o sottodominio partner.  Contatta il tuo consulente [!DNL Adobe] o l&#39;[Assistenza clienti](https://helpx.adobe.com/it/marketing-cloud/contact-support.html) se non conosci il nome del tuo partner. |
| `containerNSID` | Obbligatorio. La maggior parte dei clienti può semplicemente impostare `"containerNSID":0`. Tuttavia, se la tua azienda deve personalizzare le sincronizzazioni ID con un contenitore diverso, puoi specificare tale ID contenitore qui. |
| `uuidCookie` | Facoltativo. Questa configurazione consente di impostare un cookie [!DNL Adobe] nel dominio di prime parti. [!DNL cookie] contiene [UUID](../../reference/ids-in-aam.md). |
| `visitorService` - `namespace` | Obbligatorio. Il parametro `namespace` è necessario se si utilizza il modulo [!DNL AudienceManagement] in bundle con [!UICONTROL AppMeasurement] versione 2.10 o successiva. Questo modulo [!UICONTROL AudienceManagement] richiede l&#39;utilizzo di [!UICONTROL Adobe Experience Platform Identity Service] versione 3.3 o successiva. <br><br>[!UICONTROL Experience Cloud Organization ID] è l&#39;ID fornito a un&#39;azienda al momento della registrazione per [!UICONTROL Experience Cloud]. Scopri l&#39;ID organizzazione della tua azienda in [Organizzazioni e collegamento account](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Risultati: Inoltro dati a [!DNL Audience Manager] {#results-data-forwarding}

L&#39;implementazione di [!DNL Analytics] invia i dati a [!DNL Audience Manager] dopo che hai:

* Abilitazione di [!UICONTROL Server-Side Forwarding] (rivolgiti al tuo consulente per informazioni su questa funzione);
* Ha implementato [!DNL Adobe Experience Platform Identity Service];
* Segui i passaggi di implementazione descritti in questa esercitazione.

Questo processo invia dati a [!DNL Audience Manager]:

* Chiamate alla visualizzazione pagina;
* Da collegamenti tracciati;
* Dalle visualizzazioni video milestone e heartbeat.

>[!NOTE]
>
>Le variabili inviate a [!DNL Audience Manager] da [!DNL Analytics] utilizzano prefissi speciali. Devi comprendere e tenere conto di questi prefissi quando crei [!DNL Audience Manager] caratteristiche. Per ulteriori informazioni su questi prefissi, vedere [Requisiti dei prefissi per le variabili chiave](../../features/traits/trait-variable-prefixes.md).
