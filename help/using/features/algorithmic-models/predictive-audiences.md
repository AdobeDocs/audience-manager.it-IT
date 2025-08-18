---
description: Predictive Audiences ti aiuta a classificare tipi di pubblico sconosciuti in utenti tipo distinti in tempo reale utilizzando la scienza dei dati.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Predictive Audiences di Audience Manager
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 3%

---

# Panoramica di [!UICONTROL Predictive Audiences] {#predictive-audiences}

[!UICONTROL Predictive Audiences] ti consente di classificare in tempo reale un pubblico sconosciuto in utenti tipo distinti utilizzando tecniche avanzate di scienza dei dati.

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto e illustra come configurare e utilizzare questa funzione. Niente di ciò che è contenuto in questo documento rappresenta un parere legale. Consulta il tuo consulente legale per ricevere assistenza legale.

In un contesto di marketing, un utente tipo è un segmento di pubblico definito da visitatori, utenti o potenziali acquirenti che condividono un set specifico di caratteristiche come dati demografici, abitudini di navigazione, cronologia acquisti, ecc.

I modelli di [!UICONTROL Predictive Audiences] portano questo concetto a un livello successivo, consentendoti di utilizzare le funzionalità di machine learning di Audience Manager per classificare pubblici sconosciuti in utenti tipo distinti. Audience Manager ti consente di ottenere questo risultato calcolando la propensione del pubblico sconosciuto di prime parti per un set di tipi di pubblico noti di prime parti.

Quando crei un modello [!UICONTROL Predictive Audiences], il primo passaggio consiste nella scelta delle caratteristiche o dei segmenti della linea di base in base ai quali classificare il pubblico di destinazione. Queste caratteristiche o segmenti definiranno i tuoi utenti tipo.

Durante la fase di valutazione, il modello crea un nuovo segmento [!UICONTROL Predictive Audiences] per ogni caratteristica o segmento definito come linea di base. Alla successiva visualizzazione, da parte di Audience Manager, di un visitatore del pubblico di destinazione non classificato per un utente tipo (non idoneo per nessuna delle caratteristiche o dei segmenti della linea di base), il modello [!UICONTROL Predictive Audiences] determinerà a quale dei segmenti predittivi deve appartenere il visitatore e lo aggiungerà al segmento.

È possibile identificare i segmenti predittivi creati dal modello nella pagina [!UICONTROL Segments]. Ogni modello [!UICONTROL Predictive Audiences] ha una propria cartella nella cartella [!UICONTROL Predictive Audiences] ed è possibile visualizzare i segmenti di ogni modello facendo clic sulla cartella dei modelli.

![audience-predittive-segmenti](assets/predictive-audiences-segments.png)

## Casi d&#39;uso {#use-cases}

Per aiutarti a capire meglio come e quando puoi utilizzare [!UICONTROL Predictive Audiences], ecco alcuni casi d&#39;uso che i clienti di Audience Manager possono risolvere utilizzando questa funzione.

### #1 del caso d’uso

In qualità di addetto al marketing in un’azienda di e-commerce, voglio classificare tutti i miei visitatori web e mobili in varie categorie di affinità per il brand, in modo da poter personalizzare la loro esperienza utente.

### #2 del caso d’uso

Come addetto al marketing in una società di media, voglio classificare i visitatori web e mobili non autenticati per generi preferiti, in modo da poter suggerire loro contenuti personalizzati su tutti i canali.

### #3 del caso d’uso

In qualità di inserzionista di una compagnia aerea, voglio essere sicuro di classificare il mio pubblico in base al loro interesse per le destinazioni di viaggio, in modo da potergli fare pubblicità in tempo reale, entro una breve finestra di retargeting.

### #4 del caso d’uso

Come inserzionista, voglio classificare il mio pubblico di prime parti in tempo reale, in modo da poter reagire rapidamente alle notizie di tendenza.

### #5 del caso d’uso

In qualità di esperto di marketing, voglio prevedere in quale fase di percorso del cliente si trovano i visitatori del mio sito web, ad esempio scoperta, coinvolgimento, acquisto o fidelizzazione, in modo da poterli indirizzare di conseguenza.

### #6 del caso d’uso

Come media company, voglio categorizzare il mio pubblico, in modo da poter vendere il mio spazio pubblicitario a prezzi premium, offrendo al contempo ai miei visitatori annunci rilevanti.

## Funzionamento di [!UICONTROL Predictive Audiences] modelli {#how-predictive-audiences-models-work}

Quando si crea un modello [!UICONTROL Predictive Audiences], vengono eseguiti tre passaggi:

1. Innanzitutto, seleziona un minimo di due caratteristiche o due segmenti che definiranno i tuoi utenti tipo.
1. Quindi scegli una caratteristica o un segmento che definisce il pubblico target da classificare.
1. Infine, scegli un nome per il modello, un&#39;origine dati che memorizzerà i segmenti predittivi e un [!UICONTROL Profile Merge Rule] per il modello.

### Criteri di selezione per utenti tipo {#selection-personas}

Puoi scegliere una qualsiasi delle caratteristiche o dei segmenti di prime parti per definire i tuoi utenti tipo. Tuttavia, per risultati ottimali, ecco una serie di best practice consigliate:

* Scegli le caratteristiche o i segmenti dell&#39;utente tipo in modo che ogni utente tipo abbia almeno un centinaio di [ID dispositivo](../../reference/ids-in-aam.md).
* Se le caratteristiche sono basate su [ID multi-dispositivo](../../reference/ids-in-aam.md), puoi racchiuderle in segmenti con [Regole di unione profili](../profile-merge-rules/merge-rules-overview.md) che utilizzano [ID dispositivo](../../reference/ids-in-aam.md), ad esempio [!UICONTROL Device Graph]. In questo modo ci saranno [ID dispositivo](../../reference/ids-in-aam.md) sufficienti da cui l&#39;algoritmo può imparare.
* Consigliamo di scegliere caratteristiche o segmenti semplici per i tuoi utenti tipo, costituiti da 1 a 3 caratteristiche.
* Scegli le caratteristiche o i segmenti della linea di base con sovrapposizione minima.
* Assicurati di acquisire caratteristiche granulari nelle proprietà digitali.

### Criteri di selezione del pubblico di destinazione {#selection-audience}

A seconda del caso d&#39;uso, se si desidera classificare gli utenti in tempo reale, in batch o in entrambi, scegliere un pubblico di destinazione ([!UICONTROL trait] o [!UICONTROL segment]) con una popolazione significativa in tempo reale e/o totale. Analogamente alla selezione dell&#39;utente tipo, è consigliabile che il pubblico di destinazione [!UICONTROL trait] o [!UICONTROL segment] contenga utenti con profili avanzati (set completi di [!UICONTROL traits]).

Quando selezioni il pubblico di destinazione, analizza il tuo caso d&#39;uso e decidi quali tipi di ID vuoi classificare: [!UICONTROL device IDs] o [!UICONTROL cross-device IDs]. Il [!UICONTROL Profile Merge Rule] selezionato durante la creazione del modello definisce i dati che verranno utilizzati per inserire ogni utente nel [!UICONTROL segments] predittivo.

Come best practice, è consigliabile scegliere un [!UICONTROL Profile Merge Rule] con la stessa configurazione del pubblico di destinazione [!UICONTROL Profile Merge Rule] o uno che includa il tipo di profilo (profilo dispositivo o profilo autenticato) del pubblico di destinazione.

### Fase di formazione del modello [!UICONTROL Predictive Audiences] {#model-training}

Prima che l’algoritmo possa classificare il pubblico di prime parti negli utenti tipo giusti, deve addestrarsi sui tuoi dati.

Per ogni utente tipo definito, l’algoritmo analizza il rispettivo pubblico e valuta qualsiasi attività di caratteristiche in tempo reale e/o onboarded per i propri utenti negli ultimi 30 giorni.
Questo passaggio ha luogo una volta ogni 24 ore, per tenere conto delle modifiche nel pubblico di prime parti.

### Fase di classificazione del modello [!UICONTROL Predictive Audiences] {#model-classification}

Per la classificazione in tempo reale e in batch del pubblico, il modello controlla innanzitutto se un utente appartiene al pubblico di destinazione. Se l’utente è idoneo per il pubblico target e non appartiene a nessuno degli utenti tipo, il modello assegna loro un punteggio di qualifica dell’utente tipo.

Durante la valutazione dei tipi di pubblico di prime parti e l&#39;assegnazione dei punteggi, il modello utilizza il **[!UICONTROL Profile Merge Rule]** predefinito definito nel tuo account. Infine, il visitatore viene classificato nella persona per la quale ha ricevuto il punteggio più alto.

![audience-predittive-graph](assets/predictive-audiences-graph.png)

## Considerazioni e limitazioni {#considerations}

>[!IMPORTANT]
> Leggi attentamente questa sezione prima di passare alla fase di implementazione.

Durante la configurazione dei modelli [!UICONTROL Predictive Audiences], tenere presenti le considerazioni e le limitazioni seguenti:

* È possibile creare fino a 10 modelli [!UICONTROL Predictive Audiences].
* Per ogni modello, puoi scegliere fino a 50 caratteristiche/segmenti di base.
* I dati di seconde e terze parti non sono attualmente supportati in [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] esegue la classificazione del pubblico in base alle caratteristiche di prime parti, da tutte le origini dati di prime parti.
* La valutazione del segmento per [!UICONTROL Predictive Audiences] utilizza **[!UICONTROL Profile Merge Rule]** scelto durante la creazione del modello. Per ulteriori informazioni su [!UICONTROL Profile Merge Rules], consulta la [documentazione](../profile-merge-rules/merge-rules-overview.md) dedicata.
* Alcune caratteristiche e segmenti non sono supportati come linee di base o tipi di pubblico target. I modelli [!UICONTROL Predictive Audiences] non verranno salvati quando si sceglie uno dei seguenti tipi di pubblico come linee di base o target:
   * Caratteristiche predittive e segmenti creati con caratteristiche predittive;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) caratteristiche o segmenti;
   * Caratteristiche algoritmiche;
   * Caratteristiche di seconda e terza parte.
* Impossibile utilizzare [!UICONTROL Predictive Audience] [!UICONTROL segments] in [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

I segmenti predittivi creati dai modelli [!UICONTROL Predictive Audiences] ereditano i [Controlli sull&#39;esportazione dei dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) dalle seguenti origini dati di prime parti:

1. L’origine dati di prime parti scelta per la creazione del modello.
1. Le origini dati di prime parti del pubblico di destinazione. In particolare, i controlli di esportazione dei dati di [!UICONTROL traits] o [!UICONTROL segments] che costituiscono il pubblico di destinazione.
1. [Controlli sull&#39;esportazione dei dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) di [!UICONTROL Profile Merge Rule] selezionati per il modello.

I predittivi [!UICONTROL traits] e [!UICONTROL segments] appena creati avranno le stesse restrizioni di privacy dell&#39;unione delle origini dati di prime parti descritte in precedenza.

Le caratteristiche con restrizioni aggiuntive che non fanno parte delle restrizioni sulla privacy del segmento [!UICONTROL Predictive Audiences] saranno escluse dalla fase di formazione e non diventeranno influenti per il modello.

## [!UICONTROL Profile Merge Rules] {#pmr}

A tutti i segmenti predittivi verrà assegnato [!UICONTROL Profile Merge Rule] selezionato durante la creazione del modello. L&#39;elemento [!UICONTROL Profile Merge Rule] scelto è importante per i motivi seguenti:

* Definisce quali dispositivi e/o profili autenticati devono essere presi in considerazione quando il modello analizza l&#39;influente [!UICONTROL traits], al momento della classificazione di un utente in un [!UICONTROL segment] predittivo.
* Determina quali tipi di [!UICONTROL trait] (a livello di dispositivo o multi-dispositivo) devono essere utilizzati durante il passaggio di apprendimento del modello e sono emersi come [!UICONTROL traits] influenti. I [!UICONTROL segments] predittivi sono sottoinsiemi del pubblico di destinazione.
   * Se il pubblico di destinazione è un segmento, è consigliabile selezionare lo stesso [!UICONTROL Profile Merge Rule] per il modello assegnato al pubblico di destinazione o un [!UICONTROL Profile Merge Rule] che include il tipo di profilo del pubblico di destinazione.
   * Se il pubblico di destinazione è un [!UICONTROL trait], è consigliabile selezionare un [!UICONTROL Profile Merge Rule] che possa accedere allo stesso tipo di dati della caratteristica del pubblico di destinazione (dati del profilo dispositivo o dati del profilo multi-dispositivo).
* [!UICONTROL Profile Merge Rules] utilizzando le opzioni [!UICONTROL Current Authenticated Profiles] e [!UICONTROL No Device Profile] sono supportati solo per la classificazione del pubblico in tempo reale. Per ulteriori informazioni, vedere [Opzioni delle regole di unione profili definite](../profile-merge-rules/merge-rule-definitions.md).

La selezione di un [!UICONTROL Profile Merge Rule] che utilizza sia dati dispositivo che dati multi-dispositivo massimizza il numero di [!UICONTROL traits] che può essere utilizzato per l&#39;apprendimento del modello e la classificazione utente nel [!UICONTROL segments] predittivo.

## [!UICONTROL Role-Based Access Controls] {#rbac}

Le caratteristiche e i segmenti scelti per la classificazione degli utenti tipo e del pubblico sono soggetti ai [controlli di accesso basati sul ruolo](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html) di Audience Manager.

Gli utenti di Audience Manager possono selezionare solo caratteristiche o segmenti per utenti tipo e tipi di pubblico target, che dispongono dell&#39;autorizzazione [per visualizzare](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
