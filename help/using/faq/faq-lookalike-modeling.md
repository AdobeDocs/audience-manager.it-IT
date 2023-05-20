---
description: La modellazione lookalike consente di scoprire tipi di pubblico nuovi e univoci tramite l’analisi automatizzata dei dati. Questo articolo fornisce le risposte alle domande più frequenti.
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: Domande frequenti sulla modellazione lookalike
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Domande frequenti sulla modellazione lookalike

## Panoramica {#overview}

Questo articolo fornisce le risposte alle domande più frequenti su [!UICONTROL Look-Alike Modeling].

## Domande {#questions}

**Perché sto per avere un appartamento? [!UICONTROL Accuracy & Reach] grafico?**

Un piatto [!UICONTROL Accuracy & Reach] grafico significa che quasi ogni utente ha ricevuto lo stesso punteggio dal modello. Questo può accadere quando includi la caratteristica visitatore del sito nelle origini dati su cui hai eseguito il modello. Per evitare questo problema, rimuovete la caratteristica generica dall&#39;input del modello durante il passaggio di creazione del modello, utilizzando [!UICONTROL Exclusions] campo.

 

**Perché alcune delle mie caratteristiche più influenti hanno un pubblico molto piccolo?**

L’algoritmo seleziona caratteristiche altamente correlate alla caratteristica linea di base. Ad esempio, se una data caratteristica ha una sovrapposizione del 100% con la caratteristica linea di base, avrà un peso molto alto, anche se il numero di utenti in quella caratteristica è basso.

 

**Perché il modello non è stato eseguito/eseguito di nuovo?**

I modelli che hanno prodotto risultati continueranno a essere eseguiti solo se hai creato almeno una caratteristica algoritmica attiva e l’hai mappata a un segmento attivo e a una destinazione.

 

**Perché il mio modello non ha prodotto alcun risultato?**

Ciò è in genere causato dal fatto di non avere sovrapposizioni di caratteristiche significative tra la popolazione al basale e la popolazione nelle origini dati selezionate.

 

**Esistono consigli sulla caratteristica o dimensione del segmento della linea di base?**

Alcune migliaia di utenti dovrebbero essere sufficienti per eseguire il modello su, dato che vi è una significativa sovrapposizione di caratteristiche tra la popolazione linea di base e la popolazione nelle origini dati selezionate. [!UICONTROL Look-Alike Modeling] produce risultati più precisi, maggiore è la linea di base.

 

**Quali origini dati di terze parti devo scegliere per il mio modello?**

Utilizza origini dati che hanno almeno una sovrapposizione con la caratteristica/segmento linea di base, ma allo stesso tempo includono ulteriori utenti. È inoltre necessario considerare il costo associato a ciascun feed di dati. I modelli di costi e prezzi variano tra i fornitori di dati in [!UICONTROL Audience Marketplace].

 

**L’utilizzo di dati di terze parti per la modellazione è costoso?**

Dipende dal modello di determinazione prezzi del feed dati selezionato. Alcuni feed consentono la modellazione a costo zero, mentre altri ti addebitano una tariffa. Consulta [Fatturazione per gli acquirenti di feed di dati](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) per i dettagli.

 

**Quanti modelli/caratteristiche posso creare?**

Attualmente, puoi creare fino a 20 modelli algoritmici e 50 caratteristiche algoritmiche.

 

**Qual è la frequenza di aggiornamento della popolazione di caratteristiche algoritmiche e di apprendimento del modello?**

Il modello viene riaddestrato una volta ogni 8 giorni, insieme all’aggiornamento della popolazione delle caratteristiche algoritmiche.
