---
description: Una coppia chiave-valore è costituita da elementi correlati A, che è una costante che definisce il set di dati (ad es. genere, colore, prezzo) e un valore, ovvero una variabile che appartiene al set (ad es. uomo/donna, verde, 100). Il Generatore di destinazione invia dati formattati come coppie chiave-valore.
seo-description: Una coppia chiave-valore è costituita da elementi correlati A, che è una costante che definisce il set di dati (ad es. genere, colore, prezzo) e un valore, ovvero una variabile che appartiene al set (ad es. uomo/donna, verde, 100). Il Generatore di destinazione invia dati formattati come coppie chiave-valore.
seo-title: Coppie chiave-valore standard e chiave di serie
solution: Audience Manager
title: Coppie chiave-valore standard e chiave di serie
uuid: 43789419-5 b 3 f -4 e 62-b 2 e 0-2722340 bdd 41
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Standard and Serial Key-Value Pairs {#standard-and-serial-key-value-pairs}

Una coppia chiave-valore consiste in elementi correlati: Una chiave, ovvero una costante che definisce il set di dati (ad es. genere, colore, prezzo) e un valore, ovvero una variabile che appartiene al set (ad es. uomo/donna, verde, 100). [!UICONTROL Destination Builder] invia dati formattati come coppie chiave-valore.

## Basic Key-Value Pairs {#basic-key-value-pairs}

Completamente formattato, un set di base della coppia chiave-valore potrebbe essere:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serial Key-Value Pairs {#standard-serial-key-value-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format.

* **Coppie chiave-valore standard:** Formatta i dati di destinazione in coppie chiave-valore separate. Ogni chiave viene definita esplicitamente, anche quando viene utilizzata di nuovo per definire un altro valore.
* **Coppie chiave-valore serializzate:** Condensa più valori in una singola coppia chiave-valore. In una coppia chiave-valore serializzata, un indicatore speciale separa i valori all'interno del set chiave-valore.

Valori chiave standard e serializzati possono contenere valori singoli o multipli. Nella tabella seguente sono riportati alcuni esempi di formati chiave-valore standard e di serie.

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
   <td colname="col2"> <p> <code> x = 1; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1; 2 &amp; y = 3; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimiters and Separators {#delimiters-separators}

The characters that separate values within and between keys and values are known as *`delimiters`* and *`separators`*. Sono particolarmente importanti quando invii segmenti a una destinazione in un formato di serie. La serializzazione consente di trasmettere più valori con una singola chiave e combinare coppie chiave-valore. I delimitatori e i separatori sono definiti come segue:

* **Separatore chiave chiave:** Separa una chiave e un valore all'interno di una coppia chiave-valore.
* **Delimitatore chiave chiave:** Separa i set di coppie chiave-valore.
* **Separatore di serie:** Separa più valori all'interno di set di coppie chiave-valore serializzate.

## Esempi {#examples}

With [!UICONTROL Destination Builder] you can format key-value data in several different ways. Diamo un'occhiata ad alcuni esempi di ciascun tipo.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Esempi di coppia chiave-valore </th> 
   <th colname="col2" class="entry"> Esempio  </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Chiave singola standard</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Un set semplice di coppie chiave-valore. L'esempio contiene gli elementi seguenti: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Chiave: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Valori: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Separatore: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Delimitatore chiave chiave: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Coppie chiave-valore multiple</b> (non serie) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Un set di più coppie chiave-valore che superano i valori con set chiave chiave separati. L'esempio contiene gli elementi seguenti: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Tasti: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Valori: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Separatore: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Delimitatore chiave chiave: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Chiave singola di serie</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1; 2; 3 </code> </p> </td> 
   <td colname="col3"> <p>Un set chiave-valore che trasmette più valori con una singola chiave. Poiché questa chiave ha più valori, è definita coppia chiave-valore serializzata. L'esempio contiene gli elementi seguenti: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Chiave: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Valori: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Separatore: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Separatore di serie: semi-due punti </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Coppie chiave-valore multiple</b> (serie) </p> </td> 
   <td colname="col2"> <p> <code> X = 1; 2 &amp; Y = 3; 4 </code> </p> </td> 
   <td colname="col3"> <p>Un set di più coppie chiave-valore che passano in più valori su chiavi separate. L'esempio contiene gli elementi seguenti: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Tasti: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Valori: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Separatore: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Delimitatore: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Separatore di serie: semi-due punti </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Destination Serialization {#destination-serialized}

Una destinazione serializzata combina più caratteristiche in una singola stringa e invia tali informazioni a una destinazione.

<!-- c_dest_serialized.xml -->

La trasmissione serializzata contribuisce a migliorare l'efficienza perché più caratteristiche vengono attivate in sequenza, anziché in parallelo. Questo fornisce al server di destinazione un tempo sufficiente per ricevere, elaborare e restituire i dati prima di rispondere a richieste aggiuntive.

### Destinazioni supportate

In [!DNL Audience Manager], you can serialize and send data to just about any destination you want to work with. However, before using this feature, you will need to know the destination [!DNL URL] and where to place some required or optional macros. Ottenere le informazioni sulla posizione della macro dal partner di destinazione. See [Destination Macros Defined](../../features/destinations/destination-macros.md#destination-macros-defined) for more information.