---
description: Questo rapporto restituisce un conteggio delle frequenze di tutte le informazioni non utilizzate raccolte nell’inventario e inviate ad Audience Manager.
seo-description: Questo rapporto restituisce un conteggio delle frequenze di tutte le informazioni non utilizzate raccolte nell’inventario e inviate ad Audience Manager.
seo-title: Report Segnali non utilizzati
solution: Audience Manager
title: Report Segnali non utilizzati
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
translation-type: tm+mt
source-git-commit: dcc44161df89b44ca1a234070c4afbb0210dc723

---


# Report Segnali non utilizzati{#unused-signals-report}

Questo rapporto restituisce un conteggio delle frequenze di tutte le informazioni non utilizzate raccolte nell’inventario e inviate ad Audience Manager. Per accedere a questo rapporto, passa a **Analytics > Audience Reports (Report audience) > Other Reports (Altri report) > Unused Signals (Segnali** non utilizzati).

>[!NOTE]
>
>Se ricevi il messaggio &quot;Non hai accesso ai report Audience&quot;, contatta il tuo consulente Audience Manager o l&#39;Assistenza clienti per fornirti il rapporto.

![Screenshot del report sui segnali inutilizzati](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Panoramica

Un segnale è costituito dalle informazioni trasmesse dal sito Web [!DNL Audience Manager] sotto forma di coppie [](../../reference/key-value-pairs-explained.md) chiave-valore (ad esempio, `color=blue, price>100, gender=female`ecc.).

I segnali non utilizzati sono dati raccolti ma non mappati a una caratteristica. Il [!UICONTROL Unused Signals] rapporto mostra i dati in una tabella per data, chiave, valore e conteggio delle frequenze. Qualsiasi segnale non mappato trasmesso ad [!DNL Audience Manager] almeno 100 volte al giorno si qualifica per il [!UICONTROL Unused Signals] report.

Leggi questo report per identificare i segnali orfani che possono essere mappati su caratteristiche nuove o esistenti.

>[!NOTE]
>
>Specificate una chiave o un nome di valore nei campi di ricerca per limitare i risultati a record specifici.

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
   <td colname="col1"> <p><b>Uniformità delle caratteristiche o aggiunta di valori correlati a una chiave singola</b> </p> </td> 
   <td colname="col2"> <p>Rivedete il rapporto per tenere conto delle diverse variazioni di valore per un particolare segnale. </p> <p>Ad esempio, supponiamo di avere una caratteristica per lo stato "North Carolina" definito in una coppia chiave-valore come <code> c_state = North Carolina</code>. Il rapporto può essere utile per individuare varianti di nomi e aggiungerle alla caratteristica (ad esempio, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). In alternativa, è possibile individuare le varianti dei nomi con il rapporto e sostituirle con un valore uniforme in tutti i siti. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Crea nuove caratteristiche</b> </p> </td> 
   <td colname="col2"> <p>Rivedete il rapporto per vedere quali nuovi valori vengono passati a una chiave particolare. È possibile creare nuove coppie chiave-valore basate su questi nuovi valori. </p> <p> <p>Nota:  Controllate nel rapporto due volte alla settimana la presenza di valori che si modificano frequentemente (ad esempio, spettacoli, campagne, celebrità, ecc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Trova valori non mappati</b> </p> </td> 
   <td colname="col2"> <p>Esaminare il rapporto per il numero 1. Il numero 1 di un report <span class="wintitle"> Segnali</span> non utilizzati rappresenta un valore null. Non è necessariamente male. Significa semplicemente che a una chiave particolare non è associata una mappatura dei valori. Quando visualizzi un sacco di 1 valori per una variabile importante, chiedi al team del sito di verificare che tutte le pagine siano etichettate correttamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Best practice

Esegui e controlla il [!UICONTROL Unused Signals] rapporto:

* Dopo aver creato una caratteristica o aggiornato le regole di caratteristica. Questo consente di garantire che le caratteristiche e le regole siano impostate correttamente. Il numero 1 nei risultati indica che una nuova caratteristica potrebbe non essere configurata correttamente.
* Bicicletta o mensile. Le revisioni pianificate garantiscono l&#39;aggiornamento delle mappature delle caratteristiche.

>[!NOTE]
>
>Durante la ricerca di valori inutilizzati nel rapporto, tenere presente la seguente particolarità. Esiste una differenza di espressione tra i due esempi seguenti:

* T(v=1 [!UICONTROL AND NOT] (a=23)
* T(v=1 [!UICONTROL AND] (a!=23))
* Entrambi gli esempi mostrano una caratteristica che contiene due coppie chiave-valore v e a. La prima espressione si traduce in: la caratteristica contiene la chiave v con il valore 1 [!UICONTROL AND NOT] la chiave a con il valore 23. La seconda espressione contiene la chiave v con il valore 1 [!UICONTROL AND] la chiave a con il valore [!UICONTROL NOT EQUAL] 23.
* Considerate le due espressioni diverse di cui sopra, ad esempio per cercare i valori che vengono passati alla chiave a con un valore diverso da 23, si otterranno risultati solo nel primo caso, perché i valori per la chiave non sono stati inviati a ALL. [!UICONTROL Unused Signals Report] Nel secondo caso, sono stati inviati valori diversi da 23, quindi la chiave a non è inutilizzata.

## Creazione di tratti in blocco

Contatta il tuo rappresentante per le soluzioni partner se hai bisogno di creare in massa molte caratteristiche basate sui dati ottenuti dal [!UICONTROL Unused Signals] rapporto.
