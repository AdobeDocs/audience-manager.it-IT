---
description: Aggiungi il modulo Gestione dell'audience ad Adobe Analytics AppMeasurement per inoltrare i dati di Analytics ad Audience Manager invece di far sì che il codice di Data Integration Library dell'Audience Manager (DIL) invii un pixel dalla pagina.
keywords: analisi del pubblico; analisi; ssf; inoltro lato server
seo-description: Aggiungi il modulo Gestione dell'audience ad Adobe Analytics AppMeasurement per inoltrare i dati di Analytics ad Audience Manager invece di far sì che il codice di Data Integration Library dell'Audience Manager (DIL) invii un pixel dalla pagina.
seo-title: Implementare il modulo Gestione dell'audience
solution: Audience Manager
title: Implementare il modulo Gestione dell'audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Integrazione di Adobe Analytics
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# Come inoltrare i dati da [!DNL Adobe Analytics] a [!DNL Audience Manager] {#implement-the-audience-management-module}

Segui i passaggi descritti in questa esercitazione per inoltrare i dati [!DNL Analytics] a [!DNL Audience Manager] anziché far sì che il codice [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) invii un pixel dalla pagina.

>[!TIP]
>
>È consigliabile utilizzare [!DNL Adobe Experience Platform Launch] per inoltrare i dati [!UICONTROL Analytics] in [!DNL Audience Manager]. Utilizzando [!UICONTROL Launch], non è necessario copiare manualmente il codice in [!DNL AppMeasurement], come mostrato in questa pagina.

## Prerequisiti {#prereqs}

Oltre ad abilitare le estensioni o implementare il codice descritto in questo documento, devi anche:

* Implementa il [servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html).
* Abilita [Server-Side Forwarding](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) per le suite di rapporti in [!UICONTROL Adobe Analytics Admin Console].

## Implementazione {#implementation}

Esistono due metodi per implementare l’inoltro di dati da [!DNL Adobe Analytics] a [!DNL Audience Manager], a seconda della soluzione di gestione dei tag utilizzata.

### Implementazione utilizzando [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] consiglia di utilizzare l&#39;estensione  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launch per strumenti  [!DNL Adobe Analytics] e  [!DNL Audience Manager] sulle proprietà. In questo caso, non è necessario copiare manualmente alcun codice. Al contrario, devi abilitare la condivisione dei dati nell’ estensione [!DNL Analytics Launch] , come illustrato di seguito. Consulta anche la documentazione [Estensione Adobe Analytics](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Se installi l&#39;estensione [!DNL Adobe Analytics], *non* installa anche l&#39;estensione [!DNL Audience Manager]. L’inoltro di dati dall’estensione [!DNL Analytics] sostituisce la funzionalità di estensione [!DNL Audience Manager] .

![Come abilitare la condivisione di dati dall’estensione Adobe Analytics all’Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Elementi di codice definiti {#code-elements-defined}

La tabella seguente definisce variabili importanti nel codice di esempio.

| Parametro | Descrizione |
|--- |--- |
| `partner` | Obbligatorio. Questo è un nome di partner assegnato da [!DNL Adobe]. A volte viene indicato come sottodominio [!UICONTROL partner ID] o partner .  Contatta il tuo consulente [!DNL Adobe] o [Assistenza clienti](https://helpx.adobe.com/it/marketing-cloud/contact-support.html) se non conosci il nome del tuo partner. |
| `containerNSID` | Obbligatorio. La maggior parte dei clienti può semplicemente impostare `"containerNSID":0` . Tuttavia, se la tua azienda deve personalizzare le sincronizzazioni ID con un contenitore diverso, puoi specificarlo qui. |
| `uuidCookie` | Facoltativo. Questa configurazione ti consente di impostare un cookie [!DNL Adobe] nel dominio di prime parti. Questo [!DNL cookie] contiene [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obbligatorio. Il parametro `namespace` è necessario se utilizzi il modulo [!DNL AudienceManagement] fornito con [!UICONTROL AppMeasurement] versione 2.10 o successiva. Questo modulo [!UICONTROL AudienceManagement] richiede l&#39;utilizzo di [!UICONTROL Adobe Experience Platform Identity Service] 3.3 o successivo. <br><br>L’  [!UICONTROL Experience Cloud Organization ID] è l’ID fornito a una società al momento dell’iscrizione a  [!UICONTROL Experience Cloud]. Scopri l’ID organizzazione della tua azienda in [Organizzazioni e collegamento di account](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Risultati: Inoltro dei dati a [!DNL Audience Manager] {#results-data-forwarding}

L&#39;implementazione [!DNL Analytics] invia i dati a [!DNL Audience Manager] dopo aver effettuato:

* Abilitato [!UICONTROL Server-Side Forwarding] (rivolgiti al tuo consulente per informazioni su questa funzione);
* Implementato il [!DNL Adobe Experience Platform Identity Service];
* Segui i passaggi di implementazione in questa esercitazione.

Questo processo invia dati a [!DNL Audience Manager]:

* Chiamate per la visualizzazione a pagina;
* Da collegamenti tracciati;
* Dalle visualizzazioni video cardine e heartbeat.

>[!NOTE]
>
>Le variabili inviate a [!DNL Audience Manager] da [!DNL Analytics] utilizzano prefissi speciali. È necessario comprendere e tenere conto di questi prefissi durante la creazione di caratteristiche [!DNL Audience Manager]. Per ulteriori informazioni su questi prefissi, consulta [Requisiti di prefisso per le variabili chiave](../../features/traits/trait-variable-prefixes.md).
