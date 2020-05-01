---
description: Panoramica di DIL e del suo funzionamento.
seo-description: Panoramica di DIL e del suo funzionamento.
seo-title: Informazioni sulla libreria di integrazione dei dati (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Informazioni sulla libreria di integrazione dei dati (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Informazioni sulla libreria di integrazione dei dati (DIL){#understanding-the-data-integration-library-dil}

Panoramica, guida introduttiva e metodi di codice disponibili nella libreria di codici DIL di Audience Manager.

>[!IMPORTANT]
>
>A partire dalla versione 8.0 (rilasciata nell’agosto 2018), [!UICONTROL DIL] ha una forte dipendenza da [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), versione 3.3 o successiva. Il servizio ID utilizza per attivare le sincronizzazioni ID e le destinazioni URL. Si verifica un errore se il servizio ID risulta mancante, obsoleto o non configurato.
>
>È consigliabile utilizzare Adobe Experience Platform Launch per implementare e gestire le librerie DIL e Adobe Experience Platform Identity Service.

Tuttavia, puoi anche scaricare le ultime versioni di Experience Cloud e DIL dalla nostra pagina GitHub. Consultate i collegamenti per il download di seguito:

* Download del servizio identità [Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Scarica [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalità di DIL {#purpose-dil}

[!UICONTROL DIL] è una libreria API. Si può pensare che sia un corpo di codice di aiuto per [!DNL Adobe Audience Manager]. Non è necessario utilizzarlo [!DNL Audience Manager], ma i metodi e le funzioni [!UICONTROL DIL] consentono di non dover sviluppare il codice a cui inviare i dati [!DNL Audience Manager]. Inoltre, [!UICONTROL DIL] è diversa dall&#39;API fornita da [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html). Tale servizio è progettato per gestire l&#39;identità del visitatore tra diverse [!DNL Experience Cloud] soluzioni. Per contro, [!UICONTROL DIL] è progettato per:

* Effettuare chiamate di eventi e inviare dati al server [di raccolta](../reference/system-components/components-data-collection.md)dati.
* Invia dati alle [destinazioni](../features/destinations/destinations.md).

## Ottenere e implementare il codice DIL {#get-implement-dil-code}

[!UICONTROL DIL] il codice è disponibile per il download **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. A partire dalla versione 8.0 (rilasciata nell’agosto 2018),[!UICONTROL DIL]Adobe Experience Platform Identity Service[è dipendente dal servizio](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform, versione 3.3 o successiva. Il servizio ID utilizza per attivare le sincronizzazioni ID e le destinazioni URL. Si verifica un errore se il servizio ID risulta mancante, obsoleto o non configurato.

Invece di utilizzare [!UICONTROL DIL] e configurare [!DNL Audience Manager] manualmente, consigliamo di utilizzare [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) . [!DNL Adobe Experience Platform Launch] è lo strumento di implementazione consigliato perché semplifica la distribuzione del codice, la posizione e la gestione delle versioni. Ulteriori informazioni sull&#39;estensione [](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Audience Manager in Adobe Experience Platform Launch.

Adobe Experience Platform Launch è il successore di [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Chiamata di esempio {#sample-code}

[!UICONTROL DIL] invia i dati a [!DNL Audience Manager] una chiamata dell&#39;evento. Una chiamata evento è una richiesta HTTP XML proveniente dalla pagina. Utilizza un `POST` metodo per inviare i dati nel corpo della richiesta.

| Elemento Chiamata Evento | Descrizione |
|--- |--- |
| URL | Le chiamate agli eventi DIL utilizzano la sintassi seguente: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Come mostrato nell&#39;esempio seguente, DIL trasmette i dati come coppie chiave-valore. I caratteri di prefisso speciali identificano le coppie chiave-valore come variabili Audience Manager o partner.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Vedi anche:
* [Requisiti del prefisso per le variabili chiave](../features/traits/trait-variable-prefixes.md)
* [Attributi supportati per le chiamate API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Collegamenti correlati

* [Casi di utilizzo DIL ed esempi di codice](/help/using/dil/dil-use-cases.md)
* [Metodi DIL a livello di classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Metodi DIL a livello di istanza](/help/using/dil/dil-instance-methods.md)
* [Moduli DIL](/help/using/dil/dil-modules.md)
* [Strumenti DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)