---
description: Il processo di trasferimento dei dati in tempo reale in uscita restituisce i dati utente come una serie di oggetti JSON passati con un metodo POST.
seo-description: Il processo di trasferimento dei dati in tempo reale in uscita restituisce i dati utente come una serie di oggetti JSON passati con un metodo POST.
seo-title: Trasferimenti dati in uscita in tempo reale
solution: Audience Manager
title: Trasferimenti dati in uscita in tempo reale
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# Trasferimenti dati in uscita in tempo reale {#real-time-outbound-data-transfers}

Il processo di trasferimento dei dati in tempo reale in uscita fornisce i dati utente come una serie di messaggi [!DNL JSON] formattati a una piattaforma di destinazione.

<!-- c_outbound_json.xml -->

## Consigli

Per utilizzare questo metodo, la piattaforma di destinazione deve soddisfare i seguenti requisiti:

* Deve fornire un endpoint [!DNL URL] che possa essere ridimensionato in modo da ricevere un volume elevato di messaggi da Audience Manager;
* Accetta i dati nel [!DNL JSON] formato (`Content-type: application/json`);
* Deve accettare trasferimenti `HTTPS` di dati sicuri. [!DNL Audience Manager] non invierà messaggi tramite il `HTTP` protocollo non sicuro.

## Frequenza

This data transfer method can send data in near real-time as users qualify for segments. I messaggi in tempo reale vengono inviati solo mentre l'utente è online e attivo visibile sulla rete Edge di Audience Manager. Facoltativamente, questo metodo può anche inviare batch di dati offline o caricati con la stessa frequenza con cui ogni 24 ore.

## Trasferimenti batch

Both real-time and batch transfers are sent to the same endpoint and use the same message format. Quando sono abilitati i trasferimenti batch, la piattaforma di destinazione visualizzerà un picco nel volume dei messaggi mentre i messaggi batch vengono inviati. Many of the segment qualifications sent through real-time messages will be repeated in the batch messages. Batch transfers will include only the segment qualifications (or un-qualifications) that have changed since the last batch was delivered.

## Limiti di velocità

Non sono impostati limiti di velocità per il throughput dei messaggi eliminati. La fissazione di limiti di velocità potrebbe comportare una perdita di dati.

## Risposte richieste

Per impostazione predefinita, il server destinatario deve restituire il `200 OK` codice per indicare l'avvenuta ricezione. Altri codici saranno interpretati come errori. Questa risposta è prevista entro 3000 millisecondi. In risposta a un errore, [!DNL Audience Manager] verrà eseguito un nuovo tentativo solo.

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
   <td colname="col3"> <p>An ID that indicates the type of device IDs contained within the message, in the User.DataPartner_UUID property. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android IDs (GAID):  20914<code></code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS IDs (IDFA):  20915<code></code> </li>
     <li>ID Web/cookie: varia in base alla piattaforma di destinazione</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Represents the target account in the destination platform. This ID originates from the destination platform.</p> </td> 
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
   <td colname="col3"> <p>L’UUID <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Destination platform UUID or the global device ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Utente.AAM_Region</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> L'ID di regione di <span class="keyword"> Audience Manager</span> in cui abbiamo visto questo dispositivo. For instance, if the device had some activity in Paris (Europe), the region ID would be  6. <code></code> Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID regioni DCS, posizioni e nomi host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmenti</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>An array of segment objects. For real-time messages, the array contains all of the segments the user belongs to. For batch messages, the array contains only segment changes since the last batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmnent.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>The identifier for the segment. Nella maggior parte dei casi, si tratta dell’ID del segmento generato da Audience Manager (un numero intero). In some cases, if the destination platform allows, customers can define the segment identifier in the Audience Manager UI (open text field), which would then reflect in this property. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Definisce lo stato di un utente nel segmento. Accetta i seguenti valori: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Attivo (predefinito) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inattivo, escluso o non segmentato. </li> 
    </ul> <p>Gli utenti non sono segmentati quando: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Rimosso da un segmento in base alla regola del segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Rimosso da un segmento in base all'intervallo <a href="../../../features/traits/segment-ttl-explained.md"> time-to-live del segmento</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Moved to an inactive state if they have not been seen for the last 120-days. </li>
     <li>Removed due to a privacy change request (i.e. [!DNL GDPR])</li>
    </ul> <p>Tutti gli ID partner sincronizzati con un ID <span class="keyword"> Audience Manager</span> riceveranno il flag <code> "Status":"0"</code> quando un utente non è segmentato. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>The time when the user-segment qualification was most recently verified.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicurezza

You can secure your real-time outbound data transfer process by signing HTTP requests using private keys or by having  authenticate through the OAuth 2.0 protocol.[](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)[!DNL Audience Manager][](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md)

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
