---
description: Una richiesta in blocco restituisce dati che è possibile utilizzare con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Richieste in blocco
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
TQID: https://experienceleague.adobe.com/9VACsTAdf5nqwXAeQCqA7ME7M1sTOwt-eW-fyVdE-Ag
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 253
ht-degree: 0%

---

# Richieste in blocco{#bulk-requests}

Una richiesta in blocco restituisce dati che è possibile utilizzare con le diverse intestazioni nei fogli di lavoro Aggiorna, Crea, Stima ed Elimina.

>[!IMPORTANT]
>
>Gli strumenti di gestione in blocco non sono un’offerta ufficialmente supportata da Adobe. La risoluzione dei problemi e il supporto tramite l’Assistenza clienti verranno gestiti caso per caso.

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
