---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# Istruzioni

**Nota: Questa pagina (o qualsiasi pagina leggimi. md) non verrà pubblicata nella documentazione del cliente**

## Sommario

+ `TOC.md` nella directory principale della guida utente fornisce l&#39;organizzazione degli argomenti contenuti nella guida per questa soluzione.
+ Ogni guida utente sarà univoca `TOC.md`, in cui potete ordinare tutte le pagine o gli argomenti secondo necessità.
+ La prima pagina di tutte le guide utente è `overview.md`.

## Guida utente

+ L&#39;introduzione alla guida utente è denominata `overview.md`
+ Ogni argomento della guida utente ha una propria directory distinta.
   + Se nella guida è presente un argomento denominato *Implementazione*, la directory corrispondente è `/implementation`
+ Tutte le risorse di immagini sono memorizzate nella `/assets` directory principale della guida utente.
   + Tutte le immagini della `/assets` directory vengono localizzate.
   + Tutte le immagini della `/no-localize` directory non vengono localizzate (c&#39;è una sorpresa!). Questo può essere utilizzato per garantire nelle versioni loc che le risorse specifiche non vengono riprodotte inutilmente.

## Metadati livello guida utente

+ I metadati che descrivono la guida utente sono memorizzati in `TOC.md`. Ciò include:
   + product - nome del prodotto/funzionalità.
   + cloud - cloud a cui appartiene il prodotto.
   + pubblico - pubblico o archetype al quale viene indirizzato il targeting.
   + guida utente - Nome della guida utente.

## Metadati di livello di pagina

+ I metadati necessari per descrivere un documento sono memorizzati come parte di ogni singola pagina. Ciò include:
   + titolo - titolo della pagina.
   + descrizione - descrizione della pagina.
   + seo-title - titolo alternativo.
   + seo-description - titolo alternativo a scopo SEO.
   + breve titolo - (campo facoltativo).
   + index - yes/no - la pagina verrà indicizzata dalla piattaforma di ricerca di Adobe.
   + translate - yes/no - will this page be localized.
   + versione - utilizzata principalmente per AEM e Campaign, per indicare la versione del prodotto.
   + private-feature-pack - utilizzato principalmente per AEM.
   + beta - this product in beta?
   + reindirizzamento: può essere utilizzato per creare un ref a una nuova pagina.
   + doc-type: reference (predefinito)/troubleshooting/developer/tutorial/kb/whitepaper.

## Ulteriori informazioni

Per ulteriori istruzioni sulla pubblicazione, guide di stile, esempi e altre risorse, visitate il [repo della documentazione Collaborativo](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
