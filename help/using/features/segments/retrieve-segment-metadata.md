---
description: Quando Audience Manager invia informazioni sui segmenti a un partner dati, identifica tali oggetti con ID numerici. In qualità di partner dati, quando condividi queste informazioni con i tuoi clienti (o lavori con te stesso), un nome e una descrizione effettivi forniscono ai clienti una migliore esperienza in report, dashboard o altre interfacce utente (interfaccia utente). I partner dati possono rendere questi nomi descrittivi disponibili ai propri clienti con i metodi manuali o automatizzati descritti in questa sezione.
seo-description: Quando Audience Manager invia informazioni sui segmenti a un partner dati, identifica tali oggetti con ID numerici. In qualità di partner dati, quando condividi queste informazioni con i tuoi clienti (o lavori con te stesso), un nome e una descrizione effettivi forniscono ai clienti una migliore esperienza in report, dashboard o altre interfacce utente (interfaccia utente). I partner dati possono rendere questi nomi descrittivi disponibili ai propri clienti con i metodi manuali o automatizzati descritti in questa sezione.
seo-title: Recupero dei metadati dei segmenti
solution: Audience Manager
title: Recupero dei metadati dei segmenti
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: 'Segmenti '
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---

# Recupero dei metadati dei segmenti {#retrieving-segment-metadata}

Quando Audience Manager invia informazioni sui segmenti a un partner dati, identifica tali oggetti con ID numerici. In qualità di partner dati, quando condividi queste informazioni con i tuoi clienti (o lavori con te stesso), un nome e una descrizione effettivi forniscono ai clienti una migliore esperienza in report, dashboard o altre interfacce utente ([!DNL UI]). I partner dati possono rendere questi nomi descrittivi disponibili ai propri clienti con i metodi manuali o automatizzati descritti in questa sezione.

## Metodo manuale {#manual-method}

In qualità di partner di dati, sei probabilmente abituato a ricevere i metadati del pubblico dai tuoi clienti attraverso processi manuali. Questo potrebbe includere file allegati alle e-mail o dai clienti che aggiungono tali dati tramite un [!DNL UI] creato e mantenuto a questo scopo. Questi processi funzionano, ma spesso sono complicati e richiedono molto tempo e possono richiedere l’inserimento manuale dei dati. Questi metodi sono spesso utilizzati per facilitare l’avvio e l’esecuzione rapida di un’integrazione, ma non offrono la migliore esperienza cliente a lungo termine. In alternativa, puoi utilizzare [!DNL Audience Manager] [!DNL API] per ottenere automaticamente i metadati dei segmenti.

## Metodo automatizzato {#automated-method}

[!DNL Audience Manager] fornisce un set di  [API ](../../api/rest-api-main/rest-api-main.md) REST che ti consente di recuperare automaticamente i metadati dei segmenti. Con [!DNL API] è possibile creare processi che recuperano i metadati dei segmenti a intervalli pianificati o automaticamente, ogni volta che si elaborano i dati [!DNL Audience Manager] e si trova un nuovo ID segmento. Per ulteriori informazioni, consulta i passaggi seguenti.

### Passaggio 1: Controlla le API di Audience Manager

La sezione [Guida introduttiva alle API REST](../../api/rest-api-main/aam-api-getting-started.md) contiene informazioni su requisiti generali, autenticazione, metodi disponibili, ecc. Questo è un buon punto di partenza se non hai lavorato con [!DNL Audience Manager] [!DNL API] prima.

### Passaggio 2: Richiedere le credenziali di accesso OAuth2

Per effettuare chiamate [!DNL API] è necessario un ID client e un segreto. Durante il processo di configurazione dell’integrazione, puoi ottenere un ID cliente e un segreto dallo specialista dell’integrazione. Puoi anche inviare una richiesta e-mail a [!UICONTROL Audience Manager Customer Care] all’indirizzo [!DNL amsupport@adobe.com].

### Passaggio 3: Raccogliere informazioni specifiche per cliente da ogni cliente integrato

Richiedi quanto segue da ogni cliente integrato:

* Nome utente: Questo è per un utente con restrizioni che dispone di autorizzazioni di sola lettura per la destinazione associata a una specifica integrazione.
* Password: Password utente.
* ID destinazione: Si tratta dell&#39;ID (un numero intero) associato alla destinazione creata per l&#39;integrazione server-to-server specifica.

### Passaggio 4: Recupera i metadati dei segmenti con una chiamata API

Dopo aver completato i passaggi precedenti, puoi utilizzare un metodo `GET` per recuperare i metadati dei segmenti. Per un esempio di richiesta e risposta, consulta [Invio di mappature di destinazione](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Questa chiamata restituisce i dati del segmento formattati come coppie chiave-valore in un oggetto [!DNL JSON] . Alcuni degli attributi importanti del segmento restituiti nella risposta sono elencati nella tabella seguente.

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
   <td colname="col2"> <p>ID del segmento <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>Nome del segmento. </p> </td> 
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
