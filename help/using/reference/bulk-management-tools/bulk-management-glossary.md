---
description: Definite le etichette di intestazione delle colonne.
seo-description: Definite le etichette di intestazione delle colonne.
seo-title: Glossario degli strumenti di gestione in blocco
solution: Audience Manager
title: Glossario degli strumenti di gestione in blocco
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: baaam
translation-type: tm+mt
source-git-commit: adab01a81c0002d28c2387a20d8ae284e11a5e41
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 4%

---


# Glossario degli strumenti di gestione in blocco{#bulk-management-tools-glossary}

Definite le etichette di intestazione delle colonne.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[Le autorizzazioni](../../features/administration/administration-overview.md) del gruppo RBAC assegnate nell’ [!DNL Audience Manager] interfaccia utente sono rispettate nella [!UICONTROL Bulk Management Tools].

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Intestazione colonna </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>L'ID di un'origine <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"></a> dati da restituire o assegnare in massa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivateSignalId</span> </p> </td> 
   <td colname="col2"> <p>Un ID segnale <a href="../../features/derived-signals.md"></a> derivato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>Breve descrizione informativa che è possibile fornire a un oggetto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>ID della <a href="../../features/destinations/destinations.md"> destinazione</a> da mappare o eliminare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> DestinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>Un ID speciale assegnato a un segmento quando viene mappato a una destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>L’ID del segmento o della cartella delle caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>Nome dell’oggetto con cui state lavorando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>L'ID di un segmento o di una cartella di caratteristiche che contiene altre cartelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>ID segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>I segnali sono bit di dati passati al <span class="keyword"> Audience Manager</span>  in base all'attività dell'utente. Questi vengono trasmessi come coppie <a href="../../reference/key-value-pairs-explained.md"></a>chiave-valore. La chiave di origine è una costante che non viene modificata. Consente di classificare il valore di origine che può essere modificato. Consulta <a href="../../features/derived-signals.md"> Segnali</a>derivati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>Il valore di origine è una variabile passata come parte di una coppia <a href="../../reference/key-value-pairs-explained.md"></a>chiave-valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica quando un segmento può iniziare a essere inviato a una destinazione. Utilizza <code>yyyy-mm-dd</code> il formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">Chiave utilizzata nel segnale derivato. Consulta <a href="../../features/derived-signals.md"> Segnali</a>derivati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>Il valore passato con una chiave di segnale derivata. Consulta <a href="../../features/derived-signals.md"> Segnali</a>derivati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>Un ID passato a una destinazione non basata su cookie. Per una destinazione basata su cookie, si tratta della chiave in una coppia <a href="../../reference/key-value-pairs-explained.md"></a>chiave-valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule/segmentRule</span> </p> </td> 
   <td colname="col2"> <p>La caratteristica o la regola del segmento utilizzata per raccogliere i dati. Una richiesta in massa restituisce le regole create in <span class="keyword"> Audience Manager</span> con il generatore <a href="../../features/traits/about-trait-builder.md"> di regole di</a> caratteristica o con il generatore <a href="../../features/segments/segment-builder.md"> di regole di</a>segmento. Potete inoltre utilizzare questi strumenti per creare regole e applicarle in blocco quando aggiornate un segmento o una caratteristica. </p> <p>See also, <a href="../../reference/bulk-management-tools/bulk-rules.md"> Create or Update Trait Rules and Segment Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>Stringa che identifica il tipo di caratteristica. Le opzioni includono: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel generati dal DIL quando un utente si qualifica per un segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>Chiave in una coppia <a href="../../reference/key-value-pairs-explained.md"> chiave-valore</a> passata a una destinazione cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

