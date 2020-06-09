---
description: Codici di errore e messaggi generati dai Data Collection Servers (DCS) elencati in ordine numerico in base all'ID del codice.
seo-description: Codici di errore e messaggi generati dai Data Collection Servers (DCS) elencati in ordine numerico in base all'ID del codice.
seo-title: Codici errore DCS, messaggi ed esempi
solution: Audience Manager
title: Codici errore DCS, messaggi ed esempi
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
translation-type: tm+mt
source-git-commit: 07fb9269f285a8662a9ce5e03d8be8b8d51df553
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 4%

---


# Codici errore DCS, messaggi ed esempi {#dcs-error-codes-messages-and-examples}

Codici di errore e messaggi generati dal [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]) elenco in ordine numerico per ID codice.

Nelle tabelle seguenti, il *corsivo* rappresenta un segnaposto variabile.

## Codici di errore del sistema {#system-error-codes}

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
   <td colname="col3"> <p>Si tratta di un errore catch-all che gestisce gli eventi non coperti dagli altri gestori di errori. È difficile risolvere questo errore. Può essere causato da una serie di azioni o eventi sconosciuti. </p> <p>Se ricevete questo errore, riprovate la richiesta <span class="wintitle"> DCS</span> . Se il problema persiste, contattate il rappresentante Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Impossibile trovare la configurazione per il nome host: <code><i>hostname</i></code> </p> </td> 
   <td colname="col3"> <p>Il nome host inviato nella richiesta non è stato configurato dal nostro team di provisioning partner. Se ricevete questo messaggio di errore, contattate il vostro rappresentante Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Valore non valido <code> d_orgid</code> (impossibile trovare una configurazione per questo ID organizzazione): <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L'ID organizzazione non è corretto. </p> <p>Controlla l’ID e riprova la richiesta. Se non conosci o non disponi del tuo ID organizzazione, consulta la sezione "Pagina di amministrazione" in <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html" format="https" scope="external"> Organizzazioni e collegamento</a> dell’account per informazioni su come trovarlo. </p> </td> 
  </tr>
 </tbody>
</table>

## Codici errore di integrazione {#integration-error-codes}

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
   <td colname="col3"> <p>Una chiamata API non ha inviato l'intestazione HTTP dell'host nella richiesta. </p> <p>Aggiungete l’intestazione host alla chiamata e riprovate. Nota: la maggior parte dei browser e dei client API lo fanno automaticamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>ID Experience Cloud non valido passato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>La chiamata <span class="wintitle"> DCS</span> contiene un ID <span class="keyword"> Experience Cloud</span> non valido. </p> <p>Controllare la coppia chiave-valore nella stringa di intestazione. <code> d_mid=</code> Assicurati di trasmettere l’ID <span class="keyword"> Experience Cloud</span> corretto e riprova. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>ID aam non valido passato nella richiesta <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>La chiamata <span class="wintitle"> DCS</span> contiene un ID <span class="keyword"> Audience Manager</span> non valido. </p> <p>Controllare la coppia chiave-valore nella stringa di intestazione. <code> d_uuid=</code> Assicurati di trasmettere l’ID <span class="keyword"> Audience Manager</span> corretto e riprova. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>Tutti gli ID cliente non sono validi </p> </td> 
   <td colname="col3"> <p>Tutti gli ID cliente nella chiamata non sono validi. Controlla gli ID e riprova. </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p>109</p> </td> 
   <td colname="col2"> <p>Referente non <code>HTTP referer</code> consentito per il partner <code>Partner ID</code> </p> </td> 
   <td colname="col3"> <p>L’ <code>HTTP referer</code> intestazione della chiamata non è consentita per l’ID partner nella chiamata. Verificate che l’ <code>HTTP referer</code> intestazione sia corretta.</p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>Token <span class="wintitle"> IMS</span> non valido ricevuto </p> </td> 
   <td colname="col3"> <p>Restituito per le integrazioni Audience Manager - Adobe Target. L'errore viene generato quando viene effettuata una chiamata al DCS contenente un token IMS non valido. Il token potrebbe essere danneggiato, scaduto o l'utente potrebbe non essere autorizzato ad accedere alla risorsa richiesta. </p> </td>
  </tr>
 </tbody>
</table>

## Codici di errore di rifiuto {#opt-out-error-codes}

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
   <td colname="col2"> <p>È stato rilevato il tag di rifiuto per l’ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un cliente ha rinunciato a ricevere pubblicità basata sugli interessi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookie bloccati </p> </td> 
   <td colname="col3"> <p>Restituito quando il browser dell'utente blocca i cookie di terze parti.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relazione di trust rilevata tramite <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>L'utente ha avviato un processo di rifiuto tramite NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Le richieste di questo paese sono bloccate dal partner </p> </td> 
   <td colname="col3"> <p>In base all'indirizzo IP, il <span class="wintitle"> DCS</span> blocca le richieste provenienti dai paesi in cui il partner ha deliberatamente limitato il traffico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Richieste da questo paese non sono consentite </p> </td> 
   <td colname="col3"> <p>In base all’indirizzo IP, il <span class="wintitle"> DCS</span> blocca le richieste provenienti dai seguenti paesi: </p> <p> 
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
   <td colname="col3"> <p>Restituito quando un profilo utente non può essere letto dallo storage interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Impossibile leggere gli ID dispositivo dalla cache del profilo per l'ID cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l’ID <a href="../../../reference/ids-in-aam.md"></a> dispositivo non può essere recuperato per una regola di unione Collegamento profilo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Impossibile leggere il cliente correlato all'ID dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'ID cliente (UUID) <a href="../../../reference/ids-in-aam.md"></a> associato a un ID dispositivo non può essere recuperato per una regola di unione Autenticata ultima dal nostro archivio interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Impossibile leggere il cluster di dispositivi per l'ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Impossibile restituire gli ID dispositivo collegati dallo stesso cluster grafico dispositivi per questo ID dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Impossibile eseguire la migrazione perché la lettura del profilo non è riuscita per il dispositivo principale </p> </td> 
   <td colname="col3"> <p>Se ricevi questo errore, potrebbero verificarsi problemi di scalabilità con il nostro archivio dati (<span class="wintitle"> PCS</span>). Se il problema persiste, contattate il rappresentante Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Impossibile eseguire la migrazione da <code><i>ID</i></code> a <code><i>ID</i></code>. Impossibile leggere il profilo per <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Se ricevi questo errore, potrebbero verificarsi problemi di scalabilità con il nostro archivio dati (<span class="wintitle"> PCS</span>). Se il problema persiste, contattate il rappresentante Adobe. </p> </td> 
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
   <td colname="col3"> <p>L'ID cliente non è valido (valori mancanti per l'origine dati, codici di integrazione mancanti, formato non valido per le origini dati, ID cliente bloccato, ID cliente vuoto, tentativo di accesso non autorizzato a un'origine dati che non appartiene al partner). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Numero massimo di ID cliente superato. Il valore massimo consentito è <code><i>maximum allowed</i></code>. Trovato è <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>Il numero di ID cliente associati a un'origine dati multi-dispositivo supera il numero consentito di ID cross-device per richiesta. Questi ID includono ID per dispositivi diversi, dispositivi mobili o cookie. Il limite è attualmente impostato su 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID cliente non autorizzato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'origine dati ID cliente non è di proprietà dell'ID organizzazione corrente. Se non conosci o non disponi del tuo ID organizzazione, consulta la sezione "Trova il tuo ID organizzazione" in <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizations and Account Linking (Organizzazione e collegamento</a> account) per informazioni su come trovarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID cliente bloccato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l’ID cliente è stato identificato come dannoso ed è stato inserito in blacklist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID origine dati bloccata <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l’ID origine dati è stato identificato come dannoso ed è stato inserito in blacklist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID dispositivo dichiarato bloccato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L'ID dispositivo è stato identificato come dannoso ed è stato inserito in blacklist. Questo può accadere quando riceviamo una quantità estrema di richieste <span class="wintitle"> DCS</span> contenenti questo ID dispositivo in poco tempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operazione profilo bloccato per <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un'azione di lettura/scrittura è stata bloccata perché un ID è stato identificato come dannoso ed è stato inserito in blacklist. Vedere codice di errore 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>ID cliente <code><i>ID</i></code> scartato perché superava il limite di ID cliente dichiarati per richiesta </p> </td> 
   <td colname="col3"> <p>Relativo all'errore 301. Questo errore specifica quale ID cliente è stato scartato perché il limite è stato superato. </p> <p>Ad esempio, se 12 ID cliente sono dichiarati nella chiamata <span class="wintitle"> DCS</span> , due di essi verranno scartati. Per comunicare quali sono stati scartati, l'errore verrà visualizzato due volte nella risposta (una volta per ciascun ID cliente scartato). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>ID cliente scartato perché superava il limite per uno spazio nomi specificato. ID spazio nomi è <code><i>ID</i></code>, ID cliente è <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Questo codice di errore viene restituito se ci sono più di 3 ID cliente dichiarati per lo stesso namespace (<code> DPID</code>) in una chiamata <span class="wintitle"> DCS</span> . </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In questa richiesta <span class="wintitle"> DCS</span> di esempio, sono stati dichiarati 4 ID per lo stesso namespace (con il codice di integrazione uno). Uno degli ID viene eliminato e viene restituito l’errore 310. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La richiesta contiene parametri non validi </p> </td> 
   <td colname="col3"> <p>Il <span class="wintitle"> DCS</span> restituisce questo codice di errore quando almeno un parametro URL non è codificato correttamente. In questo caso, il <span class="wintitle"> DCS</span> ignora l’intera richiesta. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>Nella richiesta di esempio precedente, la <code> %</code> sequenza non è codificata correttamente. Di conseguenza, il <span class="wintitle"> DCS</span> non lo terrà in considerazione. </p> <p>L’esempio codificato correttamente deve essere simile al seguente: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La richiesta contiene un ID dispositivo globale non valido </p> </td> 
   <td colname="col3"> <p>Il <span class="wintitle">DCS</span> restituisce questo codice di errore quando la richiesta contiene un ID dispositivo globale non valido. Il DCS ignora l’ID non valido e genera un errore 312 con gli errori specifici dell’ID non valido. Per informazioni dettagliate sui formati ID pubblicitari dei dispositivi corretti e sulle origini dati globali corrispondenti, consulta Origini <a href="../../../features/global-data-sources.md" format="dita" scope="local">dati</a> globali e <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Indice di ID in Audience Manager</a> .</p>
   <p>Esempio di chiamata non corretta: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Spiegazione: Un <span class="keyword">IDFA (DPID 2015)</span> deve essere un ID maiuscolo. L’ID fornito nella richiesta è minuscolo.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>L’ID CMP non è presente in GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e la stringa IAB TC viene generata da un ID CMP che non è presente nella versione cache di Audience Manager dell’elenco CMP globale al momento della valutazione, il plug-in Audience Manager per IAB TCF elimina la stringa IAB TC ed elabora la richiesta come di consueto. La macro IAB TCF v2.0 ${GDPR} è impostata su 0 e la macro ${GDPR_CONSENT_XXX} è vuota.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>L’ID CMP è contrassegnato come eliminato in GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e la stringa IAB TC viene generata da un CMP contrassegnato come eliminato nella nostra versione memorizzata nella cache dell’Elenco CMP globale, il plug-in Audience Manager per IAB TCF elimina la stringa TC ed elabora la richiesta come di consueto, se il tempo di valutazione supera il tempo di eliminazione dall’elenco CMP globale. La macro IAB TCF v2.0 ${GDPR} è impostata su 0 e la macro ${GDPR_CONSENT_XXX} è vuota.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>La stringa di consenso indica che non è stato raggiunto alcun consenso</p> </td> 
   <td colname="col3"> <p>Se non viene fornito alcun consenso, il plug-in Audience Manager per IAB TCF esclude l’utente da un’ulteriore raccolta di dati, oppure interrompe completamente la chiamata se non viene rilevato alcun contesto partner.</p>
   </td>
  </tr>

</tbody>
</table>

## Messaggi di codice di errore di esempio {#sample-error-codes}

Il metodo [!UICONTROL DCS] restituisce i codici di errore e i messaggi in un [!DNL JSON] oggetto o in un&#39;intestazione X nella stringa di risposta HTTP.

### Codice di errore e messaggio DCS di esempio

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

I codici di errore acquisiti dall&#39;intestazione X vengono visualizzati nella stringa URL come questa, `X-Error: 101,102`.

[Condizioni di gara e gestione errori](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)