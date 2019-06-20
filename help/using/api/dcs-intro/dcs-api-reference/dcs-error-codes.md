---
description: Codici di errore e messaggi generati dai server di raccolta dati (DCS) elencati in ordine numerico tramite ID codice.
seo-description: Codici di errore e messaggi generati dai server di raccolta dati (DCS) elencati in ordine numerico tramite ID codice.
seo-title: Codici errore DCS, messaggi ed esempi
solution: Audience Manager
title: Codici errore DCS, messaggi ed esempi
uuid: d 3290038-567 b -4 c 00-bc 95-2 cec 683 da 5 ec
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Codici errore DCS, messaggi ed esempi {#dcs-error-codes-messages-and-examples}

Codici di errore e messaggi generati da [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]) elencati in ordine numerico tramite ID codice.

Nelle tabelle riportate di seguito, *il corsivo* rappresenta un segnaposto variabile.

## Codici di errore di sistema {#system-error-codes}

<table id="table_43F4321BEA6A4D1BBDFE2E9FB4402914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID codice </th> 
   <th colname="col2" class="entry"> Messaggio di errore </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>0 </p> </td> 
   <td colname="col2"> <p>Errore non specificato </p> </td> 
   <td colname="col3"> <p>Si tratta di un errore catch-all che gestisce gli eventi non coperti dagli altri gestori di errore. La risoluzione di problemi è difficile. Può essere causato da una serie di azioni o eventi sconosciuti. </p> <p>Se ricevi questo errore, prova nuovamente la richiesta <span class="wintitle"> DCS</span> . Se il problema persiste, contattate il rappresentante Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Impossibile trovare la configurazione per nomehost: <code><i>nomehost</i></code> </p> </td> 
   <td colname="col3"> <p>Il nome host inviato nella richiesta non è stato configurato dal nostro team di provisioning del partner. Se viene visualizzato questo messaggio di errore, contattate il rappresentante Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Valore <code> d_ orgid</code> non valido (impossibile trovare una configurazione per questo ID organizzazione): <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L'ID organizzazione non è corretto. </p> <p>Controlla l'ID e riprova. Se non conosci o non disponi del tuo ID organizzazione, consulta la sezione «Pagina di amministrazione» nell'amministrazione <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> di Experience Cloud</a> per informazioni su come trovarlo. </p> </td> 
  </tr>
 </tbody>
</table>

## Codici di errore per l&#39;integrazione {#integration-error-codes}

<table id="table_EFF06FB3D045459BA7802872AF22DF79"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID codice </th> 
   <th colname="col2" class="entry"> Messaggio </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>100 </p> </td> 
   <td colname="col2"> <p>Impossibile recuperare il nome host per la richiesta </p> </td> 
   <td colname="col3"> <p>Una chiamata API non ha inviato l'intestazione HTTP host nella richiesta. </p> <p>Aggiungi l'intestazione host alla chiamata e riprova. La maggior parte dei browser e i client API effettuano questa operazione automaticamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>ID Experience Cloud non valido trasmesso in <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>La <span class="wintitle"> chiamata DCS</span> contiene un Experience <span class="keyword"> Cloud</span> ID non valido. </p> <p>Controllare la <code> coppia d_ mid =</code> key-value nella stringa dell'intestazione. Assicurati di passare l'Experience <span class="keyword"> Cloud</span> ID corretto e riprova. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>ID aam non valido trasmesso in <code><i>ID richiesta</i></code> </p> </td> 
   <td colname="col3"> <p>La <span class="wintitle"> chiamata DCS</span> contiene un ID <span class="keyword"> Audience Manager</span> non valido. </p> <p>Controllare la <code> coppia d_ uuid =</code> key-value nella stringa dell'intestazione. Assicurati di passare l'ID <span class="keyword"> Audience Manager</span> corretto e riprova. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>Tutti gli ID cliente non sono validi </p> </td> 
   <td colname="col3"> <p>Tutti gli ID cliente nella chiamata non sono validi. Controlla gli ID e riprova. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>Token <span class="wintitle"> IMS</span> non valido ricevuto </p> </td> 
   <td colname="col3"> <p>Restituito per le integrazioni Audience Manager - Adobe Target. L'errore viene restituito quando viene effettuata una chiamata al DCS, contenente un token IMS non valido. Il token potrebbe essere formattato, scaduto o l'utente potrebbe non essere autorizzato ad accedere alla risorsa richiesta. </p> </td>
  </tr>
 </tbody>
</table>

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
   <td colname="col2"> <p>Tag di rifiuto rilevato per <code><i>ID ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un cliente ha rinunciato alla ricezione della pubblicità basata sugli interessi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookie bloccati </p> </td> 
   <td colname="col3"> <p>Restituito quando il browser dell'utente blocca i cookie di terze parti.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relazione di affidabilità rilevata tramite <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>L'utente ha avviato un processo di rinuncia tramite NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Le richieste di questo paese sono bloccate dal partner </p> </td> 
   <td colname="col3"> <p>In base all'indirizzo IP, <span class="wintitle"> il DCS</span> blocca le richieste da paesi in cui il partner ha deliberatamente limitato il traffico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Non sono consentite richieste da questo paese </p> </td> 
   <td colname="col3"> <p>In base all'indirizzo IP, il <span class="wintitle"> DCS</span> blocca i seguenti paesi: </p> <p> 
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

## Codici di errore Recupero profilo {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> Impossibile leggere le caratteristiche dalla cache del profilo per id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando non è possibile leggere un profilo utente dall'archivio interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Impossibile leggere gli ID dispositivo dalla cache del profilo per ID cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando non è possibile recuperare l' <a href="../../../reference/ids-in-aam.md"> ID</a> dispositivo per una regola Unione collegamento profilo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Impossibile leggere il cliente correlato per l'ID dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'ID <a href="../../../reference/ids-in-aam.md"> cliente (UUID)</a> associato a un ID dispositivo non può essere recuperato per un'ultima regola di unione autenticata dal nostro archivio interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Impossibile leggere cluster dispositivo per id: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Non è possibile restituire gli ID dispositivo collegati dello stesso cluster di grafico dispositivo per questo ID dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Impossibile eseguire la migrazione dalla lettura del profilo per il dispositivo principale </p> </td> 
   <td colname="col3"> <p>Se ricevi questo errore, potrebbero verificarsi problemi di scalabilità con il nostro archivio dati<span class="wintitle"> (PCS</span>). Se il problema persiste, contattate il rappresentante Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Impossibile eseguire la migrazione da <code><i>ID</i></code> a <code><i>ID</i></code>, perché la lettura del profilo non è riuscita per <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Se ricevi questo errore, potrebbero verificarsi problemi di scalabilità con il nostro archivio dati<span class="wintitle"> (PCS</span>). Se il problema persiste, contattate il rappresentante Adobe. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Codici di avviso per l&#39;integrazione {#integration-warning-codes}

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
   <td colname="col2"> <p>ID ID cliente <code><i>non valido</i></code> </p> </td> 
   <td colname="col3"> <p>L'ID cliente non è valido (valori mancanti per l'origine dati, codici di integrazione mancanti, formato non valido per le origini dati, ID cliente bloccato, ID cliente vuoto, tentativo di accesso non autorizzato a un'origine dati che non appartiene al partner). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Numero massimo di ID cliente superato. Il massimo consentito è <code><i>consentito</i></code>. Trovato <code><i>il massimo trovato</i></code>.</p> </td> 
   <td colname="col3"> <p>Il numero di ID cliente associati a un'origine dati multi-dispositivo supera il numero consentito di ID cross-device per richiesta. Questi ID includono ID per dispositivi mobili, mobili o cookie. Il limite è attualmente impostato su 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p><code><i>ID ID cliente non autorizzato</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'origine dati ID cliente non è di proprietà dall'ID organizzazione corrente. Se non conosci o non disponi del tuo ID organizzazione, consulta la sezione «Trova ID organizzazione» in <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizzazioni e collegamento</a> account per informazioni su come trovarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID ID cliente <code><i>bloccato</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'ID cliente è stato identificato come dannoso ed è stato inserito in blacklist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID ID datasource <code><i>bloccato</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'ID di origine dati è stato identificato come dannoso ed è stato inserito in blacklist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p><code><i>ID ID dispositivo dichiarato bloccato</i></code> </p> </td> 
   <td colname="col3"> <p>L'ID dispositivo è stato identificato come dannoso ed è stato inserito in blacklist. Questo può verificarsi quando ricevete una quantità estrema di richieste <span class="wintitle"> DCS</span> contenenti questo ID dispositivo in un breve lasso di tempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operazione di profilo bloccata per <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un'azione di lettura/scrittura è stata bloccata perché un ID è stato identificato come dannoso ed è stato inserito in blacklist. Vedere codice di errore 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p><code><i>ID ID</i></code> cliente è stato eliminato perché superato il limite degli ID cliente dichiarati per richiesta </p> </td> 
   <td colname="col3"> <p>Correlato all'errore 301. Questo errore specifica quale ID cliente è stato eliminato perché il limite è stato superato. </p> <p>Ad esempio, se nella chiamata <span class="wintitle"> DCS</span> sono presenti 12 ID cliente, due di essi verranno eliminati. Per relazionare quali sono stati eliminati, questo errore apparirà due volte nella risposta (una per ogni ID cliente eliminato). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>ID cliente è stato eliminato perché eccede il limite di un determinato namespace. Namespace id is <code><i>ID</i></code>, customer id is <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Questo codice di errore viene restituito se vi sono più di 3 ID cliente dichiarati per lo stesso namespace (<code> DPID</code>) in una <span class="wintitle"> chiamata DCS</span> . </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In questa richiesta <span class="wintitle"> DCS</span> di esempio, sono presenti 4 ID dichiarati per lo stesso namespace (con il codice di integrazione uno). Uno degli ID viene eliminato e viene restituito l'errore 310. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La richiesta contiene parametri non validi </p> </td> 
   <td colname="col3"> <p>Il <span class="wintitle"> DCS</span> restituisce questo codice di errore quando almeno un parametro URL non è codificato correttamente. In questo caso, <span class="wintitle"> il DCS</span> ignora l'intera richiesta. </p> <p><code>http (s): // partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp; d_ creative = % ecid!&amp; d_ adgroup = % eaid!&amp; d_ placement = % epid!&amp; d_ campaign = % ebuy!&amp; d_ adsrc = 48123</code> </p> <p>Nella richiesta di esempio sopra, la <code> sequenza %</code> è codificata in modo errato. Di conseguenza, <span class="wintitle"> il DCS</span> lo ignorerà. </p> <p>L'esempio correttamente codificato deve essere simile al seguente: </p> <p><code>http (s): // partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp; d_ creative = % 25 ecid!&amp; d_ adgroup = % 25 eaid!&amp; d_ placement = % 25 epid.&amp; d_ campaign = % 25 ebuy!&amp; d_ adsrc = 48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La richiesta contiene un ID dispositivo globale non valido </p> </td> 
   <td colname="col3"> <p>Il <span class="wintitle">DCS</span> restituisce questo codice di errore quando la richiesta contiene un ID dispositivo globale non valido. DCS ignora l'ID non valido e genera un errore 312 insieme agli errori specifici dell'ID non valido. Fai riferimento a Origini dati <a href="../../../features/global-data-sources.md" format="dita" scope="local">globali</a> e <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Indice degli ID in Audience Manager</a> per informazioni dettagliate sui formati corretti degli ID pubblicitari e sulle origini dati globali corrispondenti.</p>
   <p>Esempio di chiamata errata: <code>" http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z "</code></p>
   <p>Spiegazione: Un <span class="keyword">IDFA (DPID 20915)</span> deve essere un ID maiuscolo. L'ID fornito nella richiesta è minuscolo.</p>
   </td>
  </tr>

</tbody>
</table>

## Messaggi di codice errori di esempio {#sample-error-codes}

I [!UICONTROL DCS] codici di errore e i messaggi restituiscono i messaggi in un [!DNL JSON] oggetto o in un&#39;intestazione X- nella stringa di risposta HTTP.

### Codice e messaggio di errore DCS di esempio

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

### Errore X

Error codes captured by the X- header appear in the URL string like this, `X-Error: 101,102`.

[Condizioni race ed Errori](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)