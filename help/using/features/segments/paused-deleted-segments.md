---
description: Descrive gli effetti su utenti, dati e destinazioni segmentati quando metti in pausa o elimini un segmento attivo utilizzando Segment Builder (Generatore di segmenti).
seo-description: Descrive gli effetti su utenti, dati e destinazioni segmentati quando metti in pausa o elimini un segmento attivo utilizzando Segment Builder (Generatore di segmenti).
seo-title: Segmenti in pausa ed eliminati
solution: Audience Manager
title: Segmenti in pausa ed eliminati
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: 'Segmenti '
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 6%

---

# Segmenti in pausa ed eliminati {#paused-and-deleted-segments}

Descrive gli effetti su utenti, dati e destinazioni segmentati quando metti in pausa o elimini un segmento attivo utilizzando [!UICONTROL Segment Builder].

## Accesso ai controlli Pausa ed Elimina

Passa il puntatore del mouse sul nome di un segmento nell’elenco dei segmenti per esporre le icone **[!UICONTROL pause]** e **[!UICONTROL delete]** (nella colonna [!UICONTROL Actions] ). Queste funzioni influiscono sui segmenti come descritto di seguito.

## Funzionalità del segmento in pausa

Un segmento in pausa (disattivato):

* Interrompe la segmentazione di nuovi utenti qualificati.
* Mantiene lo stato o l’iscrizione di segmentazione di un utente (non rimuove un utente dal segmento).
* Rimane nell’elenco dei segmenti e può essere riattivato.
* Non invia dati alle destinazioni associate.
* Restituisce i dati nei rapporti disponibili (fino alla data di disattivazione).

## Funzionalità segmento eliminata

Un segmento eliminato:

* Interrompe la segmentazione di nuovi utenti qualificati.
* Rimuove gli utenti qualificati dall’appartenenza al segmento.
* Viene rimosso dall’elenco dei segmenti.
* Impossibile annullare l&#39;eliminazione.
* Non invia dati alle destinazioni associate.
* Non restituisce i dati nei rapporti disponibili.

>[!NOTE]
>
>Puoi anche mettere in pausa ed eliminare i segmenti utilizzando un metodo [!DNL API] . Per ulteriori informazioni, consulta [API REST](../../api/rest-api-main/rest-api-main.md).
