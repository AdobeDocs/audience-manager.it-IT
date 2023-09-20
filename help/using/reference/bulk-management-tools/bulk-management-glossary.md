---
description: Definite le etichette di intestazione di colonna.
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Glossario degli strumenti di gestione in blocco
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 3%

---

# Glossario degli strumenti di gestione in blocco{#bulk-management-tools-glossary}

Definite le etichette di intestazione di colonna.

>[!IMPORTANT]
>
>Gli strumenti di gestione in blocco non sono un’offerta di Adobe ufficialmente supportata. La risoluzione dei problemi e il supporto tramite l’Assistenza clienti verranno gestiti caso per caso.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[Autorizzazioni del gruppo RBAC](../../features/administration/administration-overview.md) assegnato in [!DNL Audience Manager] L’interfaccia utente di è rispettata in [!UICONTROL Bulk Management Tools].

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
   <td colname="col2"> <p>ID di un <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> origine dati</a> si desidera restituire o assegnare in blocco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivatoSignalId</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../features/derived-signals.md"> segnale derivato</a> ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> descrizione</span> </p> </td> 
   <td colname="col2"> <p>Breve descrizione informativa che è possibile fornire a un oggetto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>ID del <a href="../../features/destinations/destinations.md"> destinazione</a> vuoi mappare o eliminare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>Un ID speciale assegnato a un segmento quando è mappato a una destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>ID del segmento o della cartella delle caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'oggetto che si sta utilizzando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>ID di un segmento o di una cartella di caratteristiche che contiene altre cartelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>ID segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>I segnali sono bit di dati trasmessi a <span class="keyword"> Audience Manager</span> in base all’attività dell’utente. Questi vengono trasmessi come <a href="../../reference/key-value-pairs-explained.md"> coppie chiave-valore</a>. La chiave di origine è una costante che non cambia. Consente di categorizzare il valore sorgente che può cambiare. Consulta <a href="../../features/derived-signals.md"> Segnali derivati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>Il valore sorgente è una variabile passata come parte a <a href="../../reference/key-value-pairs-explained.md"> coppia chiave-valore</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica quando un segmento può iniziare a essere inviato a una destinazione. Usa <i>aaaa-mm-gg</i> formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">Chiave utilizzata nel segnale derivato. Consulta <a href="../../features/derived-signals.md"> Segnali derivati</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>Valore passato con una chiave di segnale derivata. Consulta <a href="../../features/derived-signals.md"> Segnali derivati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>ID passato a una destinazione non basata su cookie. Per una destinazione basata su cookie, questa è la chiave in una <a href="../../reference/key-value-pairs-explained.md"> coppia chiave-valore</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule/segmentRule</span> </p> </td> 
   <td colname="col2"> <p>La caratteristica o regola del segmento effettiva utilizzata per raccogliere i dati. Una richiesta in blocco restituisce le regole create in <span class="keyword"> Audience Manager</span> con <a href="../../features/traits/about-trait-builder.md"> generatore di regole per caratteristiche</a> o <a href="../../features/segments/segment-builder.md"> generatore di regole di segmento</a>. Puoi anche utilizzare questi strumenti per creare regole e applicarle in blocco quando aggiorni un segmento o una caratteristica. </p> <p>Vedi anche, <a href="../../reference/bulk-management-tools/bulk-rules.md"> Creare o aggiornare regole di caratteristiche e di segmenti</a>. </p> </td> 
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
   <td colname="col2"> <p>Pixel generati da DIL quando un utente si qualifica per un segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>La chiave in una <a href="../../reference/key-value-pairs-explained.md"> coppia chiave-valore</a> passato a una destinazione cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>
