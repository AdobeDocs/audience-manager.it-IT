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


# Prefix Requirements for Key Variables {#prefix-requirements-for-key-variables}

Questo articolo descrive i prefissi da associare alle variabili chiave durante la creazione di regole per le caratteristiche.

<!-- r_tb_variable_prefixes.xml -->

## Scopo dei prefissi variabili chiave

When you create [!UICONTROL Trait Builder] rules, it is important to preface the key variable with a recommended prefix. These prefixes identify the type of data passed in and help avoid namespace conflicts within [!DNL Audience Manager]. In genere, è possibile assegnare un nome a una variabile, ma i dati per una regola non saranno elaborati se il nome della variabile chiave non corrisponde al nome della variabile in una chiamata dell'evento.

## Prefissi per variabili chiave

The following table defines the common prefixes used by [!UICONTROL Trait Builder].

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
   <td colname="col2"> <p>At the <span class="keyword"> Audience Manager</span> level. This data is uniform across the <span class="keyword"> Audience Manager</span> ecosystem. See <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a> for a more complete list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>That contains <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP header</a> information. Includes header parameters such as <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Note: For customers using DIL versions older than 9.0, data collection using the <code> h_referer</code> signal will not work on Safari browsers. With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, Safari browsers may classify the demdex.net domain as a tracker and will truncate the referrer on the data collection request to only contain the origin instead of the full URL. See <a href="../../dil/dil-overview.md#get-implement-dil-code">Getting and Implementing DIL Code</a> for the latest DIL version.. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Our <span class="wintitle"> Data Collection Servers</span> allow passing of private parameters. Basically, any parameter that starts with <code> p_</code> will be used for trait evaluation, but it will not be logged downstream, nor stored. </p> <p>Example: given <code> /event?p_age=23</code> and a trait like <code> YoungPeople = p_age &lt; 25</code>, the trait will be realized, but the <code> p_age=23</code> key-value pair will be dropped after the request and will not be logged. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Panoramica di base delle informazioni](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Gestione delle regole di caratteristica](../../features/traits/manage-trait-rules.md#managing-trait-rules)

