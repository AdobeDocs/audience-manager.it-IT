---
description: Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.
seo-description: Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.
seo-title: Importare file di dati Google Ad Manager in Audience Manager
solution: Audience Manager
title: Importare file di dati Google Ad Manager in Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 16%

---

# Importa file di dati di Google Ad Manager (precedentemente DFP) in Audience Manager{#import-dfp-data-files-into-audience-manager}

Prima che Audience Manager possa abilitare l’ottimizzazione del pubblico per gli editori, assicurati che siano soddisfatti tutti i prerequisiti definiti in questo articolo. Dopo aver verificato i prerequisiti, contatta l’Assistenza clienti.

## Prerequisiti per l’acquisizione dei registri di Google Ad Manager {#prereqs-dfp-ingestion}

Tieni presente che il processo descritto in questa sezione deve essere completato *prima di* per passare ai prerequisiti per l’abilitazione dell’acquisizione del registro.

Per utilizzare i file di registro [!DNL Google Ad Manager] (precedentemente Google DFP) in [!DNL Audience Manager], devi prima impostare il nostro [ID utente univoco Audience Manager (UUID)](../../../reference/ids-in-aam.md) nella chiamata del tag dell’annuncio. In questo modo, il nostro ID è incluso nei registri [!DNL Google Ad Manager] e possiamo abbinare gli ID tra [!DNL Google Ad Manager] e [!DNL Audience Manager]. Utilizza il codice [!DNL Audience Manager] [!UICONTROL DIL] o [!UICONTROL Audience Management Module] per impostare l&#39;UUID [!DNL Audience Manager] in un cookie di prime parti.

Ecco come impostare l’ [!DNL Audience Manager] ID nella chiamata del tag dell’annuncio, come spiegato nella nostra documentazione:

* [Tramite Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Tramite una destinazione cookie](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Devi impostare tu stesso l&#39; [!DNL Audience Manager] ID e puoi lavorare con la [!DNL Audience Manager] consulenza per verificare se tutto funziona. Hai impostato correttamente l&#39; [!DNL Audience Manager] ID se:

* `'aamid'` è la chiave utilizzata come identificatore.
* Il valore ID utente viene formattato correttamente come UUID [!DNL Audience Manager], come descritto nel nostro [Indice degli ID in Audience Manager](../../../reference/ids-in-aam.md).
* Hai incluso l’ [!DNL Audience Manager] UUID in un campo definito nei tuoi registri [!DNL Google Ad Manager] (ad esempio CustomTargeting).

## Prerequisiti per l’abilitazione all’acquisizione del registro {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Conferma che i passaggi necessari per impostare l' <span class="keyword"> Audience Manager</span> UUID (descritti sopra) sono stati completati prima di passare al passaggio 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Assistenza clienti o consulenza </span> di Audience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 2 </p> </td> 
   <td colname="col2"> <p>L'amministratore di Google Ad Manager crea: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Un account di servizio per l’acquisizione di Google Ad Manager accede a <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nuove credenziali. <p>Nota:  Questo può richiedere un indirizzo e-mail univoco specifico per questo progetto e verrà utilizzato quando si effettua il provisioning dell'accesso al bucket di archiviazione Google. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Una chiave privata (credenziale basata su JSON) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Amministratore di Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 3 </p> </td> 
   <td colname="col2"> <p>L’amministratore di Google Ad Manager concede l’accesso API all’account del servizio. Questo passaggio consente di accedere ai metadati per delineare le dimensioni (elementi di riga, ordini, creativi). <p>Nota:  Utilizza l'accesso e-mail all'account del servizio configurato nel passaggio 2 per concedere l'autorizzazione all'accesso all'API. </p> </p> </td> 
   <td colname="col3"> <p>Amministratore di Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 4 </p> </td> 
   <td colname="col2"> <p>L'amministratore di Google Ad Manager stabilisce l'accesso al bucket di archiviazione Google. Ricorda: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Questo può essere fatto tramite un gruppo Google. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associa l’indirizzo e-mail univoco assegnato all’account del servizio al bucket di archiviazione. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Amministratore di Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 5 </p> </td> 
   <td colname="col2"> <p>L’amministratore di Google Ad Manager fornisce l’ID di rete di Google Ad Manager. Questo ci consente di passare l’ID di rete quando effettuiamo chiamate all’API. </p> </td> 
   <td colname="col3"> <p>Amministratore di Google Ad Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Passaggio 6 </p> </td> 
   <td colname="col2"> <p>Compila i prerequisiti in un messaggio e-mail per AAM l’Assistenza clienti (aamsupport@adobe.com) per avviare il processo di acquisizione del registro. Bozza l’e-mail utilizzando il modello nella sezione successiva. </p> </td> 
   <td colname="col3"> <p>o <span class="keyword"> Audience Manager</span> Consulting per conto tuo </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modello e-mail {#email-template}

Per completare l’abilitazione dell’acquisizione del registro, inviaci un’e-mail a aamsupport@adobe.com. Utilizzare il [modello di posta elettronica allegato](assets/enable_dfp_ingestion.txt).
