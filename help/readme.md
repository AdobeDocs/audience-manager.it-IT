---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---
# Istruzioni

**Nota: questa pagina (o qualsiasi pagina readme.md) non verrà pubblicata nella documentazione del cliente**

## SOMMARIO

+ `TOC.md` nella directory principale della guida utente fornisce l&#39;organizzazione degli argomenti contenuti nella guida per questa soluzione.
+ Ogni guida utente avrà il proprio `TOC.md` univoco, in cui puoi ordinare tutte le pagine o gli argomenti secondo necessità.
+ La prima pagina di tutte le guide utente è `overview.md`.

## Guida utente

+ L&#39;introduzione alla guida utente è denominata `overview.md`
+ Ogni argomento nella guida utente ha una directory distinta.
   + Se nella guida è presente un argomento denominato *Implementazione*, la directory corrispondente è `/implementation`
+ Tutte le risorse di immagini sono archiviate in `/assets` nella directory principale della guida utente.
   + Tutte le immagini nella directory `/assets` verranno localizzate.
   + Tutte le immagini nella directory `/no-localize` non verranno localizzate (c&#39;è una sorpresa!). Può essere utilizzato per garantire nelle versioni locali che determinate risorse non vengano riprodotte inutilmente.

## Metadati a livello guida utente

+ I metadati che descrivono la guida utente sono memorizzati in `TOC.md`. Ciò include:
   + product: nome del prodotto/funzionalità.
   + cloud: cloud a cui appartiene questo prodotto.
   + pubblico: pubblico o archetipo a cui è destinata la guida.
   + user-guide: nome della guida utente.

## Metadati a livello di pagina

+ I metadati necessari per descrivere un documento vengono memorizzati come parte di ogni singola pagina. Ciò include:
   + title: titolo della pagina.
   + description: descrizione della pagina.
   + seo-title: titolo seo alternativo.
   + seo-description: titolo alternativo ai fini della SEO.
   + short-title: campo facoltativo.
   + index - yes/no: indica se la pagina verrà indicizzata dalla piattaforma di ricerca di Adobe.
   + translate - yes/no: indica se la pagina verrà localizzata.
   + version: utilizzato principalmente per AEM e Campaign, per indicare la versione del prodotto.
   + private-feature-pack: utilizzato principalmente per AEM.
   + beta - il prodotto è in versione beta?
   + redirect: può essere utilizzato per creare un riferimento a una nuova pagina, se necessario.
   + tipo documento: riferimento (predefinito) / risoluzione dei problemi / sviluppatore / tutorial / kb / whitepaper.

## Ulteriori informazioni

Per ulteriori istruzioni sulla pubblicazione, guide di stile, esempi e altre risorse, visita il [repository con documentazione collaborativa](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
