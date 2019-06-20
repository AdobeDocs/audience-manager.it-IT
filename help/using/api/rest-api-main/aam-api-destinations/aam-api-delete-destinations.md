---
description: I metodi DELETE e POST consentono di rimuovere le destinazioni e le mappature dei segmenti.
seo-description: I metodi DELETE e POST consentono di rimuovere le destinazioni e le mappature dei segmenti.
seo-title: Elimina destinazioni
solution: Audience Manager
title: Elimina destinazioni
uuid: 38 fb 2228-e 564-49 a 3-9930-3139 f 8799 a 8 f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Elimina destinazioni {#delete-destinations}

`DELETE` e `POST` metodi che consentono di rimuovere le destinazioni e le mappature dei segmenti.

<!-- r_delete_destinations_all.xml -->

## Eliminare una destinazione

`DELETE` Metodo che rimuove una destinazione.

>[!NOTE]
>
>Devi rimuovere tutte le mappature dei segmenti prima di poter eliminare una destinazione.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.

## Destinazioni di eliminazione in blocco

Rimuovere più destinazioni con questo `POST` metodo. Passa gli ID di destinazione ( `destinationId`) con un array nel corpo della richiesta.

* Richiesta: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.

## Elimina mappature di destinazione per ID mappatura segmento

`POST` Un metodo che rimuove le mappature di destinazione in base all&#39;ID del segmento specificato.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/segments/`*`<mappingId>`*
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.