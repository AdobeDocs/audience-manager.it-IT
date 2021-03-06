---
description: Descrive i passaggi e le funzionalit√† di configurazione specifici del processo di creazione delle caratteristiche basato su regole e onboarded.
keywords: creare caratteristiche;creare caratteristiche
seo-description: Descrive i passaggi e le funzionalit√† di configurazione specifici del processo di creazione delle caratteristiche basato su regole e onboarded.
seo-title: Creare caratteristiche basate su regole o onboarded
solution: Audience Manager
title: Creare caratteristiche basate su regole o onboarded
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: 'Caratteristiche '
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 7%

---

# Crea [!UICONTROL Rules-Based] o [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Descrive i passaggi e le funzionalit√† di configurazione specifici del processo di creazione delle caratteristiche [!UICONTROL rules-based] e [!UICONTROL onboarded].

<!-- c_tb_rules_traits.xml -->

## Informazioni di base per le caratteristiche {#basics}

In [!UICONTROL Trait Builder], le impostazioni [!UICONTROL Basic Information] consentono di creare nuove impostazioni o modificare [!UICONTROL traits] esistenti. Le impostazioni [!UICONTROL Basic Information] sono le stesse per [!UICONTROL rules-based], [!UICONTROL onboarded] e [!UICONTROL algorithmic traits]. Per creare un nuovo [!UICONTROL trait], fornisci un nome (evita caratteri speciali), un [!UICONTROL data source] e seleziona un [!UICONTROL storage folder]. Altri campi [!UICONTROL Basic Information] sono facoltativi.

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
   <td colname="col2"> <p>Nome della caratteristica. Obbligatorio. </p> <p>Lunghezza massima: 255 caratteri. </p> <p> <p>Nota: Durante la denominazione delle caratteristiche, evita i seguenti caratteri speciali: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Virgole </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Trattini </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Trattini </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Schede </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Simbolo a barre o a barre verticali </li> 
      </ul> </p> </p> <p>Questo aiuta a ridurre gli errori di elaborazione quando si imposta un <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> trasferimento di file di dati in entrata</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Descrizione</span></b> </td> 
   <td colname="col2"> Poche parole per descrivere lo scopo o la funzione della caratteristica. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Origine dati</span></b> </td> 
   <td colname="col2"> Associa la caratteristica a un provider di dati specifico. Obbligatorio. <p>Utilizza il primo menu a discesa per filtrare tra origini dati di Audience Manager, suite di rapporti Adobe Analytics o entrambe. Quindi, utilizza il secondo menu a discesa per scegliere l‚Äôorigine dati.</p><p> Se non usi le suite di rapporti di Adobe Analytics, il selettore del tipo di origine dati √® disabilitato e viene impostato come impostazione predefinita solo per le origini dati di Audience Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Tipo evento</span></b> </td> 
   <td colname="col2"> Assegna la caratteristica a un tipo o a una categoria, in genere in base alla funzione (ad esempio conversione, visitatore del sito, partner, visualizzazione della pagina, ecc.). Facoltativo. <p> Per scoprire come creare le caratteristiche di conversione, guarda il video di Audience Manager <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Creazione di caratteristiche di conversione</a> . </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Codice di integrazione</span></b> </td> 
   <td colname="col2"> Campo per un ID, una SKU o un altro valore utilizzato dai processi aziendali interni. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Commenti</span></b> </td> 
   <td colname="col2"> Note generali su una caratteristica. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Archivia in</span></b> </td> 
   <td colname="col2"> Determina la cartella di archiviazione a cui appartiene la caratteristica. Obbligatorio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Categoria dati</span></b> </td> 
   <td colname="col2"> Classifica le caratteristiche in base alle categorie comunemente comprese. <p>Nota:  Le caratteristiche appartengono a una sola categoria. Facoltativo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Imposta un intervallo di scadenza [!UICONTROL Trait] {#set-expiration-interval}

In [!UICONTROL Trait Builder], il [!UICONTROL Advanced Options] consente di impostare un intervallo time-to-live ([!DNL TTL]) per un valore [!UICONTROL trait]. [!DNL TTL] definisce quanti giorni un visitatore qualificato rimane in un  [!UICONTROL trait] (120 giorni √® l‚Äôimpostazione predefinita). Se √® impostato su 0, l&#39;iscrizione a [!UICONTROL trait] non scade mai.

<!-- t_tb_ttl.xml -->

### Impostare il TTL per un [!UICONTROL trait]

1. Espandi la sezione [!UICONTROL Advanced Options] e inserisci un numero per impostare un valore [!DNL TTL] per il valore [!UICONTROL trait].
1. Clic **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Spiegazione della durata del segmento](../../features/traits/segment-ttl-explained.md)

