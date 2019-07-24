---
description: Panoramica di DIL e modalità di funzionamento.
seo-description: Panoramica di DIL e modalità di funzionamento.
seo-title: Informazioni sulla libreria di integrazione dei dati (DIL)
solution: Audience Manager
title: Informazioni sulla libreria di integrazione dei dati (DIL)
uuid: 77 b 12 f 35-81 e 4-4639-ada 6-bf 982 f 27 b 36 e
translation-type: tm+mt
source-git-commit: 8f2cbf8a31335762f03cad278114d9ab7c520763

---


# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Panoramica, guida introduttiva e metodi di codice disponibili nella libreria codice DIL di Audience Manager.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Utilizza il servizio ID per attivare le sincronizzazioni ID e le destinazioni URL. Si verifica un errore se il servizio ID è mancante, vecchio o non configurato.
>
>Consigliamo di utilizzare Adobe Launch per implementare e gestire le librerie di servizio ID DIL e Experience Cloud.

Tuttavia, puoi anche scaricare le versioni più recenti di Experience Cloud e DIL dalla nostra pagina github. Consultate i collegamenti di download di seguito:

* Download the [Experience Cloud ID Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Purpose of DIL {#purpose-dil}

[!UICONTROL DIL] è una libreria API. You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don't have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. By contrast, [!UICONTROL DIL] is designed to:

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md).
* Send data to [destinations](../features/destinations/destinations.md).

## Getting and Implementing DIL Code {#get-implement-dil-code}

[!UICONTROL DIL] è disponibile per il download **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Utilizza il servizio ID per attivare le sincronizzazioni ID e le destinazioni URL. Si verifica un errore se il servizio ID è mancante, vecchio o non configurato.

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Launch] è lo strumento di implementazione consigliato perché semplifica implementazione del codice, posizionamento e gestione delle versioni. Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Sample Call {#sample-code}

[!UICONTROL DIL] invia dati a [!DNL Audience Manager] una chiamata evento. Una chiamata all'evento è una richiesta HML HTTP dalla pagina. It uses a `POST` method to send data in the body of the request.

| Elemento chiamata evento | Descrizione |
|--- |--- |
| URL | DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Come mostrato nell'esempio seguente, DIL trasmette i dati come coppie chiave-valore. Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Vedi anche:
* [Requisiti di prefisso per variabili chiave](../features/traits/trait-variable-prefixes.md)
* [Attributi supportati per chiamate API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Collegamenti correlati

* [Casi di utilizzo DIL e esempi di codice](/help/using/dil/dil-use-cases.md)
* [Metodi DIL a livello di classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Metodi DIL a livello di istanza](/help/using/dil/dil-instance-methods.md)
* [Moduli DIL](/help/using/dil/dil-modules.md)
* [Strumenti DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)