---
description: Domande e problemi comuni relativi alla targeting.
seo-description: Domande e problemi comuni relativi alla targeting.
seo-title: Domande frequenti sul targeting
solution: Audience Manager
title: Domande frequenti sul targeting
uuid: ee 96 ef 71-b 903-4953-afc 4-8 ec 8 e 48 bd 49 e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Targeting FAQ{#targeting-faq}

Domande e problemi comuni relativi alla targeting.

<br> 

<!-- 

faq_targeting.xml

 -->

**Dove è possibile trovare un elenco completo dei fornitori di dati di terze parti supportati da Audience Manager?**

See the [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) for a complete list of third-party data providers that [!DNL Audience Manager] supports.

<br> 

**Per indirizzare gli utenti che non ho mai visto sul mio sito con dati di terze parti, posso utilizzare dati di terze parti in Audience Manager o in una DSP?**

La risposta dipende dagli obiettivi. Ad esempio, se la tua campagna è progettata per trovare nuovi client con dati di terze parti, puoi lavorare direttamente con una DSP. Ricorda che Audience Manager sincronizza i dati con un provider di dati terze parti solo quando li vediamo. Se non abbiamo mai visto un utente prima, il sistema non avrà informazioni per quel visitatore del sito. Per campagne che desiderano solo utilizzare dati di terze parti per eseguire il targeting degli utenti che non hanno mai visitato una delle tue proprietà, quindi creano tali segmenti tramite la DSP.

<br> 

**Posso vendere mercato a singoli utenti?**

Audience Manager consente di aggregare gli utenti e il mercato in base a attributi o caratteristiche condivisi. However, to comply with industry regulations, [!DNL Audience Manager] customers may not send personally identifiable information (PII) to our systems. Di conseguenza, non potete utilizzare indirizzi e-mail, nomi singoli, indirizzi fisici ecc. per il targeting.

<br> 

**Come posso tenere in sicurezza i dati di retargeting?**

È consigliabile utilizzare una connessione server-to-server per scambiare dati con la piattaforma di retargeting preferita. Audience Manager scambia dati con la maggior parte dei principali DSP attraverso connessioni server-to-server. I trasferimenti di dati server-to-server consentono agli altri attori di intercettare i dati e di rivendere nuovamente le informazioni relative al pubblico.

<br> 

**L'ID utente univoco di Audience Manager (UUID) è associato all'ID utente univoco di un server tramite la sincronizzazione degli ID direttamente sulla pagina?**

No. Le sincronizzazioni ID non vengono eseguite sulla pagina per editori o server on-site. The Audience Manager UUID is inserted into the `u=` field of the ad server log files. Questo accade quando il segmento viene passato per il targeting. Il modulo codice DIL esegue questa funzione. Si tratta dello stesso meccanismo che ci consente di mappare l'ID utente del server a un utente Audience Manager per il reporting delle prestazioni dei segmenti. Tuttavia, se nel sito è presente un server pubblicitario, gli ID vengono sincronizzati direttamente sulla pagina.

<br> 

**Audience Manager conta un utente che accede da dispositivi diversi come un utente unico o per altri utenti univoci?**

[Il targeting ID dichiarato](../features/declared-ids.md#declared-id-targeting) aiuta Audience Manager a identificare un visitatore su più dispositivi con un unico identificatore univoco. Tuttavia, da un punto di vista di targeting o destinazione, si tratta ancora di 2 (o più) utenti perché i DSP non possono riconciliare tali ID multipli.

<br> 

**Audience Manager identifica un utente dalla visualizzazione e dai dispositivi mobili.**

Sì. See [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**Posso valutare gli utenti con dati raccolti online e reindirizzarli in base a questo punteggio del modello?**

Sì. Audience Manager può fornire file di dati per aiutarti a valutare gli utenti, ma devi lavorare con altri fornitori o software per analizzarle e classificarle. Invia questi dati ad Audience Manager sotto forma di coppie chiave-valore. Possiamo prendere queste informazioni e aggiungerla ai profili utente esistenti. Per rivedere il processo, contattate il rappresentante delle soluzioni partner.

<br> 

**Quali sono i tassi di eliminazione dei cookie per un periodo di 1 mesi specificato?**

L'eliminazione dei cookie è difficile da misurare. La maggior parte dei cookie viene eliminata da alcuni visitatori che eliminano spesso i cookie. Tuttavia, la maggior parte dei cookie del browser sono stabili per almeno 30 giorni, anche se alcuni potrebbero avere una durata limitata. Alcuni studi suggeriscono targeting superiore e funnel maggiore di 30 giorni, eliminando in tal modo il 7% del pubblico di destinazione del browser per un periodo di 30 giorni. Come sai, le campagne di 30 giorni per un determinato messaggio creativo sono standard nel settore. Da ciò che abbiamo visto, il rilascio del 7% è accurato.

L'eliminazione del cookie ha un impatto negativo sui calcoli di portata e frequenza. Di conseguenza, sottolineiamo il valore dei dati comportamentali nel tentativo di capire il tipo reale di tendenze del consumatore per la pianificazione della campagna. I nostri client possono sfruttare i report di sovrapposizione segmenti Audience Manager, i report sulla frequenza di impression ottimali e le tendenze univoche degli utenti su intervalli di date specifici, in modo da essere più scientifici sulla pianificazione delle campagne e su intervalli di date ottimali per le campagne.

<br> 

**Qual è la finestra di scadenza per i cookie di Audience Manager?**

L'interfaccia utente consente di determinare l'intervallo di scadenza dei cookie. You can set cookies to expire after *n* number of days or never.

<br> 

**Implementare una campagna creativa in una chiamata di evento ci costa più?**

Dipende da Costo è basato su utenti univoci. Se una campagna genera dei nuovi utenti, sì, questo costo sarà più costoso. Se la campagna raggiunge i luoghi in cui stiamo già raccogliendo i dati, non c'è alcun costo aggiuntivo. Se la campagna viene eseguita su siti correlati in cui esiste una sovrapposizione significativa, per i nuovi utenti unici verranno costi aggiuntivi.

<br> 

**Audience Manager visualizza[!UICONTROL Addressable Audiences]le metriche e le percentuali di corrispondenza solo per[!UICONTROL Server-to-Server]le destinazioni. Can you explain why we don't see these figures for Cookie and URL destinations?**

Si tratta di sincronizzazioni ID. For [!UICONTROL Server-to-Server] destinations, we transfer data offline (either real-time or batch) and we need to send the ID that the destination partner understands, so they can map it back to the browser. Il numero indirizzabile segmento è un sottoinsieme della popolazione del segmento totale.

In the case of Cookie and URL destinations, the user is already on the browser, and what [!DNL Audience Manager] sends is just the segments that the user qualified for. Il partner di destinazione può semplicemente ritirare le mappature dei segmenti e lavorare con tali informazioni. Considerate quindi le percentuali di corrispondenza per le destinazioni Cookie e URL sempre 100%.
