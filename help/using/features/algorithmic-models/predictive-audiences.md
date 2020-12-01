---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-title: Panoramica di Predictive Audiences
solution: Audience Manager
title: Predictive Audiences di Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 3c39ef38d2833d5d706641f70649251d79b2ee6f
workflow-type: tm+mt
source-wordcount: '1511'
ht-degree: 8%

---


# [!UICONTROL Predictive Audiences] Panoramica {#predictive-audiences}

[!UICONTROL Predictive Audiences] consente di classificare un pubblico sconosciuto in persone distinte, in tempo reale, utilizzando tecniche avanzate di scienza dei dati.

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

 In un contesto di marketing, un utente tipo è un segmento di pubblico definito da visitatori, utenti o potenziali acquirenti che condividono un set specifico di caratteristiche come dati demografici, abitudini di navigazione, cronologia acquisti, ecc..

I modelli di [!UICONTROL Predictive Audiences] portano questo concetto a un livello successivo, consentendoti di utilizzare le funzionalità di machine learning di Audience Manager per classificare pubblici sconosciuti in utenti tipo distinti. Audience Manager ti consente di ottenere questo risultato calcolando la propensione del pubblico sconosciuto di prime parti per un set di pubblici noti di prime parti.

Quando create un modello [!UICONTROL Predictive Audiences], il primo passo consiste nella scelta delle caratteristiche o dei segmenti di base per i quali desiderate classificare il pubblico di destinazione. Queste caratteristiche o segmenti definiranno le tue personalità.

Durante la fase di valutazione, il modello crea un nuovo segmento [!UICONTROL Predictive Audiences] per ogni caratteristica o segmento definito come linea di base. La volta successiva  Audience Manager vede un visitatore dal pubblico di destinazione che non è classificato per un soggetto (non era idoneo per nessuna delle caratteristiche o dei segmenti di base), il modello [!UICONTROL Predictive Audiences] determinerà a quale dei segmenti predittivi il visitatore deve appartenere e aggiungerà il visitatore a tale segmento.

È possibile identificare i segmenti predittivi creati dal modello, nella pagina [!UICONTROL Segments]. Ogni modello [!UICONTROL Predictive Audiences] ha una propria cartella all&#39;interno della cartella [!UICONTROL Predictive Audiences] ed è possibile visualizzare i segmenti di ciascun modello facendo clic sulla cartella del modello.

![previsione-audience-segmenti](assets/predictive-audiences-segments.png)

## Casi d&#39;uso {#use-cases}

Per aiutarti a capire meglio come e quando potresti utilizzare [!UICONTROL Predictive Audiences], ecco alcuni casi d&#39;uso che  clienti del Audience Manager possono risolvere utilizzando questa funzione.

### Caso di utilizzo n. 1

In qualità di esperto di marketing in un&#39;azienda di e-commerce, voglio classificare tutti i visitatori Web e mobili in varie categorie di affinità del marchio, in modo da poter personalizzare la loro esperienza utente.

### Caso di utilizzo n. 2

In qualità di esperto di marketing in un&#39;azienda di media, voglio classificare i visitatori Web e mobili non autenticati in base ai generi preferiti, in modo da poter suggerire loro contenuti personalizzati su tutti i canali.

### Caso di utilizzo n. 3

In qualità di inserzionista per una compagnia aerea, voglio essere certo di classificare il mio pubblico in base al loro interesse per le destinazioni di viaggio, in modo da poter pubblicizzarlo in tempo reale, entro una breve finestra di retargeting.

### Caso di utilizzo n. 4

Come inserzionista, voglio classificare il mio pubblico di prime parti in tempo reale, in modo da poter reagire rapidamente alle notizie di tendenza.

### Caso di utilizzo n. 5

Come esperto di marketing, voglio prevedere in quale fase del percorso del cliente si trovano i visitatori del mio sito web, come scoperta, coinvolgimento, acquisto o conservazione, in modo da poterli indirizzare di conseguenza.

### Caso di utilizzo n. 6

Come azienda di media, voglio classificare il mio pubblico, in modo da poter vendere il mio spazio pubblicitario a prezzi vantaggiosi, offrendo al contempo ai miei visitatori annunci rilevanti.

## Funzionamento dei modelli [!UICONTROL Predictive Audiences] {#how-predictive-audiences-models-work}

Quando si crea un modello [!UICONTROL Predictive Audiences], si passano tre passaggi:

1. Innanzitutto, selezionate almeno due caratteristiche o due segmenti che definiranno le vostre personalità.
1. Quindi, scegli una caratteristica o un segmento che definisca il pubblico di destinazione da classificare.
1. Infine, è possibile scegliere un nome per il modello, un&#39;origine dati che memorizzerà i segmenti predittivi e un [!UICONTROL Profile Merge Rule] per il modello.

### Criteri di selezione per le persone {#selection-personas}

Puoi scegliere una qualsiasi delle caratteristiche o dei segmenti di prime parti per definire le tue personalità. Tuttavia, per ottenere risultati ottimali, si consiglia di seguire una serie di procedure ottimali:

* Scegli le caratteristiche personali o i segmenti in modo che ogni persona abbia almeno un centinaio di [ID dispositivo](../../reference/ids-in-aam.md).
* Se le caratteristiche si basano su [ID cross-device](../../reference/ids-in-aam.md), puoi racchiudere i segmenti con [Regole di unione profilo](../profile-merge-rules/merge-rules-overview.md) che utilizzano [ID dispositivo](../../reference/ids-in-aam.md), ad esempio [!UICONTROL Device Graph]. In questo modo si garantirà che gli [ID dispositivo](../../reference/ids-in-aam.md) possano essere sufficientemente &lt;a0/>utili per l&#39;apprendimento dell&#39;algoritmo.
* Consigliamo di scegliere caratteristiche o segmenti semplici per le vostre persone, composti da 1 a 3 caratteristiche.
* Scegliete caratteristiche o segmenti della linea di base con sovrapposizione minima.
* Accertatevi di acquisire caratteristiche granulari nelle proprietà digitali.

### Criteri di selezione per l&#39;audience di Target {#selection-audience}

A seconda del caso d&#39;uso, se desiderate classificare gli utenti in tempo reale, in batch o in entrambi, scegliete un&#39;audience target ([!UICONTROL trait] o [!UICONTROL segment]) con una popolazione significativa in tempo reale e/o totale. Come per la selezione di persone, si consiglia agli utenti [!UICONTROL trait] o [!UICONTROL segment] di destinazione di disporre di profili avanzati (set completi di [!UICONTROL traits]).

Quando selezionate l&#39;audience di destinazione, analizzate il caso di utilizzo e stabilite i tipi di ID da classificare: [!UICONTROL device IDs] o [!UICONTROL cross-device IDs]. La [!UICONTROL Profile Merge Rule] selezionata al momento della creazione del modello definisce i dati che verranno utilizzati per inserire ogni utente nel predittivo [!UICONTROL segments].

Come procedura ottimale, si consiglia di scegliere una [!UICONTROL Profile Merge Rule] con la stessa configurazione dell&#39;audience di destinazione [!UICONTROL Profile Merge Rule], o una con il tipo di profilo (profilo dispositivo o profilo autenticato) dell&#39;audience di destinazione.

### [!UICONTROL Predictive Audiences] Fase di formazione del modello  {#model-training}

Prima che l&#39;algoritmo possa classificare il pubblico di prime parti nelle persone giuste, deve formarsi sui dati.

Per ogni persona definita dall&#39;utente, l&#39;algoritmo analizza il relativo pubblico e valuta qualsiasi attività relativa alle caratteristiche in tempo reale e/o registrate per i relativi utenti negli ultimi 30 giorni.
Questo passaggio ha luogo una volta ogni 24 ore, per tenere conto dei cambiamenti nel pubblico di prime parti.

### [!UICONTROL Predictive Audiences] Fase classificazione modello  {#model-classification}

Per la classificazione dell&#39;audience in tempo reale e in batch, il modello verifica innanzitutto se un utente appartiene al pubblico di destinazione. Se l&#39;utente si qualifica per l&#39;audience target e non appartiene ad alcuna persona, il modello assegna loro un punteggio di qualifica personale.

Durante la valutazione dei tipi di pubblico di prime parti e l&#39;assegnazione dei punteggi, il modello utilizza la **[!UICONTROL Profile Merge Rule]** predefinita definita nel vostro account. Infine, il visitatore viene classificato nella persona per la quale ha ricevuto il punteggio più alto.

![grafico predittivo-pubblico](assets/predictive-audiences-graph.png)

## Considerazioni e limitazioni {#considerations}

>[!IMPORTANT]
> Leggi attentamente questa sezione prima di passare alla fase di implementazione.

Durante la configurazione dei modelli [!UICONTROL Predictive Audiences], tieni presente quanto segue:

* Puoi creare fino a 10 modelli [!UICONTROL Predictive Audiences]. 
* Per ciascun modello, potete scegliere fino a 50 tratti/segmenti di base.
* I dati di seconda e terza parte non sono attualmente supportati in [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] esegue la classificazione dell&#39;audience in base alle caratteristiche di prime parti, da tutte le origini dati di prime parti.
* La valutazione del segmento per [!UICONTROL Predictive Audiences] utilizza la **[!UICONTROL Profile Merge Rule]** scelta durante la creazione del modello. Per ulteriori informazioni su [!UICONTROL Profile Merge Rules] consultare la [documentazione ](../profile-merge-rules/merge-rules-overview.md) dedicata.
* Alcune caratteristiche e segmenti non sono supportati come linee di base o come audience di destinazione. [!UICONTROL Predictive Audiences] i modelli non verranno salvati quando si sceglie uno dei seguenti tipi di base o di pubblico target:
   * Caratteristiche predittive e segmenti creati con caratteristiche predittive;
   * [Piattaforme o segmenti ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) di Adobe Experience;
   * caratteristiche algoritmiche;
   * Caratteristiche di seconda e terza parte.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] non può essere utilizzato in  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

I segmenti predittivi creati dai modelli [!UICONTROL Predictive Audiences] ereditano i [Controlli sull&#39;esportazione dei dati](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) dalle seguenti origini dati di prime parti:

1. L&#39;origine dati di prime parti scelta al momento della creazione del modello.
1. Le origini dati di prime parti del pubblico di destinazione. Nello specifico, i controlli di esportazione dei dati di [!UICONTROL traits] o [!UICONTROL segments] che costituiscono il pubblico di destinazione.
1. I [Controlli sull&#39;esportazione dei dati](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) della [!UICONTROL Profile Merge Rule] selezionata per il modello.

Le nuove versioni predittive [!UICONTROL traits] e [!UICONTROL segments] avranno le stesse restrizioni di privacy dell&#39;unione delle origini dati di prime parti descritte in precedenza.

Le caratteristiche con restrizioni aggiuntive che non fanno parte delle restrizioni di privacy del segmento [!UICONTROL Predictive Audiences] saranno escluse dalla fase di formazione e non diventeranno influenti per il modello.

## [!UICONTROL Profile Merge Rules] {#pmr}

A tutti i segmenti predittivi verrà assegnato il [!UICONTROL Profile Merge Rule] selezionato al momento della creazione del modello. La [!UICONTROL Profile Merge Rule] scelta è importante per i seguenti motivi:

* Definisce quali dispositivi e/o profili autenticati devono essere presi in considerazione quando il modello analizza l&#39;influente [!UICONTROL traits], al momento di classificare un utente in un predittivo [!UICONTROL segment].
* Regola i tipi [!UICONTROL trait] (livello dispositivo o livello cross-device) da utilizzare durante la fase di formazione del modello e che devono essere visualizzati come influenti [!UICONTROL traits]. Predictive [!UICONTROL segments] sono sottoinsiemi del pubblico di destinazione.
   * Se l&#39;audience di destinazione è un segmento, si consiglia di selezionare per il modello lo stesso [!UICONTROL Profile Merge Rule] assegnato al pubblico di destinazione, oppure un [!UICONTROL Profile Merge Rule] che include il tipo di profilo del pubblico di destinazione.
   * Se l&#39;audience di destinazione è un [!UICONTROL trait], si consiglia di selezionare un [!UICONTROL Profile Merge Rule] in grado di accedere allo stesso tipo di dati della caratteristica dell&#39;audience di destinazione (dati del profilo dispositivo o dati del profilo cross-device).
* [!UICONTROL Profile Merge Rules] l&#39;utilizzo  [!UICONTROL Current Authenticated Profiles] e  [!UICONTROL No Device Profile] le opzioni sono supportate solo per la classificazione dell&#39;audience in tempo reale. Per ulteriori informazioni, vedere [Opzioni delle regole di unione dei profili definite](../profile-merge-rules/merge-rule-definitions.md).

Se si seleziona un elemento [!UICONTROL Profile Merge Rule] che utilizza sia i dati dispositivo che i dati cross-device, viene massimizzato il numero di [!UICONTROL traits] che possono essere utilizzati per la formazione sul modello e la classificazione utente nel predictive [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

Le caratteristiche e i segmenti scelti per le persone e la classificazione dell&#39;audience sono soggetti  Audience Manager [Controlli di accesso basati sul ruolo](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

 utenti di Audienci Manager possono selezionare solo caratteristiche o segmenti per le persone e i tipi di pubblico target, che dispongono dell&#39;autorizzazione [per visualizzare](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
