---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# Istruzioni

**Nota: Questa pagina (o qualsiasi pagina readme.md) non verrà pubblicata nella documentazione del cliente**

## TOC

+ `TOC.md` nella directory principale della guida utente è disponibile l’organizzazione degli argomenti contenuti nella guida per questa soluzione.
+ Ogni guida utente avrà il proprio `TOC.md` univoco, in cui puoi ordinare tutte le pagine/argomenti in base alle tue esigenze.
+ La prima pagina di tutte le guide utente è `overview.md`.

## Guida utente

+ L’introduzione alla guida utente si chiama `overview.md`
+ Ogni argomento nella guida utente dispone di una propria directory distinta.
   + Se nella guida è presente un argomento denominato *Implementazione*, la directory corrispondente è `/implementation`
+ Tutte le risorse di immagini sono memorizzate in `/assets` nella directory principale della guida utente.
   + Tutte le immagini nella directory `/assets` verranno localizzate.
   + Tutte le immagini nella directory `/no-localize` non verranno localizzate (c&#39;è una sorpresa!). Questo può essere utilizzato per garantire nelle versioni di blocco che specifiche risorse non vengano riprodotte inutilmente.

## Metadati a livello di guida utente

+ I metadati che descrivono la guida utente sono memorizzati in `TOC.md`. Ciò include:
   + product: nome del prodotto/funzionalità.
   + cloud - cloud a cui appartiene il prodotto.
   + audience: pubblico o archetipo a cui è destinata la guida.
   + user-guide: nome della guida utente.

## Metadati a livello di pagina

+ I metadati necessari per descrivere un documento vengono memorizzati come parte di ogni singola pagina. Ciò include:
   + title: titolo della pagina.
   + description: descrizione della pagina.
   + seo-title: titolo seo alternativo.
   + seo-description: titolo alternativo a scopo di SEO.
   + short-title - (campo facoltativo).
   + index - yes/no: la pagina verrà indicizzata dalla piattaforma di ricerca di Adobe.
   + translate - yes/no: indica se la pagina verrà localizzata.
   + version: utilizzato principalmente per AEM e Campaign, per indicare la versione del prodotto.
   + private-feature-pack - utilizzato principalmente per AEM.
   + beta: il prodotto è in versione beta?
   + reindirizzamento : può essere utilizzato per creare un riferimento a una nuova pagina, se necessario.
   + tipo doc: reference (predefinito) / risoluzione dei problemi / sviluppatore / tutorial / kb / whitepaper.

## Ulteriori informazioni

Per ulteriori istruzioni su pubblicazione, guide di stile, esempi e altre risorse, visita il [repository con la documentazione collaborativa](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
