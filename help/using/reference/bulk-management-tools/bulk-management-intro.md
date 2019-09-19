---
description: Gli strumenti di gestione di massa consentono di creare e gestire più oggetti contemporaneamente con un'unica operazione. Puoi utilizzare Strumenti di gestione di massa per lavorare con origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.
keywords: baam;BAAAM
seo-description: Gli strumenti di gestione di massa consentono di creare e gestire più oggetti contemporaneamente con un'unica operazione. Puoi utilizzare Strumenti di gestione di massa per lavorare con origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.
seo-title: Guida Introduttiva Alla Gestione Di Gruppi
solution: Audience Manager
title: Guida Introduttiva Alla Gestione Di Gruppi
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
translation-type: tm+mt
source-git-commit: 215054718e9248bd44ba99baeb2a10236701d98e

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

Gli strumenti di gestione di massa consentono di creare e gestire più oggetti contemporaneamente con un'unica operazione. Puoi utilizzare Strumenti di gestione di massa per lavorare con origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>Le [!UICONTROL Bulk Management Tools] opzioni non *sono supportate da* [!DNL Audience Manager]. Questo strumento è fornito per comodità e solo come cortesia. Per modifiche di massa, consigliamo di lavorare con le API [](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

## Panoramica {#overview}

Questa funzione utilizza un foglio di calcolo di Microsoft Excel con macro che eseguono chiamate sicure e autenticate alle [!DNL Audience Manager] API. L'API fornisce i metodi e i servizi che consentono di apportare modifiche in blocco. Non è necessario sapere come codificare o utilizzare le nostre API. Il foglio di lavoro contiene intestazioni e schede di colonna che eseguono specifiche funzioni di modifica collettiva. Per apportare modifiche collettive, è sufficiente aggiungere le intestazioni predefinite a fogli di lavoro specifici, fornire le informazioni che si desidera modificare in massa e fare clic su un pulsante di azione. Il foglio di lavoro e le API eseguono il resto del lavoro.

## Scarica {#download}

Scarica il foglio di lavoro più recente **[qui](assets/BAAAM_August_2018.xlsm)**.

## Prerequisiti {#prereqs}

Per utilizzare il [!DNL Bulk Management Tools], è necessario disporre dei seguenti elementi:

* Nome [!DNL Audience Manager] utente e password. In qualità di cliente, dovreste già avere queste credenziali.
* ID client API e chiave segreta. Il tuo account manager può fornirti queste informazioni.
* Il [!UICONTROL Bulk Management Tools] foglio di lavoro. [Scaricate il foglio di lavoro](/help/using/reference/bulk-management-tools/bulk-management-intro.md#download) per ottenere la versione più recente.

* Microsoft Excel in esecuzione su [!DNL Windows] o in una [!DNL Microsoft Windows] macchina virtuale in esecuzione su [!DNL macOS X]. Per poter [!UICONTROL Bulk Management Tools] funzionare è necessario utilizzare Excel a 32 bit.

## Azioni e operazioni {#actions-ops}

Il [!UICONTROL Bulk Management Tools] foglio di lavoro è costituito da schede di azioni, pulsanti di azione e una **[!UICONTROL Headers]** scheda. La **[!UICONTROL Headers]** scheda contiene le intestazioni di colonna preformattate utilizzate dalle schede delle azioni. Le schede delle azioni contengono macro che eseguono l'operazione in blocco selezionata. Per eseguire un'operazione in blocco, copiare un set di intestazioni nella scheda delle azioni appropriata, immettere i dati dell'intestazione e fare clic su un pulsante di azione.

Aprite il foglio di calcolo e fate clic su un pulsante di azione per iniziare.

![](assets/bamwrkbk.png)

Nella tabella seguente sono elencate le operazioni che è possibile eseguire e gli elementi che è possibile manipolare con i [!UICONTROL Bulk Management Tools] fogli di lavoro.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Azioni </th> 
   <th colname="col2" class="entry"> Oggetti </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Le azioni di massa vengono visualizzate nelle schede nella parte inferiore del foglio di lavoro e includono: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Richieste </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Aggiornamento </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Creare    </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Stima </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Elimina </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Gli oggetti che è possibile modificare in blocco si trovano nella scheda <b><span class="uicontrol"> Intestazioni</span></b> e includono: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Origini dati</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Segnali derivati</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Destinazioni</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Cartelle</a> caratteristiche e cartelle segmenti </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segmenti</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Caratteristiche</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio di operazione in blocco**

Ad esempio, vediamo come creare più caratteristiche contemporaneamente. Per creare più caratteristiche in un'operazione in blocco, è necessario:

1. Fare clic sulla **[!UICONTROL Headers]** scheda e copiare tutte le etichette sotto l' [!UICONTROL Create a Trait] opzione.

2. Fare clic sulla **[!UICONTROL Create]** scheda e incollare le etichette a partire dalla riga 1, colonna A.
3. Fornire informazioni relative a ciascuna intestazione di colonna e fare clic su **[!UICONTROL Create Traits]**. Questa azione richiede di effettuare l’accesso. Il processo di massa viene eseguito dopo l’autenticazione (vedete i requisiti [di](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) autenticazione indicati di seguito). Verificare che nell'angolo inferiore sinistro del foglio di lavoro sia presente una notifica dello stato del processo.

>[!NOTE]
>
>Quando si utilizzano richieste di grandi dimensioni, il foglio di lavoro potrebbe non rispondere e risultare inattivo. In questi casi, lasciamo perdere. Il foglio di lavoro diventa reattivo al completamento della richiesta in blocco. Se il foglio di lavoro non risponde per un lungo periodo di tempo, consultare la sezione [](../../reference/bulk-management-tools/bulk-troubleshooting.md)Risoluzione dei problemi.

## Requisiti e opzioni di autenticazione {#auth-reqs}

Le modifiche di massa richiedono l'autenticazione. Quando si seleziona un'azione, il foglio di lavoro richiede di eseguire il login. Poiché il foglio di lavoro esegue chiamate API, è necessario configurarlo per leggere la chiave segreta. Inoltre, il **[!UICONTROL Domain]** campo consente di apportare modifiche collettive in un ambiente di verifica/staging o nell’account di produzione live.

![](assets/bamauth.png)

**Requisiti di autenticazione API**

Per impostare l'autenticazione API, dovete:

* Copiate e salvate la chiave segreta in un file di testo (.txt).
* Denominate il file di testo con il vostro ID client API. Ad esempio, se l’ID client è "Bulk-User", salvate la chiave in un file denominato "Bulk-User.txt".
* Salvare la chiave segreta e il foglio di lavoro insieme nella stessa cartella.

Durante le modifiche di massa, dovrete comunque immettere un nome utente, una password, un ID client e un dominio, ma l'autenticazione API è automatica.

**Opzioni di autenticazione del dominio**

L'autenticazione del dominio consente di sottoporre a test le richieste in massa o di applicarle direttamente al proprio account di produzione. Le modifiche di massa all'ambiente di test non influiranno sull'account di produzione. Le modifiche alla produzione diventano immediatamente effettive. Il **[!UICONTROL Domain]** campo accetta i seguenti indirizzi, a seconda dell'ambiente in cui si desidera lavorare:

* Test: `api-beta.demdex.com`
* Produzione: `api.demdex.com`

>[!MORE_LIKE_this]
>
>* [Scarica il foglio di lavoro Gestione di massa](assets/BAAAM_August_2018.xlsm)

