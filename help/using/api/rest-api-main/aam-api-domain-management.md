---
description: Metodi di gestione del dominio che consentono di creare e gestire i domini a cui si desidera inviare i dati (solo per le destinazioni dei cookie).
seo-description: Metodi di gestione del dominio che consentono di creare e gestire i domini a cui si desidera inviare i dati (solo per le destinazioni dei cookie).
seo-title: Metodi API di gestione dei domini
solution: Audience Manager
title: Metodi API di gestione dei domini
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 6%

---


# Metodi API di gestione dei domini {#domain-management-api-methods}

Metodi di gestione del dominio che consentono di creare e gestire i domini a cui si desidera inviare i dati (solo per le destinazioni dei cookie).

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

Un `POST` metodo che consente di creare un nuovo dominio per (solo destinazioni di cookie).

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

Una risposta corretta restituisce `201 created` e il sito partner, incluso il relativo ID univoco.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Eliminare un dominio {#delete-domain}

Un `DELETE` metodo che consente di rimuovere un dominio (solo per le destinazioni dei cookie).

<!-- r_delete_partner_site.xml -->

### Richiesta

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Risposta

Viene restituita una risposta corretta `204 no content`. Restituisce `404 not found` se non è possibile trovare il sito partner.

## Proprietà di restituzione per un dominio {#return-props-domain}

Un `GET` metodo che restituisce dettagli sul dominio specificato (solo per le destinazioni dei cookie).

<!-- r_get_partner_site.xml -->

### Richiesta

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Risposta

Una risposta corretta restituisce `200 OK` e dati come mostrato nell&#39;esempio seguente. Restituisce `404 Not found` se l’ID del sito o del partner non è stato trovato.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Proprietà di restituzione per tutti i domini {#return-props-all-domains}

Un `GET` metodo che restituisce informazioni su tutti i domini (solo per le destinazioni dei cookie).

<!-- r_get_partner_sites.xml -->

### Richiesta

`GET https://api.demdex.com/v1/partner-sites/`

### Parametri query opzionali

È possibile utilizzare questi parametri facoltativi con [!DNL API] metodi che restituiscono *tutte* le proprietà di un oggetto. Impostate queste opzioni nella stringa di richiesta quando la query viene passata alla [!DNL API]. Consultate Parametri [](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)opzionali.

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
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Imposta il numero di risultati della risposta restituiti dalla richiesta (il valore predefinito è 10). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Ordina e restituisce i risultati in base alla proprietà JSON specificata. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Ordina e restituisce risultati in ordine decrescente. Ascendente è il valore predefinito. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che si desideri trovare risultati per tutti i modelli con la parola "Test" in uno qualsiasi dei campi di valore per l'elemento. Esempio di richiesta: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>È possibile cercare qualsiasi valore restituito da un metodo "get all". </p> </td>
  </tr> 
 </tbody> 
</table>

### Risposta

Una risposta di successo restituisce `200 OK` e dati in un array come mostrato nell&#39;esempio seguente. Restituisce `404 Not found` se l’ID del sito o del partner non è stato trovato.

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
