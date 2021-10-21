---
description: Aggiungi il modulo Gestione dell'audience ad Adobe Analytics AppMeasurement per inoltrare i dati di Analytics ad Audience Manager invece di far sì che il codice di Data Integration Library dell'Audience Manager (DIL) invii un pixel dalla pagina.
keywords: analisi del pubblico; analisi; ssf; inoltro lato server
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementare il modulo Gestione dell'audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# Come inoltrare i dati da [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Segui i passaggi descritti in questa esercitazione per proseguire [!DNL Analytics] dati a [!DNL Audience Manager] invece di avere [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) invia un pixel dalla pagina.

>[!TIP]
>
>Si consiglia di utilizzare [!DNL Adobe Experience Platform Tags] inoltrare [!UICONTROL Analytics] dati [!DNL Audience Manager]. Utilizzando [!UICONTROL Tags], non è necessario copiare manualmente il codice in [!DNL AppMeasurement], come mostrato in questa pagina.

## Prerequisiti {#prereqs}

Oltre ad abilitare le estensioni o implementare il codice descritto in questo documento, devi anche:

* Implementare [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Abilita [Inoltro lato server](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) per le suite di rapporti [!UICONTROL Adobe Analytics Admin Console].

## Implementazione {#implementation}

Esistono due metodi per implementare l&#39;inoltro dei dati da [!DNL Adobe Analytics] a [!DNL Audience Manager], a seconda della soluzione di gestione tag utilizzata.

### Implementazione tramite [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] consiglia di utilizzare [Tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) estensione allo strumento [!DNL Adobe Analytics] e [!DNL Audience Manager] sulle proprietà. In questo caso, non è necessario copiare manualmente alcun codice. Invece, devi abilitare la condivisione dei dati nella [!DNL Analytics] , come illustrato di seguito. Vedi anche [Estensione Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) documentazione.

>[!TIP]
>
>Se installi [!DNL Adobe Analytics] estensione, *non* installa inoltre [!DNL Audience Manager] estensione. Inoltro dei dati dal [!DNL Analytics] l&#39;estensione sostituisce [!DNL Audience Manager] funzionalità di estensione.

![Come abilitare la condivisione di dati dall’estensione Adobe Analytics all’Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Elementi di codice definiti {#code-elements-defined}

La tabella seguente definisce variabili importanti nel codice di esempio.

| Parametro | Descrizione |
|--- |--- |
| `partner` | Obbligatorio. Questo è un nome di partner assegnato da [!DNL Adobe]. A volte viene indicato come [!UICONTROL partner ID] o sottodominio partner.  Contatta il tuo [!DNL Adobe] consulente o [Assistenza clienti](https://helpx.adobe.com/it/marketing-cloud/contact-support.html) se non conosci il tuo nome partner. |
| `containerNSID` | Obbligatorio. La maggior parte dei clienti può semplicemente impostare  `"containerNSID":0` . Tuttavia, se la tua azienda deve personalizzare le sincronizzazioni ID con un contenitore diverso, puoi specificarlo qui. |
| `uuidCookie` | Facoltativo. Questa configurazione consente di impostare un [!DNL Adobe] nel dominio di prime parti. Questo [!DNL cookie] contiene [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obbligatorio. La `namespace` se utilizzi [!DNL AudienceManagement] modulo fornito con [!UICONTROL AppMeasurement] versione 2.10 o successiva. Questo [!UICONTROL AudienceManagement] Il modulo richiede l&#39;utilizzo di [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o successivo. <br><br>La [!UICONTROL Experience Cloud Organization ID] è l&#39;ID fornito a un&#39;azienda al momento della registrazione al [!UICONTROL Experience Cloud]. Scopri l’ID organizzazione della tua azienda in [Organizzazioni e collegamento di account](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Risultati: Inoltro dei dati a [!DNL Audience Manager] {#results-data-forwarding}

Le [!DNL Analytics] l’implementazione invia dati a [!DNL Audience Manager] dopo aver ottenuto:

* Abilitato [!UICONTROL Server-Side Forwarding] (rivolgiti al tuo consulente su questa funzione);
* Implementato il [!DNL Adobe Experience Platform Identity Service];
* Segui i passaggi di implementazione in questa esercitazione.

Questo processo invia dati a [!DNL Audience Manager]:

* Chiamate per la visualizzazione a pagina;
* Da collegamenti tracciati;
* Dalle visualizzazioni video cardine e heartbeat.

>[!NOTE]
>
>Le variabili inviate a [!DNL Audience Manager] da [!DNL Analytics] utilizza prefissi speciali. È necessario comprendere e tenere conto di questi prefissi durante la creazione di [!DNL Audience Manager] caratteristiche. Per ulteriori informazioni su questi prefissi, vedi [Requisiti di prefisso delle variabili chiave](../../features/traits/trait-variable-prefixes.md).
