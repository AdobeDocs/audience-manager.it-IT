---
description: Descrive le coppie chiave-valore comuni a livello di piattaforma che puoi utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell'account Audience Manager.
seo-description: Descrive le coppie chiave-valore comuni a livello di piattaforma che puoi utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell'account Audience Manager.
seo-title: Targeting dispositivo con chiavi a livello di piattaforma
solution: Audience Manager
title: Targeting dispositivo con chiavi a livello di piattaforma
uuid: bc 048 cc 5-3 df 1-49 bc-ac 78-0 ea 5 d 7 edd 9 cc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Targeting dispositivo con chiavi a livello di piattaforma {#device-targeting-with-platform-level-keys}

Descrive le coppie chiave-valore comuni a livello di piattaforma che puoi utilizzare per eseguire il targeting degli utenti con variabili relative al dispositivo in tutte le proprietà dell&#39;account Audience Manager.

## Scopo delle variabili a livello di piattaforma {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Le variabili a livello di piattaforma consentono di prendere dati trasmessi da un particolare sito e renderli disponibili per il targeting in tutte le proprietà dell&#39; [!DNL Audience Manager] account. Queste variabili sono formate da [coppie chiave-valore](../../reference/key-value-pairs-explained.md) con la chiave prefissa, `d_` come mostrato di seguito.

## Tasti a livello di piattaforma definiti dall&#39;agente utente {#keys-user-agent}

Estraete [!UICONTROL Data Collection Servers] i valori per queste chiavi dall&#39;intestazione dell&#39;agente [utente](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) nelle `HTTP` richieste. I valori rappresentano informazioni a livello di dispositivo dal [!UICONTROL Device Atlas] database. I segnali nella tabella seguente sono disponibili, come estratti dall&#39;esempio dell&#39;agente utente. [Scaricate un elenco delle chiavi](assets/device_keys.csv)più comuni, in base [!UICONTROL Device Atlas] alle misurazioni.

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
>Anche se non è possibile recuperare uno o più segnali dall&#39;intestazione dell&#39;agente utente, gli altri segnali continueranno a essere trasmessi al [!UICONTROL Data Collection Servers].

>[!MORE_ LIKE_ THIS]
>
>* [Requisiti di prefisso per variabili chiave](../../features/traits/trait-variable-prefixes.md)

