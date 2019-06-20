---
description: Questo articolo descrive i prefissi da associare alle variabili chiave durante la creazione di regole per le caratteristiche.
seo-description: Questo articolo descrive i prefissi da associare alle variabili chiave durante la creazione di regole per le caratteristiche.
seo-title: Requisiti di prefisso per variabili chiave
solution: Audience Manager
title: Requisiti di prefisso per variabili chiave
uuid: df 2 ef 9 c 8-606 a -45 f 9-a 836-859 f 856 a 7 d 4 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Requisiti di prefisso per variabili chiave {#prefix-requirements-for-key-variables}

Questo articolo descrive i prefissi da associare alle variabili chiave durante la creazione di regole per le caratteristiche.

<!-- r_tb_variable_prefixes.xml -->

## Scopo dei prefissi variabili chiave

Quando create [!UICONTROL Trait Builder] delle regole, è importante preoccuparvi della variabile chiave con un prefisso consigliato. These prefixes identify the type of data passed in and help avoid namespace conflicts within [!DNL Audience Manager]. In genere, è possibile assegnare un nome a una variabile, ma i dati per una regola non saranno elaborati se il nome della variabile chiave non corrisponde al nome della variabile in una chiamata dell&#39;evento.

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
   <td colname="col2"> <p>Come cliente specifico. Questi sono dati chiave inviati dalle vostre proprietà. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>A livello di <span class="keyword"> Audience Manager</span> . Questi dati sono uniformi nell'ecosistema <span class="keyword"> Audience Manager</span> . Consulta <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Attributi supportati per le chiamate DCS API</a> per un elenco più completo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Contiene <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> informazioni sull'intestazione</a> HTTP. Include parametri di intestazione come <code> referer</code>,<code> IP</code>, <code> accept-language</code>, ecc. </p> <p> <p>Nota: Per i clienti che usano versioni DIL precedenti alla 9.0, la raccolta di dati con il segnale <code> h_ referer</code> non funzionerà sui browser Safari. Con l'introduzione <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> di ITP 2.0</a>, i browser Safari possono classificare il dominio demdex. net come tracciatore e troncherà il referente nella richiesta di raccolta dati per contenere solo l'origine invece dell'URL completo. Consultate <a href="../../dil/dil-overview.md#get-implement-dil-code">Ottenimento e implementazione di codice</a> DIL per la versione DIL più recente. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>I nostri <span class="wintitle"> server di raccolta dati</span> consentono il passaggio di parametri privati. In sostanza, per la valutazione delle caratteristiche viene utilizzato qualsiasi parametro che inizia con <code> p_,</code> ma non verrà registrato a valle né memorizzato. </p> <p>Esempio: given <code> /event? p_ age = 23</code> and a trait like <code> youngpeople = p_ age &lt; 25</code>, the trait will be realized, but the <code> p_ age = 23</code> key-value = key-value pair after the request and will not be logged. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Panoramica di base delle informazioni](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Gestione delle regole di caratteristica](../../features/traits/manage-trait-rules.md#managing-trait-rules)

