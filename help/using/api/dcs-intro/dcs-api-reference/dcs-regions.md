---
description: Per effettuare chiamate al DCS è necessario specificare il nome host del server DCS regionale. Questo perché il DCS memorizza le informazioni in centri dati geograficamente vicini ai visitatori del sito. Le query funzioneranno se le invii al DCS sbagliato, ma queste chiamate sono inefficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fai corrispondere l’ID di regione al nome host regionale corrispondente e crea la query con il nome host corretto.
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: ID dell’area geografica dei DCS, luoghi e nomi host
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 6%

---

# ID dell’area geografica dei DCS, luoghi e nomi host {#dcs-region-ids-locations-and-host-names}

L&#39;area [!DNL DCS] è necessario il nome host del server per effettuare chiamate al [!DNL DCS]. Questo perché il [!DNL DCS] memorizza le informazioni in data center geograficamente vicini ai visitatori del sito. Le query funzioneranno se vengono inviate a [!DNL DCS], ma queste chiamate sono inefficienti e possono ritardare la risposta. Per creare un [!DNL DCS] richiesta, fai corrispondere l’ID di regione al nome host regionale corrispondente e crea la query con il nome host corretto.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID regione DCS (dcs_region) </th> 
   <th colname="col2" class="entry"> Area geografica (e ubicazione) </th> 
   <th colname="col3" class="entry"> Nome host </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>Sud-est asiatico (Singapore) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>Sudamerica (San Paolo, Brasile) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublino, Irlanda) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>USA orientale (Virginia, USA) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>Pacifico meridionale/Oceania (Sydney, Australia) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>USA occidentale (Oregon, USA) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>Asia (Tokyo, Giappone) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>India </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Puoi anche utilizzare [!DNL API] metodi per ottenere un elenco dei [!DNL DCS] aree geografiche. Consulta [Metodi API per le aree geografiche dei DCS](../../../api/rest-api-main/aam-api-dcs-regions.md).
