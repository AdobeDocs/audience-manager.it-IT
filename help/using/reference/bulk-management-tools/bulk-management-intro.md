---
description: Gli strumenti Gestione massa consentono di creare e gestire più oggetti contemporaneamente con un'unica operazione. Puoi usare Strumenti di gestione collettiva per lavorare con sorgenti dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.
keywords: baaam; BAAAM
seo-description: Gli strumenti Gestione massa consentono di creare e gestire più oggetti contemporaneamente con un'unica operazione. Puoi usare Strumenti di gestione collettiva per lavorare con sorgenti dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.
seo-title: Guida introduttiva alla gestione collettiva
solution: Audience Manager
title: Guida introduttiva alla gestione collettiva
uuid: 4 bc 6 ae 0 a -315 c -4 ce 7-a 68 e-cc 0 c 6 c 6 aa 2 f 1
translation-type: tm+mt
source-git-commit: f6fd1b99467a35b3f2c978c4b2e28d562eaa3c52

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

Gli strumenti Gestione massa consentono di creare e gestire più oggetti contemporaneamente con un'unica operazione. Puoi usare Strumenti di gestione collettiva per lavorare con sorgenti dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell' [!DNL Audience Manager] interfaccia utente vengono rispettate nell' [!UICONTROL Bulk Management Tools]interfaccia.

## Panoramica {#overview}

This feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs. L'API fornisce i metodi e i servizi che consentono di apportare modifiche in gruppo. Non è necessario conoscere il codice o lavorare con le API per utilizzarlo. Il foglio di lavoro contiene intestazioni di colonna e schede che consentono di modificare in massa specifiche funzioni. Per apportare modifiche collettive, basta aggiungere le intestazioni predefinite a fogli di lavoro specifici, fornire le informazioni che si desidera modificare in gruppo e fare clic sul pulsante di azione. Il foglio di lavoro e le API elaborano il resto del lavoro.

## Prerequisiti {#prereqs}

To use the [!DNL Bulk Management Tools], you need the following:

* Your [!DNL Audience Manager] user name and password. In qualità di cliente, devi già disporre di queste credenziali.
* Un ID client API e una chiave segreta. Il vostro account manager può fornirvi questi.
* The [!UICONTROL Bulk Management Tools] worksheet. **[Scarica il foglio di lavoro](assets/BAAAM_August_2018.xlsm)** per ottenere la versione più recente.

* Microsoft Excel running on [!DNL Windows] or in a [!DNL Microsoft Windows] virtual machine running on [!DNL macOS X]. You must use 32-bit Excel for the [!UICONTROL Bulk Management Tools] to work.

## Actions and operations {#actions-ops}

[!UICONTROL Bulk Management Tools] Il foglio di lavoro è costituito da schede action, pulsanti di azione e **[!UICONTROL Headers]** schede. The **[!UICONTROL Headers]** tab contains the pre-formatted column headers used by the action tabs. Le schede delle azioni contengono macro che eseguono l'operazione di massa selezionata. Per eseguire un'operazione in blocco, copiate un set di intestazioni nella scheda dell'azione appropriata, immettete i dati dell'intestazione e fate clic sul pulsante di azione.

Aprite il foglio di calcolo e fate clic sul pulsante di un'azione per iniziare.

![](assets/bamwrkbk.png)

The table below lists the operations you can perform and items you can manipulate with the [!UICONTROL Bulk Management Tools] worksheets.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Azioni </th> 
   <th colname="col2" class="entry"> Oggetti </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Le azioni in blocco appaiono nelle schede nella parte inferiore del foglio di lavoro e includono: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Richieste </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Aggiornamento </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Creare    </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Stima </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Elimina </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>The objects you can change in bulk are located under the <b><span class="uicontrol"> Headers</span></b> tab and include: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Origini dati</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Segnali derivati</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Destinazioni</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Cartelle</a> di caratteristiche e segmenti </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segmenti</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Caratteristiche</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio di operazione in blocco**

Ad esempio, vediamo come creare più caratteristiche contemporaneamente. Per creare più caratteristiche in un'operazione in blocco, è possibile:

1. Click the **[!UICONTROL Headers]** tab and copy all the labels under the [!UICONTROL Create a Trait] option.

2. Click the **[!UICONTROL Create]** tab and paste the labels starting in row 1, column A.
3. Provide information related to each column header and click **[!UICONTROL Create Traits]**. Questa azione richiede l'accesso. Your bulk job runs after you successfully authenticate (see the [authentication requirements](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) below). Controllate l'angolo inferiore sinistro del foglio di lavoro per una notifica di stato del processo.

>[!NOTE]
>
>Quando si lavora con richieste di grandi dimensioni, il foglio di lavoro potrebbe non rispondere e sembrare inattivo. In questi casi, lasciateli soli. Il foglio di lavoro diventa reattivo quando la richiesta di massa sarà completa. If the worksheet does not respond for a long period of time, see the [troubleshooting section](../../reference/bulk-management-tools/bulk-troubleshooting.md).

## Authentication requirements and options {#auth-reqs}

Le modifiche di massa richiedono l'autenticazione. Quando selezionate un'azione, il foglio di lavoro richiede di effettuare l'accesso. Poiché il foglio di lavoro effettua chiamate API, devi configurarlo per la lettura della chiave segreta. And, the **[!UICONTROL Domain]** field lets you make bulk changes in a staging/test environment or against your live, production account.

![](assets/bamauth.png)

**Requisiti di autenticazione API**

Per configurare l'autenticazione API, devi:

* Copiate e salvate la chiave segreta in un file di testo (.txt).
* Denominate il file di testo con il vostro ID client API. Ad esempio, se l'ID client è «Bulk-User», salvate la chiave in un file denominato «Bulk-User. txt».
* Salvate la chiave segreta e il foglio di lavoro nella stessa cartella.

Quando apportate modifiche in massa, dovete comunque immettere un nome utente, una password, un ID client e un dominio, ma l'autenticazione API è automatica.

**Opzioni di autenticazione del dominio**

L'autenticazione del dominio offre l'opzione di sottoporre a test le richieste in blocco o di applicarle direttamente all'account di produzione. Apportare modifiche in massa all'ambiente di prova non influisce sull'account di produzione. Le modifiche di produzione sono effettive immediatamente. **[!UICONTROL Domain]** Il campo accetta i seguenti indirizzi, a seconda dell'ambiente in cui si desidera lavorare:

* Testing: `api-beta.demdex.com`
* Produzione: `api.demdex.com`

>[!MORE_ LIKE_ THIS]
>
>* [Scaricare il foglio di lavoro di gestione in blocco](assets/BAAAM_August_2018.xlsm)

