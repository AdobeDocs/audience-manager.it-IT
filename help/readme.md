---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# Istruzioni

**Nota: Questa pagina (o qualsiasi altra pagina Leggimi.md) non verrà pubblicata nella documentazione rivolta al cliente**

## Sommario

+ `TOC.md` nella parte principale della guida utente è disponibile l&#39;organizzazione degli argomenti contenuti nella guida per questa soluzione.
+ Ogni guida utente avrà un `TOC.md` specifico, in cui è possibile ordinare tutte le pagine e gli argomenti in base alle esigenze.
+ La prima pagina di tutte le guide utente è `overview.md`.

## Guida utente

+ L&#39;introduzione alla guida utente è denominata `overview.md`
+ Ogni argomento della guida utente ha una propria directory distinta.
   + Se nella guida è presente un argomento denominato *Implementation*, la directory corrispondente è `/implementation`
+ Tutte le risorse di immagine sono memorizzate in `/assets` nella directory principale della guida utente.
   + Tutte le immagini nella directory `/assets` verranno localizzate.
   + Tutte le immagini presenti nella directory `/no-localize` non verranno localizzate (sorprende!). Questo può essere utilizzato per garantire che nelle versioni localizzate non vengano riprodotte risorse specifiche inutilmente.

## Metadati a livello di guida utente

+ I metadati che descrivono la guida utente sono memorizzati in `TOC.md`. Ciò include:
   + product - nome del prodotto/capacità.
   + cloud - cloud a cui appartiene il prodotto.
   + audience - audience o archetipo a cui viene indirizzata la guida.
   + guida utente - nome della guida utente.

## Metadati a livello di pagina

+ I metadati necessari per descrivere un documento vengono memorizzati come parte di ogni singola pagina. Ciò include:
   + title - titolo della pagina.
   + descrizione - descrizione della pagina.
   + seo-title - seo titolo alternativo.
   + seo-description - titolo alternativo ai fini del SEO.
   + short-title - (campo facoltativo).
   + index - yes / no - la pagina verrà indicizzata da  Adobe  piattaforma di ricerca.
   + translate - yes / no - questa pagina sarà localizzata.
   + versione - utilizzata principalmente per AEM e Campaign, per indicare la versione del prodotto.
   + private-feature-pack - utilizzato principalmente per AEM.
   + beta - questo prodotto è in beta?
   + reindirizzamento: può essere utilizzato per creare un riferimento a una nuova pagina, se necessario.
   + doc-type: reference (predefinito) / risoluzione dei problemi / sviluppatore / esercitazione / kb / whitepaper.

## Ulteriori informazioni

Per ulteriori istruzioni di pubblicazione, guide di stile, esempi e altre risorse, visitare il [Collaborative Documentation Repo](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
