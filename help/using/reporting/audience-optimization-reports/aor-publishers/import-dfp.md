---
description: Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.
seo-description: Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.
seo-title: Importazione di file di dati DFP in Audience Manager
solution: Audience Manager
title: Importazione di file di dati DFP in Audience Manager
uuid: c 685 f 34 f -3 e 50-4 c 4 b -99 fa-d 8 bbafe 0 b 268
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Importazione di file di dati DFP in Audience Manager{#import-dfp-data-files-into-audience-manager}

Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.

## Prerequisites for DFP Log Ingestion {#prereqs-dfp-ingestion}

Note that the process described in this section must be completed *before* you move on to the prerequisites for log ingestion enablement.

In order to use DFP ( [!DNL DoubleClick For Publishers]) log files in [!DNL Audience Manager], you must first set our [Audience Manager Unique User ID (UUID)](../../../reference/ids-in-aam.md) in the ad tag call. By doing this, our ID is included in the DFP logs and we can match IDs between DFP and [!DNL Audience Manager]. Use [!DNL Audience Manager] [!UICONTROL DIL] code or the [!UICONTROL Audience Management Module] to set the [!DNL Audience Manager] UUID in a first party cookie.

Here is how to set the [!DNL Audience Manager] ID in the ad tag call, as explained in our documentation:

* [Tramite Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [Tramite una destinazione cookie](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

You need to set the [!DNL Audience Manager] ID yourself, and can work with [!DNL Audience Manager] consulting to check if everything works. You have set the [!DNL Audience Manager] ID correctly if:

* `'aamid'` è la chiave utilizzata come identificatore.
* The User ID value is correctly formatted as the [!DNL Audience Manager] UUID, as described in our [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md).
* You have included the [!DNL Audience Manager] UUID in a defined field in your DFP logs (e.g. CustomTargeting).

## Prerequisites for Log Ingestion Enablement {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Confirm that the required steps to set the <span class="keyword"> Audience Manager</span> UUID (outlined above) have been completed prior to moving to Step 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Assistenza</span> clienti di Audience Manager o consulenza </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 2 </p> </td> 
   <td colname="col2"> <p>L'amministratore DFP crea: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">A service account for ingesting DFP logs into <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nuove credenziali. <p>Nota: Questo potrebbe richiedere un indirizzo e-mail univoco specifico per questo progetto e verrà utilizzato durante il provisioning di accesso al bug di Google Storage. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Una chiave privata (credenziale basata su JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Amministratore DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 3 </p> </td> 
   <td colname="col2"> <p>L'amministratore DFP concede l'accesso API all'account di servizio. Questo passaggio consente di accedere ai metadati per delineare le dimensioni (elementi della riga, ordini, creativi). <p>Nota: Utilizzate l'accesso e-mail dell'account del servizio configurato al passaggio 2 per concedere l'autorizzazione ad accedere all'API. </p> </p> </td> 
   <td colname="col3"> <p>Amministratore DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 4 </p> </td> 
   <td colname="col2"> <p>L'amministratore DFP stabilisce l'accesso al bug di Google Storage. Ricorda: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Questo può essere eseguito tramite un gruppo Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associate l'indirizzo e-mail univoco assegnato all'account di servizio al bucket dell'archivio. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Amministratore DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 5 </p> </td> 
   <td colname="col2"> <p>L'amministratore DFP fornisce l'ID di rete DFP. Questo ci consente di trasmettere l'ID rete quando effettua chiamate all'API. </p> </td> 
   <td colname="col3"> <p>Amministratore DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 6 </p> </td> 
   <td colname="col2"> <p>Compila i prerequisiti in un messaggio e-mail all'Assistenza clienti AAM (aamsupport@adobe.com) per disattivare il processo di inserimento di registro. Preparate il messaggio e-mail utilizzando il modello nella sezione successiva. </p> </td> 
   <td colname="col3"> <p>You, or <span class="keyword"> Audience Manager</span> Consulting on your behalf </p> </td> 
  </tr> 
 </tbody> 
</table>

## E-Mail Template {#email-template}

Per finalizzare l'abilitazione dell'assimilazione del registro, inviateci un messaggio e-mail a aamsupport@adobe.com. Please use the [attached e-mail template](assets/enable_dfp_ingestion.txt).
