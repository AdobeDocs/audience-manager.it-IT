---
description: Imposta un gruppo Google per inserire in Audience Manager i file di dati di Google Campaign Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti alle risorse di Google Campaign Manager per aiutarti a iniziare.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importare file di dati Google Campaign Manager in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 3%

---

# Importare file di dati Google Campaign Manager in Audience Manager {#import-dcm-data-files-into-audience-manager}

Imposta un [!DNL Google] gruppo per portare il tuo [!DNL Google Campaign Manager] file di dati in Audience Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti a [!DNL Google Campaign Manager] risorse utili per iniziare.

## Riepilogo integrazione

[!DNL Google Campaign Manager] è la soluzione [!DNL Google] che sostituisce [!DNL DoubleClick for Advertisers] (DFA). Simile al DFA, [!DNL Google Campaign Manager] I clienti possono importare, visualizzare e lavorare con i propri dati in [!DNL Audience Manager]. Ma [!DNL Audience Manager] non può accedere e importare direttamente il [!UICONTROL Data Transfer] e [!UICONTROL Match Table] file. L&#39;importazione di questi file è a carico del cliente.

Tuttavia, la procedura di configurazione è ben documentata nella [Guida di DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Inoltre, per iniziare puoi rivedere i passaggi elencati di seguito.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] i file di dati contengono dati per tutti gli inserzionisti o i client. Se devi omettere client specifici, devi modificare i file prima di renderli disponibili per [!DNL Audience Manager].

## Frequenza e disponibilità del trasferimento dei dati

[!DNL Audience Manager] verifica e trasferisce i dati una volta al giorno. In genere i dati sono disponibili in [!DNL Audience Manager] dopo 24 ore.

## Passaggi

1. [Create un gruppo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   I gruppi controllano l&#39;accesso al tuo [!DNL Google Campaign Manager] dati. Alla fine, inviterai e aggiungi [!DNL Audience Manager] a questo gruppo.

1. [Verifica lo stato di Google Cloud Storage](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage contiene il bucket dati che contiene [!UICONTROL Data Transfer] e [!UICONTROL Match Tables]. Devi impostare un bucket o assicurarti che il nuovo gruppo abbia accesso a un bucket di archiviazione dati esistente.

1. [Ottenere l’URL di un file di dati](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Lavora con il tuo [!DNL Google Campaign Manager] Account Manager o Consulente per le soluzioni della piattaforma. Ti forniranno un URL per i tuoi file di dati. [!DNL Google] potrebbe modificare il formato per i nomi di file e bucket nelle versioni future. Ancora una volta, lavora con il tuo [!DNL Google Campaign Manager] Account Manager per assicurarti di utilizzare i formati giusti.

1. [Impostare le autorizzazioni del bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   La [!DNL Cloud Storage Manager] consente di controllare la condivisione dei dati e l’accesso ai bucket. Consenti al gruppo di accedere in lettura al bucket contenente il tuo [!UICONTROL Data Transfer] e [!UICONTROL Match Table] file.

1. [Configurare la condivisione dei dati](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Condiviso [!DNL Google Campaign Manager] gli ID utente sono crittografati per proteggere la privacy. La crittografia aggiunge 2 colonne alla fine del file di trasferimento dati, `PartnerId1` e `PartnerId2`. Queste colonne contengono ID utente codificati specifici per ogni società che riceve questi file.

   in qualità di terzo autorizzato, [!DNL Audience Manager] può ricevere [!DNL Google Campaign Manager] , ma non può decodificare gli ID. Tuttavia, [!DNL Audience Manager] Inoltre, sappiamo in che modo gli ID codificati corrispondono ai nostri ID. Questo significa che possiamo abbinare e sincronizzare gli utenti con affidabilità e precisione.

   >[!NOTE]
   >Non è possibile importare [!DNL Google Campaign Manager] file in [!DNL Audience Manager] se condividi già dati con altri 2 partner di terze parti.

1. Invito [!DNL Audience Manager] per unirsi al gruppo.

   Dopo aver creato un gruppo e avergli dato accesso a un bucket dati, invoca [!DNL Audience Manager] per unirsi al gruppo. Invia un messaggio e-mail di invito a dfaaam@adobe.com. Accertati di includere l’URL del file di dati dal passaggio 3. I nostri team interni collaboreranno con te per verificare l’accesso dopo aver accettato l’invito. 1. Imposta due origini dati per [!DNL Google Campaign Manager] i dati [!DNL Audience Manager] Interfaccia utente.

   Denomina le origini dati `Advertiser Analytics: DCM Platform` e `Advertiser Analytics: AAM+DCM Platform`. In [Creazione di origini dati](../../../features/manage-datasources.md#create-data-source) flusso di lavoro, imposta il tipo di ID su `Cookie`. Condividi gli ID delle due nuove origini dati con i nostri team interni.

1. Puoi creare facilmente caratteristiche dalla [!DNL Google Campaign Manager] file importati in [!DNL Audience Manager]. Vedi [File di registro fruibili](../../../integration/media-data-integration/actionable-log-files.md) e chiedi [!DNL Audience Manager] per abilitare questa funzione, rivolgiti al consulente o all’Assistenza clienti.
