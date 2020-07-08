---
description: Configurate un gruppo Google per portare i file di dati di Google Campaign Manager  Audience Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti alle risorse di Google Campaign Manager per aiutarti a iniziare.
seo-description: Configurate un gruppo Google per portare i file di dati di Google Campaign Manager  Audience Manager. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti alle risorse di Google Campaign Manager per aiutarti a iniziare.
seo-title: Importa i file di dati di Google Campaign Manager in  Audience Manager
solution: Audience Manager
title: Importa i file di dati di Google Campaign Manager in  Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 3%

---


# Importa i file di dati di Google Campaign Manager in  Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurate un [!DNL Google] gruppo per  i file di [!DNL Google Campaign Manager] dati. Il contenuto di questa sezione riepiloga il processo di integrazione e fornisce collegamenti alle [!DNL Google Campaign Manager] risorse per iniziare a utilizzarlo.

## Riepilogo integrazione

[!DNL Google Campaign Manager] è la soluzione [!DNL Google] che sostituisce [!DNL DoubleClick for Advertisers] (DFA). Similar to DFA, [!DNL Google Campaign Manager] customers can import, view, and work with their data in [!DNL Audience Manager]. Tuttavia [!DNL Audience Manager] non è possibile accedere e importare direttamente i file [!UICONTROL Data Transfer] e [!UICONTROL Match Table] i file. L&#39;importazione di questi file è a carico del cliente.

Tuttavia, la procedura di configurazione è ben documentata nella Guida [di](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)DoubleClick Campaign Manager. Inoltre, puoi consultare i passaggi elencati di seguito per iniziare.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] i file di dati contengono dati per tutti gli inserzionisti o i clienti. Se devi omettere client specifici, devi modificare i file prima di renderli disponibili a [!DNL Audience Manager].

## Frequenza e disponibilità del trasferimento dei dati

[!DNL Audience Manager] verifica e trasferisce i dati una volta al giorno. In genere i dati sono disponibili [!DNL Audience Manager] dopo 24 ore.

## Passaggi

1. [Create un gruppo](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   I gruppi controllano l&#39;accesso ai [!DNL Google Campaign Manager] dati. Alla fine, inviterete e aggiungete [!DNL Audience Manager] a questo gruppo.

1. [Verifica dello stato](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)dell&#39;archiviazione di Google Cloud.

   Google Cloud Storage contiene il bucket di dati che contiene il tuo [!UICONTROL Data Transfer] e [!UICONTROL Match Tables]. Sarà necessario impostare un bucket o assicurarsi che il nuovo gruppo abbia accesso a un bucket di archiviazione dati esistente.

1. [Ottenere l’URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)di un file di dati.

   Consulta il tuo [!DNL Google Campaign Manager] Account Manager o Platform Solutions Consultant. Forniranno un URL ai vostri file di dati. [!DNL Google] potrebbe modificare il formato per i nomi di file e bucket nelle release future. Anche in questo caso, utilizzate il vostro [!DNL Google Campaign Manager] Account Manager per essere certi di usare i formati corretti.

1. [Impostare le autorizzazioni](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)del bucket.

   Consente di [!DNL Cloud Storage Manager] controllare la condivisione dei dati e l&#39;accesso fisso. Consente al gruppo di accedere in lettura al bucket che contiene [!UICONTROL Data Transfer] e [!UICONTROL Match Table] i file.

1. [Configurare la condivisione](https://support.google.com/dcm/partner/answer/6206106?hl=en)dei dati.

   Gli ID [!DNL Google Campaign Manager] utente condivisi sono crittografati per proteggere la privacy. La cifratura aggiunge 2 colonne alla fine del file di trasferimento dati `PartnerId1` e `PartnerId2`. Queste colonne contengono ID utente codificati specifici per ogni società che riceve tali file.

   In qualità di terza parte autorizzata, [!DNL Audience Manager] può ricevere [!DNL Google Campaign Manager] dati, ma non può decodificare gli ID. Tuttavia, dal [!DNL Audience Manager] lato, sappiamo in che modo gli ID codificati corrispondono ai nostri ID. Questo significa che possiamo far corrispondere e sincronizzare gli utenti con sicurezza e precisione.

   >[!NOTE]
   >Non potete importare [!DNL Google Campaign Manager] i file in [!DNL Audience Manager] se state già condividendo dati con altri due partner di terze parti.

1. Invitate [!DNL Audience Manager] a far parte del gruppo.

   Dopo aver creato un gruppo e averlo accesso a un bucket dati, invitate [!DNL Audience Manager] a unirvi al gruppo. Inviate un messaggio e-mail di invito a DFA-AAM@adobe.com. Assicuratevi di includere l&#39;URL del file di dati dal passaggio 3. I nostri team interni collaboreranno con voi per verificare l’accesso dopo l’accettazione dell’invito. 1. Configurate due origini dati per [!DNL Google Campaign Manager] i dati nell&#39;interfaccia [!DNL Audience Manager] utente.

   Denominate le origini dati `Advertiser Analytics: DCM Platform` e `Advertiser Analytics: AAM+DCM Platform`. Nel flusso di lavoro [Crea origini](../../../features/manage-datasources.md#create-data-source) dati, imposta il tipo di ID su `Cookie`. Condividi gli ID delle due nuove origini dati con i nostri team interni.

1. Potete facilmente creare tratti dai [!DNL Google Campaign Manager] file importati in [!DNL Audience Manager]. Consulta File [di registro](../../../integration/media-data-integration/actionable-log-files.md) fruibili e chiedi al tuo [!DNL Audience Manager] consulente o all&#39;Assistenza clienti di abilitare questa funzione.
