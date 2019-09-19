---
description: Domande e problemi comuni relativi al targeting.
seo-description: Domande e problemi comuni relativi al targeting.
seo-title: Domande frequenti sul targeting
solution: Audience Manager
title: Domande frequenti sul targeting
uuid: e96ef71-b903-4953-afc4-8ec8e48bd49e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Domande frequenti sul targeting{#targeting-faq}

Domande e problemi comuni relativi al targeting.

<br> 

<!-- 

faq_targeting.xml

 -->

**Dove posso trovare un elenco completo dei fornitori di dati di terze parti supportati da Audience Manager?**

Per un elenco completo dei provider di dati di terze parti che supportano, consultate [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) [!DNL Audience Manager] .

<br> 

**Per eseguire il targeting degli utenti che non ho mai visto sul mio sito con dati di terze parti, devo utilizzare dati di terze parti in Audience Manager o in un DSP?**

La risposta dipende dai vostri obiettivi. Ad esempio, se la campagna è progettata per individuare nuovi client con dati di terze parti, è possibile utilizzare direttamente un DSP. Tenete presente che Audience Manager sincronizza i dati con un fornitore di dati di terze parti solo quando viene visualizzato tale utente. Se non abbiamo mai visto un utente prima, il nostro sistema non avrà alcuna informazione per quel visitatore del sito. Per campagne che desiderano utilizzare solo dati di terze parti per target di utenti che non hanno mai visitato alcuna delle tue proprietà, crea quindi questi segmenti attraverso il DSP.

<br> 

**Posso commercializzare con gli individui?**

Audience Manager consente di aggregare utenti e commercializzarli in base ad attributi o caratteristiche condivisi. Tuttavia, per rispettare le normative di settore, [!DNL Audience Manager] i clienti potrebbero non inviare informazioni personali identificabili ai nostri sistemi. Di conseguenza, non è possibile utilizzare indirizzi e-mail, nomi singoli, indirizzi fisici, ecc. per il targeting.

<br> 

**Come posso mantenere sicuri i dati di retargeting?**

È consigliabile utilizzare una connessione server-to-server per scambiare dati con la piattaforma di retargeting preferita. Audience Manager scambia dati con la maggior parte dei principali DSP attraverso connessioni server-to-server. I trasferimenti di dati da server a server consentono di impedire ad altri attori di intercettare i dati e rivendere nuovamente le informazioni sul pubblico.

<br> 

**L’ID utente univoco di Audience Manager (UUID) è associato all’ID utente univoco di un server di annunci tramite la sincronizzazione ID direttamente sulla pagina?**

No. Le sincronizzazioni ID non vengono effettuate sulla pagina per gli editori o i server sul sito. L'UUID di Audience Manager viene inserito nel `u=` campo dei file di registro del server di annunci. Questo accade quando il segmento viene passato per il targeting. Il modulo di codice DIL esegue questa funzione. Questo è lo stesso meccanismo che ci consente di mappare l'ID utente del server a un utente Audience Manager per la generazione di rapporti sulle prestazioni dei segmenti. Tuttavia, se sul sito è presente un server di annunci, gli ID vengono sincronizzati direttamente sulla pagina.

<br> 

**Audience Manager conta un utente che accede da diversi dispositivi come un unico utente o diversi utenti univoci?**

[Il targeting degli ID dichiarati](../features/declared-ids.md#declared-id-targeting) aiuta Audience Manager a identificare un visitatore tra più dispositivi con un unico identificatore. Tuttavia, dal punto di vista del targeting o della destinazione, si tratta ancora di due (o più) utenti, perché i DSP non possono riconciliare questi ID multipli.

<br> 

**Può Audience Manager identificare un utente dalla visualizzazione e dai dispositivi mobili.**

Sì. Consulta Targeting degli ID [dichiarati](../features/declared-ids.md#declared-id-targeting).

<br> 

**Posso segnare gli utenti con i dati raccolti online e riutilizzarli in base a questo punteggio del modello?**

Sì. Audience Manager può fornire file di dati che consentono di valutare gli utenti, ma devi collaborare con altri fornitori o software per analizzare e classificare queste informazioni. Invia questi dati ad Audience Manager sotto forma di coppie chiave-valore. Possiamo prendere queste informazioni e aggiungerle ai profili utente esistenti. Contatta il tuo rappresentante per le soluzioni partner per rivedere questo processo.

<br> 

**Quali sono i tassi di cancellazione dei cookie in un dato periodo di 1 - 2 mesi?**

L'eliminazione dei cookie è difficile da misurare. La maggior parte dell'eliminazione dei cookie proviene da alcuni visitatori che eliminano i cookie di frequente. Tuttavia, la maggior parte dei cookie del browser sono stabili per almeno 30 giorni, anche se alcuni possono avere una durata limitata. Alcuni studi suggeriscono targeting con funnel superiore superiore a 30 giorni che in effetti eliminerebbe il 7% del pubblico target del browser in un periodo di 30 giorni. Come sapete, le campagne di 30 giorni per un determinato messaggio creativo sono standard nel settore. Da quanto abbiamo visto, il 7% di sconto è accurato.

L'eliminazione dei cookie ha un effetto negativo sui calcoli di portata e frequenza. Di conseguenza, sottolineiamo il valore dei dati comportamentali quando cerchiamo di capire la vera natura delle tendenze dei consumatori per la pianificazione delle campagne di visualizzazione. I nostri clienti possono sfruttare i rapporti di sovrapposizione dei segmenti di Audience Manager, i rapporti sulle frequenze di impression ottimali e le tendenze dell’utente univoche su intervalli di date specifici per essere più scientifici sulla pianificazione delle campagne e sugli intervalli di date ottimali per le campagne in esecuzione.

<br> 

**Qual è la finestra di scadenza per i cookie di Audience Manager?**

L'interfaccia utente consente di determinare l'intervallo di scadenza del cookie. Puoi impostare la scadenza dei cookie dopo *un numero* di giorni o mai.

<br> 

**Implementare una campagna creativa in una chiamata all'evento ci costa di più?**

Dipende. Il costo si basa su utenti univoci. Se una campagna genera nuovi utenti netti, allora sì, costerà di più. Se la campagna raggiunge luoghi in cui stiamo già raccogliendo dati, non ci sono costi aggiuntivi. Se la campagna viene eseguita su siti correlati in cui vi è una sovrapposizione significativa, i nuovi utenti univoci che visualizziamo avranno un costo aggiuntivo.

<br> 

**Audience Manager visualizza[!UICONTROL Addressable Audiences]metriche e percentuali di corrispondenza solo per[!UICONTROL Server-to-Server]le destinazioni. Puoi spiegare perché non vediamo queste cifre per Cookie e destinazioni URL?**

Si riduce alle sincronizzazioni ID. Per [!UICONTROL Server-to-Server] le destinazioni, trasferiamo i dati offline (in tempo reale o in batch) e dobbiamo inviare l'ID che il partner di destinazione comprende, in modo che possano mapparlo nuovamente al browser. Il numero indirizzabile del segmento è un sottoinsieme della popolazione totale del segmento.

Nel caso dei cookie e delle destinazioni URL, l'utente è già nel browser e ciò che [!DNL Audience Manager] invia sono solo i segmenti per i quali l'utente ha i requisiti necessari. Il partner di destinazione può semplicemente raccogliere le mappature dei segmenti e lavorare con tali informazioni. Considerate quindi le percentuali di corrispondenza per cookie e destinazioni URL sempre al 100%.
