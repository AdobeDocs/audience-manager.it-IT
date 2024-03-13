---
title: Configurare un’origine dati per i flussi di lavoro e-mail con hash
description: Scopri come creare un’origine dati per archiviare e-mail con hash per i flussi di lavoro delle e-mail con hash.
solution: Audience Manager
feature: Data Sources
source-git-commit: 903c2602f759e0d507e45f1db4cbc880a599c32e
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---


# Configurare un’origine dati per i flussi di lavoro e-mail con hash

I flussi di lavoro con hash per le e-mail, come ad esempio Destinazioni basate su persone, richiedono la creazione di un’origine dati per memorizzare gli indirizzi e-mail con hash.

Segui i passaggi seguenti per creare e configurare un’origine dati per le e-mail con hash.

1. Accedi al tuo account Audienci Manager e vai a **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** e fai clic su **[!UICONTROL Add New]**.
1. Immetti un **[!UICONTROL Name]** e **[!UICONTROL Description]** per la nuova origine dati.
1. In **[!UICONTROL ID Type]** menu a discesa, seleziona **[!UICONTROL Cross Device]**.
   ![Audience Manager di immagine dell’interfaccia utente che mostra la sezione dei dettagli dell’origine dati.](../features/assets/create-hashed-email-data-source.png)
1. In **[!UICONTROL Data Source Settings]** , selezionare entrambe le opzioni **[!UICONTROL Inbound]** e **[!UICONTROL Outbound]** e abilitare **[!UICONTROL Share associated cross-device IDs in people-based destinations]** opzione.
1. Utilizza il menu a discesa per selezionare **[!UICONTROL Emails(SHA256, lowercased)]** etichetta per questa origine dati.

   >[!IMPORTANT]
   >
   >Questa opzione etichetta l’origine dati solo come contenente dati con hash con quell’algoritmo specifico. L’Audience Manager non esegue l’hashing dei dati in questo passaggio. Assicurati che gli indirizzi e-mail che intendi archiviare in questa origine dati abbiano già un hash con [!DNL SHA256] algoritmo. In caso contrario, non potrai utilizzarlo per i flussi di lavoro e-mail con hash.

   ![Audience Manager di immagine dell’interfaccia utente che mostra la sezione delle impostazioni dell’origine dati.](../features/assets/data-source-settings.png)

