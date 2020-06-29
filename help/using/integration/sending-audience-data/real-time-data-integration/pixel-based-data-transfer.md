---
description: I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L'interfaccia Audience Manager  consente ai client di creare un numero qualsiasi di pixel in modalità self-service. Le stringhe in pixel sono costituite da ID semplici o da coppie chiave-valore.
seo-description: I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L'interfaccia Audience Manager  consente ai client di creare un numero qualsiasi di pixel in modalità self-service. Le stringhe in pixel sono costituite da ID semplici o da coppie chiave-valore.
seo-title: Trasferimenti di dati basati su pixel
solution: Audience Manager
title: Trasferimenti di dati basati su pixel
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---


# Trasferimenti di dati basati su pixel {#pixel-based-data-transfers}

I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L&#39;interfaccia Audience Manager  consente ai client di creare un numero qualsiasi di pixel in modalità self-service. Le stringhe in pixel sono costituite da ID semplici o da coppie chiave-valore.

<!-- c_rt_inbound_pixel_transfers.xml -->

Per abilitare i trasferimenti di dati in entrata, il fornitore e il client:

1. Determinare quali caratteristiche si desidera che il fornitore o il partner attivi.
1. Ottenete il pixel per la caratteristica. Nella schermata dell’elenco delle caratteristiche, passate il mouse sulla **[!UICONTROL Actions]** colonna e fate clic sul **[!UICONTROL Get trait URL]** simbolo della caratteristica desiderata.
1. Fornisci il [!DNL URL] prodotto al fornitore o al partner.

## Esempi

Questa chiamata dell’evento di base invia l’ID caratteristica 1234 a [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Potete serializzare gli ID delle caratteristiche in una chiamata dell&#39;evento per ridurre il `HTTP` traffico dalla pagina. Aggiungete ulteriori ID di caratteristica alla stringa URL come illustrato nell’esempio seguente:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
