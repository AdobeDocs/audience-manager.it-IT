---
description: Guida di preparazione al RGPD per i clienti di Audience Manager
seo-description: Guida di preparazione al RGPD per i clienti di Audience Manager
seo-title: Guida di preparazione al RGPD per i clienti di Audience Manager
solution: Audience Manager
title: Guida di preparazione al RGPD per i clienti di Audience Manager
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---


# Guida di preparazione al RGPD per i clienti di Audience Manager (titolari del trattamento dei dati) {#gdpr-readiness-guidance}

Audience Manager ti consiglia di essere proattivo nei settori della governance dei dati e della preparazione organizzativa. Questo ti aiuterà a garantire che i dati dei consumatori siano organizzati per consentire i processi relativi alle richieste di accesso o cancellazione, che i tuoi team siano abilitati e autorizzati a gestire tali richieste e che i consumatori (gli interessati) abbiano un’esperienza positiva e differenziata con il tuo marchio.

In qualità di responsabile del trattamento dei dati, Adobe non può fornire consulenza legale sui requisiti RGPD e sulla procedura per ottenere il consenso degli interessati. Consulta il tuo consulente legale per informazioni sul rispetto del RGPD da parte della tua organizzazione.

## Governance dei dati: iniziare a pensare alla modalità di gestione dei dati dei consumatori nell’istanza di Audience Manager

* Controlla i vari ID cliente utilizzati dai tuoi team di marketing per identificare gli utenti in Audience Manager, insieme alle sorgenti di dati in cui sono memorizzati. Questo semplifica il processo relativo alle richieste (ad esempio di cancellazione o accesso), poiché i team assegnano un hash ad alcuni tipi di dati prima dell’assimilazione in Audience Manager.
* Gli ID di dispositivi mobili IDFA/GAID vengono utilizzati per più casi d’uso in Audience Manager. Se utilizzi Adobe Mobile SDK, assicurati di inviare l’Experience Cloud ID (MID) insieme a IDFA/GAID per essere sicuro che le risposte GDPR siano complete.
* Poiché la definizione di dati personali diventa più ampia, gli indirizzi IP possono essere considerati dati personali nella tua area geografica. Rivolgiti in modo proattivo ad Adobe Consulting per oscurare l’ultimo ottetto.
* Determina una policy e un processo di convalida/autenticazione per confermare l’identità di un interessato quando effettua una richiesta RGPD.
* Valuta l’utilizzo dei [Data Export Controls](../../features/data-export-controls.md) per bloccare l’Audience Activation per le tecnologie che ospitano dati personali. Ad esempio, i segmenti con dati di terze parti non devono essere diffusi ai provider di servizi e-mail. Imposta un [!UICONTROL Data Export Control] per garantire che nessuno nell’organizzazione possa accidentalmente attivare tali dati.
* Inizia a utilizzare i [Role Based Access Controls](../../features/administration/administration-overview.md) per garantire che i team giusti abbiano accesso ai dati a loro destinati.
* Valuta [periodi di conservazione](../../faq/faq-privacy.md#data-retention-faq) adeguati ai dati.
* Esamina il collegamento delle identità e le policy e i requisiti legali relativi alla privacy per capire quando e in quali casi è opportuno legare tra loro set di identità; utilizzali in modo appropriato tramite le [Regole di unione profili](../../features/profile-merge-rules/merge-rules-overview.md) di Audience Manager.

## Preparazione organizzativa: stabilire un processo aziendale

* Identifica un processo per ricevere/rispondere alle richieste degli interessati. Prendi in considerazione la creazione di uno strumento automatizzato per inviare le richieste ad Audience Manager.
* Stabilisci un punto di contatto per la privacy all’interno del centro di eccellenza DMP. Connetti il punto di contatto per la privacy della tua organizzazione al team di utilizzo dei prodotti di Audience Manager per capire come gestire i requisiti degli ID di input.
* Esegui una revisione dei dati prima di condividerli con l’interessato. Documenta i passaggi che hai implementato, in modo da aiutarti a stabilire la responsabilità.
