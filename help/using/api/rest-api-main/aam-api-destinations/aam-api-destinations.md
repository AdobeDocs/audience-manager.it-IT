---
description: Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.
seo-description: Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.
seo-title: 'Metodi API per le destinazioni '
solution: Audience Manager
title: 'Metodi API per le destinazioni '
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 16%

---

# Metodi API per le destinazioni {#destination-api-methods}

Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.

<!-- c_destinations_api.xml -->

Ad Audience Manager, una destinazione è qualsiasi altro sistema (ad server, [!DNL DSP], ad network, exchange, il tuo cookie di prime parti, ecc.) con cui desideri condividere i dati.

## Tipi di destinazione: URL e cookie {#destination-types}

Elenca le variabili utilizzate dal parametro `destinationType`. Specificare `push` o `ADS` per lavorare con un [!UICONTROL URL] o [!UICONTROL cookie destination]. Non è possibile creare [!UICONTROL server-to-server destinations] con i metodi [!DNL API] di destinazione disponibili.

<!-- r_destination_types.xml -->

| Tipo di destinazione API | Tipo di destinazione dell&#39;interfaccia |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Come scegliere un tipo di destinazione](../../../features/destinations/destinations.md)

