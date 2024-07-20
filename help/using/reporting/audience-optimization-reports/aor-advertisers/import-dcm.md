---
description: Configura un gruppo Google per rendere Audienci Manager i file di dati di Google Campaign Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti alle risorse di Google Campaign Manager per aiutarti a iniziare.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importare file di dati di Google Campaign Manager in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# Importare file di dati di Google Campaign Manager in Audience Manager {#import-dcm-data-files-into-audience-manager}

Configura un gruppo [!DNL Google] per rendere Audienci Manager i file di dati di [!DNL Google Campaign Manager]. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti alle risorse [!DNL Google Campaign Manager] per aiutarti a iniziare.

## Riepilogo dell’integrazione

[!DNL Google Campaign Manager] è la sostituzione di [!DNL Google] per [!DNL DoubleClick for Advertisers] (DFA). Analogamente a DFA, i clienti [!DNL Google Campaign Manager] possono importare, visualizzare e lavorare con i propri dati in [!DNL Audience Manager]. Ma [!DNL Audience Manager] non può accedere e importare direttamente i tuoi file [!UICONTROL Data Transfer] e [!UICONTROL Match Table]. L&#39;importazione di questi file è a carico del cliente.

Tuttavia, la procedura di configurazione è ben documentata nella [Guida di DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Inoltre, puoi rivedere i passaggi elencati di seguito per iniziare.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] file di dati contengono dati per tutti gli inserzionisti o i client. Se è necessario omettere client specifici, è necessario modificare i file prima di renderli disponibili per [!DNL Audience Manager].

## Frequenza e disponibilità del trasferimento dei dati

[!DNL Audience Manager] verifica e trasferisce i dati una volta al giorno. I dati sono in genere disponibili in [!DNL Audience Manager] dopo 24 ore.

## Passaggi

1. [Crea un gruppo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   I gruppi controllano l&#39;accesso ai dati di [!DNL Google Campaign Manager]. Inviterai e aggiungerai [!DNL Audience Manager] a questo gruppo.

1. [Verifica lo stato dell&#39;archiviazione cloud di Google](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage contiene il bucket di dati che contiene [!UICONTROL Data Transfer] e [!UICONTROL Match Tables]. Devi impostare un bucket o assicurarti che il nuovo gruppo abbia accesso a un bucket di archiviazione dati esistente.

1. [Ottieni un URL di file di dati](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Rivolgiti al tuo Account Manager [!DNL Google Campaign Manager] o al consulente per le soluzioni della piattaforma. Ti forniranno l’URL dei tuoi file di dati. [!DNL Google] potrebbe modificare il formato dei nomi di file e bucket nelle versioni future. Rivolgiti al tuo Account Manager [!DNL Google Campaign Manager] per assicurarti di utilizzare i formati corretti.

1. [Imposta autorizzazioni bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   [!DNL Cloud Storage Manager] consente di controllare la condivisione dei dati e l&#39;accesso ai bucket. Concedi al gruppo l&#39;accesso in lettura al bucket contenente i tuoi file [!UICONTROL Data Transfer] e [!UICONTROL Match Table].

1. [Configura condivisione dati](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Gli ID utente [!DNL Google Campaign Manager] condivisi sono crittografati per proteggere la privacy. La crittografia aggiunge 2 colonne alla fine del file di trasferimento dati, `PartnerId1` e `PartnerId2`. Queste colonne contengono ID utente codificati specifici per ogni azienda che riceve questi file.

   In qualità di terza parte autorizzata, [!DNL Audience Manager] può ricevere [!DNL Google Campaign Manager] dati, ma non può decodificare gli ID. Tuttavia, sul lato [!DNL Audience Manager], sappiamo come gli ID codificati corrispondono ai nostri ID. Questo significa che possiamo far corrispondere e sincronizzare gli utenti con sicurezza e precisione.

   >[!NOTE]
   >Non puoi importare [!DNL Google Campaign Manager] file in [!DNL Audience Manager] se stai già condividendo dati con altri 2 partner di terze parti.

1. Invita [!DNL Audience Manager] a partecipare al gruppo.

   Dopo aver creato un gruppo e avergli dato accesso a un bucket di dati, invita [!DNL Audience Manager] a partecipare al gruppo. Invia un invito e-mail a dfaaam@adobe.com. Assicurati di includere l’URL del file di dati dal passaggio 3. I nostri team interni collaboreranno con te per verificare l’accesso dopo aver accettato l’invito. 1. Configurare due origini dati per i dati [!DNL Google Campaign Manager] nell&#39;interfaccia utente [!DNL Audience Manager].

   Denomina le origini dati `Advertiser Analytics: DCM Platform` e `Advertiser Analytics: AAM+DCM Platform`. Nel flusso di lavoro [Crea origini dati](../../../features/manage-datasources.md#create-data-source), imposta il tipo ID su `Cookie`. Condividi gli ID delle due nuove origini dati con i nostri team interni.

1. È possibile creare facilmente caratteristiche dai file [!DNL Google Campaign Manager] importati in [!DNL Audience Manager]. Consulta [File di registro fruibili](../../../integration/media-data-integration/actionable-log-files.md) e chiedi al tuo consulente [!DNL Audience Manager] o all&#39;Assistenza clienti di abilitare questa funzione.
