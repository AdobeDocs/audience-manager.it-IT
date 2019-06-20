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


# Informazioni sulla libreria di integrazione dei dati (DIL){#understanding-the-data-integration-library-dil}

Panoramica, guida introduttiva e metodi di codice disponibili nella libreria codice DIL di Audience Manager.

>[!IMPORTANT]
>
>A partire dalla versione 8.0 (rilasciata agosto 2018), [!UICONTROL DIL] ha una dipendenza intensa dal servizio [](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID versione 3.3 o successiva. Utilizza il servizio ID per attivare le sincronizzazioni ID e le destinazioni URL. Si verifica un errore se il servizio ID è mancante, vecchio o non configurato.
>
>Consigliamo di utilizzare Adobe Launch per implementare e gestire le librerie di servizio ID DIL e Experience Cloud.

Tuttavia, puoi anche scaricare le versioni più recenti di Experience Cloud e DIL dalla nostra pagina github. Consultate i collegamenti di download di seguito:

* Scaricare il [servizio Experience Cloud ID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Scopo di DIL {#purpose-dil}

[!UICONTROL DIL] è una libreria API. You can think it as a body of helper code for [!DNL Adobe Audience Manager]. Non è necessario utilizzare [!DNL Audience Manager], ma i metodi e le funzioni [!UICONTROL DIL] forniscono mezzi per non dover sviluppare codice a cui [!DNL Audience Manager]inviare dati. Inoltre, [!UICONTROL DIL] è diverso dall&#39;API fornita dal servizio [Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/). Questo servizio è progettato per gestire l&#39;identità dei visitatori tra [!DNL Experience Cloud] soluzioni diverse. Per contro, [!UICONTROL DIL] è progettato per:

* Effettuare chiamate agli eventi e inviare dati a [Data Collection Server](../reference/system-components/components-data-collection.md).
* Inviare dati alle [destinazioni](../features/destinations/destinations.md).

## Ottenimento e implementazione del codice DIL {#get-implement-dil-code}

[!UICONTROL DIL] è disponibile per il download **[qui](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Tieni presente che a partire dalla versione 8.0 (rilasciata agosto 2018), [!UICONTROL DIL] ha una dipendenza intensa dal servizio [](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud ID versione 3.3 o successiva. Utilizza il servizio ID per attivare le sincronizzazioni ID e le destinazioni URL. Si verifica un errore se il servizio ID è mancante, vecchio o non configurato.

Invece di lavorare con [!UICONTROL DIL] e impostare [!DNL Audience Manager] manualmente, consigliamo di utilizzare [Adobe Launch](https://docs.adobelaunch.com/) . [!DNL Adobe Launch] è lo strumento di implementazione consigliato perché semplifica implementazione del codice, posizionamento e gestione delle versioni. Ulteriori informazioni sull&#39;estensione [Audience Manager](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch è il successore di [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Chiamata di esempio {#sample-code}

[!UICONTROL DIL] invia dati a [!DNL Audience Manager] una chiamata evento. Una chiamata all&#39;evento è una richiesta HML HTTP dalla pagina. Utilizza un `POST` metodo per inviare dati nel corpo della richiesta.

| Elemento chiamata evento | Descrizione |
|--- |--- |
| URL | Le chiamate all&#39;evento DIL usano la sintassi seguente: `https://adobe.demdex.net/event?_ts =`*`UNIX UTC timestamp`* |
| Corpo | Come mostrato nell&#39;esempio seguente, DIL trasmette i dati come coppie chiave-valore. I caratteri speciali di prefisso identificano le coppie chiave-valore come variabili di Audience Manager o partner.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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