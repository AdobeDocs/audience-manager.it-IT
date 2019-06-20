---
description: Aggiungete un'istruzione if per controllare i cookie di Audience Manager prima di richiamare il metodo Google Publisher Tag. settargeting.
seo-description: Aggiungete un'istruzione if per controllare i cookie di Audience Manager prima di richiamare il metodo Google Publisher Tag. settargeting.
seo-title: Modificare la chiamata GPT settargeting API
solution: Audience Manager
title: Modificare la chiamata GPT settargeting API
uuid: 0 cd 38 f 30-5 d 29-4511-a 779-d 32587 f 1 dafb
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Modifica della chiamata `setTargeting` API GPT {#modify-the-gpt-settargeting-api-call}

Aggiungi un&#39;istruzione if per controllare i cookie di Audience Manager prima di richiamare il [!DNL Google Publisher Tag]`.setTargeting` metodo.

## Verifica i cookie di Audience Manager con `IF` un&#39;istruzione

Il `.setTargeting` metodo riceve i dati dal cookie di destinazione Audience Manager e dal cookie ID utente univoco ( `aam_uuid`). Tuttavia, se `.setTargeting` viene richiamato prima [!UICONTROL DIL] di scrivere questi cookie, o i cookie sono vuoti, potrebbero verificarsi errori durante il caricamento della pagina. Per evitare questa situazione, racchiudere il `.setTargeting` metodo in `if` un&#39;istruzione che verifichi questi cookie. Se non sono impostate, questa istruzione impedisce `.setTargeting` la chiamata alla `AamGpt` funzione.

### `IF` Esempio di codice di istruzioni

In questo esempio, il nome del cookie di destinazione Audience Manager `Sample`è. Puoi impostare questo nome quando crei il cookie di destinazione nell&#39;interfaccia utente di Audience Manager. [!UICONTROL DIL] imposta `aam_uuid` il cookie e il nome non può essere modificato.

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>A seconda della modalità di integrazione, [!DNL DFP]sono necessarie solo alcune delle righe nell&#39;esempio di codice precedente:
>
>* Integrazione lato client: utilizzare solo le righe 1-3.
>* Integrazione lato server: nessuna delle righe è necessaria.
>* Assimilazione dei file [!DNL DFP] di registro per i rapporti in [!DNL Audience Manager]: utilizzare solo le righe 4-6. Questo codice inserisce il valore del `aam_uuid` cookie nei registri in modo che possano essere assimilati per il reporting.


### `AamGpt` Funzioni e tipi di dati

Definisce le variabili chiave utilizzate nell&#39; `if` istruzione.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzione </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getkey </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Restituisce la chiave nella coppia di segmenti chiave-valore. Ad esempio, se la coppia chiave-valore è rappresentata <code> da color = blue </code>, restituisce <code> il colore </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getvalues </code> </p> </td> 
   <td colname="col2"> <p>Array di stringhe </p> </td> 
   <td colname="col3"> <p>Restituisce valori in un array, ad esempio <code> ["valore 1", "valore 2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getcookie </code> </p> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Restituisce l'ID utente di Audience Manager, ad esempio <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Creare una destinazione GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Codice Audience Manager per tag Editore Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

