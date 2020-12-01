---
description: In questo articolo vengono descritti i prefissi da associare alle variabili chiave per la creazione di regole per le caratteristiche.
seo-description: In questo articolo vengono descritti i prefissi da associare alle variabili chiave per la creazione di regole per le caratteristiche.
seo-title: Requisiti di prefisso delle variabili chiave
solution: Audience Manager
title: Requisiti di prefisso delle variabili chiave
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
translation-type: tm+mt
source-git-commit: 1c0d40082cd0753a9b4326aae764eb74aefb8be4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 5%

---


# Requisiti di prefisso delle variabili chiave {#prefix-requirements-for-key-variables}

In questo articolo vengono descritti i prefissi da associare alle variabili chiave per la creazione di regole per le caratteristiche.

<!-- r_tb_variable_prefixes.xml -->

## Finalità dei predefiniti per variabili chiave

Quando create delle regole [!UICONTROL Trait Builder], è importante preimpostare la variabile chiave con un prefisso consigliato. Questi prefissi identificano il tipo di dati passati e aiutano a evitare conflitti tra i namespace in [!DNL Audience Manager]. In genere è possibile assegnare a una variabile qualsiasi nome, ma i dati per una regola non vengono elaborati se il nome della variabile chiave non corrisponde al nome della variabile in una chiamata dell&#39;evento.

## Prefissi per variabili chiave

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
   <td colname="col2"> <p>Come cliente specifico. Si tratta di dati chiave inviati dalle proprie proprietà. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>Al livello <span class="keyword">  Audience Manager</span>. Questi dati sono uniformi nell'ecosistema <span class="keyword">  Audience Manager</span>. Per un elenco più completo, consultate <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Attributi supportati per le chiamate API DCS</a>.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Contiene informazioni su <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> intestazione HTTP</a>. Include parametri di intestazione come <code> referer</code>,<code> IP</code>, <code> accept-language</code>, ecc. </p> <p> <p>Nota: Per i clienti che utilizzano versioni DIL precedenti alla 9.0, la raccolta dei dati utilizzando il segnale <code> h_referer</code> non funzionerà sui browser Safari. Con l'introduzione di <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, i browser Safari possono classificare il dominio demdex.net come tracciatore e troncare il referente nella richiesta di raccolta dati per contenere solo l'origine invece dell'URL completo. Vedere <a href="../../dil/dil-overview.md#get-implement-dil-code">Ottenimento e implementazione del codice DIL</a> per la versione DIL più recente.<p>I segnali che utilizzano questo prefisso non vengono visualizzati in <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Ricerca segnale</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>I <span class="wintitle"> Data Collection Servers</span> consentono il passaggio di parametri privati. In sostanza, qualsiasi parametro che inizia con <code> p_</code> verrà utilizzato per la valutazione delle caratteristiche, ma non verrà registrato a valle né memorizzato. </p> <p>Esempio: data <code> /event?p_age=23</code> e una caratteristica come <code> YoungPeople = p_age &lt; 25</code>, la caratteristica verrà realizzata, ma la coppia chiave-valore <code> p_age=23</code> verrà eliminata dopo la richiesta e non verrà registrata. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Informazioni di base](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Gestione delle regole delle caratteristiche](../../features/traits/manage-trait-rules.md#managing-trait-rules)

