---
description: Il processo di trasferimento dei dati in uscita in tempo reale restituisce i dati utente come una serie di oggetti JSON trasmessi con un metodo POST.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: Trasferimenti di dati in uscita in tempo reale
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 5%

---

# Trasferimenti di dati in uscita in tempo reale {#real-time-outbound-data-transfers}

Il processo di trasferimento dei dati in uscita in tempo reale fornisce dati utente sotto forma di [!DNL JSON] i messaggi formattati su una piattaforma di destinazione.

<!-- c_outbound_json.xml -->

## Consigli

Per utilizzare questo metodo, la piattaforma di destinazione deve soddisfare i seguenti requisiti:

* Deve fornire un endpoint [!DNL URL] che possono essere adattati per ricevere un elevato volume di messaggi da Audienci Manager;
* Deve accettare i dati in [!DNL JSON] formato (`Content-type: application/json`);
* Deve accettare una protezione `HTTPS` trasferimenti di dati. [!DNL Audience Manager] non invierà messaggi tramite unsecure `HTTP` protocollo.

## Frequenza

Questo metodo di trasferimento dati può inviare i dati quasi in tempo reale, in quanto gli utenti si qualificano per i segmenti. I messaggi in tempo reale vengono consegnati solo quando l’utente è online e visibile attivamente alla rete Edge di Audience Manager. Facoltativamente, questo metodo può anche inviare batch di dati offline o onboarded ogni 24 ore.

## Trasferimenti in batch

I trasferimenti in tempo reale e batch vengono inviati allo stesso endpoint e utilizzano lo stesso formato di messaggio. Quando i trasferimenti batch sono abilitati, la piattaforma di destinazione visualizza un picco nel volume dei messaggi durante la consegna dei messaggi batch. Molte delle qualifiche dei segmenti inviate tramite messaggi in tempo reale verranno ripetute nei messaggi batch. I trasferimenti in batch includeranno solo le qualifiche del segmento (o le non qualifiche) che sono cambiate dall’ultimo batch consegnato.

## Limiti di velocità

Non sono stati impostati limiti di velocità per la trasmissione dei messaggi recapitati. L’impostazione dei limiti di velocità potrebbe causare la perdita di dati.

## Risposte richieste

Per impostazione predefinita, il server destinatario deve restituire `200 OK` codice per indicare la ricezione riuscita. Altri codici verranno interpretati come errori. Questa risposta è prevista entro 3000 millisecondi. In risposta a un guasto, [!DNL Audience Manager] eseguirà un solo tentativo.

## Parametri

La tabella seguente definisce gli elementi nel [!DNL JSON] file di dati inviato alla destinazione.

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
   <td colname="col3"> <p>Ora in cui è stata eseguita la richiesta. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>ID che indica il tipo di ID dispositivo contenuti nel messaggio, nella proprietà User.DataPartner_UUID. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">ID Android (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID iOS (IDFA): <code> 20915</code> </li>
     <li>ID web/cookie: varia in base alla piattaforma di destinazione</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Rappresenta l’account di destinazione nella piattaforma di destinazione. Questo ID proviene dalla piattaforma di destinazione.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>ID dell’oggetto "destination" di Audience Manager. Questo ID ha origine da Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Numero totale di utenti nel <code> POST</code> richiesta. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Matrice di oggetti utente. Per impostazione predefinita, ogni messaggio contiene da 1 a 10 utenti, per mantenerne una dimensione ottimale. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Il <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>UUID della piattaforma di destinazione o ID del dispositivo globale. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> Il <span class="keyword"> Audience Manager</span> ID di regione in cui abbiamo visto questo dispositivo. Ad esempio, se il dispositivo avesse un’attività a Parigi (Europa), l’ID regione sarebbe <code> 6</code>. Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID regioni DCS, posizioni e nomi host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Array di oggetti segmento. Per i messaggi in tempo reale, l’array contiene tutti i segmenti a cui appartiene l’utente. Per i messaggi batch, l’array contiene solo le modifiche dei segmenti rispetto all’ultimo batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>L’identificatore del segmento. Nella maggior parte dei casi, si tratta dell’ID del segmento generato da Audience Manager (un numero intero). In alcuni casi, se la piattaforma di destinazione lo consente, i clienti possono definire l’identificatore del segmento nell’interfaccia utente di Audience Manager (campo di testo aperto), che si rifletterebbe in questa proprietà. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Definisce lo stato di un utente nel segmento. Accetta i seguenti valori: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Attivo (impostazione predefinita) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: inattiva, con rinuncia o non segmentata. </li> 
    </ul> <p>Gli utenti vengono rimossi dai segmenti quando sono: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Rimosso da un segmento in base alla regola del segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Rimosso da un segmento in base al di <a href="../../../features/traits/segment-ttl-explained.md"> intervallo time-to-live</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Se non sono stati visti negli ultimi 120 giorni, vengono trasferiti a uno stato inattivo. </li>
     <li>Rimosso a causa di una richiesta di modifica della privacy (ad es. <span class="keyword"> RGPD</span>)</li>
    </ul> <p>Tutti gli ID partner sincronizzati in un <span class="keyword"> Audience Manager</span> L’ID riceverà <code> "Status":"0"</code> Quando un utente viene rimosso dai segmenti. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>L’ultima volta che è stata verificata la qualifica utente-segmento.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicurezza

Per proteggere il processo di trasferimento dei dati in uscita in tempo reale, utilizza [firma delle richieste HTTP](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) utilizzando chiavi private o [!DNL Audience Manager] autenticare tramite [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) protocollo.

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
