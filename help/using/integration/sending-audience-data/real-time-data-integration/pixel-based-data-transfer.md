---
description: I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L’interfaccia di Audience Manager consente ai client di creare un numero qualsiasi di pixel su base self-service. Le stringhe di pixel sono costituite da ID semplici o coppie chiave-valore.
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: Trasferimenti di dati basati su pixel
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Trasferimenti di dati basati su pixel {#pixel-based-data-transfers}

I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L’interfaccia di Audience Manager consente ai client di creare un numero qualsiasi di pixel su base self-service. Le stringhe di pixel sono costituite da ID semplici o coppie chiave-valore.

<!-- c_rt_inbound_pixel_transfers.xml -->

Per abilitare i trasferimenti di dati in entrata, il fornitore e il cliente devono:

1. Determina le caratteristiche che desideri che il fornitore o il partner attivi.
1. Ottieni il pixel per la caratteristica. Nella schermata dell&#39;elenco delle caratteristiche, passa il cursore del mouse sulla colonna **[!UICONTROL Actions]** e fai clic sul simbolo **[!UICONTROL Get trait URL]** per la caratteristica desiderata.
1. Fornisci [!DNL URL] al fornitore o al partner.

## Esempi

Questa chiamata evento di base invia la caratteristica ID 1234 a [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

È possibile serializzare gli ID caratteristica in una chiamata evento per ridurre il traffico `HTTP` dalla pagina. Aggiungi ID di caratteristica aggiuntivi alla stringa URL, come illustrato nell’esempio seguente:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
