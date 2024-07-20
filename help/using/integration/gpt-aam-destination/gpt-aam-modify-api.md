---
description: Aggiungere un'istruzione if per verificare la presenza di cookie di Audience Manager prima di chiamare il metodo Google Publisher Tag .setTargeting.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Modificare la chiamata API GPT setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Modifica la chiamata API GPT `setTargeting` {#modify-the-gpt-settargeting-api-call}

Aggiungere un&#39;istruzione if per verificare la presenza di cookie Audience Manager prima di chiamare il metodo [!DNL Google Publisher Tag] `.setTargeting`.

## Cerca cookie di Audience Manager con un&#39;istruzione `IF`

Il metodo `.setTargeting` ottiene i dati dal cookie di destinazione Audience Manager e dal cookie dell&#39;ID utente univoco ( `aam_uuid`). Tuttavia, se `.setTargeting` viene richiamato prima che [!UICONTROL DIL] scriva questi cookie o se i cookie sono vuoti, è possibile che si verifichino errori al caricamento della pagina. Per evitare questo problema, racchiudere il metodo `.setTargeting` in un&#39;istruzione `if` che controlla la presenza di questi cookie. Se non sono impostati, questa istruzione impedisce a `.setTargeting` di chiamare la funzione `AamGpt`.

### Esempio di codice istruzione `IF`

In questo Audience Manager, il nome del cookie di destinazione è `Sample`. Puoi impostare questo nome quando crei il cookie di destinazione nell’interfaccia utente di Audience Manager. [!UICONTROL DIL] imposta il cookie `aam_uuid` e il nome non può essere modificato.

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
>A seconda della modalità di integrazione con [!DNL Google Ad Manager], sono necessarie solo alcune righe nell&#39;esempio di codice precedente:
>
>* Integrazione lato client: utilizzare solo le righe 1-3.
>* Integrazione lato server: nessuna delle righe è necessaria.
>* Acquisire i file di registro [!DNL Google Ad Manager] per il reporting in [!DNL Audience Manager]: utilizzare solo le righe 4-6. Questo codice inserisce il valore del cookie `aam_uuid` nei registri, in modo che possano essere acquisiti per il reporting.

### `AamGpt` funzioni e tipi di dati

Definisce le variabili chiave utilizzate nell&#39;istruzione `if`.

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
   <td colname="col3"> <p>Restituisce la chiave nella coppia chiave-valore del segmento. Ad esempio, se la coppia chiave-valore è costituita da <code> color=blue </code>, restituisce <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Array di stringhe </p> </td> 
   <td colname="col3"> <p>Restituisce i valori in una matrice, ad esempio <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Intero </p> </td> 
   <td colname="col3"> <p>Restituisce l'ID utente Audience Manager, ad esempio <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Creare una destinazione GPT](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Codice di Audience Manager per i tag publisher di Google](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
