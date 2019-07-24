---
description: Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.
seo-description: Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.
seo-title: Metodi API di destinazione
solution: Audience Manager
title: Metodi API di destinazione
uuid: 048 bcdb 9-2 b 31-46 f 4-8 b 80-4 ba 25 bf 06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination API Methods {#destination-api-methods}

Metodi che consentono di utilizzare in modo programmatico le funzioni di destinazione.

<!-- c_destinations_api.xml -->

In Audience Manager, a destination is any other system (ad server, [!DNL DSP], ad network, exchange, your own first-party cookie, etc.) con cui condividere i dati.

## Destination Types: URL and Cookie {#destination-types}

Lists the variables used by the `destinationType` parameter. Specify `push` or `ADS` to work with a [!UICONTROL URL] or [!UICONTROL cookie destination]. You cannot create [!UICONTROL server-to-server destinations] with the available destination [!DNL API] methods.

<!-- r_destination_types.xml -->

| Tipo di destinazione API | Tipo di destinazione interfaccia utente |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_ LIKE_ THIS]
>
>* [Come scegliere un tipo di destinazione](../../../features/destinations/destinations.md)

