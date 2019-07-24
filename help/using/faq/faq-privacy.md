---
description: Risposte alle domande o ai problemi relativi alla privacy e ai dati comuni.
seo-description: Risposte alle domande o ai problemi relativi alla privacy e ai dati comuni.
seo-title: Domande frequenti sulla privacy e sulla conservazione dei dati
solution: Audience Manager
title: Domande frequenti sulla privacy e sulla conservazione dei dati
uuid: ef 558 fca -35 ff -44 f 1-8527-f 8 bee 9 f 2 c 7 e 9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Risposte alle domande o ai problemi relativi alla privacy e ai dati comuni.

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**In che modo Audience Manager utilizza i cookie e i cookie che vengono impostati?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**I client di Audience Manager possono essere utilizzati dagli utenti di Target per le proprietà UE?**

Sì. Audience Manager funziona con clienti che hanno proprietà e scorte internazionali. L'Unione Europea ha leggi sulla privacy restrittive, ma Audience Manager dispone di client che utilizzano dati di prime parti per il targeting dell'audience in Europa. Audience Manager supporta il targeting per i tipi di pubblico dell'Unione Europea, ma è la tua responsabilità rispettare le normative sulla privacy locali.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Data Retention FAQ {#data-retention-faq}

Nella tabella seguente sono elencati i tempi di conservazione per i diversi tipi di dati e sistemi di archiviazione.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di dati, Sorgente o Archiviazione </th> 
   <th colname="col2" class="entry"> Periodo di conservazione dei dati </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Server back-end </p> </td> 
   <td colname="col2"> <p>120 giorni. </p> <p> Audience Manager elimina i dati utente dai server back-end 120 giorni dopo l'ultimo rilevamento di un utente sulla piattaforma Audience Manager. If <span class="keyword"> Audience Manager</span> records user activity within this 120-day cycle, we will keep this data for another 120-days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server periferici </p> </td> 
   <td colname="col2"> <p> 14 giorni. </p> <p>Audience Manager elimina i dati utente dai server periferici 14 giorni dopo l'ultimo rilevamento di un utente sulla piattaforma Audience Manager. If <span class="keyword"> Audience Manager</span> records user activity in within this 14-day cycle, we will keep this data for another 14-days. Se l'utente diventa nuovamente attivo dopo il periodo di 14 giorni, si verificherà un ritardo tra quella prima nuova pagina e quando l'utente diventa fruibile. Sono necessarie 6-18 ore per recuperare il profilo completo al centro periferico dopo oltre 14 giorni di inattività. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri raw </p> </td> 
   <td colname="col2"> <p>180 giorni (rimosso dopo 180 giorni di nessuna attività). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri di annunci di annunci </p> </td> 
   <td colname="col2"> <p><b>Generazione di rapporti</b> </p> <p>I file di registro vengono conservati a scopo di reporting per un massimo di 30 giorni. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and <span class="keyword"> Audience Manager</span> ID) in our backend storage, and matched logs stored in <span class="keyword"> Amazon S3</span> are retained for up to 30 days. </p> <p><b>File di registro fruibili</b> </p> <p>I registri associati e non associati vengono conservati per un massimo di 30 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profili a livello CRM (profili autenticati) </p> </td> 
   <td colname="col2"> <p>L'intervallo time-to-live (TTL) predefinito per i profili a livello CRM inattivo (ID cliente) è di 24 mesi. Tuttavia, puoi utilizzare l'interfaccia utente di Audience Manager per ridurre o estendere l'intervallo TTL per i profili a livello CRM inattivi tra un mese e 5 anni. Potete eseguire questa operazione al momento della creazione o della modifica di un'origine dati multi-dispositivo.</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID dispositivo mobili </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) follow the cadence described in the first two rows, back-end servers and edge servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed dati cliente (CDF) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an <span class="keyword"> Audience Manager</span> event call (/event) sends to our servers. Il periodo di conservazione è di 8 giorni. For more details about CDF, please refer to <a href="../features/cdf-files.md"> CDF Intro</a> and <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappature tra ID sincronizzati </p> </td> 
   <td colname="col2"> <p>Mappings between synchronized IDs may be kept for the life of the associated <a href="../reference/ids-in-aam.md"> Audience Manager Unique User ID (AAM UUID)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati in entrata </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to <span class="keyword"> Audience Manager</span> by FTP or directly to an <span class="keyword"> Amazon S3</span> directory. See the <a href="../faq/faq-inbound-data-ingestion.md"> Inbound Customer Data Ingestion FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati in uscita </p> </td> 
   <td colname="col2"> <p>This is the batch data that <span class="keyword"> Audience Manager</span> sends to third party activation partners. Il periodo di conservazione è di 8 giorni. For more details about Outbound data, please refer to <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait Qualification Data Retention {#trait-qual}

La tabella seguente elenca le opzioni di mantenimento per le caratteristiche delle caratteristiche.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operazione caratteristica </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eliminare una caratteristica </p> </td> 
   <td colname="col2"> <p>Eliminando un trait, i dati delle caratteristiche delle caratteristiche vengono rimossi da tutti i profili utente idonei per la caratteristica precedente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite delle caratteristiche raggiunto </p> </td> 
   <td colname="col2"> <p>Imposti un limite di 100,000 caratteristiche caratteristiche per ogni profilo utente. Il limite si applica a profili autenticati e profili dispositivo. Se un profilo utente raggiunge questo limite, elimineremo le caratteristiche più obsolete delle caratteristiche, in base alla prima e alla prima. </p> <p>For more details, read our <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

