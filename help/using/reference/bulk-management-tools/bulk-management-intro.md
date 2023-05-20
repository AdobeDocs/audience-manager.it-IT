---
description: Gli strumenti di gestione in blocco consentono di creare e gestire più oggetti contemporaneamente con una singola operazione. Puoi utilizzare gli Strumenti di gestione in blocco per lavorare con origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.
keywords: baaam;BAAAM;scaricare baaam
seo-description: The Bulk Management Tools let you create and manage multiple objects at once with single operation. You can use Bulk Management Tools to work with data sources, derived signals, destinations, folders, segments, and traits.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: Guida introduttiva alla gestione in blocco
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 911eab2d661907c6f1e2ffc08603d994bd346395
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 3%

---

# Guida introduttiva alla gestione in blocco{#getting-started-with-bulk-management}

Il [!DNL Bulk Management Tools] consente di creare e gestire più oggetti contemporaneamente con una singola operazione. È possibile utilizzare [!DNL Bulk Management Tools] per utilizzare [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments], e [!UICONTROL traits].

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[Autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnato in [!DNL Audience Manager] L&#39;interfaccia utente di è rispettata in [!UICONTROL Bulk Management Tools].

## Panoramica {#overview}

Questa funzione utilizza un [!DNL Microsoft Excel] con macro che eseguono chiamate sicure e autenticate al [!DNL Audience Manager] API. L’API fornisce i metodi e i servizi che consentono di apportare modifiche in blocco. Non devi sapere come programmare o lavorare con le nostre API per utilizzarlo. Il foglio di lavoro contiene intestazioni di colonna e schede che eseguono specifiche funzioni di modifica in blocco. Per apportare modifiche in blocco, è sufficiente aggiungere le intestazioni predefinite a fogli di lavoro specifici, fornire le informazioni che si desidera modificare in blocco e fare clic su un pulsante di azione. Il foglio di lavoro e le API eseguono il resto del lavoro.

## Scarica {#download}

Scarica il foglio di lavoro più recente **[qui](assets/BAAAM_V2_20210609.xlsm)** (aggiornato da ultimo a giugno 2021).

## Prerequisiti {#prereqs}

Per utilizzare [!DNL Bulk Management Tools], sono necessari i seguenti elementi:

* Il tuo [!DNL Experience Cloud] accesso. In qualità di cliente, dovresti già disporre di queste credenziali.
* Il [!DNL Bulk Management Tools] foglio di lavoro. [Scarica il foglio di lavoro](assets/BAAAM_V2_20200502.xlsm) per ottenere la versione più recente.
* [!DNL Microsoft Excel] in esecuzione [!DNL macOS] o a 64 bit [!DNL Microsoft Windows]. È consigliabile utilizzare l&#39;ultima versione di [!DNL Microsoft Excel].
* All&#39;apertura del foglio di lavoro, è necessario **Abilita macro** per [!DNL Bulk Management Tools] al lavoro.

## Requisiti e opzioni di autenticazione {#auth-reqs}

Le modifiche in blocco richiedono l’autenticazione. Prima di eseguire un&#39;azione, è necessario effettuare l&#39;accesso. Poiché il foglio di lavoro effettua chiamate API, devi configurarlo per l’autenticazione nell’account utente.

**Requisiti di autenticazione API**

La seconda versione del [!DNL Bulk Management Tools], rilasciato a ottobre 2019, semplifica il processo di autenticazione. I passaggi di autenticazione in questa versione sono descritti di seguito:

1. Apri il foglio di calcolo e passa alla **[!UICONTROL Config]** foglio.
2. Seguire i passaggi descritti nel foglio.
   ![](assets/baaam-authentication.png)
3. Dopo aver completato i passaggi, sei autorizzato ad apportare modifiche in blocco.

Quando apporti modifiche in blocco, dovrai comunque confermare di essere autorizzato ad apportare le modifiche, ma l’autenticazione API è automatica.

**Opzioni di autenticazione del dominio**

L’autenticazione di dominio consente di verificare le richieste in blocco o di applicarle direttamente all’account di produzione. L’apporto di modifiche in blocco all’ambiente beta non influisce sull’account di produzione. Le modifiche alla produzione diventano effettive immediatamente. Il foglio di gestione in blocco consente di lavorare nei seguenti ambienti:

* Beta
* Produzione

## Azioni e operazioni {#actions-ops}

Il [!UICONTROL Bulk Management Tools] il foglio di lavoro è costituito da pulsanti di autenticazione, schede di azione, pulsanti di azione e un **[!UICONTROL Headers]** scheda. Il **[!UICONTROL Headers]** contiene le intestazioni di colonna preformattate utilizzate dalle schede delle azioni. Le schede delle azioni contengono macro che eseguono l&#39;operazione di massa selezionata. Per eseguire un&#39;operazione di massa, copiare un set di intestazioni nella scheda delle azioni appropriata, immettere i dati dell&#39;intestazione e fare clic su un pulsante di azione.

Dopo [autenticazione](#auth-reqs), fare clic su un pulsante di azione per iniziare.

![](assets/baaam-worksheet.png)

Nella tabella seguente sono elencate le operazioni che è possibile eseguire e gli elementi che è possibile modificare con [!UICONTROL Bulk Management Tools] fogli di lavoro.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Azioni </th> 
   <th colname="col2" class="entry"> Oggetti </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Le azioni collettive vengono visualizzate in schede nella parte inferiore del foglio di lavoro e includono: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Richieste </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Aggiornamento </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Creare    </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Stima </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Elimina </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Gli oggetti che è possibile modificare in blocco si trovano sotto <b><span class="uicontrol"> Intestazioni</span></b> e includono: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Origini dati</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Segnali derivati</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md">Destinazioni </a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modelli</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Cartelle delle caratteristiche</a> cartelle di segmenti e </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md">Segmenti </a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md">Caratteristiche </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio di operazione in blocco**

Ad esempio, vediamo come creare più caratteristiche contemporaneamente. Per creare più caratteristiche in un’operazione in blocco:

1. Fai clic su **[!UICONTROL Headers]** e copiare tutte le etichette sotto [!UICONTROL Create a Trait] opzione.
2. Fai clic su **[!UICONTROL Create]** e incollare le etichette a partire dalla riga 1, colonna A.
3. Fornisci informazioni relative a ciascuna intestazione di colonna e fai clic su **[!UICONTROL Create Traits]**. Questa azione richiede di confermare l’autenticazione. Il processo in blocco viene eseguito dopo la conferma dell’autenticazione. Controllare l&#39;angolo inferiore sinistro del foglio di lavoro per la notifica dello stato di un processo.


>[!NOTE]
>
>Quando si utilizzano richieste di grandi dimensioni, il foglio di lavoro potrebbe non rispondere e apparire inattivo. In questi casi, lascialo stare. Il foglio di lavoro diventerà reattivo al termine della richiesta in blocco. Se il foglio di lavoro non risponde per un periodo di tempo prolungato, vedere [sezione risoluzione dei problemi](../../reference/bulk-management-tools/bulk-troubleshooting.md).
