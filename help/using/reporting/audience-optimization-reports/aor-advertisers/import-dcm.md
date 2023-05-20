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
source-wordcount: '596'
ht-degree: 3%

---

# Importare file di dati di Google Campaign Manager in Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurare un [!DNL Google] gruppo per portare il tuo [!DNL Google Campaign Manager] file di dati in Audience Manager. Il contenuto di questa sezione riassume il processo di integrazione e fornisce i collegamenti a [!DNL Google Campaign Manager] risorse per aiutarti a iniziare.

## Riepilogo dell’integrazione

[!DNL Google Campaign Manager] è la soluzione [!DNL Google] che sostituisce [!DNL DoubleClick for Advertisers] (DFA). Simile a DFA, [!DNL Google Campaign Manager] i clienti possono importare, visualizzare e lavorare con i propri dati in [!DNL Audience Manager]. Ma [!DNL Audience Manager] non può accedere e importare direttamente [!UICONTROL Data Transfer] e [!UICONTROL Match Table] file. L&#39;importazione di questi file è a carico del cliente.

Tuttavia, la procedura di configurazione è ben documentata nel [Guida di DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Inoltre, puoi rivedere i passaggi elencati di seguito per iniziare.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] i file di dati contengono dati per tutti gli inserzionisti o i clienti. Se è necessario omettere client specifici, è necessario modificare i file prima di renderli disponibili per [!DNL Audience Manager].

## Frequenza e disponibilità del trasferimento dei dati

[!DNL Audience Manager] verifica e trasferisce i dati una volta al giorno. I dati sono generalmente disponibili in [!DNL Audience Manager] dopo 24 ore.

## Passaggi

1. [Create un gruppo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   I gruppi controllano l’accesso al tuo [!DNL Google Campaign Manager] dati. Alla fine, potrai invitare e aggiungere [!DNL Audience Manager] a questo gruppo.

1. [Verifica lo stato dell&#39;archiviazione Google Cloud](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage contiene il bucket di dati che contiene il [!UICONTROL Data Transfer] e [!UICONTROL Match Tables]. Devi impostare un bucket o assicurarti che il nuovo gruppo abbia accesso a un bucket di archiviazione dati esistente.

1. [Ottieni un URL per file di dati](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Utilizzare [!DNL Google Campaign Manager] Account Manager o consulente per le soluzioni Platform. Ti forniranno l’URL dei tuoi file di dati. [!DNL Google] potrebbe modificare il formato dei bucket e dei nomi dei file nelle versioni future. Anche in questo caso, utilizza [!DNL Google Campaign Manager] Account Manager per essere certi di usare i formati corretti.

1. [Impostare le autorizzazioni bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Il [!DNL Cloud Storage Manager] consente di controllare la condivisione dei dati e l’accesso ai bucket. Concedi al gruppo l&#39;accesso in lettura al bucket che contiene [!UICONTROL Data Transfer] e [!UICONTROL Match Table] file.

1. [Configurare la condivisione dei dati](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Condiviso [!DNL Google Campaign Manager] Gli ID utente sono crittografati per proteggere la privacy. Encryption aggiunge 2 colonne alla fine del file di trasferimento dati, `PartnerId1` e `PartnerId2`. Queste colonne contengono ID utente codificati specifici per ogni azienda che riceve questi file.

   In qualità di terzo autorizzato, [!DNL Audience Manager] può ricevere [!DNL Google Campaign Manager] ma non può decodificare gli ID. Tuttavia, il [!DNL Audience Manager] sappiamo come gli ID codificati corrispondono ai nostri ID. Questo significa che possiamo far corrispondere e sincronizzare gli utenti con sicurezza e precisione.

   >[!NOTE]
   >Impossibile importare [!DNL Google Campaign Manager] file in [!DNL Audience Manager] se stai già condividendo dati con altri 2 partner di terze parti.

1. Invita [!DNL Audience Manager] per unirsi al gruppo.

   Dopo aver creato un gruppo e avergli dato accesso a un bucket di dati, invita [!DNL Audience Manager] per unirsi al gruppo. Invia un invito e-mail a dfaaam@adobe.com. Assicurati di includere l’URL del file di dati dal passaggio 3. I nostri team interni collaboreranno con te per verificare l’accesso dopo aver accettato l’invito. 1. Imposta due origini dati per [!DNL Google Campaign Manager] dati in [!DNL Audience Manager] Interfaccia utente.

   Denomina le origini dati `Advertiser Analytics: DCM Platform` e `Advertiser Analytics: AAM+DCM Platform`. In [Creare origini dati](../../../features/manage-datasources.md#create-data-source) flusso di lavoro, imposta il tipo ID su `Cookie`. Condividi gli ID delle due nuove origini dati con i nostri team interni.

1. Puoi creare facilmente le caratteristiche dal [!DNL Google Campaign Manager] file importati in [!DNL Audience Manager]. Consulta [File di registro fruibili](../../../integration/media-data-integration/actionable-log-files.md) e chiedi [!DNL Audience Manager] consulente o assistenza clienti per abilitare questa funzione.
