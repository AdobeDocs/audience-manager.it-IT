---
description: Il nome host del server DCS regionale è richiesto per effettuare chiamate al DCS. Questo perché il DCS memorizza le informazioni in centri dati geograficamente vicini ai visitatori del sito. Le query funzioneranno se le inviate al DCS sbagliato, ma queste chiamate non sono efficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fate corrispondere l’ID di regione al nome host regionale corrispondente e create la query con il nome host corretto.
seo-description: Il nome host del server DCS regionale è richiesto per effettuare chiamate al DCS. Questo perché il DCS memorizza le informazioni in centri dati geograficamente vicini ai visitatori del sito. Le query funzioneranno se le inviate al DCS sbagliato, ma queste chiamate non sono efficienti e possono ritardare la risposta. Per effettuare una richiesta DCS, fate corrispondere l’ID di regione al nome host regionale corrispondente e create la query con il nome host corretto.
seo-title: ID regione DCS, posizioni e nomi host
solution: Audience Manager
title: ID regione DCS, posizioni e nomi host
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

Il nome host del [!UICONTROL DCS] server regionale è necessario per effettuare chiamate al [!UICONTROL DCS]. Questo perché [!UICONTROL DCS] memorizza le informazioni in centri dati geograficamente vicini ai visitatori del sito. Le query funzioneranno se le inviate a un indirizzo errato [!UICONTROL DCS], ma queste chiamate sono inefficienti e possono ritardare la risposta. Per effettuare una [!UICONTROL DCS] richiesta, fate corrispondere l'ID di regione al nome host regionale corrispondente e create la query con il nome host corretto.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID regione DCS (dcs_region) </th> 
   <th colname="col2" class="entry"> Regione (e posizione) </th> 
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
   <td colname="col2"> <p>Sud America (San Paolo, Brasile) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublino, Irlanda) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>USA East (Virginia, USA) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>Pacifico meridionale / Oceania (Sydney, Australia) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>US West (Oregon, USA) </p> </td> 
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

È inoltre possibile utilizzare [!DNL API] i metodi per ottenere un elenco delle [!UICONTROL DCS] aree disponibili. Consultate Metodi [API per regione](../../../api/rest-api-main/aam-api-dcs-regions.md)DCS.