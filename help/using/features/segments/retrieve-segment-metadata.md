---
description: Quando Audience Manager invia informazioni sul segmento a un partner dati, identifica questi oggetti con ID numerici. In qualità di partner dati, quando condividete queste informazioni con i vostri clienti (o lavorate con voi stessi), un nome e una descrizione effettivi offrono un'esperienza migliore ai clienti nei report, nelle dashboard o in altre interfacce utente (interfaccia utente). I partner di dati possono rendere disponibili ai clienti questi nomi descrittivi con i metodi manuali o automatizzati descritti in questa sezione.
seo-description: Quando Audience Manager invia informazioni sul segmento a un partner dati, identifica questi oggetti con ID numerici. In qualità di partner dati, quando condividete queste informazioni con i vostri clienti (o lavorate con voi stessi), un nome e una descrizione effettivi offrono un'esperienza migliore ai clienti nei report, nelle dashboard o in altre interfacce utente (interfaccia utente). I partner di dati possono rendere disponibili ai clienti questi nomi descrittivi con i metodi manuali o automatizzati descritti in questa sezione.
seo-title: Recupero dei metadati del segmento
solution: Audience Manager
title: Recupero dei metadati del segmento
uuid: 719 e 2 c 41-8788-4 e 8 a -967 a-e 367421 f 9 f 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Retrieving Segment Metadata {#retrieving-segment-metadata}

Quando Audience Manager invia informazioni sul segmento a un partner dati, identifica questi oggetti con ID numerici. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces ([!DNL UI]). I partner di dati possono rendere disponibili ai clienti questi nomi descrittivi con i metodi manuali o automatizzati descritti in questa sezione.

## Manual method {#manual-method}

In qualità di partner dati, sei probabilmente utilizzato per ottenere i metadati del pubblico dai clienti tramite processi manuali. This could include files attached to emails or from customers adding that data through a [!DNL UI] you've built and maintained for this purpose. Questi processi funzionano, ma spesso sono molto difficili e richiedono un'immissione manuale di dati. Questi metodi vengono spesso utilizzati per facilitare l'integrazione e l'esecuzione rapida, ma non forniscono la migliore esperienza cliente nel lungo periodo. As an alternative, you can use the [!DNL Audience Manager] [!DNL API] to get segment metadata automatically.

## Automated method {#automated-method}

[!DNL Audience Manager] fornisce un set di [API](../../api/rest-api-main/rest-api-main.md) REST che consentono di recuperare automaticamente i metadati del segmento. With the [!DNL API], you can create jobs that retrieve segment metadata at scheduled intervals or automatically, whenever you process [!DNL Audience Manager] data and find a new segment ID. Per ulteriori informazioni, vedi la procedura seguente.

### Passaggio 1: Rivedete le API Audience Manager

The [Getting Started with REST APIs](../../api/rest-api-main/aam-api-getting-started.md) section contains information about general requirements, authentication, available methods, etc. This is a good place to begin if you haven't worked with the [!DNL Audience Manager] [!DNL API] before.

### Passaggio 2: Richiedi credenziali di accesso oauth 2

You need a client ID and secret to make [!DNL API] calls. Potete ottenere un ID client e un segreto dal vostro specialista di integrazione durante il processo di configurazione dell'integrazione. You can also send an email request to [!UICONTROL Audience Manager Customer Care] at [!DNL amsupport@adobe.com].

### Passaggio 3: Raccolta di informazioni specifiche per i clienti da ciascun cliente integrato

Richiedi quanto segue da ciascun cliente integrato:

* Nome utente: Si tratta di un utente con restrizioni che dispone delle autorizzazioni di sola lettura per la destinazione associata a un'integrazione specifica.
* Password: La password utente.
* ID destinazione: Si tratta dell'ID (un numero intero) associato alla destinazione creata per l'integrazione server-to-server specifica.

### Passaggio 4: Ottenimento dei metadati del segmento con una chiamata API

After completing the previous steps, you can use a `GET` method to retrieve segment metadata. For a sample request and response, see [Return Destination Mappings](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). This call returns segment data formatted as key-value pairs in a [!DNL JSON] object. Alcuni degli importanti attributi del segmento restituiti nella risposta sono elencati nella tabella seguente.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Purchionmappingid</code> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager</span> segment ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementname</code> </p> </td> 
   <td colname="col2"> <p>Il nome del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementdescription</code> </p> </td> 
   <td colname="col2"> <p>Testo che descrive brevemente il segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementstatus</code> </p> </td> 
   <td colname="col2"> <p>Lo stato corrente della mappatura segmenti. Le opzioni di stato restituite includono: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> eliminati</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>