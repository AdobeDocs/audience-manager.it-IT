---
description: Procedura da eseguire quando i fogli di lavoro restituiscono un errore o la richiesta in blocco non riesce.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: Suggerimenti per la risoluzione dei problemi relativi agli strumenti di gestione in blocco
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 3%

---

# Suggerimenti per la risoluzione dei problemi relativi agli strumenti di gestione in blocco{#troubleshooting-tips-for-bulk-management-tools}

Procedura da eseguire quando i fogli di lavoro restituiscono un errore o la richiesta in blocco non riesce.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[Autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnato in [!DNL Audience Manager] L’interfaccia utente di è rispettata in [!UICONTROL Bulk Management Tools].

Fattori quali il traffico di rete elevato, l’utilizzo del server e i set di dati di grandi dimensioni possono causare il mancato funzionamento o il timeout di una richiesta in blocco. In caso di problemi, il foglio di lavoro smette di scrivere i dati e visualizza un messaggio di errore. In questo caso, dovresti:

* Leggi il messaggio di errore.
* Risolvi il problema.
* Elimina tutte le righe già aggiornate.
* Prova di nuovo la richiesta in blocco.

## Errori di autenticazione, ritardi prolungati o comportamento non reattivo {#delays-behavior}

Nella tabella seguente sono elencati alcuni problemi comuni che possono verificarsi quando si eseguono richieste in blocco con i fogli di lavoro. Prova a risolvere questi problemi con le soluzioni consigliate. Se le soluzioni consigliate non risolvono il problema, è consigliabile salvare il lavoro, riavviare il computer e riprovare la richiesta senza avviare o utilizzare altre applicazioni.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Problema </th> 
   <th colname="col2" class="entry"> Soluzione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Errore di autenticazione</b> </td> 
   <td colname="col2"> 
    <b>Aggiornamento alla versione più recente di Microsoft Excel</b>: quando viene rilasciata una nuova versione di Microsoft Excel e si utilizza una versione precedente, è possibile che si verifichi un errore di autenticazione nel foglio di lavoro Gestione in blocco. Aggiornare alla versione più recente di Microsoft Excel per risolvere l'errore di autenticazione.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ritardi lunghi</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Disattiva modalità di compatibilità</b>: verificare che nella modalità di compatibilità di Microsoft Excel siano aperti altri fogli di lavoro. La modalità di compatibilità può aumentare i tempi di esecuzione. Chiudere eventuali fogli di calcolo aperti in questa modalità e riprovare a eseguire la richiesta in blocco. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Risorse di sistema</b>: risorse di sistema limitate contribuiscono a causare ritardi prolungati. Prova a chiudere tutti gli altri programmi prima di effettuare una richiesta in blocco. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nessuna risposta</b> </td> 
   <td colname="col2">Se fai clic su un pulsante di azione e non succede nulla: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Assicurati di disporre del set corretto di intestazioni per l’azione di selezione. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Assicurarsi di utilizzare il foglio di lavoro corretto per le intestazioni copiate. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Controllare la posizione dei dati che si desidera utilizzare in un'operazione di massa. Tutte le intestazioni iniziano nella colonna A, riga 1. Tutti i dati vengono inseriti nelle intestazioni corrispondenti a partire dalla colonna A, riga 2 (immediatamente sotto le intestazioni). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Messaggi di errore

Talvolta è possibile ricevere messaggi di errore quando si apportano modifiche in blocco. Per interpretare il messaggio di errore, vedi [Codici di risposta definiti](/help/using/api/rest-api-main/aam-api-getting-started.md) nella documentazione API.
