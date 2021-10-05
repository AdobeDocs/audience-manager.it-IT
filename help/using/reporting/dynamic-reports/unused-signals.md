---
description: Questo rapporto restituisce un conteggio di frequenza di tutte le informazioni non utilizzate raccolte nell’inventario e inviate all’Audience Manager.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Rapporto su segnali non utilizzati
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 8fd148df6c19a5d8331faf66c671f91686954a77
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---

# Rapporto su segnali non utilizzati{#unused-signals-report}

Questo rapporto restituisce un conteggio di frequenza di tutte le informazioni non utilizzate raccolte nell’inventario e inviate all’Audience Manager. Per accedere a questo rapporto, passa a **Analytics > Rapporti sul pubblico > Altri rapporti > Segnali non utilizzati**.

>[!NOTE]
>
>Se ricevi il messaggio &quot;Non hai accesso ai rapporti sul pubblico&quot;, contatta il tuo consulente Audience Manager o l’Assistenza clienti per fornirti il rapporto.

![Screenshot del report sui segnali non utilizzati](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Panoramica

Un segnale è un&#39;informazione del sito web trasmessa a [!DNL Audience Manager] sotto forma di [coppie chiave-valore](../../reference/key-value-pairs-explained.md) (ad esempio, `color=blue, price>100, gender=female`, ecc.).

I segnali non utilizzati sono costituiti da dati raccolti ma non mappati a una caratteristica. Il rapporto [!UICONTROL Unused Signals] mostra i dati in una tabella per data, chiave, valore e conteggio di frequenza. Qualsiasi segnale non mappato trasmesso a [!DNL Audience Manager] almeno 100 volte al giorno è idoneo per il rapporto [!UICONTROL Unused Signals]. I segnali inutilizzati vengono memorizzati per 45 giorni e quindi scartati.

Rivedi questo rapporto per identificare i segnali orfani che possono essere mappati su caratteristiche nuove o esistenti.

>[!NOTE]
>
>Specifica un nome di chiave o di valore nei campi di ricerca per limitare i risultati a record specifici.

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
   <td colname="col1"> <p><b>Assicurare l’uniformità delle caratteristiche o aggiungere valori correlati a una singola chiave</b> </p> </td> 
   <td colname="col2"> <p>Rivedi il rapporto per tenere conto di diverse variazioni di valore per un particolare segnale. </p> <p>Ad esempio, supponiamo che tu abbia una caratteristica per lo stato "North Carolina" definita in una coppia chiave-valore come <code> c_state = North Carolina</code>. Il rapporto può essere utile per trovare le varianti di nome e aggiungerle alla caratteristica (ad esempio, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). In alternativa, è possibile individuare le varianti dei nomi con il rapporto e sostituirle con un valore uniforme per tutti i siti. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Creare nuove caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>Rivedi il rapporto per vedere quali nuovi valori vengono passati su una particolare chiave. È possibile creare nuove coppie chiave-valore in base a questi nuovi valori. </p> <p> <p>Nota:  Controlla il rapporto due volte alla settimana per i valori che cambiano frequentemente (ad esempio, spettacoli, campagne, celebrità, ecc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Trova valori non mappati</b> </p> </td> 
   <td colname="col2"> <p>Rivedere il rapporto per il numero 1. Il numero 1 in un report <span class="wintitle"> Segnali inutilizzati</span> rappresenta un valore null. Questo non è necessariamente negativo. Significa semplicemente che a una particolare chiave non è associata una mappatura dei valori. Quando visualizzi molti 1 valori per una variabile importante, rivolgiti al team del sito per verificare che tutte le pagine siano state contrassegnate correttamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best practice

Esegui e controlla il rapporto [!UICONTROL Unused Signals]:

* Dopo aver creato una caratteristica o aggiornato le regole della caratteristica. Questo consente di garantire che le caratteristiche e le regole siano impostate correttamente. Il numero 1 nei risultati indica che una nuova caratteristica potrebbe non essere configurata correttamente.
* Due volte al mese. Le revisioni pianificate garantiscono che le mappature delle caratteristiche siano aggiornate.

>[!NOTE]
>
>Quando cerchi valori non utilizzati nel rapporto, tieni presente quanto segue. C&#39;è una differenza di espressione tra i due esempi seguenti:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Entrambi gli esempi mostrano una caratteristica che contiene due coppie chiave-valore v e a. La prima espressione si traduce in: la caratteristica contiene la chiave v con il valore 1 [!UICONTROL AND NOT] la chiave a con il valore 23. La seconda espressione contiene la chiave v con il valore 1 [!UICONTROL AND] la chiave a con il valore [!UICONTROL NOT EQUAL] 23.
* Considerando le due diverse espressioni di cui sopra, supponiamo che tu cerchi nel [!UICONTROL Unused Signals Report] i valori che vengono passati alla chiave a con un valore diverso da 23, otterrai solo risultati nel primo caso perché i valori per la chiave non sono stati inviati A TUTTO. Nel secondo caso, sono stati inviati valori diversi da 23, pertanto la chiave a non è inutilizzata.

## Creazione di tratti in blocco

Contatta il tuo rappresentante di soluzioni dei partner per creare in massa un sacco di caratteristiche in base ai dati ottenuti dal rapporto [!UICONTROL Unused Signals] .
