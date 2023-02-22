---
description: Descrive le coppie chiave-valore comuni a livello di piattaforma che è possibile utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell'account Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Targeting dei dispositivi con chiavi a livello di piattaforma
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 5%

---

# Targeting dei dispositivi con chiavi a livello di piattaforma {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google ha aggiornato le funzionalità di [!DNL Google Chrome] e tutti [!DNL Chromium]browser basati su per ridurre al minimo le informazioni raccolte tramite `User-Agent` intestazione.
>A partire da marzo 2023, Audience Manager supporta questi aggiornamenti sfruttando [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). Per continuare a utilizzare le informazioni sulle caratteristiche fornite tramite `User-Agent` intestazione, è necessario utilizzare [SDK per web](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) e [Hint client User-Agent ad alta entropia](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>Questi aggiornamenti non sono supportati da [DIL](../../../using/dil/dil-overview.md), ad Audience Manager i clienti che utilizzano [!DNL DIL] non sarà in grado di raccogliere informazioni sulle caratteristiche tramite il `User-Agent` intestazione.

Descrive le coppie chiave-valore comuni a livello di piattaforma che è possibile utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell&#39;account Audience Manager.

## Finalità delle variabili a livello di piattaforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Le variabili a livello di piattaforma consentono di prendere i dati trasmessi da un particolare sito e di renderli disponibili per il targeting in tutte le proprietà del sito [!DNL Audience Manager] conto. Queste variabili sono costituite da [coppie chiave-valore](../../reference/key-value-pairs-explained.md) con la chiave preceduta da `d_` come mostrato di seguito.

## Chiavi a livello di piattaforma definite dall&#39;agente utente {#keys-user-agent}

La [!UICONTROL Data Collection Servers] estrae i valori di queste chiavi dalla [intestazione agente utente](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` richieste. I valori rappresentano le informazioni a livello di dispositivo dal [!UICONTROL Device Atlas] database. I segnali nella tabella seguente sono disponibili, come estratti dall’esempio dell’agente utente. [Scarica un elenco delle chiavi più comuni](assets/device_keys.csv), secondo [!UICONTROL Device Atlas] misurazioni.

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>Anche se uno o più segnali non possono essere recuperati dall&#39;intestazione dell&#39;agente utente, gli altri segnali verranno comunque trasmessi al [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Requisiti di prefisso delle variabili chiave](../../features/traits/trait-variable-prefixes.md)

