---
description: Una richiesta collettiva restituisce i dati che è possibile utilizzare con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.
seo-description: Una richiesta collettiva restituisce i dati che è possibile utilizzare con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.
seo-title: Richieste in blocco
solution: Audience Manager
title: Richieste in blocco
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# Richieste in blocco{#bulk-requests}

Una richiesta collettiva restituisce i dati che è possibile utilizzare con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate in  [!UICONTROL Bulk Management Tools].

Il foglio di lavoro [!UICONTROL Request] non dispone di un proprio set di intestazioni di colonna e non è necessario copiare gli ID in nessuna delle colonne. ma restituisce i dati in base al pulsante di azione selezionato nella barra degli strumenti. Inoltre, una funzione di reporting opzionale restituisce un conteggio di frequenza per gli incendi di pixel e un conteggio univoco degli utenti per diversi intervalli di tempo fissi.

Per effettuare richieste in blocco, apri il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fai clic sulla scheda **[!UICONTROL Request]** .
2. Nella barra degli strumenti nella parte superiore del foglio di lavoro, fare clic su un pulsante di richiesta corrispondente ai dati con cui si desidera lavorare. Puoi richiedere:

   * Modelli algoritmici
   * Origini dati
   * Segnali derivati
   * Mappature delle destinazioni
   * Caratteristiche algoritmiche, basate su regole e onboarded
   * Segmenti 
   * ID di cartelle di caratteristiche e segmenti

   L&#39;API [!DNL Audience Manager] scrive i dati in blocco sul foglio di lavoro [!UICONTROL Request].

>[!NOTE]
>
>Nei risultati, le colonne `createTime` e `updateTime` restituiscono i dati in notazione esponenziale. I timestamp/ora sottostanti vengono registrati in UNIX UTC. Attualmente, il foglio di lavoro non può restituire le marche di data/ora in un formato leggibile.

Se l&#39;aggiornamento collettivo restituisce un errore o non riesce, consulta [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
