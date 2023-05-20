---
description: Metodi DELETE e POST che consentono di rimuovere destinazioni e mappature di segmenti.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Eliminare destinazioni
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 6%

---

# Eliminare destinazioni {#delete-destinations}

`DELETE` e `POST` metodi che consentono di rimuovere destinazioni e mappature di segmenti.

<!-- r_delete_destinations_all.xml -->

## Eliminare una destinazione

A `DELETE` metodo che rimuove una destinazione.

>[!NOTE]
>
>Per eliminare una destinazione, è necessario rimuovere tutte le mappature dei segmenti.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Risposta: restituisce il codice `204 No Content` in caso di esito positivo.

## Destinazioni di eliminazione in blocco

Rimuovi più destinazioni con questo `POST` metodo. Passa gli ID di destinazione ( `destinationId`) con un array nel corpo della richiesta.

* Richiesta: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Risposta: restituisce il codice `204 No Content` in caso di esito positivo.

## Eliminare le mappature di destinazione per ID di mappatura segmento

A `POST` metodo che rimuove le mappature di destinazione in base all’ID segmento specificato.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Risposta: restituisce il codice `204 No Content` in caso di esito positivo.
