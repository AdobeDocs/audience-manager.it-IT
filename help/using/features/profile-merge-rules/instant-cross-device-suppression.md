---
description: La funzione di soppressione immediata su diversi dispositivi consente di eliminare gli utenti per i diversi dispositivi a cui sono associati, dopo il verificarsi di una specifica esperienza su uno di tali dispositivi. Questa funzione consente di fornire a un utente un’esperienza coerente su tutti i suoi dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.
seo-description: La funzione di soppressione immediata su diversi dispositivi consente di eliminare gli utenti per i diversi dispositivi a cui sono associati, dopo il verificarsi di una specifica esperienza su uno di tali dispositivi. Questa funzione consente di fornire a un utente un’esperienza coerente su tutti i suoi dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.
seo-title: Soppressione immediata su diversi dispositivi
title: Soppressione immediata su diversi dispositivi
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Soppressione immediata su diversi dispositivi {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] è la capacità di sopprimere gli utenti tra più dispositivi collegati quando si verifica una particolare esperienza su uno di questi dispositivi. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.

## Panoramica {#overview}

[!UICONTROL Instant Cross-Device Suppression] offre due casi d’uso chiave: migliore esperienza utente ed efficienza dei supporti.

* **Un'esperienza** utente migliorata: Gli utenti che hanno già acquistato il prodotto o il servizio non vedranno le stesse creatività di prima dell'acquisto. Al contrario, potresti visualizzare messaggi di upselling o cross-selling per prodotti o servizi che sai che non hanno acquistato.
* **Efficienza** dei supporti: Ottimizzate la spesa per le campagne applicando un limite di frequenza globale a tutti [!DNL DSP]gli utenti. Il limite di frequenza può essere attivato in tempo reale per più dispositivi appartenenti a un utente.

I dettagli tecnici della segmentazione in tempo reale sono descritti in lunghezza nelle regole di unione dei [profili e nei processi](merge-rule-unsegment.md)di annullamento della segmentazione del dispositivo. Continua a leggere per l’implementazione pratica dei casi d’uso sopra descritti.

## Non eseguire il targeting una volta convertito {#do-not-target-once}

Assicuratevi che gli utenti che hanno già convertito (acquistato un prodotto, acquistato un abbonamento, ecc.) non verranno visualizzati gli stessi messaggi visualizzati prima della conversione. Potete ottenere questo utilizzando la [!UICONTROL AND NOT] logica, come segue.

1. Crea un segmento utilizzando due caratteristiche e utilizza la [!UICONTROL AND NOT] logica, come illustrato nell'immagine seguente. È necessario utilizzare una caratteristica basata su regola per definire l'evento di conversione per attivare il segmento in tempo reale. Ulteriori informazioni sulla [creazione di caratteristiche](../traits/create-onboarded-rule-based-traits.md)basate su regole.
2. Mappatura del segmento su un numero qualsiasi di destinazioni da server a server in tempo reale. Ulteriori informazioni su come aggiungere segmenti alle destinazioni [da](../destinations/add-edit-segments.md)server a server.

I visitatori possono partecipare al segmento a condizione che non siano stati convertiti. Non appena si qualificano per la caratteristica di conversione, cessano di seguire la regola del segmento e vengono immediatamente rimossi dal segmento.

![](assets/and_not_use_case.png)

## Non eseguire il targeting dopo x Impression {#do-not-target-after-x}

Potete evitare di invadere gli utenti con la stessa creatività impostando controlli di aggiornamento e frequenza. In questo scenario, crea un segmento con due caratteristiche, come indicato nei passaggi sottostanti.

1. Crea un segmento utilizzando due caratteristiche e utilizza la [!UICONTROL AND] logica, come illustrato nell'immagine seguente. È necessario utilizzare una caratteristica basata su regola per definire l'evento impression affinché il segmento venga attivato in tempo reale. Ulteriori informazioni sulla [creazione di caratteristiche](../traits/create-onboarded-rule-based-traits.md)basate su regole.
   >[!NOTE]
   >
   >Potete usare [!UICONTROL Actionable Log Files] o [!UICONTROL Pixel Calls] creare caratteristiche basate sulle impression dell’utente. Ulteriori informazioni sui file di registro [fruibili](../../integration/media-data-integration/actionable-log-files.md) e sulle chiamate [pixel](../../integration/media-data-integration/impression-data-pixels.md).
2. Applicare i controlli di frequenza al secondo tratto. Se lo desiderate, potete anche aggiungere controlli di aggiornamento. Ulteriori informazioni su [come applicare i controlli](../segments/recency-and-frequency.md)di aggiornamento e frequenza.
3. Mappatura del segmento su un numero qualsiasi di destinazioni da server a server in tempo reale. Ulteriori informazioni su come aggiungere segmenti alle destinazioni [da](../destinations/add-edit-segments.md)server a server.

In questo scenario, una volta che gli utenti hanno accumulato più di tre impression, verranno rimosse da questo segmento e non visualizzeranno più questo particolare creativo.

![](assets/impressions_use_case.png)

## Aspetti importanti per le note - Elaborazione {#processing-notes}

Tenere presenti i seguenti aspetti relativi all’elaborazione:

* Per il funzionamento della funzionalità di unsegmento in tempo reale, devi mappare i segmenti desiderati su destinazioni in tempo reale da server a server.
* Per i dispositivi collegati a un dispositivo tramite un grafico [di](profile-link-use-case.md#recommendations)dispositivi, viene applicato un limite di quattro dispositivi per quanto riguarda la valutazione e la segmentazione. Questa limitazione è descritta in Opzioni [Device Graph e Separazione](merge-rule-unsegment.md#device-graph-options-unsegmentation)dispositivo. &#x200B;
* Il comando unsegment sarà incluso in un file batch, che viene inviato a destinazioni ogni 24 ore, per più dispositivi collegati dal grafico del dispositivo.
* Il dispositivo deve essere visualizzato in tempo reale (su [Edge](../../reference/system-components/components-edge.md) ) per richiedere la valutazione dei segmenti in tempo reale. Per le caratteristiche che hanno un [!UICONTROL time-to-live (TTL)] quando la caratteristica [!DNL TTL] è soddisfatta, il dispositivo verrà automaticamente ssegmentato entro 24 ore tramite il file batch.. &#x200B; Ulteriori informazioni su come [impostare un intervallo](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)di scadenza delle caratteristiche.
* Se utilizzate le caratteristiche [!UICONTROL DCS API] per le quali è presente una regola in tempo reale, potete attivare il separatore utilizzando la [!UICONTROL AND NOT] logica. Ulteriori informazioni sull' [invio di dati all'API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)DCS. &#x200B;

## Aspetti importanti da notare - Timeout {#timing-notes}

Tenere presenti i seguenti aspetti relativi al calendario:

* Un segmento verrà memorizzato sul [bordo](../../reference/system-components/components-edge.md) [!UICONTROL Edge]per lo stesso periodo di tempo in cui è memorizzato un profilo dispositivo, ovvero 14 giorni dall'ultima interazione in tempo reale. Per maggiori informazioni sulla conservazione dei dati, consulta le nostre Domande frequenti sulla conservazione [dei dati](../../faq/faq-privacy.md#data-retention-faq).
* Occorrono circa 24 ore prima che l'operazione di dissegmento si propaghi tra [!UICONTROL DCS] le regioni. Ulteriori informazioni sulle nostre [!UICONTROL DCS] regioni [qui](../..//reference/system-components/components-data-collection.md) e [qui](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
