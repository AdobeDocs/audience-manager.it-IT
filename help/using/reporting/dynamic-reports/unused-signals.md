---
description: Questo rapporto restituisce un conteggio di frequenza di tutte le informazioni inutilizzate raccolte nel magazzino e inviate all'Audience Manager.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Rapporto sui segnali non utilizzati
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 8fd148df6c19a5d8331faf66c671f91686954a77
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 1%

---

# Rapporto sui segnali non utilizzati{#unused-signals-report}

Questo rapporto restituisce un conteggio di frequenza di tutte le informazioni inutilizzate raccolte nel magazzino e inviate all&#39;Audience Manager. Per accedere a questo report, passa a **Analytics > Report pubblico > Altri report > Segnali non utilizzati**.

>[!NOTE]
>
>Se ricevi il messaggio &quot;Non hai accesso ai report sul pubblico&quot;, contatta il tuo consulente di Audienci Manager o l’Assistenza clienti per eseguire il provisioning del report per te.

![Schermata del report dei segnali non utilizzati](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Panoramica

Un segnale è costituito da informazioni trasmesse dal sito Web a [!DNL Audience Manager] sotto forma di [coppie chiave-valore](../../reference/key-value-pairs-explained.md) (ad esempio, `color=blue, price>100, gender=female`, ecc.).

I segnali non utilizzati sono costituiti da dati raccolti ma non mappati su una caratteristica. Il report [!UICONTROL Unused Signals] mostra i dati in una tabella per data, chiave, valore e conteggio frequenza. Qualsiasi segnale non mappato passato a [!DNL Audience Manager] almeno 100 volte in un giorno è idoneo per il report [!UICONTROL Unused Signals]. I segnali non utilizzati vengono conservati per 45 giorni e quindi eliminati.

Esamina questo rapporto per identificare i segnali orfani che possono essere mappati su caratteristiche nuove o esistenti.

>[!NOTE]
>
>Specifica il nome di una chiave o di un valore nei campi di ricerca per limitare i risultati a record specifici.

## Casi d&#39;uso

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Esempi </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Assicurare l'uniformità delle caratteristiche o aggiungere valori correlati a una singola chiave</b> </p> </td> 
   <td colname="col2"> <p>Rivedi il rapporto per tenere conto delle diverse varianti di valore per un determinato segnale. </p> <p>Ad esempio, supponiamo che tu abbia una caratteristica per lo stato "Carolina del Nord" definita in una coppia chiave-valore come <code> c_state = North Carolina</code>. Il report consente di trovare le varianti di nome e aggiungerle alla caratteristica (ad esempio, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). In alternativa, puoi individuare le varianti di nome nel rapporto e sostituirle con un valore uniforme in tutti i siti. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Crea nuove caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>Esamina il rapporto per vedere quali nuovi valori vengono trasmessi su una particolare chiave. Puoi creare nuove coppie chiave-valore basate su questi nuovi valori. </p> <p> <p>Nota: verifica il rapporto bi-settimanalmente per verificare se sono presenti valori che cambiano frequentemente (ad esempio spettacoli, campagne, celebrità, ecc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Trova valori non mappati</b> </p> </td> 
   <td colname="col2"> <p>Rivedi il rapporto per il numero 1. Il numero 1 in un report <span class="wintitle"> Segnali inutilizzati</span> rappresenta un valore null. Questo non è necessariamente male. Significa semplicemente che a una particolare chiave non è associata alcuna mappatura del valore. Quando vengono visualizzati molti valori pari a 1 per una variabile importante, rivolgiti al team del sito per verificare che a tutte le pagine siano assegnati tag corretti. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best practice

Esegui e controlla il report [!UICONTROL Unused Signals]:

* Dopo aver creato una caratteristica o aggiornato le regole della caratteristica. Questo ti aiuta a garantire che le caratteristiche e le regole siano impostate correttamente. Il numero 1 nei risultati indica che una nuova caratteristica potrebbe non essere configurata correttamente.
* Bi-settimanale o mensile. Le revisioni pianificate consentono di garantire che le mappature delle caratteristiche siano aggiornate.

>[!NOTE]
>
>Quando cerchi i valori non utilizzati nel rapporto, considera le seguenti particolarità. C&#39;è una differenza di espressione tra i due esempi seguenti:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23)
* Entrambi gli esempi mostrano una caratteristica che contiene due coppie chiave-valore v e a. La prima espressione si traduce in: la caratteristica contiene la chiave v con valore 1 [!UICONTROL AND NOT] la chiave a con valore 23. La seconda espressione contiene la chiave v con valore 1 [!UICONTROL AND] la chiave a con valore [!UICONTROL NOT EQUAL] 23.
* Considerando le due diverse espressioni di cui sopra, supponiamo che tu cerchi in [!UICONTROL Unused Signals Report] i valori che vengono passati sulla chiave a con qualsiasi valore diverso da 23, otterrai risultati solo nel primo caso perché i valori per la chiave non sono stati inviati AFFATTO. Nel secondo caso, sono stati inviati valori diversi da 23 in modo che la chiave a non sia inutilizzata.

## Creazione di caratteristiche in blocco

Contatta il tuo rappresentante di soluzioni dei partner se devi creare in blocco molte caratteristiche in base ai dati ottenuti dal report [!UICONTROL Unused Signals].
