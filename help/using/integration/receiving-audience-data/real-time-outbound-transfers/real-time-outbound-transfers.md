---
description: Il processo di trasferimento dei dati in tempo reale in uscita restituisce i dati utente come una serie di oggetti JSON passati con un metodo POST.
seo-description: Il processo di trasferimento dei dati in tempo reale in uscita restituisce i dati utente come una serie di oggetti JSON passati con un metodo POST.
seo-title: Trasferimenti dati in uscita in tempo reale
solution: Audience Manager
title: Trasferimenti dati in uscita in tempo reale
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


# Trasferimenti dati in uscita in tempo reale {#real-time-outbound-data-transfers}

Il processo di trasferimento dei dati in tempo reale in uscita restituisce i dati dell'utente come una serie di [!DNL JSON] oggetti passati con un `POST` metodo.

<!-- c_outbound_json.xml -->

## Consigli

Per utilizzare questo metodo, consigliamo al partner dati di:

* Accetta i dati in [!DNL JSON] formato.
* Fornisce un URL che può essere utilizzato dalla `POST` chiamata per restituire i dati.
* Accetta trasferimenti `HTTPS` di dati sicuri. [!DNL Audience Manager] non invierà questo file con il `HTTP` protocollo non sicuro.

## Frequenza

Questo metodo di trasferimento dei dati può inviare dati in tempo quasi reale, in quanto gli utenti sono idonei per i segmenti. Inoltre, questo metodo può inviare batch di dati offline o caricati con la stessa frequenza che ogni 24 ore.

## Risposte richieste

Per impostazione predefinita, il server destinatario deve restituire il `200 OK` codice per indicare l'avvenuta ricezione. Altri codici saranno interpretati come errori. Questa risposta è prevista entro 3000 millisecondi. In risposta a un errore, [!DNL Audience Manager] verrà eseguito solo 1 tentativo.

## Parametri

La tabella seguente definisce gli elementi nel file di [!DNL JSON] dati restituito.

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Tipo di dati </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Ora di esecuzione della richiesta. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Un ID che indica se il file contiene ID Android o iOS. Utilizza i seguenti valori ID: </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">ID Android (GAID): <code> 2014</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID iOS (IDFA): <code> 2015</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>ID client utilizzato dal sistema a cui si inviano i dati. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>L’ID assegnato al partner di destinazione. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Numero_utente</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Numero totale di utenti nella richiesta <code> POST</code> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Utenti</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Un array di oggetti utente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_UID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>L’UUID <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DataPartner_UID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>UUID partner dati. Lascia vuoto se il tuo partner dati non ha un UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Region</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> L'ID di regione di <span class="keyword"> Audience Manager</span> in cui abbiamo visto questo dispositivo. Ad esempio, se il dispositivo aveva qualche attività a Parigi (Europa), l'ID di regione sarebbe <code> 6</code>. Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID regioni DCS, posizioni e nomi host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmenti</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Un array di oggetti segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Mappatura destinazione ID segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Stato</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Definisce lo stato di un utente nel segmento. Accetta quanto segue: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Attivo (predefinito) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inattivo, escluso o non segmentato. </li> 
    </ul> <p>Gli utenti non sono segmentati quando: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Rimosso da un segmento in base alla regola del segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Rimosso da un segmento in base all'intervallo <a href="../../../features/traits/segment-ttl-explained.md"> time-to-live del segmento</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Spostato in uno stato inattivo se non è stato visualizzato negli ultimi 120 giorni. </li> 
    </ul> <p>Tutti gli ID partner sincronizzati con un ID <span class="keyword"> Audience Manager</span> riceveranno il flag <code> "Status":"0"</code> quando un utente non è segmentato. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Ora della qualifica del segmento più recente.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicurezza

È possibile proteggere il processo di trasferimento dei dati in uscita in tempo reale [firmando richieste](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP utilizzando chiavi private o mediante l' [!DNL Audience Manager] autenticazione tramite il protocollo [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

## Esempio di codice

Una risposta dati in tempo reale può avere un aspetto simile al seguente:

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
