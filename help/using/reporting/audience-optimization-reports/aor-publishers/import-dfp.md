---
description: Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.
seo-description: Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.
seo-title: Importazione di file di dati DFP in Audience Manager
solution: Audience Manager
title: Importazione di file di dati DFP in Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
translation-type: tm+mt
source-git-commit: 9f091fa765e937fb47b3328d8f5f2dab24a85040

---


# Importazione di file di dati DFP in Audience Manager{#import-dfp-data-files-into-audience-manager}

Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.

## Prerequisiti per l'inserimento del registro DFP {#prereqs-dfp-ingestion}

Il processo descritto in questa sezione deve essere completato *prima* di passare ai prerequisiti per l’abilitazione dell’assimilazione del registro.

Per utilizzare i file di registro DFP ( [!DNL DoubleClick For Publishers]) in [!DNL Audience Manager], devi prima impostare il nostro ID utente univoco di [Audience Manager (UUID)](../../../reference/ids-in-aam.md) nella chiamata del tag dell’annuncio. In questo modo, il nostro ID è incluso nei registri DFP e possiamo far corrispondere gli ID tra DFP e [!DNL Audience Manager]. Utilizzate [!DNL Audience Manager][!UICONTROL DIL] il codice o [!UICONTROL Audience Management Module] per impostare l' [!DNL Audience Manager] UUID in un cookie di prime parti.

Ecco come impostare l’ [!DNL Audience Manager] ID nella chiamata del tag dell’annuncio, come spiegato nella nostra documentazione:

* [Tramite Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Tramite una destinazione di cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Devi impostare tu stesso l' [!DNL Audience Manager] ID e puoi collaborare con [!DNL Audience Manager] la consulenza per verificare se tutto funziona. Hai impostato correttamente l’ [!DNL Audience Manager] ID se:

* `'aamid'` è la chiave utilizzata come identificatore.
* Il valore ID utente è formattato correttamente come [!DNL Audience Manager] UUID, come descritto nel nostro [Indice ID in Audience Manager](../../../reference/ids-in-aam.md).
* Hai incluso l’ [!DNL Audience Manager] UUID in un campo definito nei registri DFP (ad esempio CustomTargeting).

## Prerequisiti per l'abilitazione dell'inserimento del registro {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Conferma che i passaggi necessari per impostare <span class="keyword"> Audience Manager</span> UUID (come indicato sopra) sono stati completati prima di passare al punto 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Assistenza clienti o consulenza di Audience Manager</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 2 </p> </td> 
   <td colname="col2"> <p>L'amministratore DFP crea: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Un account di servizio per l’assimilazione dei log DFP in <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nuove credenziali. <p>Nota:  Questo può richiedere un indirizzo e-mail univoco specifico per questo progetto e verrà utilizzato quando si effettua il provisioning dell'accesso a Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Una chiave privata (credenziale basata su JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Amministratore DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 3 </p> </td> 
   <td colname="col2"> <p>L'amministratore DFP concede l'accesso API all'account del servizio. Questo passaggio consente di accedere ai metadati per delineare le dimensioni (elementi di linea, ordini, creatività). <p>Nota:  Utilizzate l'accesso e-mail all'account del servizio configurato nel passaggio 2 per concedere l'autorizzazione per accedere all'API. </p> </p> </td> 
   <td colname="col3"> <p>Amministratore DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 4 </p> </td> 
   <td colname="col2"> <p>L'amministratore DFP stabilisce l'accesso a Google Storage Bucket. Ricorda: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Questo può essere fatto tramite un gruppo Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associate l'indirizzo e-mail univoco assegnato all'account del servizio al bucket di archiviazione. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Amministratore DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 5 </p> </td> 
   <td colname="col2"> <p>L'amministratore DFP fornisce l'ID di rete DFP. Questo ci consente di trasmettere l'ID di rete quando si effettuano chiamate all'API. </p> </td> 
   <td colname="col3"> <p>Amministratore DFP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 6 </p> </td> 
   <td colname="col2"> <p>Compilate i prerequisiti in un messaggio e-mail all'Assistenza clienti AAM (aamsupport@adobe.com) per avviare il processo di caricamento del registro. Bozza il messaggio e-mail utilizzando il modello nella sezione successiva. </p> </td> 
   <td colname="col3"> <p>Voi o <span class="keyword"> Audience Manager</span> Consulenza per vostro conto </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modello e-mail {#email-template}

Per completare l’abilitazione dell’inserimento del registro, inviateci un messaggio e-mail a aamsupport@adobe.com. Utilizzare il modello [di posta elettronica](assets/enable_dfp_ingestion.txt)allegato.
