---
description: Aggiungete un'istruzione if per verificare  cookie Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.
seo-description: Aggiungete un'istruzione if per verificare  cookie Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.
seo-title: Modificare la chiamata API GPT setTargeting
solution: Audience Manager
title: Modificare la chiamata API GPT setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 9%

---


# Modify the GPT `setTargeting` API Call {#modify-the-gpt-settargeting-api-call}

Aggiungete un&#39;istruzione if per verificare  cookie Audience Manager prima di chiamare il [!DNL Google Publisher Tag] metodo `.setTargeting` .

## Verifica  cookie Audience Manager con un&#39; `IF` istruzione

Il `.setTargeting` metodo ottiene i dati dal cookie di destinazione Audience Manager  e dal cookie ID utente univoco ( `aam_uuid`). Tuttavia, se `.setTargeting` viene richiamato prima di [!UICONTROL DIL] scrivere questi cookie, o se i cookie sono vuoti, potrebbero verificarsi degli errori durante il caricamento della pagina. Per evitare questo problema, racchiudere il `.setTargeting` metodo in un&#39; `if` istruzione che controlla questi cookie. Se non sono impostati, questa istruzione impedisce `.setTargeting` di chiamare la `AamGpt` funzione.

### `IF` Esempio di codice istruzioni

In questo esempio, il nome del cookie di destinazione  Audience Manager è `Sample`. Questo nome viene impostato al momento della creazione del cookie di destinazione nell&#39;interfaccia utente  Audience Manager. [!UICONTROL DIL] imposta il `aam_uuid` cookie e il nome non può essere modificato.

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
>A seconda di come si desidera integrare con [!DNL Google Ad Manager], è necessario solo alcune delle righe nell’esempio di codice riportato sopra:
>
>* Integrazione lato client: utilizzare solo le righe 1-3.
>* Integrazione lato server: nessuna delle righe è necessaria.
>* Inserite i file di [!DNL Google Ad Manager] registro per il reporting in [!DNL Audience Manager]: utilizzare solo le linee 4-6. Questo codice inserisce il valore del `aam_uuid` cookie nei file di registro in modo che possano essere inseriti per il reporting.


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
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>Stringa </p> </td> 
   <td colname="col3"> <p>Restituisce la chiave nella coppia di segmenti chiave-valore. Ad esempio, se la coppia chiave-valore è costituita da <code> color=blue </code>, restituisce <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Matrice di stringhe </p> </td> 
   <td colname="col3"> <p>Restituisce valori in un array, ad esempio <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Restituisce l’ID utente Audience Manager , ad esempio <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Creare una destinazione GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Codice di Audience Manager per i tag publisher di Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

