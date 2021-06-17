---
description: Gli strumenti di gestione in blocco consentono di creare e gestire più oggetti contemporaneamente con un’unica operazione. Puoi utilizzare gli strumenti di gestione in blocco per lavorare con origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.
keywords: baaam;BAAAM;scaricare baaam
seo-description: Gli strumenti di gestione in blocco consentono di creare e gestire più oggetti contemporaneamente con un’unica operazione. Puoi utilizzare gli strumenti di gestione in blocco per lavorare con origini dati, segnali derivati, destinazioni, cartelle, segmenti e caratteristiche.
seo-title: Guida introduttiva alla gestione in blocco
solution: Audience Manager
title: Guida introduttiva alla gestione in blocco
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 911eab2d661907c6f1e2ffc08603d994bd346395
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 3%

---

# Guida introduttiva alla gestione in blocco{#getting-started-with-bulk-management}

[!DNL Bulk Management Tools] consente di creare e gestire più oggetti contemporaneamente con una singola operazione. Puoi utilizzare [!DNL Bulk Management Tools] per lavorare con [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments] e [!UICONTROL traits].

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’interfaccia  [!DNL Audience Manager] utente sono rispettate in  [!UICONTROL Bulk Management Tools].

## Panoramica {#overview}

Questa funzione utilizza un foglio di calcolo [!DNL Microsoft Excel] con macro che eseguono chiamate sicure e autenticate alle API [!DNL Audience Manager]. L’API fornisce i metodi e i servizi che consentono di apportare modifiche in blocco. Non devi sapere come codificare o lavorare con le nostre API per utilizzarle. Il foglio di lavoro contiene intestazioni di colonna e schede che eseguono specifiche funzioni di modifica collettiva. Per apportare modifiche in blocco, è sufficiente aggiungere le intestazioni predefinite a fogli di lavoro specifici, fornire le informazioni che si desidera modificare in blocco e fare clic su un pulsante di azione. Il foglio di lavoro e le API eseguono il resto del lavoro per te.

## Scarica {#download}

Scarica l&#39;ultimo foglio di lavoro **[qui](assets/BAAAM_V2_20210609.xlsm)** (aggiornato da ultimo a giugno 2021).

## Prerequisiti {#prereqs}

Per utilizzare il [!DNL Bulk Management Tools], è necessario quanto segue:

* Il tuo login [!DNL Experience Cloud]. In qualità di cliente, dovresti già disporre di queste credenziali.
* Il foglio di lavoro [!DNL Bulk Management Tools]. [Scarica la versione più recente del ](assets/BAAAM_V2_20200502.xlsm) foglio di lavoro.
* [!DNL Microsoft Excel] in esecuzione su  [!DNL macOS] o a 64 bit  [!DNL Microsoft Windows]. È consigliabile utilizzare l’ultima versione di [!DNL Microsoft Excel].
* Quando si apre il foglio di lavoro, è necessario **abilitare le macro** affinché il [!DNL Bulk Management Tools] funzioni.

## Requisiti e opzioni di autenticazione {#auth-reqs}

Le modifiche in blocco richiedono l’autenticazione. Prima di eseguire qualsiasi azione, è necessario effettuare l&#39;accesso. Poiché il foglio di lavoro effettua chiamate API, è necessario configurarlo per l&#39;autenticazione nell&#39;account utente.

**Requisiti di autenticazione API**

La seconda versione di [!DNL Bulk Management Tools], rilasciata a ottobre 2019, semplifica il processo di autenticazione. I passaggi di autenticazione in questa versione sono descritti di seguito:

1. Apri il foglio di calcolo e passa al foglio **[!UICONTROL Config]**.
2. Seguire i passaggi descritti nel foglio.
   ![](assets/baaam-authentication.png)
3. Dopo aver completato i passaggi, sei autorizzato a apportare modifiche in blocco.

Quando apporti modifiche in blocco, dovrai comunque confermare di essere autorizzato a effettuare le modifiche, ma l’autenticazione API è automatica.

**Opzioni di autenticazione del dominio**

L’autenticazione del dominio consente di testare le richieste in blocco o applicarle direttamente all’account di produzione. L’apporto di modifiche in blocco all’ambiente beta non influisce sull’account di produzione. Le modifiche alla produzione hanno effetto immediato. Il foglio di gestione in serie consente di lavorare nei seguenti ambienti:

* Beta
* Produzione

## Azioni e operazioni {#actions-ops}

Il foglio di lavoro [!UICONTROL Bulk Management Tools] è costituito da pulsanti di autenticazione, schede azioni, pulsanti di azione e una scheda **[!UICONTROL Headers]**. La scheda **[!UICONTROL Headers]** contiene le intestazioni di colonna preformattate utilizzate dalle schede delle azioni. Le schede delle azioni contengono macro che eseguono l&#39;operazione in blocco selezionata. Per eseguire un&#39;operazione in blocco, copiare un set di intestazioni nella scheda azione appropriata, immettere i dati di intestazione e fare clic su un pulsante di azione.

Dopo [l&#39;autenticazione](#auth-reqs), fai clic su un pulsante di azione per iniziare.

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
   <td colname="col1"> <p>Le azioni in blocco vengono visualizzate nelle schede nella parte inferiore del foglio di lavoro e includono: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Richieste </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Aggiornamento </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Creare    </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Stimare </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Elimina </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Gli oggetti modificabili in blocco si trovano nella scheda <b><span class="uicontrol"> Intestazioni</span></b> e includono: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Origini dati</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Segnali derivati</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md">Destinazioni </a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modelli</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Cartelle </a> caratteristiche e cartelle dei segmenti </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md">Segmenti </a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md">Caratteristiche </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio di operazione in blocco**

Ad esempio, diamo un&#39;occhiata a come creare più caratteristiche alla volta. Per creare più caratteristiche in un&#39;operazione collettiva, esegui le seguenti operazioni:

1. Fai clic sulla scheda **[!UICONTROL Headers]** e copia tutte le etichette sotto l&#39;opzione [!UICONTROL Create a Trait] .
2. Fare clic sulla scheda **[!UICONTROL Create]** e incollare le etichette a partire dalla riga 1, colonna A.
3. Fornisci informazioni relative a ciascuna intestazione di colonna e fai clic su **[!UICONTROL Create Traits]**. Questa azione richiede di confermare l’autenticazione. Il processo di massa viene eseguito dopo aver confermato l’autenticazione. Selezionare l&#39;angolo in basso a sinistra del foglio di lavoro per una notifica dello stato del processo.


>[!NOTE]
>
>Quando si utilizzano richieste di grandi dimensioni, il foglio di lavoro potrebbe non rispondere e apparire inattivo. In questi casi, lascialo in pace. Il foglio di lavoro diventerà reattivo al termine della richiesta di massa. Se il foglio di lavoro non risponde per un lungo periodo di tempo, vedere la sezione [risoluzione dei problemi](../../reference/bulk-management-tools/bulk-troubleshooting.md).
