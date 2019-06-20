---
description: Descrive la configurazione di passaggi e funzioni specifiche del processo di creazione delle caratteristiche basato su regole e registrate.
keywords: create trait; creare caratteristiche
seo-description: Descrive la configurazione di passaggi e funzioni specifiche del processo di creazione delle caratteristiche basato su regole e registrate.
seo-title: Creare caratteristiche basate su regole o caricate
solution: Audience Manager
title: Creare caratteristiche basate su regole o caricate
uuid: 4243 e 09 f -1 f 96-443 a -864 a-d 6 e 6918079 fa
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Creare caratteristiche basate su regole o caricate {#create-rules-based-or-onboarded-traits}

Descrive la configurazione di passaggi e funzioni specifiche per [!UICONTROL rules-based] il processo di creazione [!UICONTROL onboarded] delle caratteristiche.

<!-- c_tb_rules_traits.xml -->

## Informazioni di base per caratteristiche {#basics}

In [!UICONTROL Trait Builder], le [!UICONTROL Basic Information] impostazioni consentono di creare nuove caratteristiche o di modificare le caratteristiche esistenti. [!UICONTROL Basic Information] Le impostazioni sono uguali per le caratteristiche basate su regole, caricate e algoritmiche. Per creare una nuova caratteristica, specificate un nome (evitate caratteri speciali), un&#39;origine dati e selezionate una cartella di archiviazione. Altri [!UICONTROL Basic Information] campi sono facoltativi.

<!-- c_tb_basics.xml -->

### Campi di informazioni di base definiti

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento interfaccia </th> 
   <th colname="col2" class="entry"> Spiegazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Nome</span></b> </td> 
   <td colname="col2"> <p>Il nome delle caratteristiche. Obbligatorio. </p> <p>Lunghezza massima: 255 caratteri. </p> <p> <p>Nota: Per le caratteristiche, evitate questi caratteri speciali: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Virgole </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Trattini </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Trattini </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Schede </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Barra verticale o simbolo verticale </li> 
      </ul> </p> </p> <p>In questo modo si riducono gli errori di elaborazione quando si configura un <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> trasferimento di file di dati in ingresso</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descrizione</span></b> </td> 
   <td colname="col2"> Alcune parole utili per descrivere lo scopo o la funzione della caratteristica. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo evento</span></b> </td> 
   <td colname="col2"> Assegna la caratteristica a un tipo o a una categoria, in genere a seconda della funzione (ad es. conversione, visitatore del sito, partner, visualizzazione pagina, ecc.). Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Origine dati</span></b> </td> 
   <td colname="col2"> Associa la caratteristica a un provider di dati specifico. Obbligatorio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Codice integrazione</span></b> </td> 
   <td colname="col2"> Campo per un ID, SKU o altro valore utilizzato dai processi aziendali interni. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Commenti</span></b> </td> 
   <td colname="col2"> Note generali su una caratteristica. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Archiviato</span></b> </td> 
   <td colname="col2"> Determina la cartella di memorizzazione a cui appartiene. Obbligatorio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoria dati</span></b> </td> 
   <td colname="col2"> Consente di classificare le caratteristiche in base alle categorie comunemente riconosciute. <p>Nota: Le caratteristiche appartengono solo a una singola categoria. Facoltativo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Impostare un intervallo di scadenza {#set-expiration-interval}

In [!UICONTROL Trait Builder], consente [!UICONTROL Advanced Options] di impostare un intervallo time-to-live ([!DNL TTL]) per una caratteristica. [!DNL TTL] definisce quanti giorni un visitatore qualificato rimane in una caratteristica (120 giorni è predefinito). Se impostata su 0, l&#39;iscrizione alle caratteristiche non scade.

<!-- t_tb_ttl.xml -->

### Impostare il TTL per una caratteristica

1. Espandete la [!UICONTROL Advanced Options] sezione e immettete un numero per impostare [!DNL TTL] un valore per la caratteristica.
1. Fai clic su **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_ LIKE_ THIS]
>
>* [Tempo del segmento in Live Explained](../../features/traits/segment-ttl-explained.md)

