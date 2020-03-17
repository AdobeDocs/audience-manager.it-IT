---
description: Una stima in massa restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima in massa.
seo-description: Una stima in massa restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima in massa.
seo-title: Stime di massa
solution: Audience Manager
title: Stime di massa
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: 3051ca9f7c4039dafdfa01b89226c1fa8717e610

---


# Stime di massa{#bulk-estimates}

Una stima in massa restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima in massa.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, aprire il [!UICONTROL Bulk Management Tools] foglio di lavoro e:

1. Fare clic sulla **[!UICONTROL Headers]** scheda e copiare l&#39; [!UICONTROL Estimate Segment Size] intestazione.
2. Fate clic sulla **[!UICONTROL Estimate]** scheda.
3. Incollare l&#39;intestazione della stima nella prima riga del foglio di lavoro della stima.
4. Incollate o digitate i dati da modificare in una colonna corrispondente in base all&#39;etichetta dell&#39;intestazione.
5. Nella barra degli strumenti del foglio di lavoro, fare clic sul pulsante Crea che corrisponde all’elemento da aggiornare.
Questa azione consente di aprire la [!UICONTROL Account Information] finestra di dialogo.
6. Fornite le informazioni [di](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) accesso richieste e fate clic su **[!UICONTROL Submit]**.

Questa azione crea una [!UICONTROL Response] colonna nel foglio di lavoro che contiene i dati delle dimensioni del segmento stimati. Prima di immettere i dati, il foglio di lavoro delle stime di massa deve essere simile al seguente:

![](assets/estimate.png)
Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consulta Risoluzione dei [problemi relativi agli strumenti](../../reference/bulk-management-tools/bulk-troubleshooting.md)di gestione in blocco.

