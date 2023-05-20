---
description: Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando il Generatore di segmenti.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Segmenti in pausa ed eliminati
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 4%

---

# Segmenti in pausa ed eliminati {#paused-and-deleted-segments}

Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando [!UICONTROL Segment Builder].

## Accesso ai controlli di pausa ed eliminazione

Passa il puntatore del mouse sul nome di un segmento nell’elenco dei segmenti per esporre **[!UICONTROL pause]** e **[!UICONTROL delete]** icone (nella [!UICONTROL Actions] colonna). Queste funzioni influiscono sui segmenti come descritto di seguito.

## Funzionalità del segmento in pausa

Un segmento in pausa (disattivato):

* Interrompe la segmentazione di utenti nuovi e qualificati.
* Mantiene lo stato di segmentazione/appartenenza di un utente (non rimuove un utente dal segmento).
* Rimane nell’elenco dei segmenti e può essere riattivato.
* Non invia dati alle destinazioni associate.
* Restituisce i dati nei rapporti disponibili (fino alla data di disattivazione).

## Funzionalità del segmento eliminato

Un segmento eliminato:

* Interrompe la segmentazione di utenti nuovi e qualificati.
* Rimuove gli utenti qualificati dall’iscrizione al segmento.
* Viene rimosso dall’elenco dei segmenti.
* Impossibile annullare l’eliminazione.
* Non invia dati alle destinazioni associate.
* Non restituisce i dati nei rapporti disponibili.

>[!NOTE]
>
>Puoi anche mettere in pausa ed eliminare i segmenti utilizzando una [!DNL API] metodo. Per ulteriori informazioni, consulta [API REST](../../api/rest-api-main/rest-api-main.md).
