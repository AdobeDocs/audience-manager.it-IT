---
description: Il processo di trasferimento dei dati in tempo reale in uscita restituisce i dati utente come una serie di oggetti JSON passati con un metodo POST.
seo-description: Il processo di trasferimento dei dati in tempo reale in uscita restituisce i dati utente come una serie di oggetti JSON passati con un metodo POST.
seo-title: Trasferimenti dati in uscita in tempo reale
solution: Audience Manager
title: Trasferimenti dati in uscita in tempo reale
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 4e84682dea46f5b6c76464c66199f7a468bec334

---


# Real-Time Outbound Data Transfers {#real-time-outbound-data-transfers}

The outbound real-time data transfer process delivers user data as a series of  formatted messages to a destination platform.[!DNL JSON]

<!-- c_outbound_json.xml -->

## Consigli

Per utilizzare questo metodo, la piattaforma di destinazione deve soddisfare i seguenti requisiti:

* Deve fornire un endpoint [!DNL URL] che possa essere ridimensionato in modo da ricevere un volume elevato di messaggi da Audience Manager;
* Accetta i dati nel [!DNL JSON] formato (`Content-type: application/json`);
* It must accept secure  data transfers. `HTTPS` [!DNL Audience Manager] will not send messages through the unsecure  protocol.`HTTP`

## Frequenza

Questo metodo di trasferimento dei dati può inviare dati in tempo quasi reale, in quanto gli utenti sono idonei per i segmenti. I messaggi in tempo reale vengono inviati solo mentre l'utente è online e attivo visibile sulla rete Edge di Audience Manager. Facoltativamente, questo metodo può anche inviare batch di dati offline o caricati con la stessa frequenza con cui ogni 24 ore.

## Trasferimenti batch

Both real-time and batch transfers are sent to the same endpoint and use the same message format. When batch transfers are enabled, the destination platform will see a spike in message volume while the batch messages are delivered. Many of the segment qualifications sent through real-time messages will be repeated in the batch messages. Batch transfers will include only the segment qualifications (or un-qualifications) that have changed since the last batch was delivered.

## Rate Limits

There are no rate limits set on the throughput of delievered messages. Setting rate limits could lead to data loss.

## Risposte richieste

By default, the recipient server must return the  code to indicate successful receipt. `200 OK` Other codes will be interpreted as failures. This response is expected within 3000 milliseconds. In risposta a un errore, [!DNL Audience Manager] verrà eseguito un nuovo tentativo solo.

## Parametri

La tabella seguente definisce gli elementi nel file di [!DNL JSON] dati che si invia alla destinazione.

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
   <td colname="col3"> <p>Un ID che indica il tipo di ID dispositivo contenuto nel messaggio, nella proprietà User.DataPartner_UUID. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">ID Android (GAID): <code> 2014</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID iOS (IDFA): <code> 2015</code> </li>
     <li>ID Web/cookie: varia in base alla piattaforma di destinazione</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Rappresenta l'account di destinazione nella piattaforma di destinazione. Questo ID proviene dalla piattaforma di destinazione.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>ID dell’oggetto "destinazione" di Audience Manager. Questo ID proviene da Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Numero_utente</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Numero totale di utenti nella richiesta <code> POST</code> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Utenti</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Un array di oggetti utente. Per impostazione predefinita, ogni messaggio contiene da 1 a 10 utenti, per ottimizzare la dimensione del messaggio. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>The  Audience Manager UUID.<span class="keyword"></span> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>UUID piattaforma di destinazione o ID dispositivo globale. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Utente.AAM_Region</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> L'ID di regione di <span class="keyword"> Audience Manager</span> in cui abbiamo visto questo dispositivo. Ad esempio, se il dispositivo aveva qualche attività a Parigi (Europa), l'ID di regione sarebbe <code> 6</code>. Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID regioni DCS, posizioni e nomi host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmenti</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>An array of segment objects. For real-time messages, the array contains all of the segments the user belongs to. Per i messaggi batch, l'array contiene solo le modifiche al segmento dall'ultimo batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Identificatore per il segmento. Nella maggior parte dei casi, si tratta dell’ID del segmento generato da Audience Manager (un numero intero). In alcuni casi, se la piattaforma di destinazione lo consente, i clienti possono definire l’identificatore del segmento nell’interfaccia utente di Audience Manager (campo di testo aperto), che rifletterebbe in questa proprietà. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Defines the status of a user in the segment. Accepts the following values: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1: Active (default)</code> </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0: Inactive, opted-out, or unsegmented.</code> </li> 
    </ul> <p>Users are unsegmented when they are: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Removed from a segment based on the segment rule. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Rimosso da un segmento in base all'intervallo <a href="../../../features/traits/segment-ttl-explained.md"> time-to-live del segmento</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Moved to an inactive state if they have not been seen for the last 120-days. </li>
     <li>Removed due to a privacy change request (i.e. [!DNL GDPR])</li>
    </ul> <p>Tutti gli ID partner sincronizzati con un ID <span class="keyword"> Audience Manager</span> riceveranno il flag <code> "Status":"0"</code> quando un utente non è segmentato. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>L’ora in cui è stata verificata più di recente la qualifica del segmento utente.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicurezza

È possibile proteggere il processo di trasferimento dei dati in uscita in tempo reale [firmando richieste](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP utilizzando chiavi private o mediante l' [!DNL Audience Manager] autenticazione tramite il protocollo [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

## Richiesta

Una richiesta in tempo reale può avere un aspetto simile al seguente:

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
   "AAM_Regions": ["9"],
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
   "AAM_Regions": ["9"],
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
