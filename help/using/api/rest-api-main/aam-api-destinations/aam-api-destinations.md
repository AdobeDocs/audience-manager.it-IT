---
description: Metodi che consentono di lavorare in modo programmatico con le funzioni di destinazione.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: Metodi API per le destinazioni
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
TQID: https://experienceleague.adobe.com/8fUlWE0aqgltxB-bS0X1cjE4Dg0-VvHpRjvWQmjKe5s
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 89
ht-degree: 0%

---

# Metodi API per le destinazioni {#destination-api-methods}

Metodi che consentono di lavorare in modo programmatico con le funzioni di destinazione.

<!-- c_destinations_api.xml -->

In Audience Manager, una destinazione è qualsiasi altro sistema (ad server, [!DNL DSP], ad network, exchange, il cookie di prime parti di un utente, ecc.) con cui si desidera condividere i dati.

## Tipi di destinazione: URL e cookie {#destination-types}

Elenca le variabili utilizzate dal parametro `destinationType`. Specificare `push` o `ADS` per lavorare con [!UICONTROL URL] o [!UICONTROL cookie destination]. Impossibile creare [!UICONTROL server-to-server destinations] con i metodi di destinazione [!DNL API] disponibili.

<!-- r_destination_types.xml -->

| Tipo di destinazione API | Tipo di destinazione interfaccia utente |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Come scegliere un tipo di destinazione](../../../features/destinations/destinations.md)
