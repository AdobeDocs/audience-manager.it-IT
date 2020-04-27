---
description: Le audience predittive ti aiutano a classificare audience sconosciute in persone distinte in tempo reale, utilizzando la scienza dei dati.
seo-description: Le audience predittive ti aiutano a classificare audience sconosciute in persone distinte in tempo reale, utilizzando la scienza dei dati.
seo-title: Predictive Audiences Panoramica
solution: Audience Manager
title: Audience Manager Predictive
translation-type: tm+mt
source-git-commit: 74a5de961b2f9ab6afa2caf998ba1100d40cc93a

---


# Predictive Audiences Panoramica {#predictive-audiences}

[!UICONTROL Predictive Audiences] consente di classificare un pubblico sconosciuto in persone distinte, in tempo reale, utilizzando tecniche avanzate di scienza dei dati.

>[!IMPORTANT]
>Questo articolo contiene la documentazione del prodotto destinata a guidarvi nella configurazione e nell&#39;utilizzo di questa funzione. Nulla di ciò è contenuto nella consulenza legale. Consulta il tuo consulente legale per ottenere assistenza legale.

In un contesto di marketing, un soggetto è un segmento di pubblico definito da visitatori, utenti o potenziali acquirenti, che condividono un set specifico di caratteristiche, come demografiche, abitudini di navigazione, cronologia acquisti, ecc.

[!UICONTROL Predictive Audiences] i modelli fanno di questo concetto un passo avanti, consentendovi di utilizzare le funzionalità di machine learning di Audience Manager per classificare audience sconosciute in persone distinte. Audience Manager consente di ottenere questo risultato calcolando la propensione dell&#39;audience di prime parti sconosciuta per un set di audience di prime parti note.

Quando create un [!UICONTROL Predictive Audiences] modello, il primo passo consiste nella scelta delle caratteristiche o dei segmenti di base per i quali desiderate classificare il pubblico di destinazione. Queste caratteristiche o segmenti definiranno le tue personalità.

Durante la fase di valutazione, il modello crea un nuovo [!UICONTROL Predictive Audiences] segmento per ogni caratteristica o segmento definito come linea di base. La volta successiva che Audience Manager visualizzerà un visitatore dal pubblico di destinazione che non è classificato per un soggetto (non era idoneo per nessuna delle caratteristiche o dei segmenti di base), il [!UICONTROL Predictive Audiences] modello determinerà a quale dei segmenti predittivi dovrebbe appartenere il visitatore e aggiungerà il visitatore a tale segmento.

Potete identificare i segmenti predittivi creati dal modello, nella [!UICONTROL Segments] pagina. Ogni [!UICONTROL Predictive Audiences] modello ha una propria cartella sotto la [!UICONTROL Predictive Audiences] cartella, e potete vedere i segmenti di ciascun modello facendo clic sulla cartella del modello.

![previsione-audience-segmenti](assets/predictive-audiences-segments.png)

## Casi d&#39;uso {#use-cases}

Per aiutarti a capire meglio come e quando potresti usare [!UICONTROL Predictive Audiences], ecco alcuni casi d’uso che i clienti di Audience Manager possono risolvere utilizzando questa funzione.

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

## Funzionamento dei modelli di audience predittivi

Quando create un [!UICONTROL Predictive Audiences] modello, potete eseguire tre passaggi:

1. Innanzitutto, selezionate almeno due caratteristiche o due segmenti che definiranno le vostre personalità.
1. Quindi, scegli una caratteristica o un segmento che definisca il pubblico di destinazione da classificare.
1. Infine, è possibile scegliere un nome per il modello e selezionare un&#39;origine dati in cui memorizzare i segmenti predittivi.

### Criteri di selezione per le persone {#selection-personas}

Puoi scegliere una qualsiasi delle caratteristiche o dei segmenti di prime parti per definire le tue personalità. Tuttavia, per ottenere risultati ottimali, si consiglia di seguire una serie di procedure ottimali:

* Scegli le caratteristiche personali o i segmenti in modo che ogni persona abbia almeno un centinaio di ID [](../../reference/ids-in-aam.md)dispositivo.
* Se le caratteristiche sono basate su ID [](../../reference/ids-in-aam.md)cross-device, puoi racchiudere i segmenti con le regole [di unione](../profile-merge-rules/merge-rules-overview.md) profilo che utilizzano gli ID [](../../reference/ids-in-aam.md)dispositivo, ad esempio [!UICONTROL Device Graph]. In questo modo, l&#39;algoritmo potrà acquisire una quantità sufficiente di ID [](../../reference/ids-in-aam.md) dispositivo.
* È consigliabile scegliere caratteristiche o segmenti semplici per le persone, composti da 1 a 3 caratteristiche.
* Scegliete caratteristiche o segmenti della linea di base con sovrapposizione minima.
* Accertatevi di acquisire caratteristiche granulari nelle proprietà digitali.

### Criteri di selezione per l&#39;audience di Target {#selection-audience}

Simile alla selezione di persona, è necessario scegliere la caratteristica o il segmento che definisce il pubblico di destinazione in modo che abbia utenti in tempo reale con set di caratteristiche avanzate, da classificare nel soggetto giusto.

### Fase di formazione predittiva sul modello di pubblico {#model-training}

Prima che l&#39;algoritmo possa classificare il pubblico di prime parti nelle persone giuste, deve formarsi sui dati.

Per ogni persona definita dall&#39;utente, l&#39;algoritmo analizza il relativo pubblico e valuta qualsiasi attività relativa alle caratteristiche in tempo reale e/o registrate per i relativi utenti negli ultimi 30 giorni.
Questo passaggio ha luogo una volta ogni 24 ore, per tenere conto dei cambiamenti nel pubblico di prime parti.

### Fase di classificazione predittiva del modello di pubblico {#model-classification}

Quando un visitatore che fa parte del pubblico di destinazione viene visto in tempo reale, il modello valuta se il visitatore fa parte delle persone definite. Per ogni visitatore che non appartiene ad alcuna persona, il modello assegna un punteggio di qualifica personale.

Durante la valutazione dei tipi di pubblico di prime parti e l&#39;assegnazione dei punteggi, il modello utilizza il valore predefinito **[!UICONTROL Profile Merge Rule]** definito nel vostro account. Infine, il visitatore viene classificato nella persona per la quale ha ricevuto il punteggio più alto.

![grafico predittivo-pubblico](assets/predictive-audiences-graph.png)

## Considerazioni e limitazioni {#considerations}

>[!IMPORTANT]
> Leggi attentamente questa sezione prima di passare alla fase di implementazione.

Durante la configurazione dei [!UICONTROL Predictive Audiences] modelli, tenere presente le considerazioni e le limitazioni seguenti:

* Potete creare fino a 10 [!UICONTROL Predictive Audiences] modelli.
* Per ciascun modello, potete scegliere fino a 50 tratti/segmenti di base.
* I dati di seconda e terza parte non sono attualmente supportati in [!UICONTROL Predictive Audiences].
* La classificazione dell&#39;audience viene effettuata solo per audience di prime parti in tempo reale. La classificazione dell&#39;audience di prime parti caricata potrebbe essere supportata in un aggiornamento futuro.
   >[!IMPORTANT]
   > Al momento, i segmenti [!UICONTROL Total Segment Population] predittivi sono visualizzati come 0 e i trasferimenti [di dati in uscita](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) batch non sono supportati per i tipi di pubblico predittivo. Questo comportamento verrà modificato in un aggiornamento futuro.
* [!UICONTROL Predictive Audiences] esegue la classificazione dell&#39;audience in base alle caratteristiche di prime parti, da tutte le origini dati di prime parti.
* La valutazione del segmento per [!UICONTROL Predictive Audiences] utilizza l’impostazione predefinita **[!UICONTROL Profile Merge Rule]** definita nel vostro account. Per ulteriori informazioni, [!UICONTROL Profile Merge Rules] consulta la [documentazione](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html)dedicata.
* Alcune caratteristiche e segmenti non sono supportati come linee di base o come audience di destinazione. [!UICONTROL Predictive Audiences] i modelli non verranno salvati quando si sceglie uno dei seguenti tipi di base o di pubblico target:
   * Caratteristiche predittive e segmenti creati con caratteristiche predittive;
   * [Caratteristiche o segmenti della piattaforma](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Adobe Experience;
   * caratteristiche algoritmiche;
   * Caratteristiche di seconda e terza parte.

## Controlli sull&#39;esportazione dei dati{#dec}

I segmenti predittivi creati dai [!UICONTROL Predictive Audiences] modelli ereditano i controlli [di esportazione dei](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) dati dalle seguenti origini dati di prime parti:

1. L&#39;origine dati di prime parti scelta al momento della creazione del modello.
1. Le origini dati di prime parti del pubblico di destinazione. In modo specifico, i controlli di esportazione dei dati relativi alle caratteristiche o ai segmenti che costituiscono il pubblico di destinazione.

Le caratteristiche predittive e i segmenti appena creati avranno le stesse restrizioni di privacy dell&#39;unione delle origini dati di prime parti descritte in precedenza.

Le caratteristiche con restrizioni aggiuntive che non fanno parte delle restrizioni sulla privacy del [!UICONTROL Predictive Audiences] segmento saranno escluse dalla fase di formazione e non diventeranno influenti per il modello.

## Controlli di accesso basati sul ruolo{#rbac}

Le caratteristiche e i segmenti scelti per le persone e la classificazione dell&#39;audience sono soggetti ai controlli [di accesso basati sul](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)ruolo di Audience Manager.

Gli utenti di Audience Manager possono selezionare solo caratteristiche o segmenti per le persone e i tipi di pubblico di destinazione, che dispongono dell&#39; [autorizzazione per visualizzare](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
