---
description: Il processo di trasferimento dei dati in tempo reale in uscita restituisce i dati utente come una serie di oggetti JSON passati con un metodo POST.
seo-description: Il processo di trasferimento dei dati in tempo reale in uscita restituisce i dati utente come una serie di oggetti JSON passati con un metodo POST.
seo-title: Trasferimenti di dati in uscita in tempo reale
solution: Audience Manager
title: Trasferimenti di dati in uscita in tempo reale
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Trasferimenti di dati in uscita
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 5%

---

# Trasferimenti di dati in uscita in tempo reale {#real-time-outbound-data-transfers}

Il processo di trasferimento dei dati in tempo reale in uscita fornisce i dati utente come una serie di messaggi formattati [!DNL JSON] a una piattaforma di destinazione.

<!-- c_outbound_json.xml -->

## Consigli

Per utilizzare questo metodo, la piattaforma di destinazione deve soddisfare i seguenti requisiti:

* Deve fornire un endpoint [!DNL URL] scalabile in modo da ricevere un elevato volume di messaggi dall&#39;Audience Manager;
* Accetta i dati in formato [!DNL JSON] (`Content-type: application/json`);
* Deve accettare trasferimenti di dati `HTTPS` sicuri. [!DNL Audience Manager] non invierà messaggi tramite il  `HTTP` protocollo non sicuro.

## Frequenza

Questo metodo di trasferimento dati può inviare dati in tempo quasi reale, in quanto gli utenti si qualificano per i segmenti. I messaggi in tempo reale vengono inviati solo quando l’utente è online e attivamente visibile alla rete Audience Manager Edge. Facoltativamente, questo metodo può anche inviare batch di dati offline o onboarded con la stessa frequenza di ogni 24 ore.

## Trasferimenti in batch

I trasferimenti in tempo reale e in batch vengono inviati allo stesso endpoint e utilizzano lo stesso formato di messaggio. Quando i trasferimenti batch sono abilitati, la piattaforma di destinazione visualizzerà un picco nel volume dei messaggi durante la consegna dei messaggi batch. Molte delle qualifiche dei segmenti inviate tramite messaggi in tempo reale verranno ripetute nei messaggi batch. I trasferimenti in batch includeranno solo le qualifiche del segmento (o le qualifiche) modificate dall&#39;ultimo batch consegnato.

## Limiti di velocità

Non sono impostati limiti di velocità sulla velocità effettiva dei messaggi eliminati. L&#39;impostazione di limiti di velocità potrebbe causare la perdita di dati.

## Risposte richieste

Per impostazione predefinita, il server destinatario deve restituire il codice `200 OK` per indicare la ricezione corretta. Altri codici verranno interpretati come errori. Questa risposta è prevista entro 3000 millisecondi. In risposta a un errore, [!DNL Audience Manager] eseguirà un solo tentativo.

## Parametri

La tabella seguente definisce gli elementi nel file di dati [!DNL JSON] inviato alla destinazione.

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
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">ID Android (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID iOS (IDFA): <code> 20915</code> </li>
     <li>ID web/cookie: varia in base alla piattaforma di destinazione</li>
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
   <td colname="col3"> <p>ID dell'oggetto "destinazione" di Audience Manager. L'ID proviene dall'Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Numero totale di utenti nella richiesta <code> POST</code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Matrice di oggetti utente. Per impostazione predefinita, ogni messaggio contiene da 1 a 10 utenti, per mantenere la dimensione ottimale del messaggio. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>L' <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>UUID della piattaforma di destinazione o ID dispositivo globale. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> L' <span class="keyword"> ID di regione Audience Manager</span> in cui è stato visualizzato questo dispositivo. Ad esempio, se il dispositivo ha un’attività a Parigi (Europa), l’ID di regione è <code> 6</code>. Consulta <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID regioni DCS, posizioni e nomi host</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Matrice di oggetti segmento. Per i messaggi in tempo reale, l’array contiene tutti i segmenti a cui appartiene l’utente. Per i messaggi batch, l’array contiene solo le modifiche al segmento dall’ultimo batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmnent.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Identificatore del segmento. Nella maggior parte dei casi, si tratta dell’ID del segmento generato dall’Audience Manager (un numero intero). In alcuni casi, se la piattaforma di destinazione lo consente, i clienti possono definire l’identificatore del segmento nell’interfaccia utente di Audience Manager (campo di testo aperto), che rifletterebbe in questa proprietà. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Definisce lo stato di un utente nel segmento. Accetta i seguenti valori: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Attivo (predefinito) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inattivo, disattivato o non segmentato. </li> 
    </ul> <p>Gli utenti non sono segmentati quando sono: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Rimosso da un segmento in base alla regola del segmento. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Rimosso da un segmento in base all’ <a href="../../../features/traits/segment-ttl-explained.md"> intervallo time-to-live del segmento</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Se non sono stati visualizzati negli ultimi 120 giorni, lo stato attivo viene spostato in uno stato inattivo. </li>
     <li>Rimosso a causa di una richiesta di modifica della privacy (cioè <span class="keyword"> RGPD</span>)</li>
    </ul> <p>Tutti gli ID partner sincronizzati con un ID <span class="keyword"> Audience Manager</span> riceveranno il flag <code> "Status":"0"</code> quando un utente non è segmentato. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Data e ora dell’ultima verifica della qualifica del segmento utente.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicurezza

Puoi proteggere il processo di trasferimento dei dati in uscita in tempo reale firmando [richieste HTTP](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) utilizzando chiavi private o facendo sì che [!DNL Audience Manager] sia autenticato tramite il protocollo [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md).

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
