---
description: Panoramica di DIL e del suo funzionamento.
seo-description: Panoramica di DIL e del suo funzionamento.
seo-title: Informazioni sulla Data Integration Library (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Informazioni sulla Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 18%

---


# Informazioni su [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Panoramica, guida introduttiva e metodi di codice disponibili nella libreria dei [!DNL Audience Manager DIL] codici.

>[!IMPORTANT]
>
>A partire dalla versione 8.0 (rilasciata nell’agosto 2018), [!UICONTROL DIL] ha una dipendenza rigida dal servizio [identità](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html)Adobe Experience Platform, versione 3.3 o successiva. Per attivare le sincronizzazioni ID e [!DNL ID Service] le destinazioni URL, utilizza la console. Si verifica un errore se il file [!DNL ID Service] risulta mancante, obsoleto o non configurato.
>
>Consigliamo di utilizzare [!DNL Adobe Experience Platform Launch] per implementare e gestire le vostre [!DNL DIL] e [!DNL Adobe Experience Platform Identity Service] librerie.

Tuttavia, puoi anche scaricare gli ultimi  Experience Cloud e [!DNL DIL] le versioni dalla nostra pagina GitHub. Consultate i collegamenti per il download di seguito:

* Download the [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Scarica [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalità di DIL {#purpose-dil}

[!UICONTROL DIL] è una libreria API. Si può pensare che sia un corpo di codice di aiuto per [!DNL Adobe Audience Manager]. Non è necessario utilizzarlo [!DNL Audience Manager], ma i metodi e le funzioni [!UICONTROL DIL] consentono di non dover sviluppare il codice a cui inviare i dati [!DNL Audience Manager]. Inoltre, [!UICONTROL DIL] è diversa dall&#39;API fornita dal servizio [identità Adobe Experience Platform](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html). Tale servizio è progettato per gestire l&#39;identità del visitatore tra diverse [!DNL Experience Cloud] soluzioni. Per contro, [!UICONTROL DIL] è progettato per:

* Effettuare chiamate di eventi e inviare dati al server [di raccolta](../reference/system-components/components-data-collection.md)dati.
* Invia dati alle [destinazioni](../features/destinations/destinations.md).

## Ottenere e implementare il codice DIL {#get-implement-dil-code}

[!UICONTROL DIL] il codice è disponibile per il download **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. A partire dalla versione 8.0 (rilasciata nell&#39;agosto 2018),[!UICONTROL DIL]la versione 3.3 o successiva del Servizio[identità Adobe Experience Platform è strettamente dipendente dal Servizio](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html)identità. Per attivare le sincronizzazioni[!DNL ID Service]ID e[!DNL URL destinations]. Si verifica un errore se il file[!DNL ID Service]risulta mancante, obsoleto o non configurato.

Invece di utilizzare [!UICONTROL DIL] e configurare [!DNL Audience Manager] manualmente, consigliamo di utilizzare [lancio](https://docs.adobelaunch.com/) Adobe Experience Platform. [!DNL Adobe Experience Platform Launch] è lo strumento di implementazione consigliato perché semplifica la distribuzione del codice, la posizione e la gestione delle versioni. Per ulteriori informazioni sull&#39;estensione [Audience Manager](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) , consulta [!DNL Adobe Experience Platform Launch].

[!DNL Adobe Experience Platform Launch] è il successore di [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Chiamata di esempio {#sample-code}

[!UICONTROL DIL] invia i dati a [!DNL Audience Manager] una chiamata dell&#39;evento. Una chiamata evento è una richiesta HTTP XML proveniente dalla pagina. Utilizza un `POST` metodo per inviare i dati nel corpo della richiesta.

| Elemento Chiamata Evento | Descrizione |
|--- |--- |
| URL | Le chiamate agli eventi DIL utilizzano la sintassi seguente: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Come mostrato nell&#39;esempio seguente, DIL trasmette i dati come coppie chiave-valore. I caratteri di prefisso speciali identificano le coppie chiave-valore come  variabili Audience Manager o partner.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Vedi anche:
* [Requisiti di prefisso delle variabili chiave](../features/traits/trait-variable-prefixes.md)
* [Attributi supportati per le chiamate API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Collegamenti correlati

* [Casi d’uso DIL ed esempi di codice](/help/using/dil/dil-use-cases.md)
* [Metodi DIL a livello di classe ](/help/using/dil/dil-class-overview/dil-start.md)
* [Metodi DIL a livello di istanza](/help/using/dil/dil-instance-methods.md)
* [Moduli DIL](/help/using/dil/dil-modules.md)
* [Strumenti DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)