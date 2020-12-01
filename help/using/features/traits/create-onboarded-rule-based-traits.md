---
description: Descrive i passaggi e le funzionalità di configurazione specifici per il processo di creazione delle caratteristiche basato su regole e integrato.
keywords: create trait;create traits
seo-description: Descrive i passaggi e le funzionalità di configurazione specifici per il processo di creazione delle caratteristiche basato su regole e integrato.
seo-title: Creare caratteristiche basate su regole o onboarded
solution: Audience Manager
title: Creare caratteristiche basate su regole o onboarded
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 7%

---


# Creare [!UICONTROL Rules-Based] o [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Descrive i passaggi di configurazione e le funzionalità specifiche del processo di creazione delle caratteristiche [!UICONTROL rules-based] e [!UICONTROL onboarded].

<!-- c_tb_rules_traits.xml -->

## Informazioni di base sulle caratteristiche {#basics}

In [!UICONTROL Trait Builder], le impostazioni [!UICONTROL Basic Information] consentono di creare nuove impostazioni o di modificare [!UICONTROL traits] esistenti. Le impostazioni [!UICONTROL Basic Information] sono le stesse per [!UICONTROL rules-based], [!UICONTROL onboarded] e [!UICONTROL algorithmic traits]. Per creare una nuova [!UICONTROL trait], immettete un nome (evitando caratteri speciali), un [!UICONTROL data source] e selezionate un [!UICONTROL storage folder]. Altri campi [!UICONTROL Basic Information] sono facoltativi.

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
      </ul> </p> </p> <p>Questo consente di ridurre gli errori di elaborazione quando si configura un <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> trasferimento di file di dati in ingresso</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descrizione</span></b> </td> 
   <td colname="col2"> Alcune parole utili per descrivere lo scopo o la funzione della caratteristica. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Origine dati</span></b> </td> 
   <td colname="col2"> Associa la caratteristica a un provider di dati specifico. Obbligatorio. <p>Utilizzate il primo menu a discesa per filtrare tra origini dati  Audience Manager,  suite di rapporti Adobe Analytics o entrambe. Quindi, utilizzare il secondo menu a discesa per scegliere l'origine dati.</p><p> Se non si utilizzano  suite di rapporti Adobe Analytics, il selettore del tipo di origine dati è disabilitato e predefinito per  solo origini dati Audienci Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo evento</span></b> </td> 
   <td colname="col2"> Assegna la caratteristica a un tipo o una categoria, in genere in base alla funzione (ad esempio conversione, visitatore del sito, partner, visualizzazione della pagina, ecc.). Facoltativo. <p> Per informazioni su come creare caratteristiche di conversione, consultate la sezione <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Creazione di caratteristiche di conversione in  Audience Manager video</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Codice di integrazione</span></b> </td> 
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

## Impostare un [!UICONTROL Trait] intervallo di scadenza {#set-expiration-interval}

In [!UICONTROL Trait Builder], il [!UICONTROL Advanced Options] consente di impostare un intervallo di tempo per il ciclo di vita ([!DNL TTL]) per un intervallo [!UICONTROL trait]. [!DNL TTL] definisce il numero di giorni in cui un visitatore qualificato rimane in un  [!UICONTROL trait] (il valore predefinito è 120 giorni). Se è impostata su 0, l&#39;iscrizione [!UICONTROL trait] non scade mai.

<!-- t_tb_ttl.xml -->

### Impostare TTL per un [!UICONTROL trait]

1. Espandere la sezione [!UICONTROL Advanced Options] e immettere un numero per impostare un valore [!DNL TTL] per [!UICONTROL trait].
1. Clic **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Tempo segmento per vivere spiegato](../../features/traits/segment-ttl-explained.md)

