---
description: Guida alla preparazione del GDPR per i clienti di Audience Manager
seo-description: Guida alla preparazione del GDPR per i clienti di Audience Manager
seo-title: Guida alla preparazione del GDPR per i clienti di Audience Manager
solution: Audience Manager
title: Guida alla preparazione del GDPR per i clienti di Audience Manager
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# Guida alla preparazione del GDPR per i clienti di Audience Manager (Data Controller) {#gdpr-readiness-guidance}

Audience Manager consiglia di essere proattivo nei settori della governance dei dati e della disponibilità organizzativa. Questo ti aiuterà a garantire che i tuoi dati di consumo siano organizzati per i processi relativi all'accesso o all'eliminazione delle richieste, che i tuoi team saranno abilitati e autorizzati a gestire tali richieste, e che i tuoi consumatori (soggetti di dati) avranno un'esperienza positiva e differenziata con il tuo marchio.

In qualità di titolare del trattamento dati, Adobe non può fornire consulenza legale sui requisiti GDPR e sulla procedura per ottenere il consenso degli interessati. Consulta il tuo consulente legale per informazioni sulla conformità ai requisiti GDPR per la tua organizzazione.

## Governance dei dati: Inizia a pensare alla modalità di gestione dei dati del consumatore nell’istanza di Audience Manager

* Controlla i vari ID cliente utilizzati dai tuoi team di marketing per identificare gli utenti in Audience Manager, insieme alle origini dati in cui sono memorizzati. Questo semplifica il processo per le richieste (ad esempio, eliminare o accedere), dal momento che alcuni tipi di dati verranno truffati dai team prima dell’assimilazione in Audience Manager.
* Gli ID dispositivo mobile IDFA/GAID vengono utilizzati per più casi di utilizzo in Audience Manager. Se utilizzi Adobe Mobile SDK, accertati di inviare Experience Cloud ID (MID) insieme a IDFA/GAID per essere sicuro che le risposte GDPR siano complete.
* Poiché la definizione di dati personali diventa più ampia, gli indirizzi IP possono essere considerati dati personali nella tua regione. Coinvolgi in modo proattivo con Adobe Consulting per oscurare l'ultimo ottetto.
* Determinare un criterio e un processo di convalida/autenticazione per confermare l'identità di un oggetto dati quando effettua una richiesta GDPR.
* Considerare l'utilizzo dei Controlli [sull'esportazione dei](../../features/data-export-controls.md) dati per bloccare l'attivazione dell'audience a tecnologie che ospitano dati personali. Ad esempio, i segmenti con dati di terze parti non devono essere sindacati nei provider di servizi e-mail. Impostate un valore [!UICONTROL Data Export Control] per assicurare che nessuno nell'organizzazione possa accidentalmente attivare tali dati.
* Iniziate a utilizzare i controlli [di accesso basati sul](../../features/administration/administration-overview.md) ruolo per garantire che i team appropriati abbiano accesso ai dati desiderati.
* Considerare i periodi [di](../../faq/faq-privacy.md#data-retention-faq) conservazione appropriati per i dati.
* Esaminare il collegamento di identità e le politiche e i requisiti legali sulla privacy per vedere quando e dove è opportuno collegare insieme i set di identità; utilizzate in modo appropriato tramite le regole [di unione dei](../../features/profile-merge-rules/merge-rules-overview.md)profili di Audience Manager.

## Preparazione organizzativa: Stabilire un processo aziendale

* Identificare un processo per ricevere/rispondere alle richieste dell'oggetto dati. Prendete in considerazione la creazione di uno strumento automatizzato per inviare le richieste ad Audience Manager.
* Nomina un punto di contatto per la privacy all'interno del centro di eccellenza DMP. Connetti il punto di contatto sulla privacy della tua organizzazione al team di utilizzo dei prodotti Audience Manager per capire come gestire i requisiti ID di input.
* Eseguire una revisione dei dati prima di condividerla con l'Oggetto dati. Documentate i passaggi che avete implementato, per aiutarvi a stabilire la responsabilità.
