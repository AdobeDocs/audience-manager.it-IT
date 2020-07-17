---
description: Metodi DELETE e POST che consentono di rimuovere destinazioni e mappature segmenti.
seo-description: Metodi DELETE e POST che consentono di rimuovere destinazioni e mappature segmenti.
seo-title: Eliminare destinazioni
solution: Audience Manager
title: Eliminare destinazioni
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 7%

---


# Eliminare destinazioni {#delete-destinations}

`DELETE` e `POST` metodi che consentono di rimuovere le destinazioni e le mappature dei segmenti.

<!-- r_delete_destinations_all.xml -->

## Eliminazione di una destinazione

Un `DELETE` metodo che rimuove una destinazione.

>[!NOTE]
>
>È necessario rimuovere tutte le mappature dei segmenti prima di poter eliminare una destinazione.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.

## Destinazioni di eliminazione in blocco

Rimuovete più destinazioni con questo `POST` metodo. Trasmettere gli ID di destinazione ( `destinationId`) con un array nel corpo della richiesta.

* Richiesta: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.

## Elimina mappature di destinazione per ID mappatura segmento

Un `POST` metodo che rimuove le mappature di destinazione in base all&#39;ID segmento specificato.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.