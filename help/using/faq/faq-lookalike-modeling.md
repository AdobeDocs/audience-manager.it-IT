---
description: La modellazione lookalike consente di scoprire tipi di pubblico nuovi e unici tramite l’analisi automatizzata dei dati. Questo articolo fornisce le risposte alle domande più frequenti.
seo-description: La modellazione lookalike consente di scoprire tipi di pubblico nuovi e unici tramite l’analisi automatizzata dei dati. Questo articolo fornisce le risposte alle domande più frequenti.
seo-title: Domande frequenti sulla modellazione lookalike
solution: Audience Manager
title: Domande frequenti sulla modellazione lookalike
feature: Modelli algoritmici
source-git-commit: cf9368d4690b61066646054543cc60d390eea021
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Domande frequenti sulla modellazione lookalike

## Panoramica {#overview}

Questo articolo fornisce le risposte alle domande più frequenti su [!UICONTROL Look-Alike Modeling].

## Domande {#questions}

**Perché ottengo un  [!UICONTROL Accuracy & Reach] grafico piatto?**

Un grafico [!UICONTROL Accuracy & Reach] piatto significa che quasi tutti gli utenti hanno ricevuto lo stesso punteggio dal modello. Questo può accadere quando includi le caratteristiche del visitatore del sito nelle origini dati su cui hai eseguito il modello. Per evitare questo problema, rimuovere il tratto generico dall&#39;input del modello durante il passaggio di creazione del modello, utilizzando il campo [!UICONTROL Exclusions].

 

**Perché alcune delle mie caratteristiche più influenti hanno un pubblico molto piccolo?**

L’algoritmo seleziona caratteristiche altamente correlate alla caratteristica di base. Ad esempio, se una data caratteristica ha una sovrapposizione 100% con la caratteristica di base, avrà un peso molto elevato, anche se il numero di utenti in quella caratteristica è ridotto.

 

**Perché il mio modello non viene eseguito/rieseguito?**

I modelli che hanno prodotto risultati continueranno a essere eseguiti solo se hai creato almeno una caratteristica algoritmica attiva e la hai mappata a un segmento attivo e a una destinazione.

 

**Perché il mio modello non ha prodotto alcun risultato?**

Ciò è in genere causato dalla mancata sovrapposizione di caratteristiche significative tra la popolazione della linea di base e la popolazione nelle origini dati selezionate.

 

**Esiste un consiglio sulla caratteristica o sulle dimensioni del segmento della linea di base?**

Poche migliaia di utenti dovrebbero essere sufficienti per eseguire il modello su, dato che vi è una significativa sovrapposizione delle caratteristiche tra la popolazione di base e la popolazione nelle origini dati selezionate. [!UICONTROL Look-Alike Modeling] produce risultati più precisi, più grande è la linea di base.

 

**Quali origini dati di terze parti devo scegliere per il mio modello?**

Utilizza le origini dati che hanno almeno una certa sovrapposizione con la caratteristica/segmento di base, ma allo stesso tempo inserisci altri utenti. È inoltre necessario considerare il costo associato a ciascun feed di dati. I modelli di costo e prezzo variano tra i fornitori di dati in [!UICONTROL Audience Marketplace].

 

**È costoso utilizzare dati di terze parti per la modellazione?**

Dipende dal modello di determinazione dei prezzi del feed di dati selezionato. Alcuni feed consentono la modellazione senza costi, mentre altri vi addebitano una tariffa. Per ulteriori informazioni, consulta [Fatturazione per gli acquirenti di feed di dati](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) .

 

**Quanti modelli/caratteristiche posso creare?**

Attualmente, puoi creare fino a 20 modelli algoritmici e 50 caratteristiche algoritmiche.

 

**Qual è la frequenza di aggiornamento della popolazione dei tratti algoritmici e di formazione del modello?**

Il modello si riallena una volta ogni 8 giorni, aggiornando la popolazione delle caratteristiche algoritmiche.