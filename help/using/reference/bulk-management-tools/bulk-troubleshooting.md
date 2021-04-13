---
description: Cosa fare quando i fogli di lavoro restituiscono un errore o la richiesta di massa non riesce.
seo-description: Cosa fare quando i fogli di lavoro restituiscono un errore o la richiesta di massa non riesce.
seo-title: Suggerimenti per la risoluzione dei problemi relativi agli strumenti di gestione in blocco
solution: Audience Manager
title: Suggerimenti per la risoluzione dei problemi relativi agli strumenti di gestione in blocco
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 5%

---

# Suggerimenti per la risoluzione dei problemi relativi agli strumenti di gestione in blocco{#troubleshooting-tips-for-bulk-management-tools}

Cosa fare quando i fogli di lavoro restituiscono un errore o la richiesta di massa non riesce.



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[Le ](../../features/administration/administration-overview.md) autorizzazioni del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate in  [!UICONTROL Bulk Management Tools].

Fattori come traffico di rete pesante, utilizzo del server e set di dati di grandi dimensioni possono causare un errore di richiesta in massa o un timeout. Se si verifica un problema, il foglio di lavoro smette di scrivere i dati e visualizza un messaggio di errore. In questo caso, devi:

* Leggi il messaggio di errore.
* Risolvi il problema.
* Elimina tutte le righe già aggiornate.
* Riprova la richiesta in blocco.

## Errori di autenticazione, ritardi prolungati o comportamento non reattivo {#delays-behavior}

Nella tabella seguente sono elencati alcuni problemi comuni che si possono incontrare durante l&#39;esecuzione di richieste in massa con i fogli di lavoro. Prova a risolvere questi problemi con le soluzioni consigliate. Se le soluzioni consigliate non risolvono il problema, è necessario salvare il lavoro, riavviare il computer e riprovare senza avviare o utilizzare altre applicazioni.

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
    <b>Aggiornamento alla versione più recente di Microsoft Excel</b>: Quando viene rilasciata una nuova versione di Microsoft Excel e si utilizza una versione precedente, è possibile che si verifichi un errore di autenticazione nel foglio di lavoro Gestione in blocco. Aggiornamento alla versione più recente di Microsoft Excel per risolvere l'errore di autenticazione.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ritardi lunghi</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>Disattiva la modalità</b> di compatibilità: Verificare se sono aperti altri fogli di lavoro nella modalità di compatibilità di Microsoft Excel. La modalità di compatibilità può aumentare i tempi di esecuzione. Chiudi tutti i fogli di calcolo che potresti aver aperto in questa modalità e riprova la richiesta di massa. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>Risorse</b> di sistema: Le risorse limitate del sistema contribuiscono a lunghi ritardi. Prova a chiudere tutti gli altri programmi prima di effettuare una richiesta in blocco. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nessuna risposta</b> </td> 
   <td colname="col2">Se fai clic su un pulsante di azione e non accade nulla: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Assicurati di disporre del set di intestazioni corretto per l’azione di selezione. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Assicurarsi di utilizzare il foglio di lavoro corretto per le intestazioni copiate. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Consente di controllare la posizione dei dati che si desidera utilizzare in un'operazione collettiva. Tutte le intestazioni iniziano nella colonna A, riga 1. Tutti i dati vanno nelle intestazioni corrispondenti a partire dalla colonna A, riga 2 (immediatamente sotto le intestazioni). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Messaggi di errore

A volte, è possibile ricevere messaggi di errore quando si apportano modifiche in blocco. Per interpretare il messaggio di errore, consulta [Codici di risposta definiti](/help/using/api/rest-api-main/aam-api-getting-started.md) nella documentazione API.
