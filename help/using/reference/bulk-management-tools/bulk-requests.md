---
description: Una richiesta in massa restituisce i dati utilizzabili con le varie intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.
seo-description: Una richiesta in massa restituisce i dati utilizzabili con le varie intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.
seo-title: Richieste di massa
solution: Audience Manager
title: Richieste di massa
uuid: 0192 d 26 a -4 cea -4 e 12-9 fea -388 b 92 b 382 f 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Requests{#bulk-requests}

Una richiesta in massa restituisce i dati utilizzabili con le varie intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell' [!DNL Audience Manager] interfaccia utente vengono rispettate nell' [!UICONTROL Bulk Management Tools]interfaccia.

The [!UICONTROL Request] worksheet does not have its own set of column headers and you don't need to copy IDs to any of the columns. Al contrario, restituisce dati in base al pulsante azione che si fa clic sulla barra degli strumenti. Inoltre, una funzione di reporting opzionale restituisce un conteggio di frequenza per gli attivamenti pixel e il conteggio univoco degli utenti a intervalli di tempo diversi.

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Request]** tab.
2. Nella barra degli strumenti nella parte superiore del foglio di lavoro, fate clic su un pulsante di richiesta corrispondente ai dati che desiderate utilizzare. Potete richiedere:

   * ID dei fornitori di dati
   * Segnali derivati
   * Mappature di destinazione
   * Caratteristiche basate su regola e su scorrimento
   * Segmenti
   * ID delle cartelle di segmenti e segmenti
   The [!DNL Audience Manager] API writes bulk data back to the [!UICONTROL Request] worksheet.

>[!NOTE]
>
>In your results, the `createTime` and `updateTime` columns return data in exponential notation. I timestamp di data/ora sottostanti vengono registrati in ora UNIX UTC. Al momento, il foglio di lavoro non può restituire marche temporali/ora in formato leggibile.

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
