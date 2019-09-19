---
description: Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.
seo-description: Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.
seo-title: Metodi API di destinazione
solution: Audience Manager
title: Metodi API di destinazione
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Metodi API di destinazione {#destination-api-methods}

Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.

<!-- c_destinations_api.xml -->

In Audience Manager, una destinazione è qualsiasi altro sistema (server di annunci, [!DNL DSP]rete di annunci, scambio, cookie di prime parti, ecc.) con cui condividere i dati.

## Tipi di destinazione: URL e cookie {#destination-types}

Elenca le variabili utilizzate dal `destinationType` parametro. Specificate `push` o `ADS` utilizzare un [!UICONTROL URL] o [!UICONTROL cookie destination]. Non è possibile creare [!UICONTROL server-to-server destinations] con i metodi di destinazione [!DNL API] disponibili.

<!-- r_destination_types.xml -->

| Tipo di destinazione API | Tipo di destinazione interfaccia |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_LIKE_this]
>
>* [Come scegliere un tipo di destinazione](../../../features/destinations/destinations.md)

