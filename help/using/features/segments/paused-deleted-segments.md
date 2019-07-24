---
description: Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando Generatore segmenti.
seo-description: Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando Generatore segmenti.
seo-title: Segmenti in pausa ed eliminati
solution: Audience Manager
title: Segmenti in pausa ed eliminati
uuid: 88 efe 4 af-f 9 a 4-4 postal -920 a -352 bd 4 d 505 dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Paused and Deleted Segments {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using [!UICONTROL Segment Builder].

## Accesso ai controlli Pausa ed Elimina

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the [!UICONTROL Actions] column). Queste funzioni interessano i segmenti come descritto di seguito.

## Funzionalità segmento in pausa

Un segmento messo in pausa (disattivato):

* Interrompe la segmentazione di utenti nuovi e idonei.
* Mantiene lo stato di segmentazione/appartenenza di un utente (non rimuove un utente dal segmento).
* Resta nell'elenco dei segmenti e può essere riattivato.
* Non invia dati alle destinazioni associate.
* Restituisce i dati nei rapporti disponibili (fino alla data di disattivazione).

## Funzionalità segmento eliminato

Un segmento eliminato:

* Interrompe la segmentazione di utenti nuovi e idonei.
* Rimuove gli utenti qualificati dall'appartenenza al segmento.
* Viene rimosso dall'elenco dei segmenti.
* Non è possibile annullare l'eliminazione.
* Non invia dati alle destinazioni associate.
* Non restituisce dati nei rapporti disponibili.

>[!NOTE]
>
>You can also pause and delete segments using an [!DNL API] method. For more information, see [REST APIs](../../api/rest-api-main/rest-api-main.md).