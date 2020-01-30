---
description: Questa pagina include i problemi principali segnalati all'Assistenza clienti di Audience Manager.
seo-description: Questa pagina include i problemi principali segnalati all'Assistenza clienti di Audience Manager.
seo-title: Assistenza clienti - Problemi segnalati più di frequente
solution: Audience Manager
title: Assistenza clienti - Problemi segnalati più di frequente
translation-type: tm+mt
source-git-commit: f9d57da86b7e8962353b01b693a2359cade7b024

---


# Assistenza clienti - Problemi segnalati più di frequente{#most-frequent-issues}

Questa pagina include i principali problemi segnalati all’Assistenza clienti di Audience Manager nel 2019.

## Perché i nostri utenti di sola lettura possono creare, modificare o eliminare tratti e segmenti?

**domande**

Perché i nostri utenti di sola lettura possono creare, modificare o eliminare tratti e segmenti?

**Risposta**

Oltre a creare gruppi e autorizzazioni nella sezione Amministrazione, è necessario contattare l&#39;Assistenza clienti (amsupport@adobe.com) per consentire a un rappresentante di abilitare i controlli di accesso basati sul ruolo (RBAC) per il proprio account.

<br> 

## Perché la mia popolazione di tratti caricati su un tablet è scesa a 0 intorno al 15 ottobre? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Intorno al 14 ottobre 2019 ho notato che le popolazioni di caratteristiche registrate per il grafico ID dispositivo sono scese a 0, dove in precedenza erano molto più alte.

![Immagine del rilascio dell&#39;ID dispositivo](/help/using/support-issues/assets/device_id_populationdrop.png)

**Risposta**

Il 15 ottobre, è stato modificato un aggiornamento alla funzionalità Regola di unione dei profili di Audience Manager in cui i dati caricati da un ID CRM caricato su un&#39;origine dati multi-dispositivo non venivano più realizzati rispetto agli ID dispositivo.  In precedenza Audience Manager si stava realizzando sia con l&#39;ID multi-dispositivo (o CRM ID) che copiando tali realizzazioni sugli UUID Audience Manager associati (ID dispositivo).  La modifica è stata apportata per riflettere più accuratamente la natura dei dati sulle caratteristiche e i profili realizzati.

Per visualizzare le realizzazioni delle caratteristiche, seleziona l&#39;opzione &quot;ID multi-dispositivo&quot; dall&#39;elenco a discesa nell&#39;angolo superiore destro della vista Caratteristiche.

![Visualizzare le realizzazioni per ID multi-dispositivo](/help/using/support-issues/assets/deviceid-crossdevice.png)

<br> 

## Perché le caratteristiche o i segmenti non vengono visualizzati nella pagina Rapporti sovrapposizione?

Spiegazione del motivo per cui le caratteristiche e i segmenti potrebbero non essere visualizzati nella pagina Rapporti sovrapposizione.

**domande**

Perché gli utenti non vedono determinate caratteristiche e segmenti elencati nella pagina dei rapporti di sovrapposizione quando cercano di eseguire un rapporto di sovrapposizione?

**Risposta**

Affinché una caratteristica o un segmento siano elencati nei rapporti di sovrapposizione, è necessario soddisfare un requisito visitatore univoco minimo.


* Per caratteristiche: 28000 su un periodo di 14 giorni
* Per i segmenti: 70000 utenti in tempo reale su un periodo di 14 giorni

Maggiori dettagli su questo argomento sono disponibili nella pagina Campionamento [dati e tassi di errore nei report](/help/using/reporting/report-sampling.md)Audience Manager selezionati.