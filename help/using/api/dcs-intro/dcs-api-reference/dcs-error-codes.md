---
description: Codici di errore e messaggi generati dai server di raccolta dati (DCS, Data Collection Servers) elencati in ordine numerico per ID codice.
title: Codici errore DCS, messaggi ed esempi
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 2012c244f6fa5ca01c7e2719ce621214cb22f93e
workflow-type: tm+mt
source-wordcount: '1517'
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
| 2 | Valore `d_orgid` non valido (impossibile trovare una configurazione per questo ID organizzazione): `ID` | L’ID organizzazione non è corretto. Controlla il tuo ID e invia di nuovo la richiesta. Se non conosci o non possiedi il tuo ID organizzazione, consulta la sezione &quot;Pagina di amministrazione&quot; [Organizzazioni e collegamento di account](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) per informazioni su come trovarlo. |
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

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID codice </th> 
   <th colname="col2" class="entry"> Messaggio </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>ID cliente non valido <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L’ID cliente non è valido (valori mancanti per l’origine dati, codici di integrazione mancanti, formato non valido per le origini dati, ID cliente bloccato, ID cliente vuoto, tentativo di accesso non autorizzato a un’origine dati che non appartiene al partner). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>È stato superato il numero massimo di ID cliente. Il numero massimo consentito è <code><i>maximum allowed</i></code>. Trovato: <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>Il numero di ID cliente associati a un’origine dati multi-dispositivo supera il numero consentito di ID multi-dispositivo per richiesta. Questi ID includono ID per diversi dispositivi, dispositivi mobili o cookie. Il limite è attualmente impostato su 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID cliente non autorizzato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'origine dati dell'ID cliente non è di proprietà dell'ID organizzazione corrente. Se non conosci o non possiedi il tuo ID organizzazione, consulta la sezione "Trova il tuo ID organizzazione" in <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizzazioni e collegamento account</a> per informazioni su come trovarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID cliente bloccato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'ID cliente è stato identificato come dannoso e aggiunto a un elenco Bloccati di. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID origine dati bloccato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l’ID dell’origine dati è stato identificato come dannoso e aggiunto a un inserisco nell'elenco Bloccati di </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID dispositivo dichiarato bloccato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L'ID dispositivo è stato identificato come dannoso ed è stato aggiunto a un elenco Bloccati di. Questo problema può verificarsi quando si riceve una quantità estrema di <span class="wintitle"> richieste DCS</span> contenenti questo ID dispositivo in breve tempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operazione profilo bloccata per <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un'azione di lettura/scrittura è stata bloccata perché un ID è stato identificato come dannoso ed è stato aggiunto a un elenco Bloccati di lettura/scrittura. Vedere il codice di errore 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>L'ID cliente <code><i>ID</i></code> è stato eliminato perché ha superato il limite di ID cliente dichiarati per richiesta </p> </td> 
   <td colname="col3"> <p>Correlato all’errore 301. Questo errore specifica quale ID cliente è stato scartato a causa del superamento del limite. </p> <p>Ad esempio, se nella chiamata DCS<span class="wintitle"> di </span> sono dichiarati 12 ID cliente, due di essi verranno eliminati. Per inoltrare quali sono stati scartati, questo errore verrà visualizzato due volte nella risposta (una volta per ogni ID cliente scartato ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>L'ID cliente è stato scartato perché superava il limite per un dato spazio dei nomi. ID dello spazio dei nomi: <code><i>ID</i></code>; ID cliente: <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Questo codice di errore viene restituito se sono presenti più di 3 ID cliente dichiarati per lo stesso spazio dei nomi (<code> DPID</code>) in una chiamata DCS<span class="wintitle"> di </span>. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In questa richiesta <span class="wintitle"> DCS</span> di esempio sono presenti 4 ID dichiarati per lo stesso spazio dei nomi (con codice di integrazione 1). Uno degli ID viene eliminato e viene restituito l’errore 310. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La richiesta contiene parametri non validi </p> </td> 
   <td colname="col3"> <p>Il DCS<span class="wintitle"> di </span> restituisce questo codice di errore quando almeno un parametro URL non è codificato correttamente. In questo caso, il DCS <span class="wintitle"></span> ignora l'intera richiesta. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>Nella richiesta di esempio precedente, la sequenza <code> %</code> non è codificata correttamente. Di conseguenza, il DCS <span class="wintitle"></span> lo ignorerà. </p> <p>L’esempio codificato correttamente dovrebbe essere simile al seguente: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La richiesta contiene un ID dispositivo globale non valido </p> </td> 
   <td colname="col3"> <p><span class="wintitle">DCS</span> restituisce questo codice di errore se la richiesta contiene un ID dispositivo globale non valido. DCS ignora l’ID non valido e genera un errore 312 insieme a errori specifici dell’ID non valido. Consulta <a href="../../../features/global-data-sources.md" format="dita" scope="local">Global Data Sources</a> e <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index of IDs in Audience Manager</a> per informazioni dettagliate sui formati degli ID di pubblicità del dispositivo corretti e sulle corrispondenti origini dati globali.</p>
   <p>Esempio di chiamata non corretta: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Spiegazione: un <span class="keyword">IDFA (DPID 20915)</span> deve essere un ID maiuscolo. L’ID fornito nella richiesta è in minuscolo.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>L’ID CMP non è presente in GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e la stringa TC IAB vengono generati da un ID CMP non presente nella versione cache di Audience Manager dell'elenco CMP globale al momento della valutazione, il plug-in Audience Manager per IAB TCF elimina la stringa TC IAB ed elabora la richiesta come di consueto. La macro IAB TCF v2.2 ${GDPR} è impostata su 0 e la macro ${GDPR_CONSENT_XXX} è vuota.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>L’ID CMP è contrassegnato come eliminato in GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e la stringa TC IAB vengono generati da una CMP contrassegnata come eliminata nella versione cache dell'elenco CMP globale, il plug-in di Audience Manager per IAB TCF elimina la stringa TC ed elabora la richiesta come di consueto, se il tempo di valutazione è superiore al tempo di eliminazione dall'elenco CMP globale. La macro IAB TCF v2.2 ${GDPR} è impostata su 0 e la macro ${GDPR_CONSENT_XXX} è vuota.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>La stringa di consenso indica che non esiste alcun consenso</p> </td> 
   <td colname="col3"> <p>Se non viene fornito il consenso, il plug-in Audience Manager per IAB TCF rifiuta l’ulteriore raccolta di dati all’utente o elimina completamente la chiamata se non viene rilevato alcun contesto di partner.</p>
   </td>
  </tr>
 </tbody>
</table>

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
