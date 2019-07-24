---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# Istruzioni

**Nota: Questa pagina (o qualsiasi pagina leggimi. md) non verrà pubblicata nella documentazione del cliente**

## Sommario

+ `TOC.md` nella directory principale della guida utente fornisce l'organizzazione degli argomenti contenuti nella guida per questa soluzione.
+ Each user guide will have its own unique `TOC.md`, in which you can order all the pages/topics as necessary.
+ The first page of all user guides is `overview.md`.

## Guida utente

+ The introduction to the user guide is called `overview.md`
+ Ogni argomento della guida utente ha una propria directory distinta.
   + If there is a topic in the guide called *Implementation*, the corresponding directory is `/implementation`
+ All image assets are stored in `/assets` at the root of the user guide.
   + All images in the `/assets` directory will be localized.
   + Any images in the `/no-localize` directory will not be localized (there's a surprise!). Questo può essere utilizzato per garantire nelle versioni loc che le risorse specifiche non vengono riprodotte inutilmente.

## Metadati livello guida utente

+ Meta data which describes the user guide is stored in the `TOC.md`. Ciò include:
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

For more publishing instructions, style guides, samples and other resources, please visit the [Collaborative Documentation Repo](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
