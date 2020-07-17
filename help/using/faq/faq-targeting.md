---
description: Domande e problemi comuni relativi al targeting.
seo-description: Domande e problemi comuni relativi al targeting.
seo-title: Domande frequenti sul targeting
solution: Audience Manager
title: Domande frequenti sul targeting
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
translation-type: tm+mt
source-git-commit: 27ce94084e35ffa770858027d12235ca9f1f8430
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 100%

---


# Domande frequenti sul targeting {#targeting-faq}

Domande e problemi comuni relativi al targeting.

<br> 

<!-- 

faq_targeting.xml

 -->

**Dove posso trovare un elenco completo dei provider di dati di terze parti supportati da Audience Manager?**

Consulta [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) per un elenco completo dei provider di dati di terze parti supportati da [!DNL Audience Manager].

<br> 

**Per eseguire il targeting degli utenti che non hanno mai visitato il mio sito con dati di terze parti, devo utilizzare dati di terze parti in Audience Manager o in una DSP?**

La risposta dipende dai tuoi obiettivi. Ad esempio, se la tua campagna è progettata per individuare nuovi clienti con dati di terze parti, allora puoi utilizzare direttamente una DSP. Tieni presente che Audience Manager sincronizza i dati con un provider di dati di terze parti solo quando vediamo tale utente. Se non abbiamo mai visto un utente prima, il nostro sistema non avrà alcuna informazione su quel visitatore del sito. Per campagne per cui desideri utilizzare solo dati di terze parti per il targeting di utenti che non hanno mai visitato alcuna delle tue proprietà, crea quei segmenti attraverso la DSP.

<br> 

**Posso vendere a singoli utenti?**

Audience Manager ti consente di aggregare utenti e vendere a essi in base ad attributi o caratteristiche condivisi. Tuttavia, per rispettare le normative di settore, i clienti [!DNL Audience Manager] non possono inviare informazioni personali (PII, personally identifiable information) ai nostri sistemi. Di conseguenza, non puoi utilizzare indirizzi e-mail, nomi di singoli utenti, indirizzi fisici, ecc. per il targeting.

<br> 

**Come posso proteggere i dati di retargeting?**

È consigliabile utilizzare una connessione server-to-server per scambiare dati con la piattaforma di retargeting preferita. Audience Manager scambia dati con la maggior parte delle principali DSP attraverso connessioni server-to-server. I trasferimenti di dati server-to-server consentono di impedire ad altri attori di intercettare i tuoi dati e rivendere le informazioni sul pubblico.

<br> 

**L’ID utente univoco di Audience Manager (UUID) è associato all’ID utente univoco di un ad server tramite la sincronizzazione ID direttamente sulla pagina?**

No. Le sincronizzazioni ID non vengono effettuate sulla pagina per gli editori o i server presenti sul sito. L’UUID di Audience Manager viene inserito nel campo `u=` dei file di registro dell’ad server. Questo accade quando il segmento viene trasmesso per il targeting. Il modulo del codice DIL svolge questa funzione. Questo è lo stesso meccanismo che ci consente di mappare l’ID utente del server su un utente Audience Manager per il reporting sulle prestazioni dei segmenti. Tuttavia, se sul sito è presente un server di annunci, gli ID vengono sincronizzati direttamente sulla pagina.

<br> 

**Audience Manager considera un utente che accede da diversi dispositivi come un utente univoco o diversi utenti univoci?**

Il [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting) aiuta Audience Manager a identificare un visitatore su più dispositivi tramite un singolo identificatore univoco. Tuttavia, dal punto di vista del targeting o della destinazione, si tratta comunque di due (o più) utenti, poiché le DSP non possono riconciliare tali ID multipli.

<br> 

**Audience Manager può identificare un utente dalla visualizzazione e dai dispositivi mobili?**

Sì. Consulta [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**Posso valutare gli utenti tramite i dati raccolti online ed effettuare il retargeting in base alla valutazione del modello?**

Sì. Audience Manager può fornire file di dati che ti consentono di valutare gli utenti, ma devi collaborare con altri fornitori o software per analizzare e classificare tali informazioni. Invia questi dati ad Audience Manager sotto forma di coppie chiave-valore. Possiamo prendere queste informazioni e aggiungerle ai profili utente esistenti. Contatta il tuo rappresentante di soluzioni dei partner per esaminare questo processo.

<br> 

**Quali sono i tassi di cancellazione dei cookie in un dato periodo di 1-2 mesi?**

L’eliminazione dei cookie è difficile da misurare. La maggior parte delle eliminazioni dei cookie proviene da alcuni visitatori che eliminano i cookie di frequente. Tuttavia, la maggior parte dei cookie del browser sono stabili per almeno 30 giorni, anche se alcuni possono avere una durata limitata. Alcuni studi suggeriscono che un targeting con funnel superiore e una durata maggiore di 30 giorni eliminerebbe di fatto il 7% del pubblico target del browser in un periodo di 30 giorni. Come sai, le campagne di 30 giorni per un determinato messaggio creativo sono standard nel settore. Da quanto abbiamo visto, quel calo del 7% è accurato.

L’eliminazione dei cookie ha un effetto negativo sui calcoli di portata e frequenza. Di conseguenza, sottolineiamo il valore dei dati comportamentali quando si cerca di capire la vera natura delle tendenze dei consumatori per la pianificazione delle campagne display. I nostri clienti possono sfruttare i report sulla sovrapposizione dei segmenti, i report sulla frequenza di impression ottimali e le tendenze di utenti univoci su intervalli di date specifici di Audience Manager per pianificare in maniera più scientifica le campagne e gli intervalli di date ottimali per effettuare le campagne.

<br> 

**Qual è l’intervallo di scadenza per i cookie di Audience Manager?**

L’interfaccia utente ti consente di determinare l’intervallo di scadenza dei cookie. Puoi impostare i cookie affinché scadano dopo un numero *n* di giorni o mai.

<br> 

**Implementare un contenuto creativo di una campagna in una chiamata all’evento costa di più?**

Dipende. Il costo si basa su utenti univoci. Se una campagna genera nuovi utenti netti, allora sì, costerà di più. Se la campagna raggiunge luoghi in cui stiamo già raccogliendo dati, non ci sono costi aggiuntivi. Se la campagna viene eseguita su siti correlati in cui vi è una sovrapposizione significativa, i nuovi utenti univoci che visualizziamo avranno un costo aggiuntivo.

<br> 

**Audience Manager mostra metriche e percentuali di corrispondenza di [!UICONTROL Addressable Audiences] solo per le destinazioni [!UICONTROL Server-to-Server]. È possibile spiegare perché non visualizziamo queste cifre per cookie e destinazioni URL?**

È una questione di sincronizzazioni ID. Per le destinazioni [!UICONTROL Server-to-Server], trasferiamo i dati offline (in tempo reale o in batch) e dobbiamo inviare l’ID comprensibile al partner di destinazione, in modo che possa mapparlo nuovamente sul browser. Il numero indirizzabile del segmento è un sottoinsieme della popolazione totale del segmento.

Nel caso dei cookie e delle destinazioni URL, l’utente è già nel browser e [!DNL Audience Manager] invia sono solo i segmenti per i quali l’utente ha i requisiti necessari. Il partner di destinazione può semplicemente raccogliere le mappature dei segmenti e lavorare con tali informazioni. Considera quindi percentuali di corrispondenza per cookie e destinazioni URL sempre del 100%.
