---
description: Cosa fare quando i fogli di lavoro restituiscono un errore o la richiesta di massa non riesce.
seo-description: Cosa fare quando i fogli di lavoro restituiscono un errore o la richiesta di massa non riesce.
seo-title: Suggerimenti per la risoluzione di problemi per strumenti di gestione collettiva
solution: Audience Manager
title: Suggerimenti per la risoluzione di problemi per strumenti di gestione collettiva
uuid: 550908 a 1-e 24 e -4 f 31-954 b -7132 c 0 c 8 dc 3 e
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Troubleshooting Tips for Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

Cosa fare quando i fogli di lavoro restituiscono un errore o la richiesta di massa non riesce.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell' [!DNL Audience Manager] interfaccia utente vengono rispettate nell' [!UICONTROL Bulk Management Tools]interfaccia.

Fattori come traffico di rete pesante, uso server e set di dati grandi possono causare errori o timeout di una richiesta in blocco. In caso di problemi, il foglio di lavoro interrompe la scrittura dei dati e visualizza un messaggio di errore. In tal caso, è necessario:

* Leggere il messaggio di errore.
* Risolvete il problema.
* Elimina tutte le righe già aggiornate.
* Prova nuovamente la richiesta in blocco.

## Long delays or unresponsive behavior {#delays-behavior}

Nella tabella seguente sono elencati alcuni problemi comuni che si possono incontrare durante la creazione di richieste di massa con i fogli di lavoro. Provate a risolvere questi problemi con le soluzioni consigliate. Se le soluzioni consigliate non risolvono il problema, salvate il lavoro, riavviate il computer e riprovate senza avviare o lavorare con altre applicazioni.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problema </th> 
   <th colname="col2" class="entry"> Soluzione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Ritardi lunghi</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Disattivare la modalità di compatibilità</b>: Verifica se nella modalità Compatibilità di Microsoft Excel sono aperti altri fogli di lavoro. La modalità Compatibilità può aumentare i runtime. Chiudete tutti i fogli di calcolo che avete aperto in questa modalità e riprovate. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Risorse sistema</b>: Le risorse limitate del sistema contribuiscono a ritardi lunghi. Prima di effettuare una richiesta collettiva, chiudete tutti gli altri programmi. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nessuna risposta</b> </td> 
   <td colname="col2">Se fai clic sul pulsante di azione e non succede nulla: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Accertatevi di disporre del set di intestazioni corretto per l'azione di selezione. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Accertatevi di usare il foglio di lavoro corretto per le intestazioni copiate. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Verificate la posizione dei dati da utilizzare in un'operazione in blocco. Tutte le intestazioni iniziano nella colonna A, riga 1. Tutti i dati entrano nelle intestazioni corrispondenti iniziando dalla colonna A, riga 2 (immediatamente sotto le intestazioni). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

