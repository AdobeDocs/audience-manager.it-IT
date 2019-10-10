---
description: Descrive i passaggi e le funzionalità di configurazione specifici per il processo di creazione delle caratteristiche basato su regole e integrato.
keywords: creare caratteristiche;creare caratteristiche
seo-description: Descrive i passaggi e le funzionalità di configurazione specifici per il processo di creazione delle caratteristiche basato su regole e integrato.
seo-title: Creare caratteristiche basate su regole o registrate
solution: Audience Manager
title: Creare caratteristiche basate su regole o registrate
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
translation-type: tm+mt
source-git-commit: c7efca0cd13f0ca05d926e6675b74ef0170cbce1

---


# Creare caratteristiche basate su regole o registrate {#create-rules-based-or-onboarded-traits}

Descrive i passaggi di configurazione e le funzionalità specifiche del processo di creazione [!UICONTROL rules-based] e [!UICONTROL onboarded] delle caratteristiche.

<!-- c_tb_rules_traits.xml -->

## Informazioni di base sulle caratteristiche {#basics}

In [!UICONTROL Trait Builder], le [!UICONTROL Basic Information] impostazioni consentono di creare caratteristiche nuove o di modificare quelle esistenti. Le [!UICONTROL Basic Information] impostazioni sono le stesse per le caratteristiche algoritmiche, basate su regole. Per creare una nuova caratteristica, specificare un nome (evitare caratteri speciali), un'origine dati e selezionare una cartella di archiviazione. Altri [!UICONTROL Basic Information] campi sono facoltativi.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

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
   <td colname="col2"> <p>Nome della caratteristica. Obbligatorio. </p> <p>Lunghezza massima: 255 caratteri. </p> <p> <p>Nota: Quando assegnate un nome alle caratteristiche, evitate i seguenti caratteri speciali: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Virgole </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Trattini </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Trattini </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Schede </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Simbolo barra o barra verticale </li> 
      </ul> </p> </p> <p>Questo consente di ridurre gli errori di elaborazione quando si configura un trasferimento <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> di file di dati in</a>ingresso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descrizione</span></b> </td> 
   <td colname="col2"> Alcune parole utili per descrivere lo scopo o la funzione della caratteristica. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Origine dati</span></b> </td> 
   <td colname="col2"> Associa la caratteristica a un provider di dati specifico. Obbligatorio. <p>Usate il primo menu a discesa per filtrare tra le origini dati di Audience Manager, le suite di rapporti di Adobe Analytics o entrambe. Quindi, utilizzare il secondo menu a discesa per scegliere l'origine dati.</p><p> Se non hai suite di rapporti Adobe Analytics, il selettore del tipo di origine dati è disabilitato e puoi visualizzare solo le tue origini dati Audience Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo evento</span></b> </td> 
   <td colname="col2"> Assegna la caratteristica a un tipo o una categoria, in genere in base alla funzione (ad esempio conversione, visitatore del sito, partner, visualizzazione della pagina, ecc.). Facoltativo. <p> Per informazioni su come creare caratteristiche di conversione, guarda il video <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html"></a>Creazione di caratteristiche di conversione in Audience Manager. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Codice integrazione</span></b> </td> 
   <td colname="col2"> Campo per un ID, uno SKU o altro valore utilizzato dai processi aziendali interni. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Commenti</span></b> </td> 
   <td colname="col2"> Note generali su una caratteristica. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Store In</span></b> </td> 
   <td colname="col2"> Stabilisce a quale cartella di archiviazione appartiene la caratteristica. Obbligatorio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoria dati</span></b> </td> 
   <td colname="col2"> Classifica le caratteristiche in base alle categorie comunemente comprese. <p>Nota:  Le caratteristiche appartengono a una sola categoria. Facoltativo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Imposta un intervallo di scadenza caratteristica {#set-expiration-interval}

In [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] consente di impostare un intervallo di tempo ([!DNL TTL]) per una caratteristica. [!DNL TTL] definisce il numero di giorni in cui un visitatore qualificato rimane in una caratteristica (per impostazione predefinita, 120 giorni). Se è impostata su 0, l'iscrizione alla caratteristica non scade mai.

<!-- t_tb_ttl.xml -->

### Impostare il TTL per una caratteristica

1. Espandete la sezione e immettete un numero per impostare un [!UICONTROL Advanced Options] [!DNL TTL] valore per la caratteristica.
2. Fai clic su **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_LIKE_this]
>
>* [Tempo segmento per vivere spiegato](../../features/traits/segment-ttl-explained.md)

