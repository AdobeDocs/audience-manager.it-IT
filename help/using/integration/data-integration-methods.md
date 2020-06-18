---
description: Panoramica di alto livello sulle modalità di scambio  Audience Manager delle informazioni con altri fornitori e sistemi di dati.
seo-description: Panoramica di alto livello sulle modalità di scambio  Audience Manager delle informazioni con altri fornitori e sistemi di dati.
seo-title: Metodi di integrazione dei dati
solution: Audience Manager
title: Metodi di integrazione dei dati
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 1%

---


# Metodi di integrazione dei dati {#data-integration-methods}

Panoramica di alto livello sulle modalità di scambio  Audience Manager delle informazioni con altri fornitori e sistemi di dati.

## Metodi di integrazione dei dati supportati: Real-Time e da server a server {#supported-methods}

La scelta del metodo di integrazione corretto dipende dalla combinazione di requisiti aziendali e capacità tecniche del partner dati.  Audience Manager scambia informazioni sui visitatori con altri provider di dati tramite uno dei seguenti metodi:

* **In Tempo Reale:** Trasferisce i dati immediatamente quando un utente visita il sito. Questo metodo è noto anche come *`synchronous`* integrazione.
* **Batch (da server a server):** Trasferisce i dati tra i server in una pianificazione impostata dopo che un visitatore ha lasciato la pagina. Questo metodo è noto anche come integrazione *`out-of-band`* o *`asynchronous`* .

## Prerequisiti: Creare una tassonomia delle caratteristiche {#prereqs}

Prima dell’inizio del processo di integrazione, ricordate di [creare caratteristiche](../features/traits/create-onboarded-rule-based-traits.md) e una struttura [di](../features/traits/trait-storage.md#create-trait-storage-folder) cartelle nell’ [!DNL Audience Manager] interfaccia utente. La tassonomia conterrà tutte le caratteristiche organizzate in una gerarchia logica.

## Casi di utilizzo dell&#39;integrazione {#integration-use-cases}

Un riepilogo caso d&#39;uso  metodi di integrazione dei dati Audience Manager con i vantaggi e gli svantaggi di ciascuno.

### Integrazioni server-to-server in tempo reale

<!-- c_int_types_use_cases.xml -->

Un&#39;integrazione di dati server-to-server in tempo reale sincronizza rapidamente i dati utente tra  server Audience Manager e un altro sistema di targeting. Nella maggior parte dei casi, lo scambio di dati avviene entro pochi secondi o minuti, a seconda della frequenza di aggiornamento del sistema di targeting. Tuttavia, il sistema di destinazione determina questo intervallo di aggiornamento, non  Audience Manager. Inoltre, la frequenza di aggiornamento può variare da un sistema all&#39;altro. L&#39;integrazione server-to-server in tempo reale è il tipo di integrazione preferito per gli scambi di dati.  Audience Manager utilizza questo metodo ogni volta che i partner di targeting possono supportarlo.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Vantaggi: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Consente di qualificare gli utenti per i segmenti senza visualizzarli nuovamente sulla pagina, in un lettore video e così via. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Riduce il numero di chiamate HTTP dalla pagina. Un numero minore di chiamate consente di preservare l'esperienza dell'utente. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Consente di eseguire il targeting in base al tempo per intervenire rapidamente su un utente qualificato. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Utile quando si passa a un DSP per il targeting offsite. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Svantaggi:</td>
  <td class="stentry"> Meno utile per il targeting on-site quando è necessario eseguire il targeting per l'utente sulla stessa pagina, o sulla pagina successiva, in base alle qualifiche di un utente per quel segmento.</td>
 </tr>
</table>

### Integrazioni batch server-to-server

L&#39;integrazione batch server-to-server raccoglie i dati e li invia ad altri sistemi a intervalli prestabiliti anziché in tempo quasi reale. Gli intervalli di trasferimento dei dati iniziano da 24 ore. Alcuni provider di dati supportano solo questo tipo di integrazione. Tuttavia, abbiamo assistito a una tendenza generale che va dalle integrazioni batch alle metodologie di integrazione in tempo reale.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Vantaggi: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Consente di qualificare gli utenti per i segmenti senza visualizzarli nuovamente sulla pagina, in un lettore video e così via. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Utile per il targeting che non è sensibile al tempo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Svantaggi:</td>
  <td class="stentry"> L'intervallo di sincronizzazione può ritardare il targeting rispetto ai dati più recenti.</td>
 </tr>
</table>

### Chiamate in tempo reale

Le chiamate in tempo reale scambiano immediatamente dati con  Audience Manager, quando un utente visita il sito o agisce sulla pagina. Con questo metodo, i sistemi di targeting ottengono i dati di qualificazione del segmento più aggiornati e possono tenere conto di tali informazioni durante una decisione di distribuzione di contenuti o annunci. Inoltre, questo processo funziona con server di pubblicazione e server in cui i segmenti qualificati vengono aggiornati a un cookie di prime parti che viene letto in una chiamata ad annunci come coppie chiave-valore. Attualmente,  Audience Manager utilizza chiamate in tempo reale per l&#39;integrazione con [!DNL Target] e altri sistemi di gestione dei contenuti.

<table> 
 <tr>
  <td> <p>Vantaggi: </p></td>
  <td> <p> Consente di eseguire il targeting della pagina successiva, dell'area di contenuto o dell'impression annuncio in base alla qualifica del segmento più recente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Svantaggi: </p></td>
  <td> <p>Aggiunge una chiamata a  Audience Manager dalla pagina.</p></td>
 </tr> 
</table>


### Pixel Syncs to Targeting Systems

La sincronizzazione dei pixel mappa i segmenti in pixel sulla pagina. Il pixel attiva e trasmette i dati quando un utente si qualifica per un particolare segmento. La sincronizzazione dei pixel è un meccanismo di trasferimento dati rudimentale e inaffidabile. I provider e i sistemi di dati di primo livello lo utilizzano raramente.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Vantaggi: </p></td>
  <td class="stentry"> <p> Trasferimenti di dati in tempo reale. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Svantaggi: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Può aggiungere molte chiamate lato client dalla pagina. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Inaffidabile per la trasmissione dei dati. Da 5% a 20% di perdita è normale. </li>
   </ul></td>
 </tr> 
</table>

## Come scegliere un metodo di consegna dei dati {#data-delivery-choices}

Descrive i motivi tecnici e aziendali per l&#39;invio di dati tramite metodologie sincrone (in tempo reale) o asincrone (da server a server).

<!-- c_int_delivery_choices.xml -->

### Selezione di un tipo di consegna dei dati

* **Considerazioni Tecniche:** La distribuzione dei dati dipende dalle capacità tecniche del partner dati.  Audience Manager può inviare/ricevere dati in tempo reale dal browser o mediante aggiornamenti batch attraverso processi di comunicazione da server a server offline.
* **Considerazioni aziendali:** I motivi aziendali per la scelta di un metodo di consegna o di un altro dipendono dalle capacità tecniche del partner di destinazione e dalla modalità di utilizzo di tali dati. In genere, i trasferimenti di dati sincroni sono utili quando è necessario intervenire immediatamente sui dati utente. I trasferimenti di dati asincroni possono essere utili quando non è richiesta un&#39;azione immediata e quando si ha il tempo di creare profili utente più profondi per un utilizzo successivo.

## Processo di trasferimento dati in tempo reale {#real-time-data-transfer-process}

Panoramica generale delle modalità in cui  Audience Manager esegue uno scambio di dati sincrono con un fornitore di terze parti.

### Trasferimento dati in tempo reale

<!-- c_int_overview_sync.xml -->

Trasferimenti di dati in tempo reale inviano e ricevono gli ID del segmento come visita dell’utente o azione sul sito. In genere, i trasferimenti di dati sincroni sono utili quando è necessario qualificare o segmentare immediatamente gli utenti, mentre navigano all&#39;interno del proprio inventario.

### Passaggi di integrazione dei dati in tempo reale

Il processo di integrazione dei dati in tempo reale funziona come segue:

1. Un utente visita il sito del cliente che contiene  codice Audience Manager.
1.  Audience Manager carica un Iframe ed effettua una chiamata al [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. Il sistema [!DNL DCS] chiama il server di terze parti (in tempo reale) per verificare se il fornitore dispone di informazioni di segmento sull&#39;utente.
1. La terza parte restituisce ad Audience Manager le informazioni sul segmento relative a tale utente.
1.  Audience Manager acquisisce le informazioni sui segmenti e le rende disponibili per il targeting.

![](assets/rt_reduce70.png)

## Processo di trasferimento dati batch {#batch-data-transfer-process}

Panoramica generale del modo in cui  Audience Manager scambia i dati in modo sincrono (in tempo reale) con un fornitore di terze parti.

### Integrazione dei dati batch

<!-- c_int_overview_async.xml -->

Il processo di integrazione dei dati batch (server-to-server) segue la maggior parte dei passaggi descritti nel processo di trasferimento dei dati in tempo reale. Tuttavia, invece di restituire immediatamente gli ID del segmento, le informazioni utente vengono salvate nei nostri server e sincronizzate con un fornitore di dati di terze parti a intervalli regolari. Il processo di trasferimento dati asincrono è utile quando:

* Non sono necessari trasferimenti di dati immediati.
* Raccolta di dati per creare un ampio pool di utenti segmentati.
* Si desidera ridurre le discrepanze di dati e `HTTP` le chiamate dal browser.

### Passaggi di integrazione dei dati batch

1. Un utente visita un sito cliente.
1.  Audience Manager e il provider di dati di terze parti assegnano al visitatore un ID univoco (in genere con un cookie).
1.  Audience Manager chiama il provider di dati di terze parti per far corrispondere gli ID visitatore.
1. Una richiesta pianificata, in genere a intervalli giornalieri, scambia i dati del segmento dei visitatori tra  Audience Manager e il provider di dati di terze parti.

![](assets/s2s_70.png)

Per informazioni che descrivono i tempi in cui  Audience Manager elabora i trasferimenti di file da server a server ([!UICONTROL S2S]) in entrata e in uscita, vedere [Reporting and File Transfer Time-Frame Guidelines](../reference/reporting-file-transfer-timeframe.md)(Linee guida sui tempi di trasferimento dei file e dei rapporti).
