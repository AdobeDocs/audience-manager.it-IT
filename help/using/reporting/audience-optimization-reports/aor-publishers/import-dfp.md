---
description: Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.
seo-description: Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.
seo-title: Importa file di dati Google Ad Manager in  Audience Manager
solution: Audience Manager
title: Importa file di dati Google Ad Manager in  Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 15%

---


# Importa file di dati Google Ad Manager (già DFP) in  Audience Manager{#import-dfp-data-files-into-audience-manager}

Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.

## Prerequisiti per l&#39;inserimento del registro di Google Ad Manager {#prereqs-dfp-ingestion}

Tenere presente che il processo descritto in questa sezione deve essere completato *prima di* è necessario passare ai prerequisiti per l&#39;abilitazione dell&#39;assimilazione del registro.

Per utilizzare i file di registro [!DNL Google Ad Manager] (già Google DFP) in [!DNL Audience Manager], è necessario impostare il nostro [ID utente univoco  Audience Manager (UUID)](../../../reference/ids-in-aam.md) nella chiamata del tag dell&#39;annuncio. A tal fine, il nostro ID è incluso nei [!DNL Google Ad Manager] registri e possiamo far corrispondere gli ID tra [!DNL Google Ad Manager] e [!DNL Audience Manager]. Utilizzare il codice [!DNL Audience Manager] [!UICONTROL DIL] o [!UICONTROL Audience Management Module] per impostare l&#39;UUID [!DNL Audience Manager] in un cookie di prime parti.

Di seguito viene illustrato come impostare l&#39;ID [!DNL Audience Manager] nella chiamata del tag dell&#39;annuncio, come spiegato nella nostra documentazione:

* [Tramite Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Tramite una destinazione di cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

È necessario impostare l&#39;ID [!DNL Audience Manager] autonomamente e può essere utilizzato con la consulenza [!DNL Audience Manager] per verificare se tutto funziona. L&#39;ID [!DNL Audience Manager] è stato impostato correttamente se:

* `'aamid'` è la chiave utilizzata come identificatore.
* Il valore ID utente è formattato correttamente come UUID [!DNL Audience Manager], come descritto nel nostro [Indice di ID in  Audience Manager](../../../reference/ids-in-aam.md).
* L&#39;UUID [!DNL Audience Manager] è stato incluso in un campo definito nei registri [!DNL Google Ad Manager] (ad es. CustomTargeting).

## Prerequisiti per l&#39;abilitazione dell&#39;inserimento del registro {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Passaggio </th> 
   <th colname="col2" class="entry"> Dettagli </th> 
   <th colname="col3" class="entry"> Proprietario </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Passaggio 1 </p> </td> 
   <td colname="col2"> <p>Verificare che i passaggi necessari per impostare l'UUID <span class="keyword"> del Audience Manager </span>  (come indicato sopra) siano stati completati prima di passare al passaggio 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience </span> ManagerAssistenza clienti o consulenza </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 2 </p> </td> 
   <td colname="col2"> <p>L'amministratore di Google Ad Manager crea: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Un account di servizio per l'assimilazione di Google Ad Manager accede a <span class="keyword">  Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nuove credenziali. <p>Nota:  Questo può richiedere un indirizzo e-mail univoco specifico per questo progetto e verrà utilizzato quando si effettua il provisioning dell'accesso a Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Una chiave privata (credenziale basata su JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Amministratore Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 3 </p> </td> 
   <td colname="col2"> <p>L'amministratore di Google Ad Manager concede l'accesso API all'account del servizio. Questo passaggio consente di accedere ai metadati per delineare le dimensioni (elementi di linea, ordini, creatività). <p>Nota:  Utilizzate l'accesso e-mail all'account del servizio configurato nel passaggio 2 per concedere l'autorizzazione per l'accesso all'API. </p> </p> </td> 
   <td colname="col3"> <p>Amministratore Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 4 </p> </td> 
   <td colname="col2"> <p>L'amministratore di Google Ad Manager stabilisce l'accesso a Google Storage Bucket. Ricorda: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Questo può essere fatto tramite un gruppo Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associate l'indirizzo e-mail univoco assegnato all'account del servizio al bucket di archiviazione. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Amministratore Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 5 </p> </td> 
   <td colname="col2"> <p>L'amministratore di Google Ad Manager fornisce l'ID di rete Google Ad Manager. Questo ci consente di trasmettere l'ID di rete quando si effettuano chiamate all'API. </p> </td> 
   <td colname="col3"> <p>Amministratore Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 6 </p> </td> 
   <td colname="col2"> <p>Compila i prerequisiti in un messaggio e-mail per AAM l'Assistenza clienti (aamsupport@adobe.com) per avviare il processo di caricamento del registro. Bozza il messaggio e-mail utilizzando il modello nella sezione successiva. </p> </td> 
   <td colname="col3"> <p>L'utente o <span class="keyword">  Audience Manager</span> Consulenza per conto dell'utente </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modello e-mail {#email-template}

Per completare l’abilitazione dell’inserimento del registro, inviateci un messaggio e-mail a aamsupport@adobe.com. Utilizzare il [modello di posta elettronica allegato](assets/enable_dfp_ingestion.txt).
