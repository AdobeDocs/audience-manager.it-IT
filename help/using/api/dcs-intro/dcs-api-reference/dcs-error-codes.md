---
description: Codici di errore e messaggi generati dai server di raccolta dati (DCS) elencati in ordine numerico in base all’ID del codice.
title: Codici errore DCS, messaggi ed esempi
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 4%

---

# Codici errore DCS, messaggi ed esempi {#dcs-error-codes-messages-and-examples}

Codici di errore e messaggi generati da [!UICONTROL Data Collection Servers] ([!DNL DCS]) elencata in ordine numerico in base all&#39;ID del codice.

Nelle tabelle seguenti: *corsivo* rappresenta un segnaposto variabile.

## Codici di errore del sistema {#system-error-codes}

| Codice di errore | Messaggio di errore | Descrizione |
|---|---|---|
| 0 | Errore non specificato | Si tratta di un errore catch-all che gestisce gli eventi non coperti dagli altri gestori di errori. È difficile risolvere questo errore. Può essere causato da una varietà di azioni o eventi sconosciuti. Se ricevi questo errore, prova il [!DNL DCS] richiedi di nuovo. Contatta il tuo [!DNL Adobe] se il problema persiste. |
| 1 | Impossibile trovare la configurazione per il nome host: `hostname` | Il nome host inviato nella richiesta non è stato configurato dal nostro team di provisioning partner. Contatta il tuo [!DNL Adobe] se viene visualizzato questo messaggio di errore. |
| 2 | Non valido `d_orgid` value (impossibile trovare una configurazione per questo id organizzazione): `ID` | L&#39;ID organizzazione non è corretto. Controlla il tuo ID e riprova la richiesta. Se non conosci o non possiedi l&#39;ID organizzazione, consulta la sezione &quot;Pagina di amministrazione&quot; [Organizzazioni e collegamento di account](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) per informazioni su come trovarlo. |
| 10 | Impossibile valutare le caratteristiche | Le caratteristiche della richiesta sono state valutate parzialmente o non sono state valutate affatto. Contatta il tuo [!DNL Adobe] se il problema persiste. |

## Codici di errore dell’integrazione {#integration-error-codes}

| Codice di errore | Messaggio di errore | Descrizione |
|---|---|---|
| 100 | Impossibile recuperare il nome host per la richiesta | Un [!DNL API] la chiamata non ha inviato l&#39;host [!DNL HTTP] nella richiesta. Aggiungi l&#39;intestazione host alla chiamata e riprova. La maggior parte dei browser e [!DNL API] i client lo fanno automaticamente. |
| 101 | Non valido [!DNL Experience Cloud] id trasmesso `ID` | La [!DNL DCS] la chiamata contiene un [!DNL Experience Cloud] ID. Controlla la `d_mid=` coppia chiave-valore nella stringa di intestazione. Assicurati di trasmettere la risposta corretta [!DNL Experience Cloud] ID e riprova. |
| 102 | Non valido [!DNL AAM ID] richiesta trasmessa `ID` | La [!DNL DCS] la chiamata contiene un [!DNL Audience Manager] ID. Controlla la `d_uuid=` coppia chiave-valore nella stringa di intestazione. Assicurati di trasmettere la risposta corretta [!DNL Audience Manager] ID e riprova. |
| 104 | Tutti gli ID cliente non sono validi | Tutti gli ID cliente nella chiamata non sono validi. Controlla gli ID e riprova. |
| 109 | Referente `HTTP referer` non è consentito per il partner `Partner ID` | La `HTTP referer` l&#39;intestazione nella chiamata non è consentita per l&#39;ID partner nella chiamata . Controlla che la `HTTP referer` intestazione corretta. |
| 111 | Non valido `IMS` token ricevuto | Restituito per [!DNL Audience Manager] - [!DNL Adobe Target] integrazioni. L&#39;errore viene generato quando viene effettuata una chiamata al [!DNL DCS], contenente un [!DNL IMS] token. Il token potrebbe essere non valido, scaduto o l’utente potrebbe non essere autorizzato ad accedere alla risorsa richiesta. |

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
   <td colname="col2"> <p>È stato rilevato un tag di rinuncia per ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un cliente ha rinunciato a ricevere pubblicità basata sugli interessi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookie bloccati </p> </td> 
   <td colname="col3"> <p>Restituito quando il browser dell’utente blocca i cookie di terze parti.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relazione trust incontrata tramite <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>L’utente ha avviato un processo di rinuncia tramite NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Le richieste di questo paese sono bloccate dal partner </p> </td> 
   <td colname="col3"> <p>In base all’indirizzo IP, il <span class="wintitle"> DCS</span> blocca le richieste provenienti da paesi in cui il partner ha deliberatamente limitato il traffico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Le richieste provenienti da questo paese non sono consentite </p> </td> 
   <td colname="col3"> <p>In base all’indirizzo IP, il <span class="wintitle"> DCS</span> blocca le richieste dei seguenti paesi: </p> <p> 
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

## Codici di errore di recupero del profilo {#profile-retrieval-error-codes}

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
   <td colname="col3"> <p>Restituito quando non è possibile leggere un profilo utente dall’archiviazione interna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Impossibile leggere gli ID dispositivo dalla cache del profilo per l'ID cliente: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando <a href="../../../reference/ids-in-aam.md"> ID dispositivo</a> non può essere recuperato per una regola di unione collegamenti profilo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Impossibile leggere il cliente correlato per l'ID dispositivo: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando <a href="../../../reference/ids-in-aam.md"> ID cliente (UID)</a> non è possibile recuperare l'associazione a un ID dispositivo per una regola di unione autenticata dall'archiviazione interna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Impossibile leggere il cluster di dispositivi per l'ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Impossibile restituire gli ID dispositivo collegati dallo stesso cluster di grafici dei dispositivi per questo ID dispositivo. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Impossibile eseguire la migrazione perché la lettura del profilo non è riuscita per il dispositivo primario </p> </td> 
   <td colname="col3"> <p>Se ricevi questo errore, potrebbero verificarsi problemi di scalabilità con il nostro archivio dati (<span class="wintitle"> PCS</span>). Se il problema persiste, contatta il rappresentante di Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Impossibile eseguire la migrazione da <code><i>ID</i></code> a <code><i>ID</i></code>, perché la lettura del profilo non è riuscita per <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Se ricevi questo errore, potrebbero verificarsi problemi di scalabilità con il nostro archivio dati (<span class="wintitle"> PCS</span>). Se il problema persiste, contatta il rappresentante di Adobe. </p> </td> 
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
   <td colname="col2"> <p>Numero massimo di ID cliente superato. Massimo consentito <code><i>maximum allowed</i></code>. Trovato <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>Il numero di ID cliente associati a un’origine dati multi-dispositivo supera il numero consentito di ID multi-dispositivo per richiesta. Questi ID includono ID per dispositivi mobili, o cookie diversi. Il limite è attualmente impostato su 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID cliente non autorizzato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l'origine dati ID cliente non è di proprietà dell'ID organizzazione corrente. Se non conosci o non possiedi l'ID organizzazione, consulta la sezione "Trova il tuo ID organizzazione" in <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organizzazioni e collegamento di account</a> per informazioni su come trovarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID cliente bloccato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l’ID cliente è stato identificato come dannoso ed è stato aggiunto a un elenco Bloccati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID origine dati bloccato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Restituito quando l’ID dell’origine dati è stato identificato come dannoso ed è stato aggiunto a un elenco Bloccati </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID dispositivo dichiarato bloccato <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L'ID dispositivo è stato identificato come dannoso ed è stato aggiunto a un elenco Bloccati Questo può accadere quando riceviamo una quantità estrema di <span class="wintitle"> DCS</span> richieste contenenti questo ID dispositivo in un breve periodo di tempo. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Operazione di profilo bloccata per <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un'azione di lettura/scrittura è stata bloccata perché un ID è stato identificato come dannoso ed è stato aggiunto a un  elenco Bloccati Vedi il codice di errore 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>ID cliente <code><i>ID</i></code> è stato scartato perché superava il limite di ID cliente dichiarati per richiesta </p> </td> 
   <td colname="col3"> <p>Correlato all'errore 301. Questo errore specifica quale ID cliente è stato scartato perché il limite è stato superato. </p> <p>Ad esempio, se ci sono 12 ID cliente dichiarati nel <span class="wintitle"> DCS</span> Chiamate, due di esse verranno scartate. Per inoltrare quelli scartati, questo errore verrà visualizzato due volte nella risposta (una volta per ciascuno degli ID cliente scartati ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>L'ID cliente è stato scartato perché superava il limite di uno spazio dei nomi specificato. ID dello spazio dei nomi: <code><i>ID</i></code>, l'ID cliente è <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Questo codice di errore viene restituito se per lo stesso namespace sono dichiarati più di 3 ID cliente (<code> DPID</code>) su <span class="wintitle"> DCS</span> chiama. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In questo esempio <span class="wintitle"> DCS</span> sono presenti 4 ID dichiarati per lo stesso namespace (con il codice di integrazione uno). Uno degli ID viene scartato e viene restituito l'errore 310. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La richiesta contiene parametri non validi </p> </td> 
   <td colname="col3"> <p>La <span class="wintitle"> DCS</span> restituisce questo codice di errore quando almeno un parametro URL non è codificato correttamente. In questo caso, il <span class="wintitle"> DCS</span> trascura l'intera richiesta. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>Nella richiesta di esempio precedente, la <code> %</code> la sequenza non è codificata correttamente. Di conseguenza, <span class="wintitle"> DCS</span> lo ignorerò. </p> <p>L’esempio codificato correttamente deve essere simile al seguente: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La richiesta contiene un ID dispositivo globale non valido </p> </td> 
   <td colname="col3"> <p>La <span class="wintitle">DCS</span> restituisce questo codice di errore quando la richiesta contiene un ID dispositivo globale non valido. Il DCS ignora l'ID non valido e genera un errore 312 insieme agli errori specifici dell'ID non valido. Fai riferimento a <a href="../../../features/global-data-sources.md" format="dita" scope="local">Sorgenti di dati globali</a> e <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Indice degli ID nell’Audience Manager</a> per informazioni dettagliate sui formati ID pubblicità dispositivo corretti e sulle origini dati globali corrispondenti.</p>
   <p>Esempio di chiamata errata: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Spiegazione: Un <span class="keyword">IDFA (DPID 20915)</span> deve essere un ID maiuscolo. L’ID fornito nella richiesta è minuscolo.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>L'ID CMP non è presente in GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e la stringa IAB TC è generata da un ID CMP non presente nella versione cache di Audience Manager dell’elenco CMP globale al momento della valutazione, il plug-in Audience Manager per IAB TCF elimina la stringa IAB TC ed elabora la richiesta come di consueto. La macro IAB TCF v2.0 ${GDPR} è impostata su 0 e la macro ${GDPR_CONSENT_XXX} è vuota.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>L’ID CMP è contrassegnato come eliminato in GCL</p> </td> 
   <td colname="col3"> <p>Quando <code>gdpr=1</code> e la stringa IAB TC viene generata da una CMP contrassegnata come eliminata nella nostra versione cache dell’elenco CMP globale, il plug-in di Audience Manager per IAB TCF elimina la stringa TC ed elabora la richiesta come di consueto, se il tempo di valutazione supera il tempo di eliminazione dall’elenco CMP globale. La macro IAB TCF v2.0 ${GDPR} è impostata su 0 e la macro ${GDPR_CONSENT_XXX} è vuota.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>La stringa di consenso non indica il consenso</p> </td> 
   <td colname="col3"> <p>Se non viene fornito alcun consenso, il plug-in di Audience Manager per IAB TCF rifiuta l’ulteriore raccolta di dati o rilascia completamente la chiamata se non viene rilevato alcun contesto partner.</p>
   </td>
  </tr>

</tbody>
</table>

## Messaggi di codice di errore di esempio {#sample-error-codes}

La [!DNL DCS] restituisce codici di errore e messaggi in un [!DNL JSON] oggetto o in un&#39;intestazione X nella stringa di risposta HTTP.

### Messaggio e codice di errore DCS di esempio

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

I codici di errore acquisiti dall&#39;intestazione X appaiono nella stringa URL come questa, `X-Error: 101,102`.

[Race condition e gestione degli errori](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
