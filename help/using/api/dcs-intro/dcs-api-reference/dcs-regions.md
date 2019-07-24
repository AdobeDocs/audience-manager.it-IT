---
description: Per effettuare chiamate al DCS è necessario il nome host del server DCS regionale. poiché il DCS memorizza informazioni nei centri dati che sono geograficamente vicini ai visitatori del sito. Le tue query funzionano se li invii al DCS sbagliato, ma queste chiamate sono inefficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fai corrispondere l'ID regione al nome host regionale corrispondente e completa la query con il nome host corretto.
seo-description: Per effettuare chiamate al DCS è necessario il nome host del server DCS regionale. poiché il DCS memorizza informazioni nei centri dati che sono geograficamente vicini ai visitatori del sito. Le tue query funzionano se li invii al DCS sbagliato, ma queste chiamate sono inefficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fai corrispondere l'ID regione al nome host regionale corrispondente e completa la query con il nome host corretto.
seo-title: ID regioni DCS, posizioni e nomi host
solution: Audience Manager
title: ID regioni DCS, posizioni e nomi host
uuid: ad 150 ffe -4583-472 b-ac 8 b-fb 900 a 7966 e 4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

The regional [!UICONTROL DCS] server host name is required to make calls to the [!UICONTROL DCS]. This is because the [!UICONTROL DCS] stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong [!UICONTROL DCS], but these calls are inefficient and can delay the response. To make a [!UICONTROL DCS] request, match the region ID to its corresponding regional host name and form your query with the proper host name.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID regione DCS (dcs_ region) </th> 
   <th colname="col2" class="entry"> Regione (e posizione) </th> 
   <th colname="col3" class="entry"> Nome host </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>Sud-est Asia (Singapore) </p> </td> 
   <td colname="col3"> <p> <code> apse. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>Sud America (São Paulo, Brasile) </p> </td> 
   <td colname="col3"> <p> <code> sae. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublino, Irlanda) </p> </td> 
   <td colname="col3"> <p> <code> irl 1. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>USA East (Virginia, USA) </p> </td> 
   <td colname="col3"> <p> <code> use. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>South Pacific/Oceania (Sydney, Australia) </p> </td> 
   <td colname="col3"> <p> <code> apse 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>USA Occidentale (Oregon, USA) </p> </td> 
   <td colname="col3"> <p> <code> usw 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>Asia (Tokyo, Giappone) </p> </td> 
   <td colname="col3"> <p> <code> tyo 3. demdex. net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>India </p> </td> 
   <td colname="col3"> <p> <code> ind 1. demdex. net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

You can also use [!DNL API] methods to get a list of the available [!UICONTROL DCS] regions. See [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).