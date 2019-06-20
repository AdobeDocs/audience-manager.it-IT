---
description: Questo rapporto restituisce un conteggio di frequenza di tutte le informazioni inutilizzate raccolte nell'inventario e inviate ad Audience Manager.
seo-description: Questo rapporto restituisce un conteggio di frequenza di tutte le informazioni inutilizzate raccolte nell'inventario e inviate ad Audience Manager.
seo-title: Report segnali inutilizzati
solution: Audience Manager
title: Report segnali inutilizzati
uuid: 04334 a 5 c -3 e 21-44 db-b 971-0 b 4457685 e 9 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Report segnali inutilizzati{#unused-signals-report}

Questo rapporto restituisce un conteggio di frequenza di tutte le informazioni inutilizzate raccolte nell&#39;inventario e inviate ad Audience Manager.

<!-- 

c_unused_signals.xml

 -->

## Report segnali inutilizzati

Un segnale è informazioni del sito Web trasmesso sotto [!DNL Audience Manager] forma di coppie [chiave-valore](../../reference/key-value-pairs-explained.md) (ad es., `color=blue, price>100, gender=female`ecc.).

I segnali inutilizzati sono costituiti da dati raccolti ma non mappati su una caratteristica. [!UICONTROL Unused Signals] Il rapporto mostra i dati in una tabella per data, chiave, valore e conteggio delle frequenze. Qualsiasi segnale non mappato trasmesso a [!DNL Audience Manager] almeno 100 volte in un giorno qualifica per [!UICONTROL Unused Signals] il report.

Leggi questo rapporto per identificare i segnali isolati che possono essere mappati alle caratteristiche nuove o esistenti.

>[!NOTE]
>
>Specificate un nome o un nome di valore nei campi di ricerca per limitare i risultati a record specifici.

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
   <td colname="col1"> <p><b>Assicurarsi l'uniformità delle caratteristiche o aggiungere valori correlati a una singola chiave</b> </p> </td> 
   <td colname="col2"> <p>Esaminate il report per ottenere variazioni di valore diverse per un particolare segnale. </p> <p>Ad esempio, supponiamo che sia presente una caratteristica per lo stato "North Carolina" definito in una coppia chiave-valore come <code> c_ state = North Carolina</code>. Il rapporto può facilitare la ricerca delle varianti dei nomi e aggiungerli alla caratteristica (ad es <code> . c_ state = North Carolina, NC, N.C.C., ncarolina</code>). In alternativa, è possibile denominare le varianti del nome con il rapporto e sostituire quelle con un valore uniforme in tutti i siti. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Crea nuove caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>Rivedete il report per vedere i nuovi valori passati su una particolare chiave. Potreste decidere di creare nuove coppie chiave-valore basate su questi nuovi valori. </p> <p> <p>Nota: Controllate il report bisettimanale per i valori che si modificano frequentemente (ad es. mostra, campagne, celebrazioni, ecc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Trova valori non mappati</b> </p> </td> 
   <td colname="col2"> <p>Esaminate il report per il numero 1. Il numero 1 in un <span class="wintitle"> rapporto Segnali</span> inutilizzati rappresenta un valore null. Questo non è necessariamente un errore. Ciò significa semplicemente che una chiave particolare non ha una mappatura valore associata. Quando vengono visualizzati numerosi valori di una variabile importante, consultate il team del sito per verificare che tutte le pagine siano contrassegnate correttamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best practice

Eseguite e verificate il [!UICONTROL Unused Signals] rapporto:

* Dopo aver creato una caratteristica o una regola di aggiornamento. In questo modo le caratteristiche e le regole vengono configurate correttamente. Il numero 1 nei risultati indica che una nuova caratteristica potrebbe non essere configurata correttamente.
* Bicubico o mensile Le revisioni pianificate garantiscono che le mappature delle caratteristiche siano aggiornate.

>[!NOTE]
>
>Durante la ricerca di valori non utilizzati nel rapporto, prendete in considerazione la seguente particolarità. Esiste una differenza nell&#39;espressione tra i due esempi seguenti:

* T (v = 1 [!UICONTROL AND NOT] (a = 23))
* T (v = 1 [!UICONTROL AND] (a!=23))
* Entrambi gli esempi mostrano una caratteristica che contiene due coppie chiave-valore e a. La prima espressione traduce: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. La seconda espressione contiene la chiave v con il valore 1 [!UICONTROL AND] la chiave a con il valore [!UICONTROL NOT EQUAL] 23.
* Considerando le due espressioni diverse qui sopra, supponiamo che effettuiate ricerche nei [!UICONTROL Unused Signals Report] valori che vengono passati alla chiave a un valore diverso da 23; otterrete risultati nel primo caso perché i valori per la chiave non sono stati inviati ALL. Nel secondo caso, sono stati inviati valori diversi da 23, pertanto la chiave a non è utilizzata.

## Creazione di caratteristiche in blocco

Contatta il rappresentante Soluzioni Partner se devi creare in massa numerose caratteristiche in base ai dati ottenuti dal [!UICONTROL Unused Signals] report.
