---
description: Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importare File Di Dati Di Google Ad Manager In Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 11%

---

# Importare file di dati di Google Ad Manager (precedentemente DFP) in Audience Manager{#import-dfp-data-files-into-audience-manager}

Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.

## Prerequisiti per l’acquisizione del registro di Google Ad Manager {#prereqs-dfp-ingestion}

Tieni presente che il processo descritto in questa sezione deve essere completato *prima* di passare ai prerequisiti per l&#39;abilitazione dell&#39;acquisizione del registro.

Per utilizzare i file di registro [!DNL Google Ad Manager] (precedentemente Google DFP) in [!DNL Audience Manager], devi prima impostare il [ID utente univoco di Audience Manager (UUID)](../../../reference/ids-in-aam.md) nella chiamata del tag annuncio. In questo modo, il nostro ID viene incluso nei registri [!DNL Google Ad Manager] e possiamo far corrispondere gli ID tra [!DNL Google Ad Manager] e [!DNL Audience Manager]. Utilizza il codice [!DNL Audience Manager] [!UICONTROL DIL] o [!UICONTROL Audience Management Module] per impostare l&#39;UUID [!DNL Audience Manager] in un cookie di prima parte.

Di seguito è illustrato come impostare l&#39;ID [!DNL Audience Manager] nella chiamata del tag annuncio, come illustrato nella documentazione:

* [Tramite il tag publisher di Google (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Tramite una destinazione cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Devi impostare l&#39;ID [!DNL Audience Manager] autonomamente e puoi collaborare con la consulenza di [!DNL Audience Manager] per verificare se tutto funziona. L&#39;ID [!DNL Audience Manager] è stato impostato correttamente se:

* `'aamid'` è la chiave utilizzata come identificatore.
* Il valore ID utente è formattato correttamente come UUID [!DNL Audience Manager], come descritto nel nostro [Indice degli ID in Audience Manager](../../../reference/ids-in-aam.md).
* Hai incluso l&#39;UUID [!DNL Audience Manager] in un campo definito nei tuoi registri [!DNL Google Ad Manager] (ad esempio, CustomTargeting).

## Prerequisiti per l’abilitazione dell’acquisizione del registro {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Verificare che i passaggi necessari per impostare l'UUID di Audience Manager<span class="keyword"> </span> (descritti in precedenza) siano stati completati prima di passare al passaggio 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Assistenza clienti o consulenza Audience Manager</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 2 </p> </td> 
   <td colname="col2"> <p>L'amministratore di Google Ad Manager crea: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Un account di servizio per l'acquisizione di Google Ad Manager accede a <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nuove credenziali. <p>Nota: questo potrebbe richiedere un indirizzo e-mail univoco specifico per questo progetto e verrà utilizzato durante il provisioning dell’accesso al bucket di archiviazione Google. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Una chiave privata (credenziali basate su JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Il tuo amministratore di Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 3 </p> </td> 
   <td colname="col2"> <p>L’amministratore di Google Ad Manager concede l’accesso API all’account del servizio. Questo passaggio consente di accedere ai metadati per delineare le dimensioni (elementi riga, ordini, creatività). <p>Nota: utilizza l’accesso e-mail all’account di servizio configurato nel passaggio 2 per concedere le autorizzazioni di accesso all’API. </p> </p> </td> 
   <td colname="col3"> <p>Il tuo amministratore di Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 4 </p> </td> 
   <td colname="col2"> <p>L'amministratore di Google Ad Manager stabilisce l'accesso al bucket di archiviazione Google. Ricorda: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Questa operazione può essere eseguita tramite un gruppo Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associa l’indirizzo e-mail univoco assegnato all’account di servizio al bucket di archiviazione. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Il tuo amministratore di Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 5 </p> </td> 
   <td colname="col2"> <p>L'amministratore di Google Ad Manager fornisce l'ID di rete di Google Ad Manager. Questo ci consente di passare l’ID di rete quando effettuiamo chiamate all’API. </p> </td> 
   <td colname="col3"> <p>Il tuo amministratore di Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 6 </p> </td> 
   <td colname="col2"> <p>Compila i prerequisiti e apri un ticket di supporto seguendo le istruzioni dettagliate <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">qui</a> per avviare il processo di acquisizione del registro. </p> </td> 
   <td colname="col3"> <p>Tu o <span class="keyword"> Audience Manager</span> Consulting per tuo conto </p> </td> 
  </tr> 
 </tbody> 
</table>
