---
description: Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.
seo-description: Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.
seo-title: 'Metodi API per le destinazioni '
solution: Audience Manager
title: 'Metodi API per le destinazioni '
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 15%

---


# Metodi API per le destinazioni {#destination-api-methods}

Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.

<!-- c_destinations_api.xml -->

In  Audience Manager, una destinazione è qualsiasi altro sistema (server di annunci, [!DNL DSP]rete di annunci, scambio, cookie di prime parti, ecc.) con cui desideri condividere i dati.

## Tipi di destinazione: URL e cookie {#destination-types}

Elenca le variabili utilizzate dal `destinationType` parametro. Specificate `push` o `ADS` utilizzare un [!UICONTROL URL] o [!UICONTROL cookie destination]. Non è possibile creare [!UICONTROL server-to-server destinations] con i metodi di destinazione [!DNL API] disponibili.

<!-- r_destination_types.xml -->

| Tipo di destinazione API | Tipo di destinazione interfaccia |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Come scegliere un tipo di destinazione](../../../features/destinations/destinations.md)

