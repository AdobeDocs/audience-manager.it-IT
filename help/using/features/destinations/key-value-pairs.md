---
description: A [!DNL key-value pair] è costituito da [!DNL related elements]. Una chiave, che è una costante che definisce il set di dati (ad esempio, genere, colore, prezzo) e un valore, che è una variabile che appartiene al set (ad esempio, maschio/femmina, verde, 100). Il Generatore di destinazione invia dati formattati come coppie chiave-valore.
solution: Audience Manager
title: Standard e seriali [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Nozioni di base sulle destinazioni
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 2%

---

# Coppie chiave-valore standard e seriali {#standard-and-serial-key-value-pairs}

Una coppia chiave-valore è costituita da elementi correlati: Una chiave, che è una costante che definisce il set di dati (ad esempio: genere, colore, prezzo) e un valore, che è una variabile che appartiene al set (ad esempio, maschio/femmina, verde, 100). [!UICONTROL Destination Builder] invia dati formattati come coppie chiave-valore.

## Coppie chiave-valore di base {#basic-key-value-pairs}

Completamente formato, un set di base di coppie chiave-valore potrebbe essere simile al seguente:

* `gender = male`
* `color = green`
* `price > 100`

## Coppie chiave-valore standard e seriali {#standard-serial-key-value-pairs}

Le destinazioni accettano dati chiave-valore in formato *`standard`* o *`serialized`* .

* **Coppie chiave-valore standard:** formatta i dati di destinazione in coppie chiave-valore separate. Ogni chiave è indicata esplicitamente, anche quando viene utilizzata di nuovo per definire un valore diverso.
* **Coppie chiave-valore serializzate:** condensa più valori in una singola coppia chiave-valore. In una coppia chiave-valore serializzata, un indicatore speciale separa i valori all&#39;interno dell&#39;insieme chiave-valore.

I valori chiave standard e serializzati possono contenere uno o più valori. Nella tabella seguente sono riportati alcuni esempi di formati chiave standard e seriali.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formattazione </th>
   <th colname="col2" class="entry"> Coppie chiave-valore singole </th>
   <th colname="col3" class="entry"> Coppie chiave-valore multiple </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standard</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Serializzato</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimitatori e separatori {#delimiters-separators}

I caratteri che separano i valori all’interno e tra le chiavi e i valori sono noti come *`delimiters`* e *`separators`*. Questi sono particolarmente importanti quando invii segmenti a una destinazione in un formato seriale. La serializzazione consente di trasmettere più valori con una singola chiave e di combinare coppie chiave-valore. I delimitatori e i separatori sono definiti come segue:

* **Separatore chiave-valore:** separa una chiave e un valore all&#39;interno di una coppia chiave-valore.
* **delimitatore chiave-valore:** separa i set di coppie chiave-valore.
* **Separatore seriale:** separa più valori all&#39;interno di set di coppie chiave-valore serializzate.

## Esempi {#examples}

Con [!UICONTROL Destination Builder] è possibile formattare i dati chiave-valore in diversi modi. Diamo un&#39;occhiata ad alcuni esempi di ciascun tipo.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Esempi di coppia chiave-valore </th> 
   <th colname="col2" class="entry"> Esempio </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Chiave singola standard</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Un set semplice di coppie chiave-valore. L’esempio contiene i seguenti elementi: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Chiave: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Valori: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Separatore: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">delimitatore chiave-valore: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Più coppie chiave-valore</b>  (non seriali) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Set di coppie chiave-valore multiple che trasmettono valori con set chiave-valore separati. L’esempio contiene i seguenti elementi: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Chiavi: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Valori: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Separatore: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">delimitatore chiave-valore: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Chiave singola seriale</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>Set chiave-valore che trasmette più valori con una singola chiave. Poiché questa chiave ha più valori, è nota come coppia chiave-valore serializzata. L’esempio contiene i seguenti elementi: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Chiave: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Valori: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Separatore: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Separatore seriale: punto e virgola </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Più coppie chiave-valore</b>  (seriali) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>Un set di coppie chiave-valore multiple che trasmettono più valori su chiavi separate. L’esempio contiene i seguenti elementi: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Chiavi: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Valori: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Separatore: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Delimitatore: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Separatore seriale: punto e virgola </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Serializzazione delle destinazioni {#destination-serialized}

Una destinazione serializzata combina più caratteristiche in una singola stringa e le invia a una destinazione.

<!-- c_dest_serialized.xml -->

La trasmissione serializzata dei dati aiuta a migliorare l’efficienza perché più caratteristiche si attivano in sequenza, anziché in parallelo. In questo modo il server di destinazione dispone di tempo sufficiente per ricevere, elaborare e restituire i dati prima di rispondere a richieste aggiuntive.

### Destinazioni supportate

In [!DNL Audience Manager] puoi serializzare e inviare dati a praticamente qualsiasi destinazione con cui desideri lavorare. Tuttavia, prima di utilizzare questa funzione, è necessario conoscere la destinazione [!DNL URL] e il punto in cui collocare alcune macro obbligatorie o facoltative. Per ottenere informazioni sul posizionamento delle macro dal partner di destinazione, Per ulteriori informazioni, consulta [Definizione delle macro delle destinazioni](../../features/destinations/destination-macros.md#destination-macros-defined) .
