---
description: Configurate un gruppo Google per trasferire i file di dati doubleclick Campaign Manager (DCM) in Audience Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti a risorse DCM per aiutarti a iniziare.
seo-description: Configurate un gruppo Google per trasferire i file di dati doubleclick Campaign Manager (DCM) in Audience Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti a risorse DCM per aiutarti a iniziare.
seo-title: Importare file di dati DCM in Audience Manager
solution: Audience Manager
title: Importare file di dati DCM in Audience Manager
uuid: 3578 cfe 1-6 d 30-4 a 73-ab 75-8 d 272 bebcd 60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Importare file di dati DCM in Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurate un gruppo Google per trasferire i file di dati doubleclick Campaign Manager (DCM) in Audience Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti a risorse DCM per aiutarti a iniziare.

## Riepilogo integrazione

DCM è la sostituzione [!DNL Google] per [!DNL DoubleClick for Advertisers] (DFA). In modo analogo a DFA, i clienti DCM possono importare, visualizzare e lavorare con i loro dati in [!DNL Audience Manager]. ma [!DNL Audience Manager] non è possibile accedere e importare direttamente i [!UICONTROL Data Transfer] file e [!UICONTROL Match Table] i file. L&#39;importazione di questi file è a carico del cliente.

Tuttavia, la procedura di configurazione è documentata correttamente nella Guida [di doubleclick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Inoltre, potete esaminare i passaggi elencati di seguito per iniziare.

>[!CAUTION]
>
>I file di dati DCM contengono dati per tutti gli inserzionisti o i client. Se è necessario omettere client specifici, è necessario modificare i file prima [!DNL Audience Manager]di renderli disponibili.

## Frequenza e disponibilità di trasferimento dati

[!DNL Audience Manager] controlla e trasferisce i dati una volta ogni giorno. In genere, i dati sono disponibili [!DNL Audience Manager] dopo 24 ore.

## Passaggi

1. [Create un gruppo](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   I gruppi controllano l&#39;accesso ai dati DCM. Dopodiché verrà invitato e aggiunto [!DNL Audience Manager] a questo gruppo.

1. [Verifica lo stato di archiviazione Google Cloud](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage contiene il bucket dati che contiene [!UICONTROL Data Transfer] e [!UICONTROL Match Tables]. È necessario impostare un bucket o verificare che il nuovo gruppo abbia accesso a un bucket esistente.

1. [Ottenere un URL del file di dati](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Lavora con il tuo DCM Account Manager o consulente soluzioni piattaforma. Essi forniranno un URL ai file di dati. [!DNL Google] potrebbe modificare il formato di bucket e nomi dei file in rilasci futuri. Di nuovo, collabora con il tuo account manager DCM per accertarti di usare i formati giusti.

1. [Imposta le autorizzazioni di bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Consente [!DNL Cloud Storage Manager] di controllare la condivisione dei dati e l&#39;accesso a un bug. Assegnate al gruppo l&#39;accesso al bucket che contiene i [!UICONTROL Data Transfer][!UICONTROL Match Table] vostri e i file.

1. [Configurare la condivisione dei dati](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Gli ID utente DCM condivisi sono crittografati per proteggere la privacy. La crittografia aggiunge 2 colonne alla fine del file di trasferimento dati e `PartnerId1``PartnerId2`. Queste colonne contengono ID utente codificati specifici per ogni società che riceve questi file.

   In qualità di terze parti autorizzato [!DNL Audience Manager] , può ricevere dati DCM, ma non decodificare gli ID. Tuttavia, a [!DNL Audience Manager] parte, sappiamo in che modo gli ID codificati corrispondono ai nostri ID. Ciò significa che possiamo abbinare e sincronizzare utenti con confidenza e precisione.

   >[!NOTE]
   >Non potete importare file DCM in [!DNL Audience Manager] se state già condividendo dati con altri 2 partner di terze parti.

1. Invita [!DNL Audience Manager] a partecipare al gruppo.

   Dopo aver creato un gruppo e fornito l&#39;accesso a un bucket dati, invita [!DNL Audience Manager] a partecipare al gruppo. Inviate un messaggio e-mail a DFA-AAM@adobe.com. Accertatevi di includere l&#39;URL del file di dati dal passaggio 3. I team interni collaboreranno con te per verificare l&#39;accesso dopo l&#39;accettazione dell&#39;invito. 1. Configura due origini dati per i dati DCM nell&#39;interfaccia [!DNL Audience Manager] utente.

   Denominate le origini `Advertiser Analytics: DCM Platform` dati e `Advertiser Analytics: AAM+DCM Platform`. Nel flusso di lavoro [Crea origini](../../../features/manage-datasources.md#create-data-source) dati, imposta il tipo ID su `Cookie`. Condividi gli ID delle due nuove sorgenti dati con i nostri team interni.

1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. Consultate [File di registro fruibili](../../../integration/media-data-integration/actionable-log-files.md) e chiedere al [!DNL Audience Manager] consulente o all&#39;Assistenza clienti di abilitare la funzionalità.
