---
description: Panoramica di alto livello sul modo in cui Audience Manager scambia informazioni con altri fornitori e sistemi di dati.
seo-description: A high-level overview of how Audience Manager exchanges information with other data providers and systems.
seo-title: Data Integration Methods
solution: Audience Manager
title: Metodi di integrazione dei dati
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Metodi di integrazione dei dati {#data-integration-methods}

Panoramica di alto livello sul modo in cui Audience Manager scambia informazioni con altri fornitori e sistemi di dati.

## Metodi di integrazione dei dati supportati: in tempo reale e [!DNL Server-to-Server] {#supported-methods}

La scelta del metodo di integrazione corretto dipende da una combinazione di requisiti aziendali e funzionalità tecniche del partner dati. Audience Manager scambia informazioni sui visitatori con altri provider di dati tramite uno dei seguenti metodi:

* **Real-Time:** trasferisce i dati immediatamente quando un utente visita il tuo sito. Questo metodo è noto anche come integrazione *`synchronous`*.
* **Batch ([!DNL Server-to-Server]):** trasferisce dati tra server in base a una pianificazione impostata dopo che un visitatore ha lasciato la pagina. Questo metodo è noto anche come integrazione *`out-of-band`* o *`asynchronous`*.

## Prerequisiti: creare una tassonomia delle caratteristiche {#prereqs}

Prima dell&#39;inizio del processo di integrazione, ricorda di [creare caratteristiche](../features/traits/create-onboarded-rule-based-traits.md) e una [struttura di cartelle](../features/traits/trait-storage.md#create-trait-storage-folder) nell&#39;interfaccia utente [!DNL Audience Manager]. La tassonomia conterrà tutti i [!UICONTROL traits] organizzati in una gerarchia logica.

## Casi di utilizzo dell’integrazione {#integration-use-cases}

Riepilogo del caso d’uso dei metodi di integrazione dei dati di Audience Manager con i vantaggi e gli svantaggi di ciascuno.

### Integrazioni [!DNL Server-to-Server] in tempo reale

<!-- c_int_types_use_cases.xml -->

L&#39;integrazione dei dati [!DNL server-to-server] in tempo reale sincronizza rapidamente i dati utente tra i server Audience Manager e un altro sistema di targeting. Nella maggior parte dei casi, lo scambio di dati avviene in pochi secondi o minuti, a seconda della frequenza di aggiornamento del sistema di targeting. Tuttavia, il sistema di destinazione determina l&#39;intervallo di aggiornamento, non l&#39;Audience Manager. Inoltre, la frequenza di aggiornamento può variare tra i diversi sistemi. L&#39;integrazione in tempo reale di [!UICONTROL server-to-server] è il tipo di integrazione preferito per gli scambi di dati. Audience Manager utilizza questo metodo ogni volta che i partner di targeting possono supportarlo.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Vantaggi: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Consente di qualificare gli utenti per i segmenti senza visualizzarli nuovamente sulla pagina, in un lettore video, ecc. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Riduce il numero di chiamate HTTP dalla pagina. Un numero inferiore di chiamate consente di preservare l’esperienza utente. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Aiuta con il targeting sensibile al tempo in modo da poter intervenire rapidamente su un utente qualificato. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Utile quando si passa a un DSP per il targeting offsite. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Svantaggi:</td>
  <td class="stentry"> Meno utile per il targeting nel sito quando devi eseguire il targeting dell’utente sulla stessa pagina o sulla pagina successiva, in base alla qualifica di un utente per quel segmento.</td>
 </tr>
</table>

### [!DNL Server-to-Server] integrazioni batch

L&#39;integrazione batch [!DNL server-to-server] raggruppa i dati e li invia ad altri sistemi a intervalli prestabiliti anziché in tempo reale. Gli intervalli di trasferimento dei dati iniziano da 24 ore. Alcuni provider di dati supportano solo questo tipo di integrazione. Tuttavia, abbiamo notato una tendenza generale dalle integrazioni in batch a metodologie di integrazione in tempo reale.

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
  <td class="stentry"> L’intervallo di sincronizzazione può ritardare il targeting dei dati più recenti.</td>
 </tr>
</table>

### Chiamate in tempo reale

Le chiamate in tempo reale si scambiano dati con Audience Manager immediatamente, quando un utente visita il tuo sito o interviene sulla pagina. Con questo metodo, i sistemi di targeting ottengono i dati di qualificazione dei segmenti più aggiornati e possono tenere conto di tali informazioni durante una decisione di distribuzione di contenuti o annunci. Inoltre, questo processo funziona con i server di annunci di pubblicazione in cui aggiorniamo i segmenti qualificati in un cookie di prime parti che viene letto in una chiamata pubblicitaria come coppie chiave-valore. Attualmente, Audience Manager utilizza chiamate in tempo reale per l&#39;integrazione con [!DNL Adobe Target] e altri sistemi di gestione dei contenuti.

<table> 
 <tr>
  <td> <p>Vantaggi: </p></td>
  <td> <p> Consente di impostare come destinazione la pagina successiva, l’area dei contenuti o l’impression pubblicitaria in base alla qualificazione del segmento più recente. </p></td> 
 </tr> 
 <tr>
  <td> <p>Svantaggi: </p></td>
  <td> <p>Aggiunge una chiamata all'Audience Manager dalla pagina.</p></td>
 </tr> 
</table>


### Pixel sincronizzati con i sistemi di targeting

La sincronizzazione dei pixel associa i segmenti ai pixel nella pagina. Il pixel genera e trasmette i dati quando un utente è idoneo per un particolare segmento. La sincronizzazione dei pixel è un meccanismo di trasferimento dei dati rudimentale e inaffidabile. I principali fornitori e sistemi di dati di livello superiore lo utilizzano raramente.

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
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Inaffidabile per la trasmissione dei dati. Una perdita compresa tra il 5% e il 20% è normale. </li>
   </ul></td>
 </tr> 
</table>

## Come scegliere un metodo di distribuzione dei dati {#data-delivery-choices}

Descrive i motivi tecnici e aziendali per l&#39;invio di dati tramite metodologie sincrone (in tempo reale) o asincrone (server-to-server).

<!-- c_int_delivery_choices.xml -->

### Selezione di un tipo di consegna dati

* **Considerazioni tecniche:** la distribuzione dei dati dipende dalle funzionalità tecniche del partner dati. Audience Manager può inviare/ricevere dati in tempo reale dal browser o tramite aggiornamenti batch tramite processi di comunicazione offline server-to-server.
* **Considerazioni aziendali:** i motivi aziendali per selezionare un metodo di consegna o un altro dipendono dalle capacità tecniche del partner di destinazione e dal modo in cui desideri utilizzare questi dati. In genere, i trasferimenti sincroni di dati sono utili quando è necessario intervenire immediatamente sui dati utente. I trasferimenti asincroni di dati possono essere utili quando non è necessaria un’azione immediata e quando hai il tempo di creare profili utente più profondi da utilizzare in un secondo momento.

## Processo di trasferimento dati in tempo reale {#real-time-data-transfer-process}

Panoramica generale sulle prestazioni di Audience Manager per lo scambio sincrono di dati con un fornitore di terze parti.

### Trasferimento dati in tempo reale

<!-- c_int_overview_sync.xml -->

I trasferimenti di dati in tempo reale inviano e ricevono ID di segmenti quando un utente visita o interviene sul sito. In genere, i trasferimenti di dati sincroni sono utili quando è necessario qualificare o segmentare immediatamente gli utenti che navigano nel tuo inventario.

### Passaggi dell’integrazione dei dati in tempo reale

Il processo di integrazione dei dati in tempo reale funziona come segue:

1. Un utente visita il sito di un cliente che contiene codice di Audience Manager.
1. Audience Manager carica un Iframe e effettua una chiamata a [!UICONTROL Data Collection Server] ([!DNL DCS]).
1. [!DNL DCS] chiama il server di terze parti (in tempo reale) per verificare se il fornitore dispone di informazioni sui segmenti dell&#39;utente.
1. La terza parte restituisce ad Audience Manager le informazioni del segmento relative a tale utente.
1. Audience Manager acquisisce le informazioni sui segmenti e le rende disponibili per il targeting.

![](assets/rt_reduce70.png)

## Processo di trasferimento di dati in batch {#batch-data-transfer-process}

Panoramica generale del modo in cui Audience Manager scambia i dati in modo sincrono (in tempo reale) con un fornitore di terze parti.

### Integrazione dei dati in batch

<!-- c_int_overview_async.xml -->

Il processo di integrazione dei dati batch ([!DNL server-to-server]) segue la maggior parte dei passaggi descritti nel processo di trasferimento dei dati in tempo reale. Tuttavia, invece di restituire immediatamente gli ID segmento, le informazioni utente vengono salvate sui nostri server e sincronizzate con un provider di dati di terze parti a intervalli regolari. Il processo di trasferimento dati asincrono è utile quando:

* Non sono necessari trasferimenti immediati di dati.
* Raccolta di dati per creare un ampio pool di utenti segmentati.
* Vuoi ridurre le discrepanze di dati e `HTTP` chiamate dal browser.

### Passaggi dell’integrazione dei dati in batch

1. Un utente visita una sede del cliente.
1. Audience Manager e il provider di dati di terze parti assegnano al visitatore un ID univoco (di solito con un cookie).
1. Audience Manager chiama il provider di dati di terze parti per far corrispondere gli ID visitatore.
1. Una richiesta pianificata, in genere a intervalli giornalieri, scambia i dati del segmento del visitatore tra Audience Manager e il provider di dati di terze parti.

![](assets/s2s_70.png)

Per informazioni che descrivono gli intervalli di tempo in cui Audience Manager elabora i trasferimenti di file [!DNL Server-to-Server] ([!UICONTROL S2S]) in entrata e in uscita, vedere [Linee guida per gli intervalli di tempo di reporting e trasferimento dei file](../reference/reporting-file-transfer-timeframe.md).
