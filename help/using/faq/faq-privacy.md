---
description: Risposte alle domande o ai problemi comuni relativi alla privacy e ai dati.
seo-description: Risposte alle domande o ai problemi comuni relativi alla privacy e ai dati.
seo-title: Domande frequenti sulla privacy e sulla conservazione dei dati
solution: Audience Manager
title: Domande frequenti sulla privacy e sulla conservazione dei dati
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 96%

---


# Domande frequenti sulla privacy e sulla conservazione dei dati {#privacy-and-data-retention-faq}

Risposte alle domande o ai problemi comuni relativi alla privacy e ai dati.

<!-- faq_privacy.xml -->

## Domande frequenti sulla privacy {#privacy-faq}

>[!TIP]
>
>Per ulteriori informazioni, visita il [Centro per la privacy di Adobe](https://www.adobe.com/it/privacy.html).

**In che modo Audience Manager utilizza i cookie e quali cookie imposta?**

Consulta [Audience Manager Cookies](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-am.html).

**I clienti di Audience Manager negli Stati Uniti possono effettuare il targeting di utenti su proprietà nell’UE?**

Sì. Audience Manager funziona con client che dispongono di proprietà e inventario internazionali. L’UE ha leggi sulla privacy severe, ma Audience Manager ha client che utilizzano dati di prime parti per il targeting del pubblico in Europa. Audience Manager può supportare il targeting di pubblici dell’UE, ma è responsabilità dell’utente rispettare le normative locali sulla privacy.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Domande frequenti sulla conservazione dei dati {#data-retention-faq}

Nella tabella seguente sono elencati i tempi di conservazione per i diversi tipi di dati e sistemi di archiviazione.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di dati, sorgente o archiviazione </th> 
   <th colname="col2" class="entry"> Periodo di conservazione dei dati </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Server back-end </p> </td> 
   <td colname="col2"> <p>120 giorni. </p> <p> Audience Manager elimina i dati utente dai server back-end 120 giorni dopo l’ultima visualizzazione di un utente sulla piattaforma Audience Manager. Se <span class="keyword">Audience Manager</span> registra l’attività dell’utente durante questo ciclo di 120 giorni, questi dati verranno conservati per altri 120 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server perimetrali </p> </td> 
   <td colname="col2"> <p> 14 giorni. </p> <p>Audience Manager elimina i dati utente dai server perimetrali 14 giorni dopo l’ultima visualizzazione di un utente sulla piattaforma Audience Manager. Se <span class="keyword">Audience Manager</span> registra l’attività dell’utente durante questo ciclo di 14 giorni, questi dati verranno conservati per altri 14 giorni. Se l’utente torna ad essere attivo dopo 14 giorni, si verifica un ritardo tra la prima visualizzazione di una nuova pagina e il momento in cui l’utente diventa actionable. Ci vogliono 6-18 ore per riportare il profilo completo al centro perimetrale dopo più di 14 giorni di inattività. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri non elaborati </p> </td> 
   <td colname="col2"> <p>180 giorni (rimossi dopo 180 giorni di assenza di attività). </p> <p>I registri non elaborati sono dati ricevuti da un server perimetrale tramite chiamate HTTP o da file onboarded inviati ad <span class="keyword">Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri di ad Server </p> </td> 
   <td colname="col2"> <p><b>Generazione di report</b> </p> <p>I file di registro vengono conservati per scopi di reporting per un massimo di 30 giorni. I file di registro senza corrispondenza (ossia quelli per i quali non esiste la sincronizzazione ID tra l’ID ad server del visitatore e l’ID di <span class="keyword"> Audience Manager</span>) nel nostro archivio di back-end e i file di registro con corrispondenza memorizzati in <span class="keyword">Amazon S3</span> vengono conservati per un massimo di 30 giorni. </p> <p><b>File di registro fruibili</b> </p> <p>I registri con e senza corrispondenza vengono conservati per un massimo di 30 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profili a livello di gestione delle relazioni con i clienti (profili autenticati) </p> </td> 
   <td colname="col2"> <p>L’intervallo TTL (time-to-live) predefinito per i profili a livello di gestione delle relazioni con i clienti inattivi (ID cliente) è di 24 mesi. Tuttavia, puoi utilizzare l'interfaccia utente  Audience Manager per ridurre o estendere l'intervallo TTL per i profili a livello CRM inattivi tra un mese e cinque anni. Puoi eseguire questa operazione durante la creazione o la modifica di una sorgente di dati multi-dispositivo.</p> <p>Per ulteriori informazioni, consulta Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings">Create a Cross-Device Data Source</a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID di dispositivi mobili </p> </td> 
   <td colname="col2"> <p>Le condizioni di conservazione per gli ID di dispositivi mobili (<a href="../reference/ids-in-aam.md">IDFA, GAID</a>) seguono la frequenza descritta nelle prime due righe, quelle cioè relative ai server back-end e ai server perimetrali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed di dati cliente (CDF, Customer Data Feeds) </p> </td> 
   <td colname="col2"> <p>Un file CDF contiene gli stessi dati inviati ai nostri server da una chiamata evento (/event) di <span class="keyword"> Audience Manager</span>. Il periodo di conservazione è di 8 giorni. Per ulteriori informazioni su CDF, consulta <a href="../features/cdf-files.md">CDF Intro</a> e <a href="../faq/faq-cdf.md">CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappature tra ID sincronizzati </p> </td> 
   <td colname="col2"> <p>La durata delle <a href="../features/administration/usage-limits.md#id-mapping-limits">mappature ID</a> tra gli ID dei cookie di Audience Manager (<a href="../reference/ids-in-aam.md">ID utente univoci di Audience Manager o AAM UUID</a>) e gli ID dei cookie di terze parti è limitata a 120 giorni. La durata della mappatura ID viene ripristinata ogni volta che il cookie di Audience Manager viene visualizzato nella rete Audience Manager. La sincronizzazione della mappatura ID più recente verrà mantenuta per tutta la durata dell’<a href="../reference/ids-in-aam.md">ID utente univoco di Audience Manager (AAM UUID)</a> associato.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati in entrata </p> </td> 
   <td colname="col2"> <p>Si tratta di dati in entrata inviati ad <span class="keyword">Audience Manager</span> tramite FTP o direttamente a una directory <span class="keyword">Amazon S3</span>. Consulta <a href="../faq/faq-inbound-data-ingestion.md">Inbound Customer Data Ingestion FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati in uscita </p> </td> 
   <td colname="col2"> <p>Si tratta dei dati batch che <span class="keyword">Audience Manager</span> invia ai partner di attivazione di terze parti. Il periodo di conservazione è di 8 giorni. Per ulteriori dettagli sui dati in uscita, consulta <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Conservazione dei dati di qualifica delle caratteristiche {#trait-qual}

Nella tabella seguente sono elencate le opzioni di conservazione per le qualifiche delle caratteristiche.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operazione sulle caratteristiche </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eliminare una caratteristica </p> </td> 
   <td colname="col2"> <p>L’eliminazione di una caratteristica rimuove i dati di qualifica della caratteristica da tutti i profili utente che erano stati qualificati per la caratteristica in passato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite di caratteristiche raggiunto </p> </td> 
   <td colname="col2"> <p>Imponiamo un limite di 100.000 qualifiche di caratteristiche per ogni profilo utente. Il limite si applica ai profili autenticati e ai profili dispositivo. Se un profilo utente raggiunge questo limite, elimineremo le qualifiche delle caratteristiche più vecchie in base al metodo first in first out. </p> <p>Per maggiori dettagli, leggi <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

