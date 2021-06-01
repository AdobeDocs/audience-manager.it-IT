---
description: Metodi di DELETE e POST che consentono di rimuovere destinazioni e mappature dei segmenti.
seo-description: Metodi di DELETE e POST che consentono di rimuovere destinazioni e mappature dei segmenti.
seo-title: Eliminare destinazioni
solution: Audience Manager
title: Eliminare destinazioni
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 8%

---

# Eliminare destinazioni {#delete-destinations}

`DELETE` e  `POST` metodi che consentono di rimuovere destinazioni e mappature dei segmenti.

<!-- r_delete_destinations_all.xml -->

## Eliminare una destinazione

Un metodo `DELETE` che rimuove una destinazione.

>[!NOTE]
>
>È necessario rimuovere tutte le mappature dei segmenti prima di poter eliminare una destinazione.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.

## Eliminare in blocco le destinazioni

Rimuovi più destinazioni con questo metodo `POST` . Passa gli ID di destinazione ( `destinationId`) con una matrice nel corpo della richiesta.

* Richiesta: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.

## Eliminare le mappature di destinazione per ID mappatura segmento

Un metodo `POST` che rimuove le mappature di destinazione in base all’ID del segmento specificato.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Risposta: Restituisce il codice `204 No Content` in caso di esito positivo.
