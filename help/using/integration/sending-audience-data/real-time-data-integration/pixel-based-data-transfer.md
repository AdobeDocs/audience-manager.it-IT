---
description: I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L'interfaccia Audience Manager consente ai client di creare un numero qualsiasi di pixel su base self-service. Le stringhe pixel sono costituite da ID semplici o coppie chiave-valore.
seo-description: I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L'interfaccia Audience Manager consente ai client di creare un numero qualsiasi di pixel su base self-service. Le stringhe pixel sono costituite da ID semplici o coppie chiave-valore.
seo-title: Trasferimenti di dati basati su pixel
solution: Audience Manager
title: Trasferimenti di dati basati su pixel
uuid: 8773 bfc 0-6 b 8 d -4 a 6 a-a 8 b 7-e 043744486 ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Trasferimenti di dati basati su pixel {#pixel-based-data-transfers}

I pixel semplici (che possono essere utilizzati per qualificare gli utenti per le caratteristiche) eseguono trasferimenti di dati in tempo reale. L&#39;interfaccia Audience Manager consente ai client di creare un numero qualsiasi di pixel su base self-service. Le stringhe pixel sono costituite da ID semplici o coppie chiave-valore.

<!-- c_rt_inbound_pixel_transfers.xml -->

Per abilitare i trasferimenti di dati in entrata, il fornitore e il client devono:

1. Determinate le caratteristiche che desiderate vengano attivate dal fornitore o partner.
1. Ottenete il pixel per la caratteristica. Nella schermata dell&#39;elenco delle caratteristiche, passate il mouse sulla **[!UICONTROL Actions]** colonna e fate clic sul **[!UICONTROL Get trait URL]** simbolo desiderato.
1. Fornire il [!DNL URL] fornitore o il partner.

## Esempi

Questa chiamata di eventi di base invia l&#39;ID di caratteristica 1234 a [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Potete serializzare gli ID delle caratteristiche in una chiamata evento per ridurre `HTTP` il traffico dalla pagina. Aggiungete ulteriori ID caratteristiche alla stringa URL come illustrato nell&#39;esempio seguente:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
