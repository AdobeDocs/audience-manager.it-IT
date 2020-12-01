---
description: La funzione di soppressione immediata su diversi dispositivi consente di eliminare gli utenti per i diversi dispositivi a cui sono associati, dopo il verificarsi di una specifica esperienza su uno di tali dispositivi. Questa funzione consente di fornire a un utente un’esperienza coerente su tutti i suoi dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.
seo-description: La funzione di soppressione immediata su diversi dispositivi consente di eliminare gli utenti per i diversi dispositivi a cui sono associati, dopo il verificarsi di una specifica esperienza su uno di tali dispositivi. Questa funzione consente di fornire a un utente un’esperienza coerente su tutti i suoi dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.
seo-title: Soppressione immediata su diversi dispositivi
title: Soppressione immediata su diversi dispositivi
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 15%

---


# Soppressione immediata su diversi dispositivi {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] è la capacità di sopprimere gli utenti tra più dispositivi collegati quando si verifica una particolare esperienza su uno di questi dispositivi. Utilizzate la funzionalità [!UICONTROL Instant Cross-Device Suppression] per offrire agli utenti un&#39;esperienza coerente su tutti i dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.

## Panoramica {#overview}

[!UICONTROL Instant Cross-Device Suppression] offre due casi d’uso chiave: migliore esperienza utente ed efficienza dei supporti.

* **Un&#39;esperienza** utente migliorata: Gli utenti che hanno già acquistato il prodotto o il servizio non vedranno le stesse creatività di prima dell&#39;acquisto. Al contrario, potresti visualizzare messaggi di upselling o cross-selling per prodotti o servizi che sai che non hanno acquistato.
* **Efficienza** dei supporti: Ottimizzate la spesa per le campagne applicando un limite di frequenza globale a tutti  [!DNL DSP]gli utenti. Il limite di frequenza può essere attivato in tempo reale per più dispositivi appartenenti a un utente.

I dettagli tecnici della segmentazione in tempo reale sono descritti in [Regole di unione dei profili e processi di rimozione della segmentazione del dispositivo](merge-rule-unsegment.md). Continua a leggere per l’implementazione pratica dei casi d’uso descritti in precedenza.

## Non eseguire il targeting una volta convertito {#do-not-target-once}

Assicuratevi che gli utenti che hanno già convertito (acquistato un prodotto, acquistato un abbonamento, ecc.) non verranno visualizzati gli stessi messaggi visualizzati prima della conversione. È possibile ottenere questo risultato utilizzando la logica [!UICONTROL AND NOT], come segue.

1. Create un segmento utilizzando due caratteristiche e utilizzate la logica [!UICONTROL AND NOT], come illustrato nell&#39;immagine seguente. È necessario utilizzare una caratteristica basata su regola per definire l&#39;evento di conversione per attivare il segmento in tempo reale. Ulteriori informazioni su come [creare caratteristiche basate su regola](../traits/create-onboarded-rule-based-traits.md).
2. Mappatura del segmento su un numero qualsiasi di destinazioni da server a server in tempo reale. Ulteriori informazioni su come aggiungere segmenti a [destinazioni da server a server](../destinations/add-edit-segments.md).

I visitatori possono partecipare al segmento a condizione che non siano stati convertiti. Non appena si qualificano per la caratteristica di conversione, cessano di seguire la regola del segmento e vengono immediatamente rimossi dal segmento.

![](assets/and_not_use_case.png)

## Non eseguire il targeting dopo x Impression {#do-not-target-after-x}

Potete evitare di invadere gli utenti con la stessa creatività impostando i controlli di aggiornamento e frequenza. In questo scenario, crea un segmento con due caratteristiche, come indicato nei passaggi indicati di seguito.

1. Create un segmento utilizzando due caratteristiche e utilizzate la logica [!UICONTROL AND], come illustrato nell&#39;immagine seguente. È necessario utilizzare una caratteristica basata su regola per definire l&#39;evento impression affinché il segmento venga attivato in tempo reale. Ulteriori informazioni su come [creare caratteristiche basate su regola](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >È possibile utilizzare [!UICONTROL Actionable Log Files] o [!UICONTROL Pixel Calls] per creare caratteristiche basate sulle impression dell&#39;utente. Ulteriori informazioni su [File di registro fruibili](../../integration/media-data-integration/actionable-log-files.md) e [Chiamate pixel](../../integration/media-data-integration/impression-data-pixels.md).
2. Applicare i controlli di frequenza al secondo tratto. Se lo desiderate, potete anche aggiungere controlli di aggiornamento. Leggi tutto su [come applicare i controlli di frequenza e di aggiornamento](../segments/recency-and-frequency.md).
3. Mappatura del segmento su un numero qualsiasi di destinazioni da server a server in tempo reale. Ulteriori informazioni su come aggiungere segmenti a [destinazioni da server a server](../destinations/add-edit-segments.md).

In questo scenario, una volta che gli utenti hanno accumulato più di tre impression, verranno rimosse da questo segmento e non visualizzeranno più questo particolare creativo.

![](assets/impressions_use_case.png)

## Aspetti importanti da notare - Elaborazione {#processing-notes}

Tenere presenti i seguenti aspetti relativi all’elaborazione:

* Per il funzionamento della funzionalità di unsegmento in tempo reale, devi mappare i segmenti desiderati su destinazioni in tempo reale da server a server.
* Per i dispositivi collegati a un dispositivo da un [grafico del dispositivo](profile-link-use-case.md#recommendations), viene applicato un limite di quattro dispositivi per quanto riguarda la valutazione e la segmentazione. Questa limitazione è descritta in [Opzioni di Device Graph e Separazione dispositivo](merge-rule-unsegment.md#device-graph-options-unsegmentation) &#x200B;.
* Il comando unsegment sarà incluso in un file batch, che viene inviato a destinazioni ogni 24 ore, per più dispositivi collegati dal grafico del dispositivo.
* Il dispositivo deve essere visualizzato in tempo reale (su [Edge](../../reference/system-components/components-edge.md) per richiedere la valutazione dei segmenti in tempo reale. Per le caratteristiche con un [!UICONTROL time-to-live (TTL)] quando la caratteristica [!DNL TTL] è soddisfatta, il dispositivo verrà automaticamente ssegmentato entro 24 ore tramite il file batch. &#x200B; Ulteriori informazioni su come [impostare un intervallo di scadenza caratteristica](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Se si utilizza [!UICONTROL DCS API] per caratteristiche basate su regola integrata in tempo reale, è possibile attivare il separatore utilizzando la logica [!UICONTROL AND NOT]. Ulteriori informazioni sull [invio di dati all&#39;API DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Aspetti importanti da notare - Tempo {#timing-notes}

Tenere presenti i seguenti aspetti relativi al calendario:

* Un segmento verrà memorizzato sul [Edge](../../reference/system-components/components-edge.md) per lo stesso periodo di tempo in cui un profilo dispositivo viene memorizzato sul [!UICONTROL Edge], ovvero 14 giorni dall&#39;ultima interazione in tempo reale. Per maggiori informazioni sulla conservazione dei dati, consulta le [Domande frequenti sulla conservazione dei dati](../../faq/faq-privacy.md#data-retention-faq).
* Occorrono circa 24 ore prima che l&#39;operazione di non segmento si propaghi tra [!DNL DCS] aree. Ulteriori informazioni sulle [!DNL DCS] regioni [qui](../..//reference/system-components/components-data-collection.md) e [qui](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
