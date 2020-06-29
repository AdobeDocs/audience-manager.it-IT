---
description: Descrive le coppie chiave-valore comuni a livello di piattaforma che potete utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell'account Audience Manager .
seo-description: Descrive le coppie chiave-valore comuni a livello di piattaforma che potete utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell'account Audience Manager .
seo-title: Targeting dei dispositivi con chiavi a livello di Platform
solution: Audience Manager
title: Targeting dei dispositivi con chiavi a livello di Platform
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

Descrive le coppie chiave-valore comuni a livello di piattaforma che potete utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell&#39;account Audience Manager .

## Finalità delle variabili a livello di Platform {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Le variabili a livello di Platform consentono di prendere i dati passati da un particolare sito e renderli disponibili per il targeting tra tutte le proprietà dell&#39; [!DNL Audience Manager] account. Queste variabili sono costituite da coppie [chiave-valore con il prefisso key di](../../reference/key-value-pairs-explained.md) `d_` come mostrato di seguito.

## Chiavi a livello di Platform definite dall&#39;agente utente {#keys-user-agent}

I valori di [!UICONTROL Data Collection Servers] queste chiavi vengono estratti dall&#39;intestazione [agente](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) utente nelle `HTTP` richieste. I valori rappresentano le informazioni a livello di dispositivo provenienti dal [!UICONTROL Device Atlas] database. I segnali riportati nella tabella seguente sono disponibili, come estratto dall&#39;esempio dell&#39;agente utente. [Scarica un elenco delle chiavi](assets/device_keys.csv)più comuni, in base alle [!UICONTROL Device Atlas] misurazioni.

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
>* [Requisiti del prefisso per le variabili chiave](../../features/traits/trait-variable-prefixes.md)

