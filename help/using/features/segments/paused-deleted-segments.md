---
description: Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando il Generatore di segmenti.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Segmenti in pausa ed eliminati
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
TQID: https://experienceleague.adobe.com/aLnmaOxB3fkGdwq4XjKz8SFKizwHI7Ll5rBUb-o34BM
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2: id: c2c33729-f309-4bc2-92ba-87c475259df3
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 0%

---

# Segmenti in pausa ed eliminati {#paused-and-deleted-segments}

Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando [!UICONTROL Segment Builder].

## Accesso ai controlli di pausa ed eliminazione

Passa il puntatore del mouse sul nome di un segmento nell&#39;elenco dei segmenti per esporre le icone **[!UICONTROL pause]** e **[!UICONTROL delete]** (nella colonna [!UICONTROL Actions]). Queste funzioni influiscono sui segmenti come descritto di seguito.

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
>È inoltre possibile sospendere ed eliminare segmenti utilizzando un metodo [!DNL API]. Per ulteriori informazioni, vedere [API REST](../../api/rest-api-main/rest-api-main.md).
