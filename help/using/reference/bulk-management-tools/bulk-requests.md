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


# Richieste di massa{#bulk-requests}

Una richiesta in massa restituisce i dati utilizzabili con le varie intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>Non [!UICONTROL Bulk Management Tools]*sono* supportati da [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. Per modifiche in massa, consigliamo di lavorare con [le API](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell&#39; [!DNL Audience Manager] interfaccia utente vengono rispettate nell&#39; [!UICONTROL Bulk Management Tools]interfaccia.

Il [!UICONTROL Request] foglio di lavoro non dispone di intestazioni di colonna proprie e non è necessario copiare gli ID in una qualsiasi colonna. Al contrario, restituisce dati in base al pulsante azione che si fa clic sulla barra degli strumenti. Inoltre, una funzione di reporting opzionale restituisce un conteggio di frequenza per gli attivamenti pixel e il conteggio univoco degli utenti a intervalli di tempo diversi.

Per effettuare richieste di massa, apri il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fare clic sulla **[!UICONTROL Request]** scheda.
2. Nella barra degli strumenti nella parte superiore del foglio di lavoro, fate clic su un pulsante di richiesta corrispondente ai dati che desiderate utilizzare. Potete richiedere:

   * ID dei fornitori di dati
   * Segnali derivati
   * Mappature di destinazione
   * Caratteristiche basate su regola e su scorrimento
   * Segmenti
   * ID delle cartelle di segmenti e segmenti
   L&#39; [!DNL Audience Manager] API scrive nuovamente i dati in massa sul [!UICONTROL Request] foglio di lavoro.

>[!NOTE]
>
>Nei risultati, le `createTime``updateTime` colonne restituiscono dati sotto forma di notazione esponenziale. I timestamp di data/ora sottostanti vengono registrati in ora UNIX UTC. Al momento, il foglio di lavoro non può restituire marche temporali/ora in formato leggibile.

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consultate [Risoluzione dei problemi per strumenti di gestione collettiva](../../reference/bulk-management-tools/bulk-troubleshooting.md).
