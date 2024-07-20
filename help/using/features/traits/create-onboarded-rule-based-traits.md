---
description: Descrive i passaggi di configurazione e le funzioni specifiche del processo di creazione delle caratteristiche basato su regole e onboarded.
keywords: creare caratteristiche;creare caratteristiche
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: Creare caratteristiche basate su regole o onboarded
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 1%

---

# Crea [!UICONTROL Rules-Based] o [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Descrive i passaggi di configurazione e le funzionalità specifiche del processo di creazione delle caratteristiche [!UICONTROL rules-based] e [!UICONTROL onboarded].

<!-- c_tb_rules_traits.xml -->

## Informazioni di base per le caratteristiche {#basics}

In [!UICONTROL Trait Builder], le impostazioni di [!UICONTROL Basic Information] ti consentono di creare o modificare [!UICONTROL traits] nuovo/i. Le impostazioni di [!UICONTROL Basic Information] sono le stesse per [!UICONTROL rules-based], [!UICONTROL onboarded] e [!UICONTROL algorithmic traits]. Per creare un nuovo [!UICONTROL trait], fornire un nome (evitare caratteri speciali), un [!UICONTROL data source] e selezionare un [!UICONTROL storage folder]. Altri campi [!UICONTROL Basic Information] sono facoltativi.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Campi informazioni di base definiti

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento di interfaccia </th> 
   <th colname="col2" class="entry"> Spiegazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome <b><span class="uicontrol"></span></b> </td> 
   <td colname="col2"> <p>Nome della caratteristica. Obbligatorio. </p> <p>Lunghezza massima: 255 caratteri. </p> <p> <p>Nota: quando denomini le caratteristiche, evita questi caratteri speciali: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Virgole </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Trattini </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Trattini </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Schede </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Simbolo di barra o tubo verticale </li> 
      </ul> </p> </p> <p>Ciò consente di ridurre gli errori di elaborazione durante la configurazione di un trasferimento di file di dati in entrata <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"></a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descrizione <b><span class="uicontrol"></span></b> </td> 
   <td colname="col2"> Alcune parole per descrivere lo scopo o la funzione della caratteristica. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Data Source <b><span class="uicontrol"></span></b> </td> 
   <td colname="col2"> Associa la caratteristica a un provider di dati specifico. Obbligatorio. <p>Utilizza il primo menu a discesa per filtrare tra origini dati di Audience Manager, suite di rapporti di Adobe Analytics o entrambe. Quindi, utilizza il secondo menu a discesa per scegliere l’origine dati.</p><p> Se non utilizzi le suite di rapporti di Adobe Analytics, il selettore del tipo di origine dati è disattivato e per impostazione predefinita viene utilizzato solo l’Audience Manager delle origini dati.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> Tipo di evento <b><span class="uicontrol"></span></b> </td> 
   <td colname="col2"> Assegna la caratteristica a un tipo o a una categoria, in genere in base alla funzione (ad esempio conversione, visitatore del sito, partner, visualizzazione pagina, ecc.). Facoltativo. <p> Per informazioni su come creare caratteristiche di conversione, consulta <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Creazione di caratteristiche di conversione nel video di Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Codice di integrazione <b><span class="uicontrol"></span></b> </td> 
   <td colname="col2"> Campo per un ID, una SKU (Stock Keeping Unit) o un altro valore utilizzato dai processi aziendali interni. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Commenti</span></b> </td> 
   <td colname="col2"> Note generali su una caratteristica. Facoltativo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivio <b><span class="uicontrol"> In</span></b> </td> 
   <td colname="col2"> Determina la cartella di archiviazione a cui appartiene la caratteristica. Obbligatorio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Categoria dati <b><span class="uicontrol"></span></b> </td> 
   <td colname="col2"> Classifica le caratteristiche in base a categorie comunemente note. <p>Nota: le caratteristiche appartengono a una sola categoria. Facoltativo. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Imposta un intervallo di scadenza [!UICONTROL Trait] {#set-expiration-interval}

In [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] consente di impostare un intervallo time-to-live ([!DNL TTL]) per un [!UICONTROL trait]. [!DNL TTL] definisce quanti giorni un visitatore qualificato rimane in un [!UICONTROL trait] (120 giorni è l&#39;impostazione predefinita). Se è impostato su 0, l&#39;iscrizione a [!UICONTROL trait] non scade mai.

<!-- t_tb_ttl.xml -->

### Imposta il TTL per [!UICONTROL trait]

1. Espandere la sezione [!UICONTROL Advanced Options] e immettere un numero per impostare un valore [!DNL TTL] per [!UICONTROL trait].
1. Fare clic su **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Spiegazione durata segmento](../../features/traits/segment-ttl-explained.md)
