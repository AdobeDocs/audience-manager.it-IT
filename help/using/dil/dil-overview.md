---
description: Una panoramica del DIL e di come funziona.
seo-description: Una panoramica del DIL e di come funziona.
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

Panoramica, guida introduttiva e metodi di codice disponibili nella libreria dei codici [!DNL Audience Manager DIL].

>[!IMPORTANT]
>
>A partire dalla versione 8.0 (rilasciata nell&#39;agosto 2018), [!UICONTROL DIL] ha una dipendenza su [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html), versione 3.3 o successiva. Si basa su [!DNL ID Service] per attivare le sincronizzazioni ID e le destinazioni URL. Si verifica un errore se [!DNL ID Service] è mancante, obsoleto o non è configurato.
>
>È consigliabile utilizzare [!DNL Adobe Experience Platform Launch] per implementare e gestire le librerie [!DNL DIL] e [!DNL Adobe Experience Platform Identity Service].

Tuttavia, potete anche scaricare l&#39;Experience Cloud  più recente e le [!DNL DIL] versioni dalla nostra pagina GitHub. Consultate i collegamenti per il download di seguito:

* Download di [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download di [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalità del DIL {#purpose-dil}

[!UICONTROL DIL] è una libreria API. È possibile pensare che sia un corpo di codice helper per per [!DNL Adobe Audience Manager]. Non è necessario utilizzare [!DNL Audience Manager], ma i metodi e le funzioni [!UICONTROL DIL] indicano che non è necessario sviluppare un codice personalizzato per inviare i dati a [!DNL Audience Manager]. Inoltre, [!UICONTROL DIL] è diverso dall&#39;API fornita da [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html). Tale servizio è progettato per gestire l&#39;identità del visitatore tra diverse soluzioni [!DNL Experience Cloud]. Per contro, [!UICONTROL DIL] è progettato per:

* Effettuare chiamate di eventi e inviare dati al [server di raccolta dati](../reference/system-components/components-data-collection.md).
* Invia i dati a [destinazioni](../features/destinations/destinations.md).

## Ottenimento e implementazione del codice DIL {#get-implement-dil-code}

[!UICONTROL DIL] il codice è disponibile per il download  **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. A partire dalla versione 8.0 (rilasciata nell&#39;agosto 2018), [!UICONTROL DIL] ha una dipendenza su [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), versione 3.3 o successiva. Si basa su [!DNL ID Service] per attivare le sincronizzazioni ID e [!DNL URL destinations]. Si verifica un errore se [!DNL ID Service] è mancante, obsoleto o non è configurato.

Invece di utilizzare [!UICONTROL DIL] e impostare [!DNL Audience Manager] manualmente, è consigliabile utilizzare [ Adobe Experience Platform Launch](https://docs.adobelaunch.com/). [!DNL Adobe Experience Platform Launch] è lo strumento di implementazione consigliato perché semplifica la distribuzione del codice, la posizione e la gestione delle versioni. Ulteriori informazioni sull&#39;estensione del Audience Manager [](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in [!DNL Adobe Experience Platform Launch].

[!DNL Adobe Experience Platform Launch] è il successore di  [ Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Chiamata di esempio {#sample-code}

[!UICONTROL DIL] invia i dati a  [!DNL Audience Manager] una chiamata dell&#39;evento. Una chiamata evento è una richiesta HTTP XML proveniente dalla pagina. Utilizza un metodo `POST` per inviare i dati nel corpo della richiesta.

| Elemento Chiamata Evento | Descrizione |
|--- |--- |
| URL | Le chiamate agli eventi DIL utilizzano la sintassi seguente: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Come mostrato nell&#39;esempio seguente, il DIL trasmette i dati come coppie chiave-valore. I caratteri di prefisso speciali identificano le coppie chiave-valore come variabili  Audience Manager o partner.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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