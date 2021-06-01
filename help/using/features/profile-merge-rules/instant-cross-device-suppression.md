---
description: La funzione di soppressione immediata su diversi dispositivi consente di eliminare gli utenti per i diversi dispositivi a cui sono associati, dopo il verificarsi di una specifica esperienza su uno di tali dispositivi. Questa funzione consente di fornire a un utente un’esperienza coerente su tutti i suoi dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.
seo-description: La funzione di soppressione immediata su diversi dispositivi consente di eliminare gli utenti per i diversi dispositivi a cui sono associati, dopo il verificarsi di una specifica esperienza su uno di tali dispositivi. Questa funzione consente di fornire a un utente un’esperienza coerente su tutti i suoi dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.
seo-title: Soppressione immediata su diversi dispositivi
title: Soppressione immediata su diversi dispositivi
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Unione profili
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# Soppressione immediata su diversi dispositivi {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] è la possibilità di eliminare gli utenti da più dispositivi a essi collegati quando si verifica una particolare esperienza su uno di questi dispositivi. Utilizza la funzionalità [!UICONTROL Instant Cross-Device Suppression] per fornire agli utenti un’esperienza coerente su tutti i dispositivi. Ciò è possibile grazie alle capacità di rimozione da un segmento in tempo reale di Audience Manager.

## Panoramica {#overview}

[!UICONTROL Instant Cross-Device Suppression] fornisce due casi d’uso chiave: migliore esperienza utente ed efficienza dei supporti.

* **Un’esperienza** utente migliorata: Gli utenti che hanno già acquistato il tuo prodotto o servizio non vedranno le stesse creatività di prima dell’acquisto. Puoi invece visualizzare messaggi di upselling o cross-selling per prodotti o servizi che sai che non hanno acquistato.
* **Efficienza** dei supporti: Ottimizza la spesa per le campagne applicando un limite di frequenza globale a tutti  [!DNL DSP]gli utenti. Il limite di frequenza può essere attivato in tempo reale per più dispositivi appartenenti a un utente.

I dettagli tecnici della rimozione dai segmenti in tempo reale sono descritti in [Regole di unione profili e Processi di rimozione dai segmenti del dispositivo](merge-rule-unsegment.md). Continua a leggere per l’implementazione pratica dei casi d’uso sopra descritti.

## Non eseguire il targeting una volta convertito {#do-not-target-once}

Assicurati che i tuoi utenti che hanno già convertito (acquisto di un prodotto, acquisto di un abbonamento, ecc.) non visualizzerà gli stessi messaggi di prima della conversione. Puoi ottenere questo risultato utilizzando la logica [!UICONTROL AND NOT] , come segue.

1. Crea un segmento utilizzando due caratteristiche e utilizza la logica [!UICONTROL AND NOT] , come illustrato di seguito. Devi utilizzare una caratteristica basata su regole per definire l’evento di conversione per l’attivazione in tempo reale dello ssegmento. Ulteriori informazioni su come [creare caratteristiche basate su regole](../traits/create-onboarded-rule-based-traits.md).
2. Mappa il segmento su un numero qualsiasi di destinazioni server-to-server in tempo reale. Ulteriori informazioni su come aggiungere segmenti alle [destinazioni server-to-server](../destinations/add-edit-segments.md).

I visitatori possono qualificarsi per il segmento purché non siano stati convertiti. Non appena si qualificano per la caratteristica di conversione, smettono di seguire la regola del segmento e vengono immediatamente rimossi dal segmento.

![](assets/and_not_use_case.png)

## Non eseguire il targeting dopo x impressioni {#do-not-target-after-x}

Puoi evitare di inondare gli utenti con lo stesso creativo impostando i controlli di aggiornamento e frequenza. In questo scenario, crea un segmento con due caratteristiche, come descritto nei passaggi seguenti.

1. Crea un segmento utilizzando due caratteristiche e utilizza la logica [!UICONTROL AND] , come illustrato di seguito. Devi utilizzare una caratteristica basata su regole per definire l’evento impression per l’attivazione in tempo reale dello ssegmento. Ulteriori informazioni su come [creare caratteristiche basate su regole](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Puoi utilizzare [!UICONTROL Actionable Log Files] o [!UICONTROL Pixel Calls] per creare caratteristiche in base alle impression utente. Ulteriori informazioni su [File di registro fruibili](../../integration/media-data-integration/actionable-log-files.md) e [Chiamate pixel](../../integration/media-data-integration/impression-data-pixels.md).
2. Applica i controlli di frequenza alla seconda caratteristica. Se lo desideri, puoi aggiungere anche i controlli di aggiornamento. Ulteriori informazioni su [come applicare i controlli di aggiornamento e frequenza](../segments/recency-and-frequency.md).
3. Mappa il segmento su un numero qualsiasi di destinazioni server-to-server in tempo reale. Ulteriori informazioni su come aggiungere segmenti alle [destinazioni server-to-server](../destinations/add-edit-segments.md).

In questo scenario, dopo che gli utenti hanno accumulato più di tre impression, verranno rimossi da questo segmento e non visualizzeranno più questo particolare contenuto creativo.

![](assets/impressions_use_case.png)

## Aspetti importanti da notare - Elaborazione {#processing-notes}

Tieni presente i seguenti aspetti relativi all’elaborazione:

* Affinché la funzionalità di rimozione dai segmenti in tempo reale funzioni, devi mappare i segmenti desiderati su destinazioni in tempo reale da server a server.
* Per i dispositivi collegati a un dispositivo da un [grafico dei dispositivi](profile-link-use-case.md#recommendations), viene applicato un limite di quattro dispositivi per quanto riguarda la valutazione e la rimozione dai segmenti. Questa limitazione è descritta in [Opzioni grafico dei dispositivi e rimozione dai segmenti dei dispositivi](merge-rule-unsegment.md#device-graph-options-unsegmentation) &#x200B;
* Il comando di rimozione dai segmenti sarà incluso in un file batch, che viene inviato a destinazioni ogni 24 ore, per più dispositivi collegati dal grafico del dispositivo.
* Il dispositivo deve essere visualizzato in tempo reale (su [Edge](../../reference/system-components/components-edge.md) per richiedere la valutazione dei segmenti in tempo reale. Per le caratteristiche che hanno un [!UICONTROL time-to-live (TTL)] quando la caratteristica [!DNL TTL] è soddisfatta, il dispositivo verrà automaticamente ssegmentato entro 24 ore tramite il file batch. &#x200B; Ulteriori informazioni su come [impostare un intervallo di scadenza delle caratteristiche](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Se utilizzi [!UICONTROL DCS API] per le caratteristiche basate su regole di bordo in tempo reale, puoi attivare la rimozione dai segmenti utilizzando la logica [!UICONTROL AND NOT] . Ulteriori informazioni sull&#39; [invio di dati all&#39;API DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Aspetti importanti da notare - Tempi {#timing-notes}

Tenete a mente questi aspetti relativi alla tempistica:

* Un segmento verrà memorizzato sul [Edge](../../reference/system-components/components-edge.md) per lo stesso periodo di tempo in cui un profilo dispositivo viene memorizzato sul [!UICONTROL Edge], ovvero 14 giorni dall&#39;ultima interazione in tempo reale. Ulteriori informazioni sulla conservazione dei dati sono disponibili nelle nostre [Domande frequenti sulla conservazione dei dati](../../faq/faq-privacy.md#data-retention-faq).
* Ci vogliono circa 24 ore perché l&#39;operazione di rimozione dai segmenti si propaghi tra [!DNL DCS] aree geografiche. Ulteriori informazioni sulle [!DNL DCS] aree [qui](../..//reference/system-components/components-data-collection.md) e [qui](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
