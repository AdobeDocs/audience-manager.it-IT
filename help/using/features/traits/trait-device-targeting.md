---
description: Descrive le coppie chiave-valore comuni a livello di piattaforma che puoi utilizzare per indirizzare gli utenti con variabili relative al dispositivo in tutte le proprietà nell’account di Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Targeting dei dispositivi con chiavi a livello di piattaforma
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# Targeting dei dispositivi con chiavi a livello di piattaforma {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google ha aggiornato la funzionalità di [!DNL Google Chrome] e di tutti i browser basati su [!DNL Chromium] per ridurre al minimo le informazioni raccolte tramite l&#39;intestazione `User-Agent`.
>A partire da marzo 2023, Audience Manager supporta questi aggiornamenti sfruttando [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). Per continuare a utilizzare le informazioni sulle caratteristiche fornite tramite l&#39;intestazione `User-Agent`, è necessario utilizzare [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) e abilitare [User-Agent Client Hints ad alta entropia](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>Questi aggiornamenti non sono supportati da [DIL](../../../using/dil/dil-overview.md), pertanto i clienti Audienci Manager che utilizzano [!DNL DIL] non potranno raccogliere informazioni sulle caratteristiche tramite l&#39;intestazione `User-Agent`.

Descrive le coppie chiave-valore comuni a livello di piattaforma che puoi utilizzare per indirizzare gli utenti con variabili relative al dispositivo in tutte le proprietà nell’account di Audience Manager.

## Finalità delle variabili a livello di piattaforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Le variabili a livello di piattaforma consentono di acquisire i dati trasmessi da un particolare sito e renderli disponibili per il targeting in tutte le proprietà nell&#39;account [!DNL Audience Manager]. Queste variabili sono formate da [coppie chiave-valore](../../reference/key-value-pairs-explained.md) con la chiave con prefisso `d_`, come illustrato di seguito.

## Chiavi a livello di piattaforma definite dall’agente utente {#keys-user-agent}

[!UICONTROL Data Collection Servers] estrae i valori per queste chiavi dall&#39;intestazione [dell&#39;agente utente](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) nelle richieste `HTTP`. I valori rappresentano le informazioni a livello di dispositivo dal database [!UICONTROL Device Atlas]. Sono disponibili i segnali nella tabella seguente, come estratti dall’esempio dell’agente utente. [Scarica un elenco delle chiavi più comuni](assets/device_keys.csv), in base a [!UICONTROL Device Atlas] misurazioni.

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
>Anche se uno o più segnali non possono essere recuperati dall&#39;intestazione dell&#39;agente utente, gli altri segnali verranno comunque passati a [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Requisiti di prefisso delle variabili chiave](../../features/traits/trait-variable-prefixes.md)
