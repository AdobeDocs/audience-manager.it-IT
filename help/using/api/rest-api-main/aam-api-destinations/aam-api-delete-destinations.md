---
description: Metodi DELETE e POST che consentono di rimuovere destinazioni e mappature segmenti.
seo-description: Metodi DELETE e POST che consentono di rimuovere destinazioni e mappature segmenti.
seo-title: Elimina destinazioni
solution: Audience Manager
title: Elimina destinazioni
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Elimina destinazioni {#delete-destinations}

`DELETE` e `POST` metodi che consentono di rimuovere destinazioni e mappature segmenti.

<!-- r_delete_destinations_all.xml -->

## Eliminazione di una destinazione

Un `DELETE` metodo che rimuove una destinazione.

>[!NOTE]
>
>È necessario rimuovere tutte le mappature dei segmenti prima di poter eliminare una destinazione.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.

## Destinazioni di eliminazione in blocco

Rimuovete più destinazioni con questo `POST` metodo. Trasmettere gli ID di destinazione ( `destinationId`) con un array nel corpo della richiesta.

* Richiesta: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.

## Elimina mappature di destinazione per ID mappatura segmento

Un `POST` metodo che rimuove le mappature di destinazione in base all'ID segmento specificato.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.