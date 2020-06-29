---
description: Descrive i passaggi e le funzionalità di configurazione specifici per il processo di creazione delle caratteristiche basato su regole e integrato.
keywords: create trait;create traits
seo-description: Descrive i passaggi e le funzionalità di configurazione specifici per il processo di creazione delle caratteristiche basato su regole e integrato.
seo-title: Creazione di caratteristiche basate su regole o registrate
solution: Audience Manager
title: Creazione di caratteristiche basate su regole o registrate
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 4%

---


# Crea [!UICONTROL Rules-Based] o [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Descrive i passaggi di configurazione e le funzionalità specifiche del processo di creazione [!UICONTROL rules-based] e [!UICONTROL onboarded] delle caratteristiche.

<!-- c_tb_rules_traits.xml -->

## Informazioni di base sulle caratteristiche {#basics}

In [!UICONTROL Trait Builder], le [!UICONTROL Basic Information] impostazioni consentono di creare nuove impostazioni o di modificarle esistenti [!UICONTROL traits]. Le [!UICONTROL Basic Information] impostazioni sono le stesse per [!UICONTROL rules-based], [!UICONTROL onboarded] e [!UICONTROL algorithmic traits]. Per creare un nuovo [!UICONTROL trait], immettete un nome (evitando caratteri speciali), un [!UICONTROL data source]nome e selezionate un [!UICONTROL storage folder]. Altri [!UICONTROL Basic Information] campi sono facoltativi.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Campi di informazioni di base definiti

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento di interfaccia </th> 
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
   <td colname="col2"> Associa la caratteristica a un provider di dati specifico. Obbligatorio. <p>Utilizzate il primo menu a discesa per filtrare tra  origini dati Audience Manager, suite di rapporti Adobe  Analytics o entrambe. Quindi, utilizzare il secondo menu a discesa per scegliere l'origine dati.</p><p> Se non si utilizzano suite di rapporti Adobe  Analytics, il selettore del tipo di origine dati è disabilitato e predefinito per  solo origini dati Audience Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo evento</span></b> </td> 
   <td colname="col2"> Assegna la caratteristica a un tipo o una categoria, in genere in base alla funzione (ad esempio conversione, visitatore del sito, partner, visualizzazione della pagina, ecc.). Facoltativo. <p> Per informazioni su come creare caratteristiche di conversione, consultate <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Creazione di caratteristiche di conversione in  video</a>Audience Manager. </p></td> 
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

## Imposta un intervallo [!UICONTROL Trait] di scadenza {#set-expiration-interval}

In [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] consente di impostare un intervallo di tempo ([!DNL TTL]) per un [!UICONTROL trait]. [!DNL TTL] definisce il numero di giorni in cui un visitatore qualificato rimane in un [!UICONTROL trait] (120 giorni è il periodo predefinito). Se è impostata su 0, l&#39; [!UICONTROL trait] iscrizione non scade mai.

<!-- t_tb_ttl.xml -->

### Impostare TTL per un [!UICONTROL trait]

1. Espandete la [!UICONTROL Advanced Options] sezione e immettete un numero per impostare un [!DNL TTL] valore per la [!UICONTROL trait].
1. Clic **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Tempo segmento per vivere spiegato](../../features/traits/segment-ttl-explained.md)

