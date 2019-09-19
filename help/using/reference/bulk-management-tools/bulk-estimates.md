---
description: Una stima in massa restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima in massa.
seo-description: Una stima in massa restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima in massa.
seo-title: Stime di massa
solution: Audience Manager
title: Stime di massa
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Stime di massa{#bulk-estimates}

Una stima in massa restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima in massa.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>Le [!UICONTROL Bulk Management Tools] opzioni non *sono supportate da* [!DNL Audience Manager]. Questo strumento è fornito per comodità e solo come cortesia. Per modifiche di massa, consigliamo di lavorare con le API [](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, aprire il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fare clic sulla **[!UICONTROL Headers]** scheda e copiare l' [!UICONTROL Estimate Segment Size] intestazione.
1. Click the **[!UICONTROL Estimate]** tab.
1. Incollare l'intestazione della stima nella prima riga del foglio di lavoro della stima.
1. Incollate o digitate i dati da modificare in una colonna corrispondente in base all'etichetta dell'intestazione.
1. Nella barra degli strumenti del foglio di lavoro, fare clic sul pulsante Crea che corrisponde all’elemento da aggiornare.
Questa azione consente di aprire la [!UICONTROL Account Information] finestra di dialogo.

1. Fornite le informazioni [di](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) accesso richieste e fate clic su **[!UICONTROL Submit]**.

Questa azione crea una [!UICONTROL Response] colonna nel foglio di lavoro che contiene i dati delle dimensioni del segmento stimati. Prima di immettere i dati, il foglio di lavoro delle stime di massa deve essere simile al seguente:

![](assets/estimate.png)Se l'aggiornamento in blocco restituisce un errore o non riesce, consultate Risoluzione dei [problemi relativi agli strumenti](../../reference/bulk-management-tools/bulk-troubleshooting.md)di gestione in blocco.

