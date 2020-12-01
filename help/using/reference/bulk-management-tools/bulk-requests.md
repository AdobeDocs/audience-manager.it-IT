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
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella  [!UICONTROL Bulk Management Tools].

Il foglio di lavoro [!UICONTROL Request] non dispone di un proprio set di intestazioni di colonna e non è necessario copiare gli ID in nessuna delle colonne. ma restituisce i dati in base al pulsante di azione selezionato nella barra degli strumenti. Inoltre, una funzione di reporting opzionale restituisce un conteggio di frequenza per gli incendi di pixel e un conteggio univoco degli utenti per diversi intervalli di tempo fissi.

Per eseguire richieste in massa, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Request]**.
2. Nella barra degli strumenti nella parte superiore del foglio di lavoro, fare clic su un pulsante di richiesta corrispondente ai dati con cui si desidera lavorare. Potete richiedere:

   * Modelli algoritmici
   * Origini dati
   * Segnali derivati
   * Mappature di destinazione
   * Caratteristiche algoritmiche, basate su regole e integrate
   * Segmenti 
   * ID cartella caratteristiche e segmento

   L&#39;API [!DNL Audience Manager] riscrive i dati di massa nel foglio di lavoro [!UICONTROL Request].

>[!NOTE]
>
>Nei risultati, le colonne `createTime` e `updateTime` restituiscono i dati in notazione esponenziale. I timbri data/ora sottostanti sono registrati in UNIX UTC. Attualmente, il foglio di lavoro non può restituire data/ora in un formato leggibile.

Se l&#39;aggiornamento in blocco restituisce un errore o un errore, vedere [Risoluzione dei problemi per gli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
