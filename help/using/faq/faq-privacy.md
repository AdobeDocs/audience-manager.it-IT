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


# Domande frequenti sulla privacy e sulla conservazione dei dati{#privacy-and-data-retention-faq}

Risposte alle domande o ai problemi relativi alla privacy e ai dati comuni.

<!-- faq_privacy.xml -->

## Domande frequenti sulla privacy {#privacy-faq}

>[!TIP]
>
>Per [ulteriori informazioni, visita il Centro](https://www.adobe.com/privacy.html) per la privacy di Adobe.

**In che modo Audience Manager utilizza i cookie e i cookie che vengono impostati?**

Vedi [Cookie di Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**I client di Audience Manager possono essere utilizzati dagli utenti di Target per le proprietà UE?**

Sì. Audience Manager funziona con clienti che hanno proprietà e scorte internazionali. L&#39;Unione Europea ha leggi sulla privacy restrittive, ma Audience Manager dispone di client che utilizzano dati di prime parti per il targeting dell&#39;audience in Europa. Audience Manager supporta il targeting per i tipi di pubblico dell&#39;Unione Europea, ma è la tua responsabilità rispettare le normative sulla privacy locali.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Domande frequenti sulla conservazione dei dati {#data-retention-faq}

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
   <td colname="col2"> <p>120 giorni. </p> <p> Audience Manager elimina i dati utente dai server back-end 120 giorni dopo l'ultimo rilevamento di un utente sulla piattaforma Audience Manager. Se <span class="keyword"> Audience Manager</span> registra l'attività dell'utente entro questo ciclo di 120 giorni, i dati saranno conservati per altri 120 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server periferici </p> </td> 
   <td colname="col2"> <p> 14 giorni. </p> <p>Audience Manager elimina i dati utente dai server periferici 14 giorni dopo l'ultimo rilevamento di un utente sulla piattaforma Audience Manager. Se <span class="keyword"> Audience Manager</span> registra l'attività utente entro questo ciclo di 14 giorni, i dati saranno conservati per altri 14 giorni. Se l'utente diventa nuovamente attivo dopo il periodo di 14 giorni, si verificherà un ritardo tra quella prima nuova pagina e quando l'utente diventa fruibile. Sono necessarie 6-18 ore per recuperare il profilo completo al centro periferico dopo oltre 14 giorni di inattività. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri raw </p> </td> 
   <td colname="col2"> <p>180 giorni (rimosso dopo 180 giorni di nessuna attività). </p> <p>I registri raw sono dati ricevuti da un server periferico tramite chiamate HTTP o da file caricati inviati ad <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri di annunci di annunci </p> </td> 
   <td colname="col2"> <p><b>Generazione di rapporti</b> </p> <p>I file di registro vengono conservati a scopo di reporting per un massimo di 30 giorni. Non sono persistenti registri senza confronti (ovvero i registri per i quali non esiste alcuna sincronizzazione ID tra l'ID del server pubblicitario di un visitatore e l'ID <span class="keyword"> Audience Manager</span> ) nella nostra memorizzazione retroend e i registri corrispondenti memorizzati in <span class="keyword"> Amazon S 3</span> vengono conservati per un massimo di 30 giorni. </p> <p><b>File di registro fruibili</b> </p> <p>I registri associati e non associati vengono conservati per un massimo di 30 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profili a livello CRM (profili autenticati) </p> </td> 
   <td colname="col2"> <p>L'intervallo time-to-live (TTL) predefinito per i profili a livello CRM inattivo (ID cliente) è di 24 mesi. Tuttavia, puoi utilizzare l'interfaccia utente di Audience Manager per ridurre o estendere l'intervallo TTL per i profili a livello CRM inattivi tra un mese e 5 anni. Potete eseguire questa operazione al momento della creazione o della modifica di un'origine dati multi-dispositivo.</p> <p>Per ulteriori informazioni, vedi Impostazioni origine dati in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Crea un'origine </a>dati multi-dispositivo.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID dispositivo mobili </p> </td> 
   <td colname="col2"> <p>Le condizioni di mantenimento per gli ID dispositivo mobili (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) seguono la cadenza descritta nelle prime due righe, server back-end e server periferici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed dati cliente (CDF) </p> </td> 
   <td colname="col2"> <p>Un file CDF contiene gli stessi dati inviati da un <span class="keyword"> evento (/event) di Audience Manager</span> ai server. Il periodo di conservazione è di 8 giorni. Per ulteriori dettagli su CDF, fare riferimento alle <a href="../features/cdf-files.md"> domande frequenti su Intro</a> CDF e <a href="../faq/faq-cdf.md"> CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappature tra ID sincronizzati </p> </td> 
   <td colname="col2"> <p>Le mappature tra gli ID sincronizzati possono essere mantenute per tutta la durata dell'ID utente univoco <a href="../reference/ids-in-aam.md"> di Audience Manager (UUID)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati in entrata </p> </td> 
   <td colname="col2"> <p>Questi sono dati in entrata inviati ad <span class="keyword"> Audience Manager</span> da FTP o direttamente a una <span class="keyword"> directory Amazon S 3</span> . Consultate <a href="../faq/faq-inbound-data-ingestion.md"> le domande frequenti</a>sull'assimilazione dei dati cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati in uscita </p> </td> 
   <td colname="col2"> <p>Questi sono i dati batch inviati <span class="keyword"> da Audience Manager</span> a partner di attivazione terze parti. Il periodo di conservazione è di 8 giorni. Per ulteriori dettagli sui dati in uscita, consultate Trasferimento batch <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> in uscita</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Conservazione dei dati delle caratteristiche {#trait-qual}

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
   <td colname="col2"> <p>Imposti un limite di 100,000 caratteristiche caratteristiche per ogni profilo utente. Il limite si applica a profili autenticati e profili dispositivo. Se un profilo utente raggiunge questo limite, elimineremo le caratteristiche più obsolete delle caratteristiche, in base alla prima e alla prima. </p> <p>Per maggiori dettagli, leggi il limite <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> di Qualifica caratteristica</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

