---
description: Gli strumenti di gestione di massa consentono di creare e gestire più oggetti contemporaneamente con un'unica operazione. Puoi utilizzare Strumenti di gestione di massa per lavorare con origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.
keywords: baaam;BAAAM;download baaam
seo-description: Gli strumenti di gestione di massa consentono di creare e gestire più oggetti contemporaneamente con un'unica operazione. Puoi utilizzare Strumenti di gestione di massa per lavorare con origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.
seo-title: Guida introduttiva alla gestione in blocco
solution: Audience Manager
title: Guida introduttiva alla gestione in blocco
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 3%

---


# Guida introduttiva alla gestione in blocco{#getting-started-with-bulk-management}

[!DNL Bulk Management Tools] consente di creare e gestire più oggetti contemporaneamente con una singola operazione. È possibile utilizzare [!DNL Bulk Management Tools] per lavorare con [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments] e [!UICONTROL traits].

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’interfaccia  [!DNL Audience Manager] utente sono rispettate nella  [!UICONTROL Bulk Management Tools].

## Panoramica {#overview}

Questa funzione utilizza un foglio di calcolo [!DNL Microsoft Excel] con macro che eseguono chiamate sicure e autenticate alle [!DNL Audience Manager] API. L&#39;API fornisce i metodi e i servizi che consentono di apportare modifiche in blocco. Non devi sapere come codificare o lavorare con le nostre API per utilizzarle. Il foglio di lavoro contiene intestazioni e schede di colonna che eseguono specifiche funzioni di modifica collettiva. Per apportare modifiche collettive, è sufficiente aggiungere le intestazioni predefinite a fogli di lavoro specifici, fornire le informazioni che si desidera modificare in massa e fare clic su un pulsante di azione. Il foglio di lavoro e le API eseguono il resto del lavoro.

## Scarica {#download}

Scarica il foglio di lavoro più recente **[qui](assets/BAAAM_V2_20200502.xlsm)**.

## Prerequisiti {#prereqs}

Per utilizzare il [!DNL Bulk Management Tools], è necessario disporre dei seguenti elementi:

* Login [!DNL Experience Cloud]. In qualità di cliente, dovreste già avere queste credenziali.
* Il foglio di lavoro [!DNL Bulk Management Tools]. [Scarica la versione più recente del ](assets/BAAAM_V2_20200502.xlsm) foglio di lavoro.
* [!DNL Microsoft Excel] con  [!DNL macOS] o a 64 bit  [!DNL Microsoft Windows]. È consigliabile utilizzare la versione più recente di [!DNL Microsoft Excel].
* Quando si apre il foglio di lavoro, è necessario **abilitare Macros** affinché [!DNL Bulk Management Tools] funzioni.

## Requisiti e opzioni di autenticazione {#auth-reqs}

Le modifiche di massa richiedono l&#39;autenticazione. Prima di eseguire qualsiasi azione, è necessario effettuare il login. Poiché il foglio di lavoro esegue chiamate API, è necessario configurarlo per l&#39;autenticazione nell&#39;account utente.

**Requisiti di autenticazione API**

La seconda versione di [!DNL Bulk Management Tools], rilasciata a ottobre 2019, semplifica il processo di autenticazione. I passaggi di autenticazione di questa versione sono descritti di seguito:

1. Aprite il foglio di calcolo e passate al foglio **[!UICONTROL Config]**.
2. Seguire i passaggi descritti nel foglio.
   ![](assets/baaam-authentication.png)
3. Dopo aver completato i passaggi, siete autorizzati a apportare modifiche collettive.

Durante le modifiche di massa, dovrete comunque confermare di essere autorizzati a effettuare le modifiche, ma l&#39;autenticazione API è automatica.

**Opzioni di autenticazione del dominio**

L&#39;autenticazione del dominio consente di sottoporre a test le richieste in massa o di applicarle direttamente al proprio account di produzione. Apportare modifiche collettive all&#39;ambiente Beta non influirà sull&#39;account di produzione. Le modifiche alla produzione diventano immediatamente effettive. Il foglio di gestione di massa consente di lavorare nei seguenti ambienti:

* Beta
* Produzione

## Azioni e operazioni {#actions-ops}

Il foglio di lavoro [!UICONTROL Bulk Management Tools] è costituito da pulsanti di autenticazione, schede azioni, pulsanti di azione e una scheda **[!UICONTROL Headers]**. La scheda **[!UICONTROL Headers]** contiene le intestazioni di colonna preformattate utilizzate dalle schede delle azioni. Le schede delle azioni contengono macro che eseguono l&#39;operazione in blocco selezionata. Per eseguire un&#39;operazione in blocco, copiare un set di intestazioni nella scheda delle azioni appropriata, immettere i dati dell&#39;intestazione e fare clic su un pulsante di azione.

Dopo [l&#39;autenticazione](#auth-reqs), fare clic su un pulsante di azione per iniziare.

![](assets/baaam-worksheet.png)

Nella tabella seguente sono elencate le operazioni che è possibile eseguire e gli elementi che è possibile manipolare con i fogli di lavoro [!UICONTROL Bulk Management Tools].

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
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md">Destinazioni </a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modelli</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Cartelle caratteristiche e </a> cartelle segmenti </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md">Segmenti </a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md">Caratteristiche </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio di operazione in blocco**

Ad esempio, vediamo come creare più caratteristiche contemporaneamente. Per creare più caratteristiche in un&#39;operazione in blocco, è necessario:

1. Fare clic sulla scheda **[!UICONTROL Headers]** e copiare tutte le etichette sotto l&#39;opzione [!UICONTROL Create a Trait].
2. Fare clic sulla scheda **[!UICONTROL Create]** e incollare le etichette a partire dalla riga 1, colonna A.
3. Fornire informazioni relative a ciascuna intestazione di colonna e fare clic su **[!UICONTROL Create Traits]**. Questa azione richiede di confermare l’autenticazione. Il processo di massa viene eseguito dopo aver confermato l’autenticazione. Verificare che nell&#39;angolo inferiore sinistro del foglio di lavoro sia presente una notifica dello stato del processo.


>[!NOTE]
>
>Quando si utilizzano richieste di grandi dimensioni, il foglio di lavoro potrebbe non rispondere e risultare inattivo. In questi casi, lasciamo perdere. Il foglio di lavoro diventa reattivo al completamento della richiesta in blocco. Se il foglio di lavoro non risponde per un lungo periodo di tempo, vedere la sezione [risoluzione dei problemi](../../reference/bulk-management-tools/bulk-troubleshooting.md).

