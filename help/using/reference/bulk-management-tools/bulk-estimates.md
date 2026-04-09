---
description: Una stima in blocco restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Segui queste istruzioni per effettuare una richiesta di stima in blocco.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Stime in blocco
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
TQID: https://experienceleague.adobe.com/FDD4gSg00I8p4sRqxE9sEpO5dSkGEXpH3hUD6h5CAtI
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# Stime in blocco{#bulk-estimates}

Una stima in blocco restituisce i dati delle dimensioni del segmento in base alle regole del segmento. Segui queste istruzioni per effettuare una richiesta di stima in blocco.

>[!IMPORTANT]
>
>Gli strumenti di gestione in blocco non sono un’offerta ufficialmente supportata da Adobe. La risoluzione dei problemi e il supporto tramite l’Assistenza clienti verranno gestiti caso per caso.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Le autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnate nell&#39;interfaccia utente [!DNL Audience Manager] vengono rispettate in [!UICONTROL Bulk Management Tools].

Per eseguire aggiornamenti in blocco, aprire il foglio di lavoro [!UICONTROL Bulk Management Tools] e:

1. Fare clic sulla scheda **[!UICONTROL Headers]** e copiare l&#39;intestazione [!UICONTROL Estimate Segment Size].
2. Fare clic sulla scheda **[!UICONTROL Estimate]**.
3. Incollare l&#39;intestazione della stima nella prima riga del foglio di lavoro della stima.
4. Incolla o digita i dati che desideri modificare in una colonna corrispondente in base all’etichetta dell’intestazione.
5. Nella barra degli strumenti del foglio di lavoro fare clic sul pulsante Crea corrispondente all&#39;elemento che si sta aggiornando.
Questa azione apre la finestra di dialogo [!UICONTROL Account Information].
6. Fornisci le [informazioni di accesso](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) richieste e fai clic su **[!UICONTROL Submit]**.

Questa azione crea una colonna [!UICONTROL Response] nel foglio di lavoro che contiene i dati delle dimensioni di segmento stimate. Prima di immettere i dati, il foglio di lavoro della stima in blocco deve avere un aspetto simile al seguente:

![](assets/estimate.png)
Se l&#39;aggiornamento in blocco restituisce un errore o non riesce, vedere [Risoluzione dei problemi relativi agli strumenti di gestione in blocco](../../reference/bulk-management-tools/bulk-troubleshooting.md).
