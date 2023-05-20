---
description: Quando Audience Manager invia informazioni sui segmenti a un partner dati, identifica questi oggetti con ID numerici. In qualità di partner dati, quando condividi queste informazioni con i clienti (o lavori con essi personalmente), un nome e una descrizione effettivi offrono ai clienti un’esperienza migliore nei rapporti, nelle dashboard o in altre interfacce utente (interfaccia utente). I partner di dati possono rendere questi nomi descrittivi disponibili ai propri clienti con i metodi manuali o automatizzati descritti in questa sezione.
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: Recupero dei metadati dei segmenti
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 1%

---

# Recupero dei metadati dei segmenti {#retrieving-segment-metadata}

Quando Audience Manager invia informazioni sui segmenti a un partner dati, identifica questi oggetti con ID numerici. In qualità di partner dati, quando condividi queste informazioni con i clienti (o lavori con essi personalmente), un nome e una descrizione effettivi offrono ai clienti un’esperienza migliore nei rapporti, nelle dashboard o in altre interfacce utente ([!DNL UI]). I partner di dati possono rendere questi nomi descrittivi disponibili ai propri clienti con i metodi manuali o automatizzati descritti in questa sezione.

## Metodo manuale {#manual-method}

In qualità di partner dati, probabilmente sei abituato a ottenere metadati di pubblico dai clienti attraverso processi manuali. Potrebbe includere file allegati alle e-mail o provenienti da clienti che aggiungono tali dati tramite una [!DNL UI] hai creato e gestito per questo scopo. Questi processi funzionano, ma sono spesso complicati, richiedono tempo e possono richiedere l&#39;immissione manuale dei dati. Questi metodi vengono spesso utilizzati per rendere operativa rapidamente un’integrazione, ma non forniscono la migliore esperienza del cliente nel lungo periodo. In alternativa, è possibile utilizzare [!DNL Audience Manager] [!DNL API] per ottenere automaticamente i metadati dei segmenti.

## Metodo automatizzato {#automated-method}

[!DNL Audience Manager] fornisce una serie di [API REST](../../api/rest-api-main/rest-api-main.md) che ti consente di recuperare automaticamente i metadati del segmento. Con il [!DNL API], è possibile creare processi che recuperano i metadati del segmento a intervalli pianificati o automaticamente, ogni volta che si elabora [!DNL Audience Manager] e trova un nuovo ID segmento. Per ulteriori informazioni, consulta i passaggi seguenti.

### Passaggio 1: rivedere le API di Audience Manager

Il [Guida introduttiva alle API REST](../../api/rest-api-main/aam-api-getting-started.md) Questa sezione contiene informazioni su requisiti generali, autenticazione, metodi disponibili e così via. Questo è un buon punto di partenza se non hai lavorato con il [!DNL Audience Manager] [!DNL API] prima.

### Passaggio 2: richiesta delle credenziali di accesso OAuth2

È necessario un ID client e un segreto per effettuare [!DNL API] chiamate. Puoi ottenere un ID client e un segreto dallo specialista dell’integrazione durante il processo di configurazione dell’integrazione. Puoi anche inviare una richiesta e-mail a [!UICONTROL Audience Manager Customer Care] a [!DNL amsupport@adobe.com].

### Passaggio 3: raccogliere informazioni specifiche su ciascun cliente integrato

Richiedi quanto segue a ogni cliente integrato:

* Nome utente: si tratta di un utente con restrizioni che dispone di autorizzazioni di sola lettura per la destinazione associata a una specifica integrazione.
* Password: password utente.
* ID destinazione: questo è l’ID (un numero intero) associato alla destinazione creata per l’integrazione server-to-server specifica.

### Passaggio 4: recuperare i metadati dei segmenti con una chiamata API

Dopo aver completato i passaggi precedenti, puoi utilizzare un’ `GET` per recuperare i metadati del segmento. Per un esempio di richiesta e risposta, consulta [Restituisci mappature destinazione](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Questa chiamata restituisce dati del segmento formattati come coppie chiave-valore in una [!DNL JSON] oggetto. Alcuni degli attributi importanti del segmento restituiti nella risposta sono elencati nella tabella seguente.

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
   <td colname="col2"> <p>Il <span class="keyword"> Audience Manager</span> ID segmento. </p> </td> 
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
   <td colname="col2"> <p>Lo stato corrente del mapping dei segmenti. Le opzioni di stato restituite includono: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
