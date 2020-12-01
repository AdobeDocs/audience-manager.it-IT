---
description: Una stima in massa restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima in massa.
seo-description: Una stima in massa restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima in massa.
seo-title: Stime in blocco
solution: Audience Manager
title: Stime in blocco
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# Stime in blocco{#bulk-estimates}

Una stima in massa restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Seguite queste istruzioni per effettuare una richiesta di stima in massa.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella  [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Headers]** e copiare l&#39;intestazione [!UICONTROL Estimate Segment Size].
2. Fare clic sulla scheda **[!UICONTROL Estimate]**.
3. Incollare l&#39;intestazione della stima nella prima riga del foglio di lavoro della stima.
4. Incollate o digitate i dati da modificare in una colonna corrispondente in base all&#39;etichetta dell&#39;intestazione.
5. Nella barra degli strumenti del foglio di lavoro, fare clic sul pulsante Crea che corrisponde all’elemento da aggiornare.
Questa azione apre la finestra di dialogo [!UICONTROL Account Information].
6. Specificare le informazioni di accesso [necessarie](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) e fare clic su **[!UICONTROL Submit]**.

Questa azione crea una colonna [!UICONTROL Response] nel foglio di lavoro che contiene i dati delle dimensioni del segmento stimati. Prima di immettere i dati, il foglio di lavoro delle stime di massa deve essere simile al seguente:

![](assets/estimate.png)
Se l&#39;aggiornamento in blocco restituisce un errore o un errore, consulta Risoluzione dei  [problemi relativi agli strumenti](../../reference/bulk-management-tools/bulk-troubleshooting.md) di gestione in blocco.

