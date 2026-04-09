---
description: Metodi DELETE e POST che consentono di rimuovere destinazioni e mappature di segmenti.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Elimina destinazioni
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
TQID: https://experienceleague.adobe.com/hONQoLCrSxcMnDY7yPf-RX22Etj3WIykBhKEx1IyRMo
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 104
ht-degree: 0%

---

# Elimina destinazioni {#delete-destinations}

Metodi `DELETE` e `POST` che consentono di rimuovere destinazioni e mappature di segmenti.

<!-- r_delete_destinations_all.xml -->

## Eliminare una destinazione

Metodo `DELETE` che rimuove una destinazione.

>[!NOTE]
>
>Per eliminare una destinazione, è necessario rimuovere tutte le mappature dei segmenti.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Risposta: in caso di esito positivo, restituisce il codice `204 No Content`.

## Destinazioni di eliminazione in blocco

Rimuovere più destinazioni con questo metodo `POST`. Passa gli ID di destinazione ( `destinationId`) con un array nel corpo della richiesta.

* Richiesta: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Risposta: in caso di esito positivo, restituisce il codice `204 No Content`.

## Eliminare le mappature di destinazione per ID di mappatura segmento

Metodo `POST` che rimuove i mapping di destinazione in base all&#39;ID segmento specificato.

* Richiesta: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Risposta: in caso di esito positivo, restituisce il codice `204 No Content`.
