---
description: Risposte alle domande o ai problemi più comuni relativi alla privacy e ai dati.
seo-description: Risposte alle domande o ai problemi più comuni relativi alla privacy e ai dati.
seo-title: Domande frequenti sulla privacy e sulla conservazione dei dati
solution: Audience Manager
title: Domande frequenti sulla privacy e sulla conservazione dei dati
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Domande frequenti sulla privacy e sulla conservazione dei dati{#privacy-and-data-retention-faq}

Risposte alle domande o ai problemi più comuni relativi alla privacy e ai dati.

<!-- faq_privacy.xml -->

## Domande frequenti sulla privacy {#privacy-faq}

>[!TIP]
>
>Per ulteriori informazioni, visitare l&#39; [Adobe Privacy Center](https://www.adobe.com/privacy.html) .

**Come  Audience Manager utilizza i cookie e quali cookie imposta?**

Consultate [Cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)Audience Manager.

**clienti Audience Manager negli Stati Uniti possono rivolgersi agli utenti in merito alle proprietà dell&#39;UE?**

Sì.  Audience Manager funziona con clienti che hanno proprietà e scorte internazionali. L&#39;UE ha leggi severe sulla privacy, ma  Audience Manager ha clienti che utilizzano dati di prime parti per il targeting del pubblico in Europa.  Audience Manager può supportare il targeting per il pubblico dell&#39;UE, ma è responsabilità dell&#39;utente rispettare le normative locali sulla privacy.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Domande frequenti sulla conservazione dei dati {#data-retention-faq}

Nella tabella seguente sono elencati i tempi di conservazione per i diversi tipi di dati e sistemi di storage.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di dati, origine o archiviazione </th> 
   <th colname="col2" class="entry"> Periodo di conservazione dei dati </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Server back-end </p> </td> 
   <td colname="col2"> <p>120 giorni. </p> <p>  Audience Manager elimina i dati utente dai server back-end 120 giorni dopo l'ultima visualizzazione di un utente sulla piattaforma Audience Manager . Se <span class="keyword"> Audience Manager</span> registra l'attività dell'utente entro questo ciclo di 120 giorni, questi dati verranno conservati per altri 120 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server periferici </p> </td> 
   <td colname="col2"> <p> 14 giorni. </p> <p> Audience Manager elimina i dati utente dai nostri server periferici 14 giorni dopo l'ultima visualizzazione di un utente sulla piattaforma Audience Manager . Se <span class="keyword"> Audience Manager</span> registra l'attività dell'utente in questo ciclo di 14 giorni, questi dati verranno conservati per altri 14 giorni. Se l'utente torna ad essere attivo dopo 14 giorni, si verifica un ritardo tra la prima visualizzazione della pagina e quando l'utente diventa fruibile. Ci vogliono 6-18 ore per riportare il profilo completo al centro del margine dopo più di 14 giorni di inattività. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri non elaborati </p> </td> 
   <td colname="col2"> <p>180 giorni (rimossi dopo 180 giorni di assenza di attività). </p> <p>I registri non elaborati sono dati ricevuti da un server periferico tramite chiamate HTTP o da file caricati inviati a <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri Ad Server </p> </td> 
   <td colname="col2"> <p><b>Generazione di rapporti</b> </p> <p>I file di registro vengono conservati a scopo di reporting per un massimo di 30 giorni. I file di registro non corrispondenti (ossia i file di registro per i quali non esiste la sincronizzazione ID tra l’ID server e l’ID <span class="keyword"> Audience Manager</span> di un visitatore) nell’archivio di back-end e i file di registro corrispondenti memorizzati in <span class="keyword"> Amazon S3</span> vengono conservati per un massimo di 30 giorni. </p> <p><b>File di registro fruibili</b> </p> <p>I registri associati e non associati vengono conservati per un massimo di 30 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profili a livello di CRM (profili autenticati) </p> </td> 
   <td colname="col2"> <p>L'intervallo TTL (time-to-live) predefinito per i profili a livello di CRM inattivi (ID cliente) è di 24 mesi. Tuttavia, puoi utilizzare l'interfaccia utente  Audience Manager per ridurre o estendere l'intervallo TTL per i profili a livello CRM inattivi tra un mese e cinque anni. È possibile eseguire questa operazione durante la creazione o la modifica di un'origine dati multi-dispositivo.</p> <p>Per ulteriori informazioni, vedi Impostazioni origine dati in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Creazione di un'origine dati multi-dispositivo </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID dispositivo mobile </p> </td> 
   <td colname="col2"> <p>Le condizioni di conservazione per gli ID dispositivo mobile (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) seguono la frequenza descritta nelle prime due righe, nei server back-end e nei server periferici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed dati cliente (CDF) </p> </td> 
   <td colname="col2"> <p>Un file CDF contiene gli stessi dati che una chiamata <span class="keyword"> evento Audience Manager</span> (/event) invia ai nostri server. Il periodo di conservazione è di 8 giorni. Per ulteriori informazioni su CDF, consultate <a href="../features/cdf-files.md"> CDF Intro</a> e <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappature tra ID sincronizzati </p> </td> 
   <td colname="col2"> <p>La durata delle mappature <a href="../features/administration/usage-limits.md#id-mapping-limits"> ID</a> ID tra  ID cookie Audience Manager (<a href="../reference/ids-in-aam.md">ID utente univoci Audience Manager o UUID</a>AAM) e ID di cookie di terze parti è limitata a 120 giorni. La durata della mappatura ID viene ripristinata ogni volta che il cookie Audience Manager  viene visualizzato nella rete Audience Manager . La sincronizzazione della mappatura ID più recente verrà mantenuta per tutta la durata dell’ID utente univoco <a href="../reference/ids-in-aam.md">Audience Manager associato (AAM UUID)</a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati in entrata </p> </td> 
   <td colname="col2"> <p>Si tratta di dati in entrata inviati a <span class="keyword"> Audience Manager</span> tramite FTP o direttamente a una directory <span class="keyword"> Amazon S3</span> . Consulta le domande frequenti sull' <a href="../faq/faq-inbound-data-ingestion.md"> inserimento dei dati dei clienti in entrata</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati in uscita </p> </td> 
   <td colname="col2"> <p>Si tratta dei dati batch che <span class="keyword"> Audience Manager</span> invia ai partner di attivazione di terze parti. Il periodo di conservazione è di 8 giorni. Per ulteriori dettagli sui dati in uscita, fare riferimento a Trasferimenti <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> batch in</a>uscita. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mantenimento dei dati di qualifica {#trait-qual}

Nella tabella seguente sono elencate le opzioni di conservazione per le qualifiche delle caratteristiche.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzionamento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eliminare una caratteristica </p> </td> 
   <td colname="col2"> <p>L’eliminazione di una caratteristica rimuove i dati sulla qualifica della caratteristica da tutti i profili utente che erano stati qualificati per la caratteristica in passato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite di caratteristiche raggiunto </p> </td> 
   <td colname="col2"> <p>Imponiamo un limite di 100.000 qualifiche per ogni profilo utente. Il limite si applica ai profili e ai profili dispositivo autenticati. Se un profilo utente raggiunge questo limite, elimineremo le qualifiche di caratteristiche più vecchie, in base al primo ingresso e al primo accesso. </p> <p>Per maggiori dettagli, leggi il nostro <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit"> limite</a>di qualificazione delle caratteristiche. </p> </td> 
  </tr> 
 </tbody> 
</table>

