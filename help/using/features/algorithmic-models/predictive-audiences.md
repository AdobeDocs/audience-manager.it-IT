---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-title: Panoramica di Predictive Audiences
solution: Audience Manager
title: Predictive Audiences di Audience Manager
feature: Modelli algoritmici
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 8%

---

# [!UICONTROL Predictive Audiences] Panoramica {#predictive-audiences}

[!UICONTROL Predictive Audiences] ti aiuta a classificare un pubblico sconosciuto in utenti tipo distinti, in tempo reale, utilizzando tecniche avanzate di scienza dei dati.

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarti nella configurazione e nell’utilizzo di questa funzione. Nulla in essa contenuto è costituito da una consulenza legale. Consulta il tuo consulente legale per una guida legale.

 In un contesto di marketing, un utente tipo è un segmento di pubblico definito da visitatori, utenti o potenziali acquirenti che condividono un set specifico di caratteristiche come dati demografici, abitudini di navigazione, cronologia acquisti, ecc..

I modelli di [!UICONTROL Predictive Audiences] portano questo concetto a un livello successivo, consentendoti di utilizzare le funzionalità di machine learning di Audience Manager per classificare pubblici sconosciuti in utenti tipo distinti. Audience Manager ti consente di ottenere questo risultato calcolando la propensione del pubblico sconosciuto di prime parti per un set di pubblici noti di prime parti.

Quando crei un modello [!UICONTROL Predictive Audiences], il primo passaggio consiste nel scegliere le caratteristiche o i segmenti della linea di base per i quali vuoi che il pubblico di destinazione sia classificato. Queste caratteristiche o segmenti definiranno i tuoi utenti tipo.

Durante la fase di valutazione, il modello crea un nuovo segmento [!UICONTROL Predictive Audiences] per ogni caratteristica o segmento definito come linea di base. La prossima volta che un Audience Manager vede un visitatore del pubblico di destinazione che non è classificato per un utente tipo (non si è qualificato per nessuna delle caratteristiche o dei segmenti della linea di base), il modello [!UICONTROL Predictive Audiences] determinerà a quale dei segmenti predittivi il visitatore deve appartenere e aggiungerà il visitatore a quel segmento.

Puoi identificare i segmenti predittivi creati dal modello, nella pagina [!UICONTROL Segments] . Ogni modello [!UICONTROL Predictive Audiences] ha una propria cartella sotto la cartella [!UICONTROL Predictive Audiences] e puoi visualizzare i segmenti di ciascun modello facendo clic sulla cartella del modello.

![segmenti predittivi-pubblici](assets/predictive-audiences-segments.png)

## Casi d&#39;uso {#use-cases}

Per aiutarti a comprendere meglio come e quando utilizzare [!UICONTROL Predictive Audiences], ecco alcuni casi d’uso che i clienti di Audience Manager possono risolvere utilizzando questa funzione.

### Caso d&#39;uso n. 1

In qualità di addetto al marketing in un’azienda di e-commerce, voglio classificare tutti i miei visitatori web e mobili in varie categorie di affinità al marchio, in modo da poter personalizzare la loro esperienza utente.

### Caso d&#39;uso n. 2

In qualità di addetto al marketing in un&#39;azienda di media, voglio classificare i miei visitatori web e mobili non autenticati in base ai generi preferiti, in modo da poter suggerire loro contenuti personalizzati su tutti i canali.

### Caso d&#39;uso n. 3

In qualità di inserzionista di una compagnia aerea, voglio essere sicuro di classificare il mio pubblico in base al loro interesse per le destinazioni di viaggio, in modo da poter pubblicizzarlo in tempo reale, entro una breve finestra di retargeting.

### Caso d&#39;uso n. 4

Come inserzionista, voglio classificare il mio pubblico di prime parti in tempo reale, in modo da poter reagire rapidamente alle notizie più diffuse.

### Caso d&#39;uso n. 5

In qualità di addetto al marketing, voglio prevedere in quale fase del percorso del cliente si trovano i visitatori del mio sito web, come scoperta, impegno, acquisto o fidelizzazione, in modo da poterli indirizzare di conseguenza.

### Caso d&#39;uso n. 6

Come azienda di media, voglio classificare il mio pubblico in modo da poter vendere il mio spazio pubblicitario a prezzi premium, offrendo al contempo ai miei visitatori annunci pertinenti.

## Funzionamento dei modelli [!UICONTROL Predictive Audiences] {#how-predictive-audiences-models-work}

Quando crei un modello [!UICONTROL Predictive Audiences], esegui tre passaggi:

1. Innanzitutto, scegli almeno due caratteristiche o due segmenti che definiranno i tuoi utenti tipo.
1. Quindi scegli una caratteristica o un segmento che definisce il pubblico target da classificare.
1. Infine, scegli un nome per il modello, un’origine dati che memorizzerà i segmenti predittivi e un [!UICONTROL Profile Merge Rule] per il modello.

### Criteri di selezione per le persone {#selection-personas}

Puoi scegliere una qualsiasi delle caratteristiche o dei segmenti di prime parti per definire i tuoi utenti tipo. Tuttavia, per ottenere risultati ottimali, ecco una serie di best practice consigliate:

* Scegli le caratteristiche o i segmenti dell’utente tipo in modo che ogni utente tipo abbia almeno poche centinaia di [ID dispositivo](../../reference/ids-in-aam.md).
* Se le caratteristiche sono basate su [ID multi-dispositivo](../../reference/ids-in-aam.md), puoi racchiuderle in segmenti con [Regole di unione profili](../profile-merge-rules/merge-rules-overview.md) che utilizzano [ID dispositivo](../../reference/ids-in-aam.md), ad esempio [!UICONTROL Device Graph]. Questo assicurerà che ci siano abbastanza [ID dispositivo](../../reference/ids-in-aam.md) da cui l&#39;algoritmo può imparare.
* Consigliamo di scegliere caratteristiche o segmenti semplici per i tuoi utenti tipo, costituiti da 1 a 3 caratteristiche.
* Scegli caratteristiche o segmenti della linea di base con sovrapposizione minima.
* Assicurati di acquisire caratteristiche granulari nelle proprietà digitali.

### Criteri di selezione per il pubblico di Target {#selection-audience}

A seconda del caso d’uso, che desideri classificare gli utenti in tempo reale, in batch o entrambi, scegli un pubblico target ([!UICONTROL trait] o [!UICONTROL segment]) con una popolazione significativa in tempo reale e/o totale. Simile alla selezione dell’utente tipo, consigliamo al pubblico di destinazione [!UICONTROL trait] o [!UICONTROL segment] di avere utenti con profili avanzati (set avanzati di [!UICONTROL traits]).

Quando selezioni il pubblico di destinazione, analizza il tuo caso d’uso e stabilisci quali tipi di ID desideri classificare: [!UICONTROL device IDs] o [!UICONTROL cross-device IDs]. La [!UICONTROL Profile Merge Rule] selezionata al momento della creazione del modello definisce i dati che verranno utilizzati per inserire ogni utente nel predittivo [!UICONTROL segments].

Come best practice, consigliamo di scegliere un [!UICONTROL Profile Merge Rule] con la stessa configurazione del pubblico di destinazione [!UICONTROL Profile Merge Rule] o uno che includa il tipo di profilo (profilo dispositivo o profilo autenticato) del pubblico di destinazione.

### [!UICONTROL Predictive Audiences] Fase di formazione del modello  {#model-training}

Prima di poter classificare il pubblico di prime parti nelle persone giuste, l’algoritmo deve addestrarsi sui dati.

Per ogni tipo di utente definito, l’algoritmo analizza il proprio pubblico rispettivo e valuta qualsiasi attività sulle caratteristiche in tempo reale e/o onboarded per i suoi utenti negli ultimi 30 giorni.
Questo passaggio si svolge una volta ogni 24 ore, per tenere conto dei cambiamenti nel pubblico di prime parti.

### [!UICONTROL Predictive Audiences] Fase di classificazione del modello  {#model-classification}

Per la classificazione del pubblico in tempo reale e in batch, il modello controlla innanzitutto se un utente appartiene al pubblico di destinazione. Se l’utente è idoneo per il pubblico di destinazione e non appartiene ad alcun utente tipo, il modello assegna loro un punteggio di qualificazione personale.

Durante la valutazione dei tipi di pubblico di prime parti e l’assegnazione di punteggi, il modello utilizza il **[!UICONTROL Profile Merge Rule]** predefinito definito nel tuo account. Infine, il visitatore viene classificato nell’utente tipo per il quale ha ricevuto il punteggio più alto.

![grafico predittivo-pubblico](assets/predictive-audiences-graph.png)

## Considerazioni e limitazioni {#considerations}

>[!IMPORTANT]
> Leggi attentamente questa sezione prima di passare alla fase di implementazione.

Durante la configurazione dei modelli [!UICONTROL Predictive Audiences], tieni presente le considerazioni e le limitazioni seguenti:

* Puoi creare fino a 10 modelli [!UICONTROL Predictive Audiences]. 
* Per ogni modello, puoi scegliere fino a 50 caratteristiche/segmenti di base.
* I dati di seconde e terze parti non sono attualmente supportati in [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] esegue la classificazione del pubblico in base alle caratteristiche di prime parti, da tutte le origini dati di prime parti.
* La valutazione del segmento per [!UICONTROL Predictive Audiences] utilizza la **[!UICONTROL Profile Merge Rule]** scelta durante la creazione del modello. Per ulteriori informazioni su [!UICONTROL Profile Merge Rules], consulta la [documentazione](../profile-merge-rules/merge-rules-overview.md) dedicata.
* Alcune caratteristiche e segmenti non sono supportati come linee di base o come tipi di pubblico target. [!UICONTROL Predictive Audiences] i modelli non verranno salvati quando si sceglie uno dei seguenti tipi di pubblico come linee di base o target:
   * Caratteristiche predittive e segmenti creati con caratteristiche predittive;
   * [caratteristiche o segmenti di Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Platform;
   * caratteristiche algoritmiche;
   * Caratteristiche di seconde e terze parti.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] non può essere utilizzato in  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

I segmenti predittivi creati dai modelli [!UICONTROL Predictive Audiences] ereditano i [Controlli sull&#39;esportazione dei dati](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) dalle seguenti origini dati di prime parti:

1. L&#39;origine dati di prime parti scelta durante la creazione del modello.
1. Le origini dati di prime parti del pubblico di destinazione. Nello specifico, i controlli per l’esportazione dei dati di [!UICONTROL traits] o [!UICONTROL segments] che costituiscono il pubblico di destinazione.
1. I [Controlli sull&#39;esportazione dei dati](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) del [!UICONTROL Profile Merge Rule] selezionato per il modello.

I nuovi predittivi [!UICONTROL traits] e [!UICONTROL segments] avranno le stesse restrizioni di privacy dell&#39;unione delle origini dati di prime parti descritte in precedenza.

Le caratteristiche che hanno restrizioni aggiuntive che non fanno parte delle restrizioni di privacy dei segmenti [!UICONTROL Predictive Audiences] verranno escluse dalla fase di formazione e non diventeranno influenti per il modello.

## [!UICONTROL Profile Merge Rules] {#pmr}

A tutti i segmenti predittivi verrà assegnato il [!UICONTROL Profile Merge Rule] selezionato al momento della creazione del modello. Il [!UICONTROL Profile Merge Rule] scelto è importante per i motivi seguenti:

* Definisce i dispositivi e/o i profili autenticati di cui tenere conto quando il modello analizza l’ influente [!UICONTROL traits] al momento della classificazione di un utente in un predittivo [!UICONTROL segment].
* Regola quali tipi [!UICONTROL trait] (a livello di dispositivo o a livello di dispositivo) devono essere utilizzati durante la fase di formazione del modello e visualizzati come influenti [!UICONTROL traits]. Predictive [!UICONTROL segments] sono sottoinsiemi del pubblico di destinazione.
   * Se il pubblico di destinazione è un segmento, ti consigliamo di selezionare lo stesso [!UICONTROL Profile Merge Rule] per il modello assegnato al pubblico di destinazione o un [!UICONTROL Profile Merge Rule] che include il tipo di profilo del pubblico di destinazione.
   * Se il pubblico target è un [!UICONTROL trait], ti consigliamo di selezionare un [!UICONTROL Profile Merge Rule] che può accedere allo stesso tipo di dati della caratteristica del pubblico target (sia i dati del profilo dispositivo che i dati di profilo multi-dispositivo).
* [!UICONTROL Profile Merge Rules] l’utilizzo delle  [!UICONTROL Current Authenticated Profiles]   [!UICONTROL No Device Profile] opzioni e sono supportate solo per la classificazione del pubblico in tempo reale. Per ulteriori informazioni, consulta [Opzioni delle regole di unione profili definite](../profile-merge-rules/merge-rule-definitions.md).

Selezionando un elemento [!UICONTROL Profile Merge Rule] che utilizza sia i dati dei dispositivi che quelli tra dispositivi, si massimizza il numero di [!UICONTROL traits] che possono essere utilizzati per la formazione sui modelli e la classificazione degli utenti nel predittivo [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

Le caratteristiche e i segmenti scelti per le persone e la classificazione del pubblico sono soggetti ad Audience Manager [Role-Based Access Controls](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Gli utenti di Audience Manager possono selezionare solo caratteristiche o segmenti per gli utenti tipo e target, che dispongono dell&#39; [autorizzazione per visualizzare](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
