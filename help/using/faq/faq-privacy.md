---
description: Risposte alle domande o ai problemi più comuni relativi alla privacy e ai dati.
seo-description: Risposte alle domande o ai problemi più comuni relativi alla privacy e ai dati.
seo-title: Domande frequenti sulla privacy e sulla conservazione dei dati
solution: Audience Manager
title: Domande frequenti sulla privacy e sulla conservazione dei dati
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 3a4f23bc853a2324a4c91c6e65b14455293a5b1b

---


# Domande frequenti sulla privacy e sulla conservazione dei dati{#privacy-and-data-retention-faq}

Risposte alle domande o ai problemi più comuni relativi alla privacy e ai dati.

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**How does Audience Manager use cookies and what cookies does it set?**

See Audience Manager Cookies.[](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

**Can Audience Manager clients in the US target users on EU properties?**

Sì. Audience Manager works with clients who have international properties and inventory. The EU has strict privacy laws, but Audience Manager has clients who use first-party data for audience targeting in Europe. Audience Manager can support targeting to EU audiences, but it is your responsibility to comply with local privacy regulations.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Data Retention FAQ {#data-retention-faq}

Nella tabella seguente sono elencati i tempi di conservazione per diversi tipi di dati e sistemi di storage.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Data Type, Source, or Storage </th> 
   <th colname="col2" class="entry"> Data Retention Period </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Server back-end </p> </td> 
   <td colname="col2"> <p>120-days. </p> <p> Audience Manager deletes user data from our back-end servers 120 days after last seeing a user on the Audience Manager platform. If  Audience Manager records user activity within this 120-day cycle, we will keep this data for another 120-days.<span class="keyword"></span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge servers </p> </td> 
   <td colname="col2"> <p> 14 giorni. </p> <p>Audience Manager elimina i dati utente dai nostri server periferici 14 giorni dopo l’ultima visualizzazione di un utente sulla piattaforma Audience Manager. Se <span class="keyword"> Audience Manager</span> registra l'attività utente in questo ciclo di 14 giorni, questi dati verranno conservati per altri 14 giorni. Se l'utente torna ad essere attivo dopo 14 giorni, si verifica un ritardo tra la prima visualizzazione della pagina e quando l'utente diventa utilizzabile. Ci vogliono 6-18 ore per riportare il profilo completo al centro del margine dopo più di 14 giorni di inattività. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri non elaborati </p> </td> 
   <td colname="col2"> <p>180 giorni (rimossi dopo 180 giorni di assenza di attività). </p> <p>I registri non elaborati sono dati ricevuti da un server periferico tramite chiamate HTTP o da file caricati inviati ad <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Registri Ad Server </p> </td> 
   <td colname="col2"> <p><b>Generazione di rapporti</b> </p> <p>I file di registro vengono conservati a scopo di reporting per un massimo di 30 giorni. I file di registro non corrispondenti (ossia quelli per i quali non esiste la sincronizzazione ID tra l’ID del server di annunci del visitatore e l’ID di <span class="keyword"> Audience Manager</span> ) nell’archivio di back-end e i file di registro corrispondenti memorizzati in <span class="keyword"> Amazon S3</span> vengono conservati per un massimo di 30 giorni. </p> <p><b>File di registro fruibili</b> </p> <p>I registri associati e non associati vengono conservati per un massimo di 30 giorni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profili a livello di CRM (profili autenticati) </p> </td> 
   <td colname="col2"> <p>L'intervallo TTL (time-to-live) predefinito per i profili a livello di CRM inattivi (ID cliente) è di 24 mesi. Tuttavia, puoi utilizzare l’interfaccia utente di Audience Manager per ridurre o estendere l’intervallo TTL per i profili a livello CRM inattivi tra un mese e cinque anni. È possibile eseguire questa operazione durante la creazione o la modifica di un'origine dati multi-dispositivo.</p> <p>Per ulteriori informazioni, vedi Impostazioni origine dati in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Creazione di un'origine dati multi-dispositivo </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID dispositivo mobile </p> </td> 
   <td colname="col2"> <p>Le condizioni di conservazione per gli ID dispositivo mobile (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) seguono la frequenza descritta nelle prime due righe, nei server back-end e nei server periferici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed dati cliente (CDF) </p> </td> 
   <td colname="col2"> <p>Un file CDF contiene gli stessi dati inviati ai nostri server da una chiamata evento <span class="keyword"> Audience Manager</span> (/event). Il periodo di conservazione è di 8 giorni. Per ulteriori informazioni su CDF, consultate <a href="../features/cdf-files.md"> CDF Intro</a> e <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappature tra ID sincronizzati </p> </td> 
   <td colname="col2"> <p>La durata delle mappature <a href="../features/administration/usage-limits.md#id-mapping-limits"> degli</a> ID tra gli ID dei cookie di Audience Manager (ID utente univoci di<a href="../reference/ids-in-aam.md">Audience Manager o UUID</a>AAM) e gli ID dei cookie di terze parti è limitata a 120 giorni. La durata della mappatura ID viene ripristinata ogni volta che il cookie Audience Manager viene visualizzato nella rete Audience Manager. La sincronizzazione della mappatura ID più recente verrà mantenuta per tutta la durata dell’ID utente univoco di <a href="../reference/ids-in-aam.md">Audience Manager associato (AAM UUID)</a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati in entrata </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to  Audience Manager by FTP or directly to an  Amazon S3 directory. <span class="keyword"></span><span class="keyword"></span> See the  Inbound Customer Data Ingestion FAQ.<a href="../faq/faq-inbound-data-ingestion.md"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Outbound data </p> </td> 
   <td colname="col2"> <p>This is the batch data that  Audience Manager sends to third party activation partners. <span class="keyword"></span> The retention period is 8 days. For more details about Outbound data, please refer to  Outbound Batch Transfers.<a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"></a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait Qualification Data Retention {#trait-qual}

The table below lists the retention options for trait qualifications.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Trait Operation </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Delete a trait </p> </td> 
   <td colname="col2"> <p>Deleting a trait removes the trait qualification data from all the user profiles that had qualified for the trait in the past. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trait limit reached </p> </td> 
   <td colname="col2"> <p>We impose a limit of 100,000 trait qualifications for each user profile. The limit applies to authenticated profiles and device profiles. If a user profile reaches this limit, we will delete the oldest trait qualifications, on a first-in, first-out basis. </p> <p>Per maggiori dettagli, leggi il nostro <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> limite</a>di qualificazione delle caratteristiche. </p> </td> 
  </tr> 
 </tbody> 
</table>

