---
description: Una richiesta in blocco restituisce dati che è possibile utilizzare con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Richieste in blocco
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Richieste in blocco{#bulk-requests}

Una richiesta in blocco restituisce dati che è possibile utilizzare con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.

>[!IMPORTANT]
>
>Gli strumenti di gestione in blocco non sono un’offerta di Adobe ufficialmente supportata. La risoluzione dei problemi e il supporto tramite l’Assistenza clienti verranno gestiti caso per caso.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[Le autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnate nell&#39;interfaccia utente [!DNL Audience Manager] vengono rispettate in [!UICONTROL Bulk Management Tools].

Il foglio di lavoro [!UICONTROL Request] non dispone di un proprio set di intestazioni di colonna e non è necessario copiare gli ID in nessuna delle colonne. Restituisce invece dati in base al pulsante di azione su cui si fa clic nella barra degli strumenti. Inoltre, una funzione di reporting opzionale restituisce un conteggio delle frequenze per gli incendi di pixel e un conteggio di utenti univoco per diversi intervalli di tempo fissi.

Per effettuare richieste in blocco, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Request]**.
2. Nella barra degli strumenti nella parte superiore del foglio di lavoro fare clic su un pulsante di richiesta corrispondente ai dati che si desidera utilizzare. Puoi richiedere:

   * Modelli algoritmici
   * Origini dati
   * Segnali derivati
   * Mappature di destinazione
   * Caratteristiche algoritmiche, basate su regole e onboarded
   * Segmenti
   * ID delle caratteristiche e delle cartelle di segmenti

   L&#39;API [!DNL Audience Manager] riscrive i dati in blocco nel foglio di lavoro [!UICONTROL Request].

>[!NOTE]
>
>Nei risultati, le colonne `createTime` e `updateTime` restituiscono dati in notazione esponenziale. I timestamp sottostanti vengono registrati all’ora UTC UNIX. Attualmente, il foglio di lavoro non può restituire data/ora in un formato leggibile.

Se l&#39;aggiornamento in blocco restituisce un errore o non riesce, vedere [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
