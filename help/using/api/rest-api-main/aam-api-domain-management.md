---
description: Metodi di gestione del dominio che consentono di creare e gestire i domini ai quali vuoi inviare dati (solo per le destinazioni dei cookie).
seo-description: Metodi di gestione del dominio che consentono di creare e gestire i domini ai quali vuoi inviare dati (solo per le destinazioni dei cookie).
seo-title: Metodi API di gestione dominio
solution: Audience Manager
title: Metodi API di gestione dominio
uuid: f 2 f 08 bc 5-ea 42-4171-9 a 43-0 b 20976 f 0 cb 0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domain Management API Methods {#domain-management-api-methods}

Metodi di gestione del dominio che consentono di creare e gestire i domini ai quali vuoi inviare dati (solo per le destinazioni dei cookie).

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

`POST` Un metodo che consente di creare un nuovo dominio per (solo destinazioni dei cookie).

<!-- r_post_new_partner_site.xml -->

### Richiesta

`POST` `https://api.demdex.com/v1/partner-sites/`

### Richiesta di esempio

```
{
   "url":"example1.com"
}
```

### Risposta

A successful response returns `201 created` and the partner site, including its unique ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Delete a Domain {#delete-domain}

`DELETE` Un metodo che consente di rimuovere un dominio (solo per le destinazioni dei cookie).

<!-- r_delete_partner_site.xml -->

### Richiesta

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Risposta

A successful response returns `204 no content`. Returns `404 not found` if the partner site cannot be found.

## Return Properties for a Domain {#return-props-domain}

`GET` Un metodo che restituisce dettagli sul dominio specificato (solo per le destinazioni dei cookie).

<!-- r_get_partner_site.xml -->

### Richiesta

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Risposta

A successful response returns `200 OK` and data as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Return Properties for all Domains {#return-props-all-domains}

`GET` Un metodo che restituisce informazioni su tutti i domini (solo per le destinazioni dei cookie).

<!-- r_get_partner_sites.xml -->

### Richiesta

`GET https://api.demdex.com/v1/partner-sites/`

### Parametri query facoltativi

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> Restituisce i risultati per numero di pagina. La numerazione inizia da 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> Pagesize</code> </td> 
   <td colname="col2"> Imposta il numero di risultati di risposta restituiti dalla richiesta (10 è predefinito). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Sortby</code> </td> 
   <td colname="col2"> Ordina e restituisce i risultati in base alla proprietà JSON specificata. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> decrescente</code> </td>
   <td colname="col2"> Ordina e restituisce i risultati in ordine decrescente. L'incremento è predefinito. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che desideri trovare risultati per tutti i modelli con la parola "Test" in uno dei campi di valore per quell'elemento. La richiesta di esempio potrebbe essere simile alla seguente: <p><code> ' GET ''https://api.demdex.com/v1/models/?search=Test '</code>. </p> <p>È possibile cercare qualsiasi valore restituito da un metodo "get all". </p> </td>
  </tr> 
 </tbody> 
</table>

### Risposta

A successful response returns `200 OK` and data in an array as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
