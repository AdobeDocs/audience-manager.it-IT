---
description: Panoramica di DIL e del suo funzionamento.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Informazioni sulla Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 10%

---

# Comprensione di [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>A partire da luglio 2023, Adobe ha interrotto lo sviluppo del [!DNL Data Integration Library (DIL)] e [!DNL DIL] estensione.
><br>
>I clienti esistenti possono continuare a utilizzare [!DNL DIL] implementazione. Tuttavia, Adobe non svilupperà [!DNL DIL] oltre questo punto. I clienti sono invitati a valutare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) per la strategia di raccolta dei dati a lungo termine.
><br>
>I clienti che desiderano implementare nuove integrazioni di raccolta dati dopo luglio 2023 devono utilizzare [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) invece.

Panoramica, guida introduttiva e metodi di codice disponibili nella [!DNL Audience Manager DIL] libreria dei codici.

>[!IMPORTANT]
>
>A partire dalla versione 8.0 (rilasciata nell’agosto 2018), [!UICONTROL DIL] ha una forte dipendenza dal [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html), versione 3.3 o successiva. Si basa sulla [!DNL ID Service] per attivare sincronizzazioni ID e destinazioni URL. Si verifica un errore se [!DNL ID Service] manca, è obsoleto o non è configurato.
>
>Si consiglia di utilizzare [!DNL Adobe Experience Platform Tags] per implementare e gestire [!DNL DIL] e [!DNL Adobe Experience Platform Identity Service] librerie.

Tuttavia, puoi anche scaricare l’Experience Cloud più recente e [!DNL DIL] versioni dalla nostra pagina GitHub. Consulta i collegamenti per il download di seguito:

* Scarica il file [Servizio Adobe Experience Platform Identity](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Scarica [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Finalità del DIL {#purpose-dil}

[!UICONTROL DIL] è una libreria API. Puoi considerarlo come un corpo di codice di supporto per [!DNL Adobe Audience Manager]. Non è necessario utilizzare [!DNL Audience Manager], ma i metodi e le funzioni [!UICONTROL DIL] fornisce significa che non è necessario sviluppare un codice personalizzato per inviare dati a [!DNL Audience Manager]. Inoltre, [!UICONTROL DIL] è diverso dall&#39;API fornita da [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html). Il servizio è progettato per gestire l’identità dei visitatori su diversi [!DNL Experience Cloud] soluzioni. Per contro, [!UICONTROL DIL] è progettato per:

* Effettuare chiamate evento e inviare dati al [Server di raccolta dati](../reference/system-components/components-data-collection.md).
* Invia dati a [destinazioni](../features/destinations/destinations.md).

## Recupero e implementazione del codice DIL {#get-implement-dil-code}

[!UICONTROL DIL] il codice è disponibile per il download **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. A partire dalla versione 8.0 (rilasciata nell’agosto 2018), [!UICONTROL DIL] ha una forte dipendenza dal [Servizio Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html), versione 3.3 o successiva. Si basa sulla [!DNL ID Service] per attivare le sincronizzazioni ID e [!DNL URL destinations]. Si verifica un errore se [!DNL ID Service] manca, è obsoleto o non è configurato.

Anziché utilizzare [!UICONTROL DIL] e configurazione [!DNL Audience Manager] manualmente, si consiglia di utilizzare [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) invece. [!DNL Adobe Experience Platform Tags] è lo strumento di implementazione consigliato perché semplifica la distribuzione del codice, il posizionamento e la gestione delle versioni. Ulteriori informazioni su [Estensione Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## Chiamata di esempio {#sample-code}

[!UICONTROL DIL] invia dati a [!DNL Audience Manager] in una chiamata evento. Una chiamata evento è una richiesta HTTP XML dalla pagina. Utilizza un `POST` metodo per inviare dati nel corpo della richiesta.

| Elemento chiamata evento | Descrizione |
|--- |--- |
| URL | Le chiamate dell’evento DIL utilizzano la seguente sintassi: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corpo | Come mostrato nell’esempio di seguito, DIL trasmette i dati come coppie chiave-valore. I caratteri speciali di prefisso identificano le coppie chiave-valore come Audienci Manager o variabili partner.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
