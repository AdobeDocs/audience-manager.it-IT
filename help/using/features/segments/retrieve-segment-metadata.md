---
description: Quando  Audience Manager invia informazioni sui segmenti a un partner di dati, identifica questi oggetti con ID numerici. In qualità di partner dati, quando condividi queste informazioni con i tuoi clienti (o lavori con te stesso), un nome e una descrizione effettivi offrono ai clienti un'esperienza migliore in rapporti, dashboard o altre interfacce utente (interfaccia utente). I partner di dati possono rendere disponibili questi nomi descrittivi ai propri clienti con i metodi manuali o automatizzati descritti in questa sezione.
seo-description: Quando  Audience Manager invia informazioni sui segmenti a un partner di dati, identifica questi oggetti con ID numerici. In qualità di partner dati, quando condividi queste informazioni con i tuoi clienti (o lavori con te stesso), un nome e una descrizione effettivi offrono ai clienti un'esperienza migliore in rapporti, dashboard o altre interfacce utente (interfaccia utente). I partner di dati possono rendere disponibili questi nomi descrittivi ai propri clienti con i metodi manuali o automatizzati descritti in questa sezione.
seo-title: Recupero dei metadati dei segmenti
solution: Audience Manager
title: Recupero dei metadati dei segmenti
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 1%

---


# Recupero dei metadati dei segmenti {#retrieving-segment-metadata}

Quando  Audience Manager invia informazioni sui segmenti a un partner di dati, identifica questi oggetti con ID numerici. In qualità di partner dati, quando condividi queste informazioni con i tuoi clienti (o lavori con te stesso), un nome e una descrizione effettivi offrono ai clienti un&#39;esperienza migliore in rapporti, dashboard o altre interfacce utente ([!DNL UI]). I partner di dati possono rendere disponibili questi nomi descrittivi ai propri clienti con i metodi manuali o automatizzati descritti in questa sezione.

## Metodo manuale {#manual-method}

In qualità di partner di dati, sei probabilmente abituato a ottenere i metadati del pubblico dai clienti attraverso processi manuali. Ciò può includere file allegati alle e-mail o dai clienti che aggiungono tali dati tramite un [!DNL UI] modulo creato e gestito a tal fine. Questi processi funzionano, ma spesso sono complicati, richiedono molto tempo e possono richiedere l&#39;immissione manuale dei dati. Questi metodi sono spesso utilizzati per rendere l&#39;integrazione operativa e funzionante rapidamente, ma non offrono la migliore esperienza cliente a lungo termine. In alternativa, puoi usare [!DNL Audience Manager] per ottenere automaticamente [!DNL API] i metadati dei segmenti.

## Metodo automatizzato {#automated-method}

[!DNL Audience Manager] fornisce un set di API [](../../api/rest-api-main/rest-api-main.md) REST che consente di recuperare automaticamente i metadati del segmento. Con [!DNL API], potete creare processi che recuperino i metadati dei segmenti a intervalli pianificati o automaticamente, ogni volta che elaborate [!DNL Audience Manager] i dati e trovate un nuovo ID segmento. Per ulteriori informazioni, consulta i passaggi riportati di seguito.

### Passaggio 1: Esaminate le API Audience Manager 

La sezione [Guida introduttiva alle API](../../api/rest-api-main/aam-api-getting-started.md) REST contiene informazioni su requisiti generali, autenticazione, metodi disponibili, ecc. Questo è un buon posto dove iniziare se non hai lavorato con il [!DNL Audience Manager] [!DNL API] prima.

### Passaggio 2: Richiedi credenziali di accesso OAuth2

Per effettuare [!DNL API] le chiamate è necessario un ID client e un segreto. Durante il processo di configurazione dell&#39;integrazione, potete ottenere un ID client e un segreto dal vostro specialista dell&#39;integrazione. Potete inoltre inviare una richiesta e-mail a [!UICONTROL Audience Manager Customer Care] all&#39;indirizzo [!DNL amsupport@adobe.com].

### Passaggio 3: Raccolta di informazioni specifiche per il cliente da ogni cliente integrato

Richiedete quanto segue da ogni cliente integrato:

* Nome utente: Si tratta di un utente con restrizioni che dispone di autorizzazioni di sola lettura per la destinazione associata a una specifica integrazione.
* Password: La password utente.
* ID destinazione: Si tratta dell&#39;ID (un numero intero) associato alla destinazione creata per l&#39;integrazione server-to-server specifica.

### Passaggio 4: Recuperare i metadati del segmento con una chiamata API

Dopo aver completato i passaggi precedenti, puoi usare un `GET` metodo per recuperare i metadati del segmento. Per un esempio di richiesta e risposta, consultate [Return Destination Mappings (Mappature delle destinazioni di ritorno)](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Questa chiamata restituisce i dati del segmento formattati come coppie chiave-valore in un [!DNL JSON] oggetto. Alcuni degli importanti attributi del segmento restituiti nella risposta sono elencati nella tabella seguente.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p>L’ID del segmento <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>Il nome del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>Testo che descrive brevemente il segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>Lo stato corrente della mappatura del segmento. Le opzioni di stato restituite includono: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>