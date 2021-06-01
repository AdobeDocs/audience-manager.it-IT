---
description: Questo articolo descrive i prefissi da allegare alle variabili chiave durante la creazione di regole per le caratteristiche.
seo-description: Questo articolo descrive i prefissi da allegare alle variabili chiave durante la creazione di regole per le caratteristiche.
seo-title: Requisiti di prefisso delle variabili chiave
solution: Audience Manager
title: Requisiti di prefisso delle variabili chiave
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: 'Caratteristiche '
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 5%

---

# Requisiti di prefisso delle variabili chiave {#prefix-requirements-for-key-variables}

Questo articolo descrive i prefissi da allegare alle variabili chiave durante la creazione di regole per le caratteristiche.

<!-- r_tb_variable_prefixes.xml -->

## Finalità dei prefissi delle variabili chiave

Quando crei delle regole [!UICONTROL Trait Builder], è importante preimpostare la variabile chiave con un prefisso consigliato. Questi prefissi identificano il tipo di dati passati e contribuiscono a evitare conflitti nello spazio dei nomi all&#39;interno di [!DNL Audience Manager]. In genere, puoi assegnare a una variabile qualsiasi nome, ma i dati per una regola non verranno elaborati se il nome della variabile chiave non corrisponde al nome della variabile in una chiamata dell&#39;evento.

## Prefissi per le variabili chiave

La tabella seguente definisce i prefissi comuni utilizzati da [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefisso variabile chiave </th> 
   <th colname="col2" class="entry"> Identifica la variabile </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>Come cliente specifico. Si tratta di dati chiave inviati dalle tue proprietà. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>A livello di <span class="keyword"> Audience Manager</span>. Questi dati sono uniformi nell'ecosistema <span class="keyword"> Audience Manager</span>. Per un elenco più completo, consulta <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Attributi supportati per le chiamate API DCS</a> .</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Contiene informazioni <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP header</a> . Include parametri di intestazione come <code> referer</code>,<code> IP</code>, <code> accept-language</code>, ecc. </p> <p> <p>Nota: Per i clienti che utilizzano versioni di DIL precedenti alla 9.0, la raccolta di dati con il segnale <code> h_referer</code> non funzionerà sui browser Safari. Con l’introduzione di <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, i browser Safari possono classificare il dominio demdex.net come tracker e troncheranno il referrer nella richiesta di raccolta dati per contenere solo l’origine invece dell’URL completo. Per informazioni sull’ultima versione di DIL, consulta <a href="../../dil/dil-overview.md#get-implement-dil-code">Guida e implementazione del codice DIL</a> .<p>I segnali che utilizzano questo prefisso non vengono visualizzati in <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Ricerca segnale</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>I <span class="wintitle"> Data Collection Servers</span> consentono il passaggio di parametri privati. In sostanza, qualsiasi parametro che inizia con <code> p_</code> verrà utilizzato per la valutazione delle caratteristiche, ma non verrà registrato a valle, né memorizzato. </p> <p>Esempio: dato <code> /event?p_age=23</code> e un tratto come <code> YoungPeople = p_age &lt; 25</code>, il tratto verrà realizzato, ma la coppia chiave-valore <code> p_age=23</code> verrà eliminata dopo la richiesta e non verrà registrata. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Informazioni di base](../../features/traits/create-onboarded-rule-based-traits.md)
* [Gestione delle regole delle caratteristiche](../../features/traits/manage-trait-rules.md#managing-trait-rules)

