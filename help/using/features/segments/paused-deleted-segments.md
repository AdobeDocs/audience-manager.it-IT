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


# Segmenti in pausa ed eliminati {#paused-and-deleted-segments}

Descrive gli effetti su utenti, dati e destinazioni segmentati quando si mette in pausa o si elimina un segmento attivo utilizzando [!UICONTROL Segment Builder].

## Accesso ai controlli Pausa ed Elimina

Passa il cursore sul nome di un segmento nell&#39;elenco dei segmenti per esporre le **[!UICONTROL pause]****[!UICONTROL delete]** icone (nella [!UICONTROL Actions] colonna). Queste funzioni interessano i segmenti come descritto di seguito.

## Funzionalità segmento in pausa

Un segmento messo in pausa (disattivato):

* Interrompe la segmentazione di utenti nuovi e idonei.
* Mantiene lo stato di segmentazione/appartenenza di un utente (non rimuove un utente dal segmento).
* Resta nell&#39;elenco dei segmenti e può essere riattivato.
* Non invia dati alle destinazioni associate.
* Restituisce i dati nei rapporti disponibili (fino alla data di disattivazione).

## Funzionalità segmento eliminato

Un segmento eliminato:

* Interrompe la segmentazione di utenti nuovi e idonei.
* Rimuove gli utenti qualificati dall&#39;appartenenza al segmento.
* Viene rimosso dall&#39;elenco dei segmenti.
* Non è possibile annullare l&#39;eliminazione.
* Non invia dati alle destinazioni associate.
* Non restituisce dati nei rapporti disponibili.

>[!NOTE]
>
>È inoltre possibile mettere in pausa ed eliminare i segmenti utilizzando un [!DNL API] metodo. Per ulteriori informazioni, consultate [API REST](../../api/rest-api-main/rest-api-main.md).