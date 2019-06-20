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

## Prerequisiti per l&#39;inserimento di log DFP {#prereqs-dfp-ingestion}

Il processo descritto in questa sezione deve essere completato *prima* di passare ai prerequisiti per l&#39;abilitazione dell&#39;assimilazione del registro.

Per utilizzare i file di registro DFP ( [!DNL DoubleClick For Publishers]) in [!DNL Audience Manager], devi prima impostare il nostro [ID utente univoco Audience Manager (UUID)](../../../reference/ids-in-aam.md) nella chiamata ad un tag pubblicitario. Il nostro ID è incluso nei registri DFP e possiamo abbinare ID tra DFP e [!DNL Audience Manager]. Usa [!DNL Audience Manager][!UICONTROL DIL] il codice o l&#39;identificatore [!UICONTROL Audience Management Module] per impostare l&#39; [!DNL Audience Manager] UUID in un cookie first party.

Ecco come impostare l&#39; [!DNL Audience Manager] ID nella chiamata di tag di annunci, come descritto nella documentazione:

* [Tramite Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [Tramite una destinazione cookie](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

Devi impostare l&#39; [!DNL Audience Manager] ID voi stessi e lavorare [!DNL Audience Manager] con la consulenza per controllare se tutto funziona. L&#39; [!DNL Audience Manager] ID è stato impostato correttamente se:

* `'aamid'` è la chiave utilizzata come identificatore.
* Il valore ID utente è formattato correttamente come [!DNL Audience Manager] UUID, come descritto nel nostro [Indice degli ID in Audience Manager](../../../reference/ids-in-aam.md).
* Hai incluso l&#39; [!DNL Audience Manager] UUID in un campo definito nei registri DFP (ad es. customtargeting).

## Prerequisiti per l&#39;abilitazione all&#39;inserimento del registro {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Verificate che i passaggi necessari per impostare l'UUID <span class="keyword"> Audience Manager</span> (descritto sopra) siano stati completati prima di passare al passaggio 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Assistenza</span> clienti di Audience Manager o consulenza </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 2 </p> </td> 
   <td colname="col2"> <p>L'amministratore DFP crea: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Un account di servizio per l'assimilazione di registri DFP in <span class="keyword"> Audience Manager</span>. </li> 
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
   <td colname="col3"> <p>Voi, o <span class="keyword"> Audience Manager</span> Consulting, a vostro nome </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modello e-mail {#email-template}

Per finalizzare l&#39;abilitazione dell&#39;assimilazione del registro, inviateci un messaggio e-mail a aamsupport@adobe.com. Utilizzate il [modello e-mail allegato](assets/enable_dfp_ingestion.txt).
