---
description: La funzione di soppressione immediata su diversi dispositivi consente di eliminare gli utenti per i diversi dispositivi a cui sono associati, dopo il verificarsi di una specifica esperienza su uno di tali dispositivi. Questa funzione consente di fornire a un utente un’esperienza coerente su tutti i suoi dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.
seo-description: La funzione di soppressione immediata su diversi dispositivi consente di eliminare gli utenti per i diversi dispositivi a cui sono associati, dopo il verificarsi di una specifica esperienza su uno di tali dispositivi. Questa funzione consente di fornire a un utente un’esperienza coerente su tutti i suoi dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.
seo-title: Soppressione immediata su diversi dispositivi
title: Soppressione immediata su diversi dispositivi
uuid: cb 11 b 9 cb -6 d 7 d -4 aa 9-91 b 0-c 2715857 d 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Soppressione immediata su diversi dispositivi {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] è la capacità di sopprimere gli utenti su più dispositivi connessi quando si verifica un'esperienza particolare su uno qualsiasi di questi dispositivi. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.

## Panoramica {#overview}

[!UICONTROL Instant Cross-Device Suppression] sono disponibili due casi d'uso principali: esperienza utente migliorata e efficienza dei supporti.

* **Un'esperienza utente migliorata**: Gli utenti che hanno già acquistato il prodotto o il servizio non vedono gli stessi creativi prima dell'acquisto. Puoi invece visualizzare messaggi upselling o cross-selling per prodotti o servizi che sai che non hanno acquistato.
* **Efficienza file multimediali**: Ottimizzate la spesa delle campagne applicando un berretto globale della frequenza tra tutte [!DNL DSP]le s. Il limite di frequenza può essere eseguito in tempo reale per più dispositivi appartenenti a un utente.

The technical details of the real-time unsegmentation are described in length in [Profile Merge Rules and Device Un-Segmentation Processes](../../features/profile-merge-rules/merge-rule-unsegment.md). Continua a leggere per l'implementazione pratica dei casi di utilizzo descritti in precedenza.

## Do Not Target Once Converted {#do-not-target-once}

Assicurati che gli utenti che hanno già effettuato la conversione (acquistato un prodotto, acquisiscano un abbonamento, ecc.) siano non vedranno gli stessi messaggi di prima della conversione. You can obtain this using the [!UICONTROL AND NOT] logic, as follows.

1. Create a segment using two traits, and use the [!UICONTROL AND NOT] logic, as shown in the image below. È necessario utilizzare una caratteristica basata su regole per definire l'evento di conversione affinché il segmento venga attivato in tempo reale. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. Mappate il segmento su un numero qualsiasi di destinazioni server-to-server in tempo reale. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

I visitatori si qualificano per il segmento purché non siano stati convertiti. Non appena sono idonei per la caratteristica di conversione, cessano di seguire la regola del segmento e vengono immediatamente rimossi dal segmento.

![](assets/and_not_use_case.png)

## Do Not Target After x Impressions {#do-not-target-after-x}

Potete assicurarvi di non estendere gli utenti con gli stessi elementi creativi impostando i controlli di recency e frequenza. In questo scenario, crea un segmento con due caratteristiche, come descritto nella procedura seguente.

1. Create a segment using two traits, and use the [!UICONTROL AND] logic, as shown in the image below. Devi usare una caratteristica basata su regole per definire l'evento di impression affinché il segmento venga attivato in tempo reale. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >You can use [!UICONTROL Actionable Log Files] or [!UICONTROL Pixel Calls] to create traits based on user impressions. Read more about [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) and [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md).
1. Applicate controlli di frequenza alla seconda caratteristica. Se lo desideri, puoi anche aggiungere controlli di recency. Read more about [how to apply recency and frequency controls](../../features/segments/recency-and-frequency.md).
1. Mappate il segmento su un numero qualsiasi di destinazioni server-to-server in tempo reale. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

In questo scenario, dopo che gli utenti hanno accumulato più di tre impression, queste verranno rimosse da questo segmento e non saranno più visibili.

![](assets/impressions_use_case.png)

## Important Aspects to Note - Processing {#processing-notes}

Considerate questi aspetti relativi all'elaborazione:

* Per il corretto funzionamento della funzionalità di annullamento del segmento, devi mappare i segmenti desiderati in destinazioni server-to-server in tempo reale.
* For devices connected to a device by a [device graph](../../features/profile-merge-rules/profile-link-use-case.md#recommendations), we enforce a four-device limit regarding evaluation and unsegmentation. This limitation is described in [Device Graph Options and Device Unsegmentation](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).&#x200B;
* Il comando di annullamento del segmento verrà incluso in un file batch, inviato alle destinazioni ogni 24 ore, per più dispositivi collegati dal grafico del dispositivo.
* The device must be seen in real-time (on the [Edge](../../reference/system-components/components-edge.md)) to prompt segment evaluation. For traits that have a [!UICONTROL time-to-live (TTL)] value, even if a trait [!DNL TTL] is met, the device will *not* automatically be unsegmented until the device is next seen in real-time.&#x200B; Read more about how to [Set a Trait Expiration Interval](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* If you are using the [!UICONTROL DCS API] to on-board rule-based traits in real-time, you can trigger the unsegment with the use of the [!UICONTROL AND NOT] logic. Read more about [sending data to the DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).&#x200B;

## Important Aspects to Note - Timing {#timing-notes}

Considerate questi aspetti relativi alla temporizzazione:

* A segment will be stored on the [Edge](../../reference/system-components/components-edge.md) for the same time period as a device profile is stored on the [!UICONTROL Edge], namely 14 days since last real-time interaction. Read more about data retention in our [Data Retention FAQ](../../faq/faq-privacy.md#data-retention-faq).
* It takes approximately 24 hours for the unsegment operation to propagate across [!UICONTROL DCS] regions. Read more about our [!UICONTROL DCS] regions [here](../../reference/system-components/components-data-collection.md) and [here](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).