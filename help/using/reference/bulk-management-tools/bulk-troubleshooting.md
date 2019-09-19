---
description: Cosa fare quando i fogli di lavoro restituiscono un errore o la richiesta in blocco non riesce.
seo-description: Cosa fare quando i fogli di lavoro restituiscono un errore o la richiesta in blocco non riesce.
seo-title: Suggerimenti per la risoluzione dei problemi per gli strumenti di gestione di massa
solution: Audience Manager
title: Suggerimenti per la risoluzione dei problemi per gli strumenti di gestione di massa
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Suggerimenti per la risoluzione dei problemi per gli strumenti di gestione di massa{#troubleshooting-tips-for-bulk-management-tools}

Cosa fare quando i fogli di lavoro restituiscono un errore o la richiesta in blocco non riesce.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>Le [!UICONTROL Bulk Management Tools] opzioni non *sono supportate da* [!DNL Audience Manager]. Questo strumento è fornito per comodità e solo come cortesia. Per modifiche di massa, consigliamo di lavorare con le API [](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

Fattori come il traffico di rete pesante, l'utilizzo del server e i set di dati di grandi dimensioni possono causare il fallimento di una richiesta in massa o il timeout. In caso di problemi, il foglio di lavoro interrompe la scrittura dei dati e visualizza un messaggio di errore. In questo caso, devi:

* Leggete il messaggio di errore.
* Risolvi il problema.
* Elimina tutte le righe che sono già state aggiornate.
* Riprovare la richiesta in massa.

## Tempi lunghi o comportamenti poco reattivi {#delays-behavior}

Nella tabella seguente sono elencati alcuni problemi comuni che si possono incontrare quando si effettuano richieste in massa con i fogli di lavoro. Provate a risolvere questi problemi con le soluzioni consigliate. Se le soluzioni consigliate non risolvono il problema, è necessario salvare il lavoro, riavviare il computer e riprovare senza avviare o utilizzare altre applicazioni.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problema </th> 
   <th colname="col2" class="entry"> Soluzione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Lunghi ritardi</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Disattiva modalità</b>compatibilità: Verificare se sono aperti altri fogli di lavoro in modalità di compatibilità di Microsoft Excel. La modalità di compatibilità può aumentare i tempi di esecuzione. Chiudete eventuali fogli di calcolo aperti in questa modalità e riprovate la richiesta in blocco. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Risorse</b>di sistema: Le limitate risorse del sistema contribuiscono a lunghi ritardi. Prova a chiudere tutti gli altri programmi prima di effettuare una richiesta in massa. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nessuna risposta</b> </td> 
   <td colname="col2">Se si fa clic su un pulsante di azione e non si verifica nulla: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Accertatevi di disporre del set di intestazioni corretto per l’azione di selezione. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Assicurarsi di utilizzare il foglio di lavoro corretto per le intestazioni copiate. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Verificare la posizione dei dati da utilizzare in un'operazione in blocco. Tutte le intestazioni iniziano nella colonna A, riga 1. Tutti i dati vanno nelle intestazioni corrispondenti a partire dalla colonna A, riga 2 (immediatamente sotto le intestazioni). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

