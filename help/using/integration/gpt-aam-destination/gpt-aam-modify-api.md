---
description: Aggiungete un'istruzione if per controllare i cookie di Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.
seo-description: Aggiungete un'istruzione if per controllare i cookie di Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.
seo-title: Modificare la chiamata API GPT setTargeting
solution: Audience Manager
title: Modificare la chiamata API GPT setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Modifica della chiamata `setTargeting` API GPT {#modify-the-gpt-settargeting-api-call}

Aggiungete un'istruzione if per controllare i cookie di Audience Manager prima di chiamare il [!DNL Google Publisher Tag] metodo `.setTargeting` .

## Verifica dei cookie di Audience Manager con un' `IF` istruzione

Il `.setTargeting` metodo ottiene i dati dal cookie di destinazione di Audience Manager e dal cookie ID utente univoco ( `aam_uuid`). Tuttavia, se `.setTargeting` viene richiamato prima di [!UICONTROL DIL] scrivere questi cookie, o se i cookie sono vuoti, potrebbero verificarsi degli errori durante il caricamento della pagina. Per evitare questo problema, racchiudere il `.setTargeting` metodo in un' `if` istruzione che controlla questi cookie. Se non sono impostati, questa istruzione impedisce `.setTargeting` di chiamare la `AamGpt` funzione.

### `IF` Esempio di codice istruzioni

In questo esempio, il nome del cookie di destinazione di Audience Manager è `Sample`. Questo nome viene impostato quando create il cookie di destinazione nell’interfaccia utente di Audience Manager. [!UICONTROL DIL] imposta il `aam_uuid` cookie e il nome non può essere modificato.

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
>A seconda di come si desidera integrare con [!DNL DFP], è necessario solo alcune delle righe nell’esempio di codice riportato sopra:
>
>* Integrazione lato client: utilizzare solo le righe 1-3.
>* Integrazione lato server: nessuna delle righe è necessaria.
>* Inserite i file di [!DNL DFP] registro per il reporting in [!DNL Audience Manager]: utilizzare solo le linee 4-6. Questo codice inserisce il valore del `aam_uuid` cookie nei file di registro in modo che possano essere inseriti per il reporting.


### `AamGpt` Funzioni e tipi di dati

Definisce le variabili chiave utilizzate nell' `if` istruzione.

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
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Restituisce la chiave nella coppia di segmenti chiave-valore. Ad esempio, se la coppia chiave-valore è costituita da <code> color=blue </code>, restituisce <code> colore </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Matrice di stringhe </p> </td> 
   <td colname="col3"> <p>Restituisce valori in un array, ad esempio <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Restituisce l’ID utente di Audience Manager, ad esempio <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORE_LIKE_this]
>
>* [Creare una destinazione GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Codice Audience Manager per i tag di Google Publisher](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

