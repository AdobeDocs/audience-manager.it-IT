---
description: Panoramica di DIL e del suo funzionamento.
seo-description: Panoramica di DIL e del suo funzionamento.
seo-title: Informazioni sulla Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: Informazioni sulla Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: Implementazione di DIL
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 16%

---

# Informazioni su [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Panoramica, guida introduttiva e metodi di codice disponibili nella libreria di codici [!DNL Audience Manager DIL] .

>[!IMPORTANT]
>
>A partire dalla versione 8.0 (rilasciata nell’agosto 2018), [!UICONTROL DIL] ha una dipendenza solida dal [servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html), versione 3.3 o successiva. Per attivare le sincronizzazioni ID e le destinazioni URL si basa su [!DNL ID Service] . Si verifica un errore se il [!DNL ID Service] è mancante, vecchio o non configurato.
>
>È consigliabile utilizzare [!DNL Adobe Experience Platform Launch] per implementare e gestire le librerie [!DNL DIL] e [!DNL Adobe Experience Platform Identity Service].

Tuttavia, puoi anche scaricare l’Experience Cloud più recente e le versioni [!DNL DIL] dalla nostra pagina GitHub. Vedi i link di download seguenti:

* Scarica il [servizio Adobe Experience Platform Identity](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Scarica [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalità di DIL {#purpose-dil}

[!UICONTROL DIL] è una libreria API. Può essere considerato come un corpo di codice helper per per [!DNL Adobe Audience Manager]. Non è necessario utilizzare [!DNL Audience Manager], ma i metodi e le funzioni [!UICONTROL DIL] consentono di non dover sviluppare un codice personalizzato per inviare dati a [!DNL Audience Manager]. Inoltre, [!UICONTROL DIL] è diverso dall’API fornita dal [servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/en/id-service/using/home.html). Tale servizio è progettato per gestire l&#39;identità del visitatore tra diverse soluzioni [!DNL Experience Cloud] . Al contrario, [!UICONTROL DIL] è progettato per:

* Effettuare chiamate evento e inviare dati al [server di raccolta dati](../reference/system-components/components-data-collection.md).
* Invia dati a [destinazioni](../features/destinations/destinations.md).

## Ottenimento e implementazione del codice DIL {#get-implement-dil-code}

[!UICONTROL DIL] Il codice è disponibile per il download  **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. A partire dalla versione 8.0 (rilasciata nell’agosto 2018), [!UICONTROL DIL] ha una dipendenza solida dal [servizio Adobe Experience Platform Identity](https://docs.adobe.com/content/help/en/id-service/using/home.html), versione 3.3 o successiva. Si basa sul [!DNL ID Service] per attivare le sincronizzazioni ID e [!DNL URL destinations]. Si verifica un errore se il [!DNL ID Service] è mancante, vecchio o non configurato.

Invece di lavorare con [!UICONTROL DIL] e impostare [!DNL Audience Manager] manualmente, ti consigliamo di utilizzare al suo posto [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html). [!DNL Adobe Experience Platform Launch] è lo strumento di implementazione consigliato perché semplifica la distribuzione del codice, il posizionamento e la gestione delle versioni. Ulteriori informazioni sull&#39; [estensione di Audience Manager](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) in [!DNL Adobe Experience Platform Launch].

## Chiamata di esempio {#sample-code}

[!UICONTROL DIL] invia dati a  [!DNL Audience Manager] in una chiamata evento. Una chiamata evento è una richiesta HTTP XML dalla pagina. Utilizza un metodo `POST` per inviare i dati nel corpo della richiesta.

| Elemento chiamata evento | Descrizione |
|--- |--- |
| URL | Le chiamate agli eventi di DIL utilizzano la sintassi seguente: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Come mostrato nell’esempio seguente, DIL trasmette i dati come coppie chiave-valore. I caratteri di prefisso speciali identificano le coppie chiave-valore come variabili di Audience Manager o partner.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
