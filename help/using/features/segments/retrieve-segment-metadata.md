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


# Recupero dei metadati del segmento {#retrieving-segment-metadata}

Quando Audience Manager invia informazioni sul segmento a un partner dati, identifica questi oggetti con ID numerici. In qualità di partner dati, quando condividete queste informazioni con i vostri clienti (o lavorate con voi stessi), un nome e una descrizione effettivi offrono un&#39;esperienza migliore ai clienti nei report, nelle dashboard o in altre interfacce utente ([!DNL UI]). I partner di dati possono rendere disponibili ai clienti questi nomi descrittivi con i metodi manuali o automatizzati descritti in questa sezione.

## Metodo manuale {#manual-method}

In qualità di partner dati, sei probabilmente utilizzato per ottenere i metadati del pubblico dai clienti tramite processi manuali. Ciò potrebbe includere file allegati alle e-mail o da clienti che aggiungono tali dati tramite un [!DNL UI] &#39;installazione e manutenzione a tale scopo. Questi processi funzionano, ma spesso sono molto difficili e richiedono un&#39;immissione manuale di dati. Questi metodi vengono spesso utilizzati per facilitare l&#39;integrazione e l&#39;esecuzione rapida, ma non forniscono la migliore esperienza cliente nel lungo periodo. In alternativa, puoi utilizzare i [!DNL Audience Manager][!DNL API] metadati per segmenti automaticamente.

## Metodo automatizzato {#automated-method}

[!DNL Audience Manager] fornisce un set di [API](../../api/rest-api-main/rest-api-main.md) REST che consentono di recuperare automaticamente i metadati del segmento. Con l &#39; [!DNL API], potete creare processi che recuperano metadati segmenti a intervalli pianificati o automaticamente, ogni volta che elaborate [!DNL Audience Manager] i dati e si trova un nuovo ID segmento. Per ulteriori informazioni, vedi la procedura seguente.

### Passaggio 1: Rivedete le API Audience Manager

La [sezione Guida introduttiva alle API](../../api/rest-api-main/aam-api-getting-started.md) REST contiene informazioni sui requisiti generali, sull&#39;autenticazione, sui metodi disponibili e così via. Questo è un buon punto di partenza se non avete mai lavorato con [!DNL Audience Manager][!DNL API] il primo.

### Passaggio 2: Richiedi credenziali di accesso oauth 2

È necessario un ID client e un segreto per [!DNL API] effettuare chiamate. Potete ottenere un ID client e un segreto dal vostro specialista di integrazione durante il processo di configurazione dell&#39;integrazione. Potete anche inviare una richiesta e-mail a [!UICONTROL Audience Manager Customer Care][!DNL amsupport@adobe.com].

### Passaggio 3: Raccolta di informazioni specifiche per i clienti da ciascun cliente integrato

Richiedi quanto segue da ciascun cliente integrato:

* Nome utente: Si tratta di un utente con restrizioni che dispone delle autorizzazioni di sola lettura per la destinazione associata a un&#39;integrazione specifica.
* Password: La password utente.
* ID destinazione: Si tratta dell&#39;ID (un numero intero) associato alla destinazione creata per l&#39;integrazione server-to-server specifica.

### Passaggio 4: Ottenimento dei metadati del segmento con una chiamata API

Dopo aver completato i passaggi precedenti, potete utilizzare un `GET` metodo per recuperare i metadati del segmento. Per una richiesta di esempio e una risposta, consultate [Restituzione di mappature di destinazione](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Questa chiamata restituisce i dati del segmento formattati come coppie chiave-valore in un [!DNL JSON] oggetto. Alcuni degli importanti attributi del segmento restituiti nella risposta sono elencati nella tabella seguente.

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
   <td colname="col2"> <p>L' <span class="keyword"> ID</span> segmento Audience Manager. </p> </td> 
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