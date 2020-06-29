---
description: Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando Segment Builder (Generatore di segmenti).
seo-description: Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando Segment Builder (Generatore di segmenti).
seo-title: Segmenti in pausa ed eliminati
solution: Audience Manager
title: Segmenti in pausa ed eliminati
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Segmenti in pausa ed eliminati {#paused-and-deleted-segments}

Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando [!UICONTROL Segment Builder].

## Accesso ai controlli Pausa ed Elimina

Passa il cursore del mouse sul nome di un segmento nell’elenco dei segmenti per visualizzare le **[!UICONTROL pause]** icone e **[!UICONTROL delete]** (nella [!UICONTROL Actions] colonna). Queste funzioni interessano i segmenti come descritto di seguito.

## Funzionalità Segmento In Pausa

Segmento in pausa (disattivato):

* Interrompe la segmentazione di nuovi utenti qualificati.
* Mantiene lo stato/l&#39;appartenenza di segmentazione di un utente (non rimuove un utente dal segmento).
* Resta nell’elenco dei segmenti e può essere riattivato.
* Non invia dati alle destinazioni associate.
* Restituisce i dati nei rapporti disponibili (fino alla data di disattivazione).

## Funzionalità segmento eliminata

Segmento eliminato:

* Interrompe la segmentazione di nuovi utenti qualificati.
* Rimuove gli utenti qualificati dall&#39;appartenenza al segmento.
* Viene rimosso dall&#39;elenco dei segmenti.
* Impossibile annullare l&#39;eliminazione.
* Non invia dati alle destinazioni associate.
* Non restituisce i dati nei rapporti disponibili.

>[!NOTE]
>
>Puoi anche mettere in pausa ed eliminare i segmenti utilizzando un [!DNL API] metodo. Per ulteriori informazioni, consultate API [REST](../../api/rest-api-main/rest-api-main.md).