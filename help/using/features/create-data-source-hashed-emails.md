---
title: Configurare un’origine dati per i flussi di lavoro e-mail con hash
description: Scopri come creare un’origine dati per archiviare e-mail con hash per i flussi di lavoro delle e-mail con hash.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
source-git-commit: d55dbc4f9630e3d22dfb988f6725f33993229c48
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Configurare un’origine dati per i flussi di lavoro e-mail con hash

I flussi di lavoro con hash per le e-mail, come ad esempio Destinazioni basate su persone, richiedono la creazione di un’origine dati per memorizzare gli indirizzi e-mail con hash.

Segui i passaggi seguenti per creare e configurare un’origine dati per le e-mail con hash.

1. Accedi al tuo account Audience Manager e passa a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, quindi fai clic su **[!UICONTROL Add New]**.
1. Immettere **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati.
1. Nel menu a discesa **[!UICONTROL ID Type]**, selezionare **[!UICONTROL Cross Device]**.
   ![Immagine dell&#39;interfaccia utente di Audience Manager che mostra la sezione dei dettagli dell&#39;origine dati.](../features/assets/create-hashed-email-data-source.png)
1. Nella sezione **[!UICONTROL Data Source Settings]** selezionare entrambe le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e abilitare l&#39;opzione **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilizzare il menu a discesa per selezionare l&#39;etichetta **[!UICONTROL Emails(SHA256, lowercased)]** per questa origine dati.

   >[!IMPORTANT]
   >
   >Questa opzione etichetta l’origine dati solo come contenente dati con hash con quell’algoritmo specifico. L’Audience Manager non esegue l’hashing dei dati in questo passaggio. Verificare che gli indirizzi di posta elettronica che si prevede di memorizzare in questa origine dati siano già sottoposti a hashing con l&#39;algoritmo [!DNL SHA256]. In caso contrario, non potrai utilizzarlo per i flussi di lavoro e-mail con hash.

   ![Immagine dell&#39;interfaccia utente di Audience Manager che mostra la sezione delle impostazioni dell&#39;origine dati.](../features/assets/data-source-settings.png)
