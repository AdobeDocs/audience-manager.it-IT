---
description: Panoramica di alto livello sulle modalità con cui Audience Manager scambia informazioni con altri fornitori e sistemi di dati.
seo-description: Panoramica di alto livello sulle modalità con cui Audience Manager scambia informazioni con altri fornitori e sistemi di dati.
seo-title: Metodi di integrazione dei dati
solution: Audience Manager
title: Metodi di integrazione dei dati
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Integrazione di terze parti
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 1%

---

# Metodi di integrazione dei dati {#data-integration-methods}

Panoramica di alto livello sulle modalità con cui Audience Manager scambia informazioni con altri fornitori e sistemi di dati.

## Metodi di integrazione dei dati supportati: In tempo reale e [!DNL Server-to-Server] {#supported-methods}

La scelta del metodo di integrazione corretto dipende da una combinazione di requisiti aziendali e capacità tecniche del partner dati. Audience Manager scambia informazioni sui visitatori con altri fornitori di dati con uno dei seguenti metodi:

* **In tempo reale:** trasferisce immediatamente i dati quando un utente visita il tuo sito. Questo metodo è noto anche come integrazione *`synchronous`* .
* **Batch ([!DNL Server-to-Server]):** trasferisce i dati tra server in una pianificazione impostata dopo che un visitatore ha lasciato la pagina. Questo metodo è noto anche come integrazione *`out-of-band`* o *`asynchronous`*.

## Prerequisiti: Creare una tassonomia delle caratteristiche {#prereqs}

Prima dell&#39;inizio del processo di integrazione, ricorda di [creare caratteristiche](../features/traits/create-onboarded-rule-based-traits.md) e una [struttura di cartelle](../features/traits/trait-storage.md#create-trait-storage-folder) nell&#39; [!DNL Audience Manager] interfaccia utente. La tassonomia conterrà tutte le [!UICONTROL traits] organizzate in una gerarchia logica.

## Casi d&#39;uso dell&#39;integrazione {#integration-use-cases}

Riepilogo dei metodi di integrazione dei dati di Audience Manager con vantaggi e svantaggi di ciascuno di essi.

### Integrazioni in tempo reale [!DNL Server-to-Server]

<!-- c_int_types_use_cases.xml -->

Un’integrazione dei dati in tempo reale [!DNL server-to-server] sincronizza rapidamente i dati utente tra i server Audience Manager e un altro sistema di targeting. Nella maggior parte dei casi, lo scambio di dati avviene in pochi secondi o minuti, a seconda della frequenza di aggiornamento del sistema di targeting. Tuttavia, il sistema di destinazione determina questo intervallo di aggiornamento, non Audience Manager. Inoltre, la frequenza di aggiornamento può variare da un sistema all&#39;altro. L’integrazione in tempo reale [!UICONTROL server-to-server] è il tipo di integrazione preferito per lo scambio di dati. Audience Manager utilizza questo metodo ogni volta che i partner di targeting possono supportarlo.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Vantaggi: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Consente di qualificare gli utenti per i segmenti senza visualizzarli nuovamente sulla pagina, in un lettore video, ecc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Riduce il numero di chiamate HTTP dalla pagina. Il minor numero di chiamate consente di preservare l’esperienza utente. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Consente di eseguire il targeting in base al tempo, in modo da poter intervenire rapidamente su un utente qualificato. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Utile quando si passa a un DSP per il targeting offsite. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Svantaggi:</td>
  <td class="stentry"> Meno utile per il targeting in sito quando devi eseguire il targeting dell’utente sulla stessa pagina o sulla pagina successiva, in base alla qualifica di un utente per quel segmento.</td>
 </tr>
</table>

### [!DNL Server-to-Server] Integrazioni batch

Un’integrazione batch [!DNL server-to-server] raggruppa i dati e li invia ad altri sistemi a intervalli definiti anziché in tempo quasi reale. Gli intervalli di trasferimento dei dati iniziano da 24 ore. Alcuni provider di dati supportano solo questo tipo di integrazione. Tuttavia, abbiamo visto una tendenza generale che si sta allontanando dalle integrazioni batch verso metodologie di integrazione in tempo reale.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Vantaggi: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Consente di qualificare gli utenti per i segmenti senza visualizzarli nuovamente sulla pagina, in un lettore video, ecc. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Utile per il targeting che non è sensibile al tempo. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Svantaggi:</td>
  <td class="stentry"> L'intervallo di sincronizzazione può ritardare il targeting rispetto ai dati più attuali.</td>
 </tr>
</table>

### Chiamate in tempo reale

Le chiamate in tempo reale scambiano immediatamente i dati con un Audience Manager, quando un utente visita il tuo sito o agisce sulla pagina. Con questo metodo, i sistemi di targeting ottengono i dati di qualificazione dei segmenti più aggiornati e possono tenerne conto durante una decisione di consegna dei contenuti o degli annunci. Inoltre, questo processo funziona con gli ad server di pubblicazione dove aggiorniamo i segmenti qualificati in un cookie di prime parti che viene letto in una ad call come coppie chiave-valore. Al momento, Audience Manager utilizza chiamate in tempo reale per l’integrazione con [!DNL Adobe Target] e altri sistemi di gestione dei contenuti.

<table> 
 <tr>
  <td> <p>Vantaggi: </p></td>
  <td> <p> Consente di eseguire il targeting della pagina successiva, dell’area di contenuto o delle impression pubblicitarie in base alla qualifica del segmento più recente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Svantaggi: </p></td>
  <td> <p>Aggiunge una chiamata ad Audience Manager dalla pagina .</p></td>
 </tr> 
</table>


### Sincronizzazioni pixel a sistemi di targeting

La sincronizzazione dei pixel mappa i segmenti in pixel sulla pagina. Il pixel attiva e trasmette i dati quando un utente si qualifica per un particolare segmento. La sincronizzazione dei pixel è un meccanismo di trasferimento dati rudimentale e inaffidabile. I provider di dati e i sistemi di livello più alto lo utilizzano raramente.

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
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Inaffidabile per la trasmissione dei dati. La perdita dal 5% al 20% è normale. </li>
   </ul></td>
 </tr> 
</table>

## Come scegliere un metodo di consegna dati {#data-delivery-choices}

Descrive i motivi tecnici e aziendali per l’invio di dati tramite metodologie sincrone (in tempo reale) o asincrone (da server a server).

<!-- c_int_delivery_choices.xml -->

### Selezione di un tipo di consegna dati

* **Considerazioni tecniche:** la consegna dei dati dipende dalle capacità tecniche del partner di dati. Audience Manager può inviare/ricevere dati in tempo reale dal browser o tramite aggiornamenti in batch attraverso processi di comunicazione offline-to-server.
* **Considerazioni aziendali:** i motivi aziendali per la selezione di un metodo di consegna o di un altro dipendono dalle capacità tecniche del partner di destinazione e da come desideri utilizzare tali dati. In genere, i trasferimenti di dati sincroni sono utili quando devi intervenire immediatamente sui dati utente. I trasferimenti di dati asincroni possono essere utili quando non è necessaria un’azione immediata e quando hai il tempo di creare profili utente più profondi per un utilizzo successivo.

## Processo di trasferimento dei dati in tempo reale {#real-time-data-transfer-process}

Panoramica generale delle prestazioni di uno scambio di dati sincrono da parte di un fornitore di terze parti in Audience Manager.

### Trasferimento dati in tempo reale

<!-- c_int_overview_sync.xml -->

I trasferimenti di dati in tempo reale inviano e ricevono gli ID del segmento quando un utente visita o agisce sul tuo sito. In genere, i trasferimenti di dati sincroni sono utili quando devi qualificare o segmentare immediatamente gli utenti mentre navigano nel tuo inventario.

### Passaggi per l’integrazione dei dati in tempo reale

Il processo di integrazione dei dati in tempo reale funziona come segue:

1. Un utente visita il sito di un cliente che contiene codice Audience Manager.
1. Audience Manager carica un Iframe ed effettua una chiamata a [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. Il [!DNL DCS] chiama il server di terze parti (in tempo reale) per verificare se il fornitore dispone di informazioni di segmento sull&#39;utente.
1. La terza parte restituisce ad Audience Manager le informazioni di segmento relative a tale utente.
1. Audience Manager acquisisce le informazioni sui segmenti e le rende disponibili per il targeting.

![](assets/rt_reduce70.png)

## Processo di trasferimento di dati in batch {#batch-data-transfer-process}

Panoramica generale del modo in cui Audience Manager scambia i dati in modo sincrono (in tempo reale) con un fornitore di terze parti.

### Integrazione di dati in batch

<!-- c_int_overview_async.xml -->

Il processo di integrazione dei dati batch ([!DNL server-to-server]) segue la maggior parte dei passaggi descritti nel processo di trasferimento dei dati in tempo reale. Tuttavia, invece di restituire immediatamente gli ID del segmento, le informazioni utente vengono salvate sui nostri server e sincronizzate con un provider di dati di terze parti a intervalli regolari. Il processo di trasferimento dati asincrono è utile quando:

* Non sono necessari trasferimenti immediati di dati.
* Raccolta di dati per creare un ampio pool di utenti segmentati.
* Vuoi ridurre le discrepanze di dati e le chiamate `HTTP` dal browser.

### Passaggi per l’integrazione di dati in batch

1. Un utente visita un sito del cliente.
1. Ad Audience Manager, e al provider di dati di terze parti, assegna al visitatore un ID univoco (in genere con un cookie).
1. Ad Audience Manager, chiama il provider di dati di terze parti per far corrispondere gli ID dei visitatori.
1. Una richiesta pianificata, solitamente a intervalli giornalieri, scambia i dati dei segmenti di visitatori tra Audience Manager e il provider di dati di terze parti.

![](assets/s2s_70.png)

Per informazioni che descrivono gli intervalli di tempo in cui Audience Manager elabora i trasferimenti di file in entrata e in uscita [!DNL Server-to-Server] ([!UICONTROL S2S]), consulta [Linee guida per i tempi di reporting e trasferimento dei file](../reference/reporting-file-transfer-timeframe.md).
