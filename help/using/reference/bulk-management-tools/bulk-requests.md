---
description: Una richiesta in massa restituisce i dati utilizzabili con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.
seo-description: Una richiesta in massa restituisce i dati utilizzabili con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.
seo-title: Richieste in blocco
solution: Audience Manager
title: Richieste in blocco
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---


# Richieste in blocco{#bulk-requests}

Una richiesta in massa restituisce i dati utilizzabili con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

Il [!UICONTROL Request] foglio di lavoro non dispone di un proprio set di intestazioni di colonna e non è necessario copiare gli ID in nessuna delle colonne. ma restituisce i dati in base al pulsante di azione selezionato nella barra degli strumenti. Inoltre, una funzione di reporting opzionale restituisce un conteggio di frequenza per gli incendi di pixel e un conteggio univoco degli utenti per diversi intervalli di tempo fissi.

Per eseguire richieste in massa, aprire il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fate clic sulla **[!UICONTROL Request]** scheda.
2. Nella barra degli strumenti nella parte superiore del foglio di lavoro, fare clic su un pulsante di richiesta corrispondente ai dati con cui si desidera lavorare. Potete richiedere:

   * Modelli algoritmici
   * Origini dati
   * Segnali derivati
   * Mappature di destinazione
   * Caratteristiche algoritmiche, basate su regole e integrate
   * Segmenti 
   * ID cartella caratteristiche e segmento

   L&#39; [!DNL Audience Manager] API riscrive i dati in massa nel [!UICONTROL Request] foglio di lavoro.

>[!NOTE]
>
>Nei risultati, le `createTime` colonne e le `updateTime` colonne restituiscono i dati in notazione esponenziale. I timbri data/ora sottostanti sono registrati in UNIX UTC. Attualmente, il foglio di lavoro non può restituire data/ora in un formato leggibile.

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consulta Risoluzione dei [problemi relativi agli strumenti](../../reference/bulk-management-tools/bulk-troubleshooting.md)di gestione in blocco.
