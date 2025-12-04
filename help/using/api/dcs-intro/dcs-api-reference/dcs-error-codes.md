---
description: Codici di errore e messaggi generati dai server di raccolta dati (DCS, Data Collection Servers) elencati in ordine numerico per ID codice.
title: Codici errore DCS, messaggi ed esempi
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: f8ba09b674b71045e08f6d171471cdcdd0efb265
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 3%

---

# Codici errore DCS, messaggi ed esempi {#dcs-error-codes-messages-and-examples}

Codici di errore e messaggi generati da [!UICONTROL Data Collection Servers] ([!DNL DCS]) elencati in ordine numerico per ID di codice.

Nelle tabelle seguenti, *corsivo* rappresenta un segnaposto variabile.

## Codici errore di sistema {#system-error-codes}

| Codice di errore | Messaggio di errore | Descrizione |
|---|---|---|
| 0 | Errore non specificato | Si tratta di un errore catch-all che gestisce eventi non coperti dagli altri gestori di errori. La risoluzione di questo errore è difficile. Può essere causata da una serie di azioni o eventi sconosciuti. Se si riceve questo errore, riprovare la richiesta [!DNL DCS]. Se il problema persiste, contatta il rappresentante [!DNL Adobe]. |
| 1 | Impossibile trovare la configurazione per il nome host: `hostname` | Il nome host inviato nella richiesta non è stato configurato dal nostro team di provisioning partner. Se ricevi questo messaggio di errore, contatta il rappresentante [!DNL Adobe]. |
| 2 | Valore `d_orgid` non valido (impossibile trovare una configurazione per questo ID organizzazione): `ID` | L’ID organizzazione non è corretto. Controlla il tuo ID e invia di nuovo la richiesta. Se non conosci o non possiedi il tuo ID organizzazione, consulta la sezione &quot;Pagina di amministrazione&quot; [Organizzazioni e collegamento di account](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=it) per informazioni su come trovarlo. |
| 10 | Impossibile valutare le caratteristiche | Le caratteristiche della richiesta sono state valutate parzialmente o non sono state valutate affatto. Se il problema persiste, contatta il rappresentante [!DNL Adobe]. |

## Codici errore di integrazione {#integration-error-codes}

| Codice di errore | Messaggio di errore | Descrizione |
|---|---|---|
| 100 | Impossibile recuperare il nome host per la richiesta | Una chiamata [!DNL API] non ha inviato l&#39;intestazione host [!DNL HTTP] nella richiesta. Aggiungi l’intestazione host alla chiamata e riprova. La maggior parte dei browser e dei client [!DNL API] esegue automaticamente questa operazione. |
| 101 | ID [!DNL Experience Cloud] non valido passato in `ID` | La chiamata [!DNL DCS] contiene un ID [!DNL Experience Cloud] non valido. Controllare la coppia chiave-valore `d_mid=` nella stringa di intestazione. Verificare di aver immesso l&#39;ID [!DNL Experience Cloud] corretto e riprovare. |
| 102 | [!DNL AAM ID] non valido passato nella richiesta `ID` | La chiamata [!DNL DCS] contiene un ID [!DNL Audience Manager] non valido. Controllare la coppia chiave-valore `d_uuid=` nella stringa di intestazione. Verificare di aver immesso l&#39;ID [!DNL Audience Manager] corretto e riprovare. |
| 104 | Tutti gli ID cliente non sono validi | Tutti gli ID cliente nella chiamata non sono validi. Controlla i tuoi ID e riprova. |
| 109 | Referer `HTTP referer` non consentito per il partner `Partner ID` | L&#39;intestazione `HTTP referer` nella chiamata non è consentita per l&#39;ID partner nella chiamata. Verificare che l&#39;intestazione `HTTP referer` sia corretta. |
| 111 | Token `IMS` non valido ricevuto | Restituito per [!DNL Audience Manager] - [!DNL Adobe Target] integrazioni. L&#39;errore viene generato quando viene effettuata una chiamata a [!DNL DCS], contenente un token [!DNL IMS] non valido. Il token potrebbe essere in un formato non valido, scaduto o l’utente potrebbe non essere autorizzato ad accedere alla risorsa richiesta. |

## Codici di errore di rinuncia {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID codice </th> 
   <th colname="col2" class="entry"> Messaggio </th> 
   <th colname="col3" class="entry"> Descrizione </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Rilevato tag di rinuncia per l'ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un cliente ha rinunciato a ricevere pubblicità basata sugli interessi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookie bloccati </p> </td> 
   <td colname="col3"> <p>Restituito quando il browser dell’utente blocca i cookie di terze parti.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Rilevata relazione di trust tramite <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>L’utente ha avviato un processo di rinuncia tramite NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Le richieste provenienti da questo paese sono bloccate dai partner </p> </td> 
   <td colname="col3"> <p>In base all'indirizzo IP, il DCS<span class="wintitle"> di </span> blocca le richieste provenienti da paesi in cui il partner ha deliberatamente limitato il traffico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Non sono consentite richieste da questo paese </p> </td> 
   <td colname="col3"> <p>In base all'indirizzo IP, il DCS<span class="wintitle"> di </span> blocca le richieste dai seguenti paesi: </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">Cuba (CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">Iran (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">Corea del Nord (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">Sudan (SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">Siria (SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Codici errore di recupero profilo {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID codice </th> 
   <th colname="col2" class="entry"> Messaggio </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> Impossibile leggere le caratteristiche dalla cache del profilo per l'ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando un profilo utente non può essere letto dall’archiviazione interna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Impossibile leggere gli ID dispositivo dalla cache del profilo per l'ID cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando non è possibile recuperare l'ID dispositivo <a href="../../../reference/ids-in-aam.md"></a> per una regola di unione Collegamento profilo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Impossibile leggere il cliente correlato per l'ID dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'ID cliente <a href="../../../reference/ids-in-aam.md"> (UUID)</a> associato a un ID dispositivo non può essere recuperato per una regola di unione Ultima autenticazione dall'archiviazione interna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Impossibile leggere il cluster di dispositivi per l'ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Per questo ID dispositivo non possono essere restituiti gli ID dispositivo collegati dallo stesso cluster di grafo dispositivi. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Impossibile eseguire la migrazione perché la lettura del profilo per il dispositivo primario non è riuscita </p> </td> 
   <td colname="col3"> <p>Se ricevi questo errore, potrebbero verificarsi problemi di scalabilità con l'archivio dati (<span class="wintitle"> PCS</span>). Se il problema persiste, contatta il rappresentante Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Impossibile eseguire la migrazione da <code><i>ID</i></code> a <code><i>ID</i></code>. Lettura del profilo non riuscita per <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Se ricevi questo errore, potrebbero verificarsi problemi di scalabilità con l'archivio dati (<span class="wintitle"> PCS</span>). Se il problema persiste, contatta il rappresentante Adobe. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Codici di avviso dell&#39;integrazione {#integration-warning-codes}

| ID codice | Messaggio | Descrizione |
| --- | --- | --- |
| 300 | ID cliente non valido `_ID_` | L’ID cliente non è valido (valori mancanti per l’origine dati, codici di integrazione mancanti, formato non valido per le origini dati, ID cliente bloccato, ID cliente vuoto, tentativo di accesso non autorizzato a un’origine dati che non appartiene al partner). |
| 301 | È stato superato il numero massimo di ID cliente. Il numero massimo consentito è `_maximum allowed_`. Trovato: `_maximum found_`. | Il numero di ID cliente associati a un’origine dati multi-dispositivo supera il numero consentito di ID multi-dispositivo per richiesta. Questi ID includono ID per diversi dispositivi, dispositivi mobili o cookie. Il limite è attualmente impostato su 10. |
| 302 | ID cliente non autorizzato `_ID_` | Restituito quando l&#39;origine dati dell&#39;ID cliente non è di proprietà dell&#39;ID organizzazione corrente. Se non conosci o non possiedi il tuo ID organizzazione, consulta la sezione &quot;Trova il tuo ID organizzazione&quot; in [Organizzazioni e collegamento account](https://experiencecloud.adobe.com/resources/help/it_IT/mcloud/organizations.html) per informazioni su come trovarlo. |
| 303 | ID cliente bloccato `_ID_` | Restituito quando l&#39;ID cliente è stato identificato come dannoso e aggiunto a un elenco Bloccati di. |
| 304 | ID origine dati bloccato `_ID_` | Restituito quando l’ID dell’origine dati è stato identificato come dannoso e aggiunto a un inserisco nell&#39;elenco Bloccati di |
| 306 | ID dispositivo dichiarato bloccato `_ID_` | L’ID dispositivo è stato identificato come dannoso ed è stato aggiunto a un elenco Bloccati di. Questo può accadere quando riceviamo una quantità estrema di richieste DCS contenenti questo ID dispositivo in un breve periodo di tempo. |
| 307 | Operazione profilo bloccata per `_ID_` | Un&#39;azione di lettura/scrittura è stata bloccata perché un ID è stato identificato come dannoso ed è stato aggiunto a un elenco Bloccati di lettura/scrittura. Vedere il codice di errore 306. |
| 309 | L&#39;ID cliente `_ID_` è stato eliminato perché ha superato il limite di ID cliente dichiarati per richiesta | Correlato all’errore 301. Questo errore specifica quale ID cliente è stato scartato a causa del superamento del limite.<br><br>Ad esempio, se nella chiamata DCS sono dichiarati 12 ID cliente, due di essi verranno eliminati. Per inoltrare quali sono stati scartati, questo errore verrà visualizzato due volte nella risposta (una volta per ogni ID cliente scartato ). |
| 310 | L&#39;ID cliente è stato scartato perché superava il limite per un dato spazio dei nomi. ID dello spazio dei nomi: `_ID_`; ID cliente: `_ID_`. | Questo codice di errore viene restituito se esistono più di 3 ID cliente dichiarati per lo stesso spazio dei nomi ( `DPID`) in una chiamata DCS.<br><br>`https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one`<br><br>In questa richiesta DCS di esempio sono presenti 4 ID dichiarati per lo stesso spazio dei nomi (con codice di integrazione 1). Uno degli ID viene eliminato e viene restituito l’errore 310. |
| 311 | La richiesta contiene parametri non validi | Il DCS restituisce questo codice di errore quando almeno un parametro URL non è codificato correttamente. In questo caso, il DCS ignora l’intera richiesta.<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%esid!&d_creative=%ecid!&d_adgroup=%eaid!&d_placement=%epid!&d_campaign=%ebuy!&d_adsrc=48123`<br><br>Nella richiesta di esempio precedente, la sequenza `%` non è codificata correttamente. Di conseguenza, il DCS lo ignorerà.<br><br>L&#39;esempio codificato correttamente dovrebbe essere simile al seguente:<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%25esid!&d_creative=%25ecid!&d_adgroup=%25eaid!&d_placement=%25epid!&d_campaign=%25ebuy!&d_adsrc=48123` |
| 312 | La richiesta contiene un ID dispositivo globale non valido | Il DCS restituisce questo codice di errore se la richiesta contiene un ID dispositivo globale non valido. DCS ignora l’ID non valido e genera un errore 312 insieme a errori specifici dell’ID non valido. Consulta [Global Data Sources](../../../features/global-data-sources.md) e [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) per informazioni dettagliate sui formati degli ID di pubblicità del dispositivo corretti e sulle corrispondenti origini dati globali.<br><br>Esempio di chiamata non corretta: `"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"`<br><br>Spiegazione: un IDFA (DPID 20915) deve essere un ID maiuscolo. L’ID fornito nella richiesta è in minuscolo. |
| 313 | L’ID CMP non è presente in GCL | Quando `gdpr=1` e la stringa TC IAB vengono generati da un ID CMP non presente nella versione cache di Audience Manager dell&#39;elenco CMP globale al momento della valutazione, il plug-in Audience Manager per IAB TCF elimina la stringa TC IAB ed elabora la richiesta come di consueto. La macro IAB TCF v2.2 ${GDPR} è impostata su 0 e la macro ${GDPR\_CONSENT\_XXX} è vuota. |
| 314 | L’ID CMP è contrassegnato come eliminato in GCL | Quando `gdpr=1` e la stringa TC IAB vengono generati da una CMP contrassegnata come eliminata nella versione cache dell&#39;elenco CMP globale, il plug-in di Audience Manager per IAB TCF elimina la stringa TC ed elabora la richiesta come di consueto, se il tempo di valutazione è superiore al tempo di eliminazione dall&#39;elenco CMP globale. La macro IAB TCF v2.2 ${GDPR} è impostata su 0 e la macro ${GDPR\_CONSENT\_XXX} è vuota. |
| 315 | La stringa di consenso indica che non esiste alcun consenso | Se non viene fornito il consenso, il plug-in Audience Manager per IAB TCF rifiuta l’ulteriore raccolta di dati all’utente o elimina completamente la chiamata se non viene rilevato alcun contesto di partner. |

## Esempi di messaggi di codice di errore {#sample-error-codes}

[!DNL DCS] restituisce codici di errore e messaggi in un oggetto [!DNL JSON] o in un&#39;intestazione X nella stringa di risposta HTTP.

### Codice errore DCS di esempio e messaggio

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-Error

I codici di errore acquisiti dall&#39;intestazione X- vengono visualizzati nella stringa dell&#39;URL come `X-Error: 101,102`.

[Race condition e gestione degli errori](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
