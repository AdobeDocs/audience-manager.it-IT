---
description: Etichette dell'intestazione colonna definite.
seo-description: Etichette dell'intestazione colonna definite.
seo-title: Glossario strumenti di gestione massa
solution: Audience Manager
title: Glossario strumenti di gestione massa
uuid: 4658 a 6 bc -9515-4 d 31-9715-0084760 b 0 cea
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Management Tools Glossary{#bulk-management-tools-glossary}

Etichette dell'intestazione colonna definite.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell' [!DNL Audience Manager] interfaccia utente vengono rispettate nell' [!UICONTROL Bulk Management Tools]interfaccia.

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Intestazione colonna </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Datasourceid</span> </p> </td> 
   <td colname="col2"> <p>The ID of a <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> you want to return or assign in bulk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Derivedsignalid</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../features/derived-signals.md"> derived signal</a> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>Una breve descrizione informativa che puoi fornire a un oggetto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Purchionid</span> </p> </td> 
   <td colname="col2"> <p>The ID of the <a href="../../features/destinations/destinations.md"> destination</a> you want to map or delete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Purchionmappingid</span> </p> </td> 
   <td colname="col2"> <p>Un ID speciale assegnato a un segmento quando viene mappato a una destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Folderid</span> </p> </td> 
   <td colname="col2"> <p>L'ID della cartella di segmenti o caratteristiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>Nome dell'oggetto con cui si sta lavorando. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Parentfolderid</span> </p> </td> 
   <td colname="col2"> <p>ID di una cartella di segmento o di caratteristiche che contiene altre cartelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>ID segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcekey</span> </p> </td> 
   <td colname="col2"> <p>Signals are bits of data passed in to <span class="keyword"> Audience Manager</span> based on user activity. These are transmitted as <a href="../../reference/key-value-pairs-explained.md"> key-value pairs</a>. La chiave source è una costante che non viene modificata. Consente di classificare il valore di origine che può cambiare. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcevalue</span> </p> </td> 
   <td colname="col2"> <p>The source value is a variable passed in as part a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica quando un segmento può iniziare a essere inviato a una destinazione. Uses <tt>yyyy-mm-dd</tt> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetkey</span> </p> </td> 
   <td colname="col2">La chiave utilizzata nel segnale derivato. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetvalue</span> </p> </td> 
   <td colname="col2"> <p>Il valore passato con un tasto segnale derivato. See <a href="../../features/derived-signals.md"> Derived Signals</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitaliani</span> </p> </td> 
   <td colname="col2"> <p>Un ID passato a una destinazione basata su cookie. For a cookie-based destination, this is the key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitrule/segmentrule</span> </p> </td> 
   <td colname="col2"> <p>La regola effettiva della caratteristica o del segmento utilizzata per raccogliere i dati. A bulk request returns the rules created in <span class="keyword"> Audience Manager</span> with the <a href="../../features/traits/about-trait-builder.md"> trait rule builder</a> or the <a href="../../features/segments/segment-builder.md"> segment rule builder</a>. Potete anche utilizzare questi strumenti per creare regole e applicarle in massa quando aggiornate un segmento o una caratteristica. </p> <p>See also, <a href="../../reference/bulk-management-tools/bulk-rules.md"> Create or Update Trait Rules and Segment Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traittype</span> </p> </td> 
   <td colname="col2"> <p>Stringa che identifica il tipo di caratteristica. Le opzioni includono: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_ BASED_ TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_ BOARDED_ TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENTO</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel attivato da DIL quando un utente è idoneo per un segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Valuealias</span> </p> </td> 
   <td colname="col2"> <p>The key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a> passed to a cookie destination. </p> </td> 
  </tr> 
 </tbody> 
</table>

