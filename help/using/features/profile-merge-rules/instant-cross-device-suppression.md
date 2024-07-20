---
description: La funzione di soppressione immediata su diversi dispositivi consente di eliminare gli utenti per i diversi dispositivi a cui sono associati, dopo il verificarsi di una specifica esperienza su uno di tali dispositivi. Utilizza la funzionalità di eliminazione immediata tra dispositivi per offrire agli utenti un’esperienza coerente su tutti i dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Soppressione immediata su diversi dispositivi
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 6%

---

# Soppressione immediata su diversi dispositivi {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] è la capacità di eliminare gli utenti su più dispositivi ad essi connessi quando si verifica una particolare esperienza su uno qualsiasi di questi dispositivi. Utilizza la funzionalità [!UICONTROL Instant Cross-Device Suppression] per fornire agli utenti un&#39;esperienza coerente su tutti i dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.

## Panoramica {#overview}

[!UICONTROL Instant Cross-Device Suppression] offre due casi d&#39;uso chiave: migliore esperienza utente ed efficienza dei supporti.

* **Esperienza utente migliorata**: gli utenti che hanno già acquistato il prodotto o il servizio non vedranno le stesse creative di prima dell&#39;acquisto. Puoi invece visualizzare messaggi di vendita a prezzo maggiorato o messaggi di cross-selling per prodotti o servizi che sai che non hanno acquistato.
* **Efficienza dei contenuti multimediali**: ottimizza la spesa della campagna applicando un limite di frequenza globale su tutti i [!DNL DSP]. Il limite di frequenza può essere azionato in tempo reale per più dispositivi appartenenti a un utente.

I dettagli tecnici della rimozione dai segmenti in tempo reale sono descritti in lunghezza in [Profile Merge Rules and Device Un-Segmentation Processes](merge-rule-unsegment.md). Ulteriori informazioni sull’attuazione pratica dei casi d’uso descritti in precedenza.

## Non eseguire il targeting dopo la conversione {#do-not-target-once}

Assicurati che gli utenti che hanno già convertito (acquistato un prodotto, acquistato un abbonamento, ecc.) non visualizzerà gli stessi messaggi visualizzati prima della conversione. È possibile ottenere questo risultato utilizzando la logica [!UICONTROL AND NOT], come segue.

1. Creare un segmento utilizzando due caratteristiche e utilizzare la logica [!UICONTROL AND NOT], come illustrato nell&#39;immagine seguente. È necessario utilizzare una caratteristica basata su regole per definire l’evento di conversione per l’attivazione in tempo reale della rimozione dai segmenti. Ulteriori informazioni su come [creare caratteristiche basate su regole](../traits/create-onboarded-rule-based-traits.md).
2. Mappa il segmento a un numero qualsiasi di destinazioni in tempo reale da server a server. Scopri come aggiungere segmenti a [destinazioni da server a server](../destinations/add-edit-segments.md).

I visitatori sono idonei per il segmento finché non sono stati convertiti. Non appena si qualificano per la caratteristica di conversione, cessano di seguire la regola del segmento e vengono rimossi istantaneamente dal segmento.

![](assets/and_not_use_case.png)

## Non eseguire il targeting dopo x impression {#do-not-target-after-x}

Per evitare di invadere gli utenti con la stessa creatività, è possibile impostare i controlli di frequenza e recency. In questo scenario, crea un segmento con due caratteristiche, come descritto nei passaggi seguenti.

1. Creare un segmento utilizzando due caratteristiche e utilizzare la logica [!UICONTROL AND], come illustrato nell&#39;immagine seguente. Devi utilizzare una caratteristica basata su regole per definire l’evento di impression per l’attivazione in tempo reale della rimozione da un segmento. Ulteriori informazioni su come [creare caratteristiche basate su regole](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >È possibile utilizzare [!UICONTROL Actionable Log Files] o [!UICONTROL Pixel Calls] per creare caratteristiche basate sulle impressioni degli utenti. Ulteriori informazioni su [File di registro fruibili](../../integration/media-data-integration/actionable-log-files.md) e [Chiamate pixel](../../integration/media-data-integration/impression-data-pixels.md).
2. Applica i controlli di frequenza alla seconda caratteristica. Se lo si desidera, è possibile aggiungere anche i controlli di aggiornamento. Ulteriori informazioni su [come applicare i controlli di aggiornamento e frequenza](../segments/recency-and-frequency.md).
3. Mappa il segmento a un numero qualsiasi di destinazioni in tempo reale da server a server. Scopri come aggiungere segmenti a [destinazioni da server a server](../destinations/add-edit-segments.md).

In questo scenario, una volta che gli utenti hanno accumulato più di tre impression, verranno rimossi da questo segmento e non vedranno più questo particolare contenuto creativo.

![](assets/impressions_use_case.png)

## Aspetti importanti da considerare: elaborazione {#processing-notes}

Tieni presente questi aspetti relativi all’elaborazione:

* Affinché la funzionalità di rimozione dai segmenti in tempo reale funzioni, è necessario mappare i segmenti desiderati su destinazioni server-to-server in tempo reale.
* Per i dispositivi connessi a un dispositivo da un [grafo di dispositivi](profile-link-use-case.md#recommendations), viene applicato un limite di quattro dispositivi per quanto riguarda la valutazione e la rimozione dai segmenti. Questa limitazione è descritta in [Opzioni del grafico dei dispositivi e rimozione dei dispositivi](merge-rule-unsegment.md#device-graph-options-unsegmentation).&#x200B;
* Il comando di rimozione dai segmenti verrà incluso in un file batch, inviato alle destinazioni ogni 24 ore, per più dispositivi connessi dal grafico dei dispositivi.
* Il dispositivo deve essere visualizzato in tempo reale (su [Edge](../../reference/system-components/components-edge.md) per richiedere la valutazione del segmento in tempo reale. Per le caratteristiche con [!UICONTROL time-to-live (TTL)] quando la caratteristica [!DNL TTL] viene soddisfatta, il dispositivo verrà automaticamente rimosso dal segmento entro 24 ore tramite il file batch..&#x200B; Ulteriori informazioni su come [impostare un intervallo di scadenza delle caratteristiche](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Se utilizzi [!UICONTROL DCS API] per integrare le caratteristiche basate su regole in tempo reale, puoi attivare la rimozione dai segmenti utilizzando la logica [!UICONTROL AND NOT]. Ulteriori informazioni sull&#39;invio di [dati all&#39;API DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).&#x200B;

## Aspetti importanti da considerare - Tempistica {#timing-notes}

Considera questi aspetti relativi alla tempistica:

* Un segmento verrà archiviato in [Edge](../../reference/system-components/components-edge.md) per lo stesso periodo di tempo in cui un profilo dispositivo viene archiviato in [!UICONTROL Edge], ovvero 14 giorni dall&#39;ultima interazione in tempo reale. Ulteriori informazioni sulla conservazione dei dati nelle [Domande frequenti sulla conservazione dei dati](../../faq/faq-privacy.md#data-retention-faq).
* La propagazione dell&#39;operazione di rimozione dai segmenti su [!DNL DCS] aree geografiche richiede circa 24 ore. Ulteriori informazioni sulle [!DNL DCS] aree geografiche [qui](../../reference/system-components/components-data-collection.md) e [qui](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
