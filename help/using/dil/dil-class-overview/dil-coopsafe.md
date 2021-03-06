---
description: Configurazione booleana opzionale che consente di determinare se il servizio DIL invia o meno dati ad Adobe Experience Cloud Device Co-op.
seo-description: Configurazione booleana opzionale che consente di determinare se il servizio DIL invia o meno dati ad Adobe Experience Cloud Device Co-op.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
feature: Implementazione di DIL
exl-id: 33dca495-6923-4966-9ec3-8b0fd2f17649
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 76%

---

# isCoopSafe{#iscoopsafe}

Configurazione booleana opzionale che consente di determinare se il servizio DIL invia o meno dati ad Adobe Experience Cloud Device Co-op.

## Requisiti {#requirements}

Per utilizzare `isCoopSafe` devi:

* Utilizza [!UICONTROL DIL] v6.11 o versione successiva.
* Partecipare a [Experience Cloud Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/home.html). Anche i potenziali membri co-op devono consultare questa documentazione per stabilire se `isCoopSafe` si occupa di possibili problemi relativi al modo in cui i dati vengono utilizzati per creare il grafico del dispositivo.

* Rivolgiti al tuo consulente [!DNL Adobe] per impostare un flag di inserire nell&#39;elenco Consentiti o elenco Bloccati sul tuo account Device Co-op. Nessun percorso self-service per abilitare questi flag.

## Casi d&#39;uso {#use-cases}

`isCoopSafe` aiuta a risolvere 2 casi d&#39;uso relativi alla raccolta di dati da parte di membri attuali o potenziali di Device Co-op. Questi casi d&#39;uso si riferiscono al modo in cui i dati dei visitatori del sito vengono trasmessi al Device Co-op per aiutare a costruire il grafico del dispositivo. La tabella seguente descrive come `isCoopSafe` funziona con questi casi d&#39;uso per bloccare o inviare dati al grafico del dispositivo

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caso d'uso </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Visitatori autenticati</b> </p> </td> 
   <td colname="col2"> <p>Aggiungi <code> isCoopSafe </code> al codice <span class="wintitle"> DIL </span> per controllare il modo in cui vengono usati i dati dal Device Co-op per costruire il grafico del dispositivo per i visitatori autenticati che hanno o meno accettato le Condizioni d'uso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL su siti di terze parti</b> </p> </td> 
   <td colname="col2"> <p>Aggiungi <code> isCoopSafe </code> al codice <span class="wintitle"> DIL </span> da utilizzare su siti di terze parti in cui: </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">Non puoi garantire che i visitatori autenticati abbiano o meno accettato le Condizioni d'uso. </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">Hai bisogno di controllare il modo in cui quei dati vengono usati dal Device Co-op per creare il grafico del dispositivo. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sintassi ed esempio di codice {#syntax-code-sample}

**Sintassi:** `isCoopSafe: true | false`

Le opzioni booleane determinano il modo in cui i dati dei clienti vengono o non vengono usati dal Device Co-op.

* `isCoopSafe: true`: i dati dei visitatori raccolti da un SDK mobile o da un sito Web *possono* essere usati per aiutare a creare il grafico del dispositivo.

* `isCoopSafe: false`: i dati dei visitatori raccolti da un SDK mobile o da un sito Web *non possono* essere usati per aiutare a creare il grafico del dispositivo.

**Esempio di codice**

Imposta questo quando DIL crea un???istanza.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## Parametri POST della chiamata dell&#39;evento {#post-parameters}

A seconda del flag impostato ( `true` o `false`), [!UICONTROL DIL] traduce `isCoopSafe` in questi parametri POST e li invia a [!DNL Adobe] in una chiamata dell&#39;evento:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

I parametri POST dicono all&#39;[!DNL Experience Cloud] Device Co-op se pu?? o meno includere i dati degli utenti nel grafico del dispositivo. La tabella seguente definisce il rapporto tra i flag booleani `isCoopSafe` e i parametri POST trasmessi durante una chiamata dell&#39;evento. Se non usi `isCoopSafe`, nessuno dei due verr?? trasmesso durante una chiamata dell&#39;evento.

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Stato della configurazione </th> 
   <th colname="col2" class="entry"> Parametro POST </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>Il Device Co-op pu?? usare i dati dei visitatori per costruire il grafico del dispositivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>Il Device Co-op non pu?? usare i dati dei visitatori per costruire il grafico del dispositivo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## API di post-istanziazione {#post-instantiation}

Questi API ti consentono di ignorare lo stato `isCoopSafe`. Questi sono necessarie perch?? ti permettono di modificare lo stato di post-istanziazione/post-login di un visitatore su un sito o in un&#39;app a pagina singola in cui la pagina non viene aggiornata. Ad esempio, avrai bisogno di chiamare queste API se un utente si autentica sul tuo sito o sulla tua app e successivamente accetta una policy sulle Condizioni d&#39;uso che consente al Device Co-op di usare i propri dati.

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>Imposta il parametro POST <code> d_coop_safe=1 </code> in tutte le chiamate dell'evento successive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>Imposta il parametro POST <code> d_coop_unsafe=1 </code> in tutte le chiamate dell'evento successive. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->
