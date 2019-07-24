---
description: Il processo di trasferimento dati in tempo reale in uscita restituisce dati utente come serie di oggetti JSON passati con un metodo POST.
seo-description: Il processo di trasferimento dati in tempo reale in uscita restituisce dati utente come serie di oggetti JSON passati con un metodo POST.
seo-title: Trasferimenti di dati in tempo reale
solution: Audience Manager
title: Trasferimenti di dati in tempo reale
uuid: 1895 e 818-7 ab 8-4569-a 920-4 b 0 a 4 c 8 b 83 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Outbound Data Transfers {#real-time-outbound-data-transfers}

The outbound real-time data transfer process returns user data as a series of [!DNL JSON] objects passed in with a `POST` method.

<!-- c_outbound_json.xml -->

## Consigli

Per utilizzare questo metodo, consigliamo di inserire il partner dati:

* Accepts data in [!DNL JSON] format.
* Provides a URL that can be used by the `POST` call to return data.
* Accepts secure `HTTPS` data transfers. [!DNL Audience Manager] non invierà questo file con il `HTTP` protocollo non sicuro.

## Frequenza

Questo metodo di trasferimento dati può inviare dati in tempo reale quando gli utenti si qualificano per i segmenti. Inoltre, questo metodo può inviare i batch di dati offline o caricati ogni 24 ore.

## Risposte richieste

By default, the recipient server must return the `200 OK` code to indicate successful receipt. Altri codici saranno interpretati come errori. Questa risposta è prevista entro 3000 millisecondi. In response to a failure, [!DNL Audience Manager] will make 1 retry attempt only.

## Parametri

The following table defines the elements in the returned [!DNL JSON] data file.

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
   <td colname="col1"> <code><i>Procesror</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>Ora in cui è stata eseguita la richiesta. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ DPID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Un ID che indica se il file contiene ID Android o iOS. Utilizza i seguenti valori ID: </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android IDs (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS IDs (IDFA): <code> 20915</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ ID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>ID client utilizzato dal sistema a cui invii i dati. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Destination_ ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>L'ID assegnato dal partner di destinazione. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ count</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Total number of users in the <code> POST</code> request. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Utenti</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Un array di oggetti utente. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ UUID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datapartner_ UUID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>UUID dei partner dati. Lascia vuoto se il tuo partner di dati non ha un UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> The <span class="keyword"> Audience Manager</span> region ID where we've seen this device. For instance, if the device had some activity in Paris (Europe), the region ID would be <code> 6</code>. Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID regioni DCS, posizioni e nomi host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmenti</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Un array di oggetti segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmento_ ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>La mappatura di destinazione ID segmento. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Stato</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Definisce lo stato di un utente nel segmento. Accetta quanto segue: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Active (predefinito) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inattivo, Rifiutato o Non segmentato. </li> 
    </ul> <p>Gli utenti non vengono segmentati quando: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Rimosso da un segmento in base alla regola del segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Removed from a segment based on the segment's <a href="../../../features/traits/segment-ttl-explained.md"> time-to-live interval</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Spostato in stato inattivo se non è stato visualizzato per gli ultimi 120 giorni. </li> 
    </ul> <p>All partner IDs that are synced to an <span class="keyword"> Audience Manager</span> ID will receive the <code> "Status":"0"</code> flag when a user is unsegmented. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datetime</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>Time that a site visitor qualified for the trait. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicurezza

You can secure your real-time outbound data transfer process by [signing HTTP requests](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) using private keys or by having [!DNL Audience Manager] authenticate through the [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) protocol.

## Esempio di codice

Una risposta dati in tempo reale può essere simile a quella di seguito:

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
