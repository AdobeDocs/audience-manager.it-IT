---
description: Panoramica di DIL e del suo funzionamento.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: Informazioni sulla Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 11%

---

# Informazioni sulla [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Panoramica, guida introduttiva e metodi di codice disponibili in [!DNL Audience Manager DIL] libreria dei codici.

>[!IMPORTANT]
>
>A partire dalla versione 8.0 (rilasciata nell’agosto 2018), [!UICONTROL DIL] ha una dipendenza difficile da [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html), versione 3.3 o successiva. Si basa sul [!DNL ID Service] per attivare le sincronizzazioni ID e le destinazioni URL. Si verifica un errore se [!DNL ID Service] è mancante, vecchio o non configurato.
>
>Si consiglia di utilizzare [!DNL Adobe Experience Platform Tags] per implementare e gestire le [!DNL DIL] e [!DNL Adobe Experience Platform Identity Service] librerie.

Tuttavia, puoi anche scaricare l’Experience Cloud più recente e [!DNL DIL] versioni dalla nostra pagina GitHub. Vedi i link di download seguenti:

* Scarica la [Servizio Adobe Experience Platform Identity](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Scarica [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalità di DIL {#purpose-dil}

[!UICONTROL DIL] è una libreria API. Si può pensare che sia un corpo di codice di supporto per [!DNL Adobe Audience Manager]. Non è necessario utilizzare [!DNL Audience Manager], ma i metodi e le funzioni [!UICONTROL DIL] fornisce significa che non devi sviluppare un codice personalizzato per inviare dati a [!DNL Audience Manager]. Inoltre, [!UICONTROL DIL] è diverso dall’API fornita da [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html). Tale servizio è progettato per gestire l&#39;identità del visitatore tra diversi [!DNL Experience Cloud] soluzioni. Per contro, [!UICONTROL DIL] è progettato per:

* Effettuare chiamate evento e inviare dati al [Server di raccolta dati](../reference/system-components/components-data-collection.md).
* Invia dati a [destinazioni](../features/destinations/destinations.md).

## Ottenimento e implementazione del codice DIL {#get-implement-dil-code}

[!UICONTROL DIL] il codice è disponibile per il download **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. A partire dalla versione 8.0 (rilasciata nell’agosto 2018), [!UICONTROL DIL] ha una dipendenza difficile da [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html), versione 3.3 o successiva. Si basa sul [!DNL ID Service] per attivare le sincronizzazioni ID e [!DNL URL destinations]. Si verifica un errore se [!DNL ID Service] è mancante, vecchio o non configurato.

Piuttosto che lavorare con [!UICONTROL DIL] e la configurazione [!DNL Audience Manager] manualmente, ti consigliamo di utilizzare [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) invece. [!DNL Adobe Experience Platform Tags] è lo strumento di implementazione consigliato perché semplifica la distribuzione del codice, il posizionamento e la gestione delle versioni. Ulteriori informazioni sulle [Estensione Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## Chiamata di esempio {#sample-code}

[!UICONTROL DIL] invia dati a [!DNL Audience Manager] in una chiamata evento. Una chiamata evento è una richiesta HTTP XML dalla pagina. Utilizza un `POST` metodo per inviare i dati nel corpo della richiesta.

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
