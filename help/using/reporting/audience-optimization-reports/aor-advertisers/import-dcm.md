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


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurate un gruppo Google per trasferire i file di dati doubleclick Campaign Manager (DCM) in Audience Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti a risorse DCM per aiutarti a iniziare.

## Riepilogo integrazione

DCM è la soluzione [!DNL Google] che sostituisce [!DNL DoubleClick for Advertisers] (DFA). In modo analogo a DFA, i clienti DCM possono importare, visualizzare e lavorare con i loro dati in [!DNL Audience Manager]. But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. L'importazione di questi file è a carico del cliente.

However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). Inoltre, potete esaminare i passaggi elencati di seguito per iniziare.

>[!CAUTION]
>
>I file di dati DCM contengono dati per tutti gli inserzionisti o i client. If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager].

## Frequenza e disponibilità di trasferimento dati

[!DNL Audience Manager] controlla e trasferisce i dati una volta ogni giorno. Data is usually available in [!DNL Audience Manager] after 24-hours.

## Passaggi

1. [Create un gruppo](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   I gruppi controllano l'accesso ai dati DCM. Eventually, you'll invite and add [!DNL Audience Manager] to this group.

1. [Verifica lo stato di archiviazione Google Cloud](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. È necessario impostare un bucket o verificare che il nuovo gruppo abbia accesso a un bucket esistente.

1. [Ottenere un URL del file di dati](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Lavora con il tuo DCM Account Manager o consulente soluzioni piattaforma. Essi forniranno un URL ai file di dati. [!DNL Google] potrebbe modificare il formato di bucket e nomi dei file in rilasci futuri. Di nuovo, collabora con il tuo account manager DCM per accertarti di usare i formati giusti.

1. [Imposta le autorizzazioni di bucket](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   The [!DNL Cloud Storage Manager] lets you control data sharing and bucket access. Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files.

1. [Configurare la condivisione dei dati](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Gli ID utente DCM condivisi sono crittografati per proteggere la privacy. Encryption adds 2 columns to the end of your Data Transfer file, `PartnerId1` and `PartnerId2`. Queste colonne contengono ID utente codificati specifici per ogni società che riceve questi file.

   As an authorized third-party, [!DNL Audience Manager] can receive DCM data, but cannot decode the IDs. However, on the [!DNL Audience Manager] side, we know how the encoded IDs match our IDs. Ciò significa che possiamo abbinare e sincronizzare utenti con confidenza e precisione.

   >[!NOTE]
   >You cannot import DCM files into [!DNL Audience Manager] if you're already sharing data with 2 other third-party partners.

1. Invite [!DNL Audience Manager] to join the group.

   After you create a group and give it access to a data bucket, invite [!DNL Audience Manager] to join the group. Inviate un messaggio e-mail a DFA-AAM@adobe.com. Accertatevi di includere l'URL del file di dati dal passaggio 3. I team interni collaboreranno con te per verificare l'accesso dopo l'accettazione dell'invito. 1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   Name the data sources `Advertiser Analytics: DCM Platform` and `Advertiser Analytics: AAM+DCM Platform`. In the [Create Data Sources](../../../features/manage-datasources.md#create-data-source) workflow, set the ID type to `Cookie`. Condividi gli ID delle due nuove sorgenti dati con i nostri team interni.

1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. See [Actionable Log Files](../../../integration/media-data-integration/actionable-log-files.md) and ask your [!DNL Audience Manager] consultant or Customer Care to enable the feature for you.
