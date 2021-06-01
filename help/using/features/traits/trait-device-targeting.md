---
description: Descrive le coppie chiave-valore comuni a livello di piattaforma che è possibile utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell'account Audience Manager.
seo-description: Descrive le coppie chiave-valore comuni a livello di piattaforma che è possibile utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell'account Audience Manager.
seo-title: Targeting dei dispositivi con chiavi a livello di piattaforma
solution: Audience Manager
title: Targeting dei dispositivi con chiavi a livello di piattaforma
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: 'Caratteristiche '
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---

# Targeting dei dispositivi con chiavi a livello di piattaforma {#device-targeting-with-platform-level-keys}

Descrive le coppie chiave-valore comuni a livello di piattaforma che è possibile utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell&#39;account Audience Manager.

## Finalità delle variabili a livello di piattaforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Le variabili a livello di piattaforma consentono di prendere i dati trasmessi da un particolare sito e renderli disponibili per il targeting in tutte le proprietà del tuo account [!DNL Audience Manager]. Queste variabili sono costituite da [coppie chiave-valore](../../reference/key-value-pairs-explained.md) con la chiave preceduta da `d_` come mostrato di seguito.

## Chiavi a livello di piattaforma definite dall&#39;agente utente {#keys-user-agent}

Le [!UICONTROL Data Collection Servers] estraggono i valori per queste chiavi dall&#39; [intestazione dell&#39;agente utente](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) nelle richieste `HTTP`. I valori rappresentano informazioni a livello di dispositivo dal database [!UICONTROL Device Atlas]. I segnali nella tabella seguente sono disponibili, come estratti dall’esempio dell’agente utente. [Scarica un elenco delle chiavi](assets/device_keys.csv) più comuni, in base alle  [!UICONTROL Device Atlas] misurazioni.

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

