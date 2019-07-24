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


# Unused Signals Report{#unused-signals-report}

Questo rapporto restituisce un conteggio di frequenza di tutte le informazioni inutilizzate raccolte nell'inventario e inviate ad Audience Manager.

<!-- 

c_unused_signals.xml

 -->

## Report segnali inutilizzati

A signal is information from your website passed in to [!DNL Audience Manager] in the form of [key-value pairs](../../reference/key-value-pairs-explained.md) (e.g., `color=blue, price>100, gender=female`, etc.).

I segnali inutilizzati sono costituiti da dati raccolti ma non mappati su una caratteristica. [!UICONTROL Unused Signals] Il rapporto mostra i dati in una tabella per data, chiave, valore e conteggio delle frequenze. Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

Leggi questo rapporto per identificare i segnali isolati che possono essere mappati alle caratteristiche nuove o esistenti.

>[!NOTE]
>
>Specificate un nome o un nome di valore nei campi di ricerca per limitare i risultati a record specifici.

## Casi d'uso

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
   <td colname="col2"> <p>Esaminate il report per ottenere variazioni di valore diverse per un particolare segnale. </p> <p>For example, say you have a trait for the state "North Carolina" defined in a key-value pair as <code> c_state = North Carolina</code>. The report can help you find name variants and add those to the trait (e.g., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). In alternativa, è possibile denominare le varianti del nome con il rapporto e sostituire quelle con un valore uniforme in tutti i siti. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Crea nuove caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>Rivedete il report per vedere i nuovi valori passati su una particolare chiave. Potreste decidere di creare nuove coppie chiave-valore basate su questi nuovi valori. </p> <p> <p>Nota: Controllate il report bisettimanale per i valori che si modificano frequentemente (ad es. mostra, campagne, celebrazioni, ecc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Trova valori non mappati</b> </p> </td> 
   <td colname="col2"> <p>Esaminate il report per il numero 1. The number 1 in an <span class="wintitle"> Unused Signals</span> report represents a null value. Questo non è necessariamente un errore. Ciò significa semplicemente che una chiave particolare non ha una mappatura valore associata. Quando vengono visualizzati numerosi valori di una variabile importante, consultate il team del sito per verificare che tutte le pagine siano contrassegnate correttamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best practice

Run and check the [!UICONTROL Unused Signals] report:

* Dopo aver creato una caratteristica o una regola di aggiornamento. In questo modo le caratteristiche e le regole vengono configurate correttamente. Il numero 1 nei risultati indica che una nuova caratteristica potrebbe non essere configurata correttamente.
* Bicubico o mensile Le revisioni pianificate garantiscono che le mappature delle caratteristiche siano aggiornate.

>[!NOTE]
>
>Durante la ricerca di valori non utilizzati nel rapporto, prendete in considerazione la seguente particolarità. Esiste una differenza nell'espressione tra i due esempi seguenti:

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let's say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you'll only obtain results in the first case because values for key were not sent AT ALL. Nel secondo caso, sono stati inviati valori diversi da 23, pertanto la chiave a non è utilizzata.

## Creazione di caratteristiche in blocco

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.
