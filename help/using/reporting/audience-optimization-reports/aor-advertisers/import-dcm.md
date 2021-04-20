---
description: Imposta un gruppo Google per inserire in Audience Manager i file di dati di Google Campaign Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti alle risorse di Google Campaign Manager per aiutarti a iniziare.
seo-description: Imposta un gruppo Google per inserire in Audience Manager i file di dati di Google Campaign Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti alle risorse di Google Campaign Manager per aiutarti a iniziare.
seo-title: Importare file di dati di Google Campaign Manager in Audience Manager
solution: Audience Manager
title: Importare file di dati di Google Campaign Manager in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# Importare file di dati di Google Campaign Manager in un Audience Manager {#import-dcm-data-files-into-audience-manager}

Imposta un gruppo [!DNL Google] per inserire in Audience Manager i file di dati [!DNL Google Campaign Manager] . Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti alle risorse [!DNL Google Campaign Manager] per aiutarti a iniziare.

## Riepilogo integrazione

[!DNL Google Campaign Manager] è la soluzione [!DNL Google] che sostituisce [!DNL DoubleClick for Advertisers] (DFA). Analogamente a DFA, i clienti [!DNL Google Campaign Manager] possono importare, visualizzare e lavorare con i propri dati in [!DNL Audience Manager]. Ma [!DNL Audience Manager] non può accedere e importare direttamente i file [!UICONTROL Data Transfer] e [!UICONTROL Match Table]. L&#39;importazione di questi file è a carico del cliente.

Tuttavia, la procedura di configurazione è ben documentata nella [Guida di DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Inoltre, per iniziare puoi rivedere i passaggi elencati di seguito.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] i file di dati contengono dati per tutti gli inserzionisti o i client. Se devi omettere client specifici, devi modificare i file prima di renderli disponibili per [!DNL Audience Manager].

## Frequenza e disponibilità del trasferimento dei dati

[!DNL Audience Manager] verifica e trasferisce i dati una volta al giorno. I dati sono solitamente disponibili in [!DNL Audience Manager] dopo 24 ore.

## Passaggi

1. [Create un gruppo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   I gruppi controllano l’accesso ai dati [!DNL Google Campaign Manager]. Alla fine, inviterai e aggiungi [!DNL Audience Manager] a questo gruppo.

1. [Verifica lo stato](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456) di Google Cloud Storage.

   Google Cloud Storage contiene il bucket dati che contiene i [!UICONTROL Data Transfer] e [!UICONTROL Match Tables]. Devi impostare un bucket o assicurarti che il nuovo gruppo abbia accesso a un bucket di archiviazione dati esistente.

1. [Ottieni l’URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456) di un file di dati.

   Collabora con il tuo account manager o consulente di soluzioni Platform. [!DNL Google Campaign Manager] Ti forniranno un URL per i tuoi file di dati. [!DNL Google] potrebbe modificare il formato per i nomi di file e bucket nelle versioni future. Anche in questo caso, collabora con il tuo Account Manager [!DNL Google Campaign Manager] per assicurarti di utilizzare i formati giusti.

1. [Imposta le autorizzazioni del bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Il [!DNL Cloud Storage Manager] ti consente di controllare la condivisione dei dati e l’accesso ai bucket. Consenti al gruppo di accedere in lettura al bucket contenente i file [!UICONTROL Data Transfer] e [!UICONTROL Match Table].

1. [Imposta la condivisione](https://support.google.com/dcm/partner/answer/6206106?hl=en) dei dati.

   Gli [!DNL Google Campaign Manager] ID utente condivisi sono crittografati per proteggere la privacy. La cifratura aggiunge 2 colonne alla fine del file di trasferimento dati, `PartnerId1` e `PartnerId2`. Queste colonne contengono ID utente codificati specifici per ogni società che riceve questi file.

   In qualità di terze parti autorizzate, [!DNL Audience Manager] può ricevere [!DNL Google Campaign Manager] dati, ma non può decodificare gli ID. Tuttavia, dal lato [!DNL Audience Manager], sappiamo in che modo gli ID codificati corrispondono ai nostri ID. Questo significa che possiamo abbinare e sincronizzare gli utenti con affidabilità e precisione.

   >[!NOTE]
   >Non puoi importare file [!DNL Google Campaign Manager] in [!DNL Audience Manager] se condividi già dati con altri due partner di terze parti.

1. Invita [!DNL Audience Manager] a unirsi al gruppo.

   Dopo aver creato un gruppo e avergli dato accesso a un bucket dati, invitate [!DNL Audience Manager] a unirsi al gruppo. Invia un messaggio e-mail di invito a DFA-AAM@adobe.com. Accertati di includere l’URL del file di dati dal passaggio 3. I nostri team interni collaboreranno con te per verificare l’accesso dopo aver accettato l’invito. 1. Imposta due origini dati per i dati [!DNL Google Campaign Manager] nell&#39; [!DNL Audience Manager] Interfaccia utente.

   Denomina le origini dati `Advertiser Analytics: DCM Platform` e `Advertiser Analytics: AAM+DCM Platform`. Nel flusso di lavoro [Crea origini dati](../../../features/manage-datasources.md#create-data-source), imposta il tipo di ID su `Cookie`. Condividi gli ID delle due nuove origini dati con i nostri team interni.

1. Puoi creare facilmente caratteristiche dai file [!DNL Google Campaign Manager] importati in [!DNL Audience Manager]. Consulta [File di registro fruibili](../../../integration/media-data-integration/actionable-log-files.md) e chiedi al tuo consulente [!DNL Audience Manager] o all&#39;Assistenza clienti di abilitare la funzione per te.
