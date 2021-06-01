---
description: Metodi di gestione del dominio che consentono di creare e gestire i domini a cui si desidera inviare i dati (solo per le destinazioni dei cookie).
seo-description: Metodi di gestione del dominio che consentono di creare e gestire i domini a cui si desidera inviare i dati (solo per le destinazioni dei cookie).
seo-title: Metodi API di gestione dei domini
solution: Audience Manager
title: Metodi API di gestione dei domini
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 6%

---

# Metodi API di gestione dei domini {#domain-management-api-methods}

Metodi di gestione del dominio che consentono di creare e gestire i domini a cui si desidera inviare i dati (solo per le destinazioni dei cookie).

<!-- c_partner_site.xml -->

## Crea un nuovo dominio {#create-new-domain}

Un metodo `POST` che consente di creare un nuovo dominio per (solo destinazioni cookie).

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

Un metodo `DELETE` che consente di rimuovere un dominio (solo per le destinazioni dei cookie).

<!-- r_delete_partner_site.xml -->

### Richiesta

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Risposta

Una risposta corretta restituisce `204 no content`. Restituisce `404 not found` se non è possibile trovare il sito partner.

## Restituisci proprietà per un dominio {#return-props-domain}

Un metodo `GET` che restituisce i dettagli sul dominio specificato (solo per le destinazioni dei cookie).

<!-- r_get_partner_site.xml -->

### Richiesta

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Risposta

Una risposta corretta restituisce `200 OK` e i dati come mostrato nell’esempio seguente. Restituisce `404 Not found` se l&#39;ID del sito o del partner non è trovato.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Restituisci proprietà per tutti i domini {#return-props-all-domains}

Un metodo `GET` che restituisce informazioni su tutti i domini (solo per le destinazioni dei cookie).

<!-- r_get_partner_sites.xml -->

### Richiesta

`GET https://api.demdex.com/v1/partner-sites/`

### Parametri di query opzionali

È possibile utilizzare questi parametri facoltativi con metodi [!DNL API] che restituiscono le proprietà *all* per un oggetto. Imposta queste opzioni nella stringa di richiesta quando trasmetti la query in a [!DNL API]. Vedere [Parametri facoltativi](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Imposta il numero di risultati di risposta restituiti dalla richiesta (10 è l’impostazione predefinita). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Ordina e restituisce i risultati in base alla proprietà JSON specificata. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Ordina e restituisce i risultati in ordine decrescente. Crescente è l'impostazione predefinita. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Restituisce i risultati in base alla stringa specificata che si desidera utilizzare come parametro di ricerca. Ad esempio, supponiamo che tu voglia trovare risultati per tutti i modelli con la parola "Test" in uno qualsiasi dei campi di valore per quell’elemento. La richiesta di esempio potrebbe essere simile alla seguente: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>Puoi cercare qualsiasi valore restituito da un metodo "get all". </p> </td>
  </tr> 
 </tbody> 
</table>

### Risposta

Una risposta corretta restituisce `200 OK` e i dati in una matrice come mostrato nell&#39;esempio seguente. Restituisce `404 Not found` se l&#39;ID del sito o del partner non è trovato.

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
