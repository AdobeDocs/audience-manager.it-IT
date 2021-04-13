---
description: I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L’interfaccia Audience Manager consente ai client di creare un numero qualsiasi di pixel in modalità self-service. Le stringhe di pixel sono costituite da ID semplici o da coppie chiave-valore.
seo-description: I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L’interfaccia Audience Manager consente ai client di creare un numero qualsiasi di pixel in modalità self-service. Le stringhe di pixel sono costituite da ID semplici o da coppie chiave-valore.
seo-title: Trasferimenti di dati basati su pixel
solution: Audience Manager
title: Trasferimenti di dati basati su pixel
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Trasferimenti di dati in entrata
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 4%

---

# Trasferimenti di dati basati su pixel {#pixel-based-data-transfers}

I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L’interfaccia Audience Manager consente ai client di creare un numero qualsiasi di pixel in modalità self-service. Le stringhe di pixel sono costituite da ID semplici o da coppie chiave-valore.

<!-- c_rt_inbound_pixel_transfers.xml -->

Per abilitare i trasferimenti di dati in entrata, il fornitore e il client:

1. Determinare le caratteristiche che si desidera che il fornitore o il partner attivino.
1. Ottieni il pixel della caratteristica. Nella schermata dell’elenco delle caratteristiche, passa il cursore del mouse sulla colonna **[!UICONTROL Actions]** e fai clic sul simbolo **[!UICONTROL Get trait URL]** per la caratteristica desiderata.
1. Fornisci il [!DNL URL] al fornitore o al partner.

## Esempi

Questa chiamata dell&#39;evento di base invia l&#39;ID caratteristica 1234 a [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Puoi serializzare gli ID delle caratteristiche in una chiamata dell&#39;evento per ridurre il traffico `HTTP` dalla pagina. Aggiungi altri ID di caratteristiche alla stringa URL come mostrato nell&#39;esempio seguente:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
