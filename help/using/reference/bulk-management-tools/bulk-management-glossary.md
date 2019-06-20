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


# Glossario strumenti di gestione massa{#bulk-management-tools-glossary}

Etichette dell&#39;intestazione colonna definite.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>Non [!UICONTROL Bulk Management Tools]*sono* supportati da [!DNL Audience Manager]. Questo strumento viene fornito per comodità e solo per cortesia. Per modifiche in massa, consigliamo di lavorare con [le API](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager. [Le autorizzazioni dei gruppi RBAC](../../features/administration/administration-overview.md) assegnate nell&#39; [!DNL Audience Manager] interfaccia utente vengono rispettate nell&#39; [!UICONTROL Bulk Management Tools]interfaccia.

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
   <td colname="col2"> <p>ID di un <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 'origine</a> dati che desideri restituire o assegnare in gruppo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Derivedsignalid</span> </p> </td> 
   <td colname="col2"> <p>Un <a href="../../features/derived-signals.md"> ID segnale</a> derivato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>Una breve descrizione informativa che puoi fornire a un oggetto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Purchionid</span> </p> </td> 
   <td colname="col2"> <p>ID della <a href="../../features/destinations/destinations.md"> destinazione</a> da mappare o eliminare. </p> </td> 
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
   <td colname="col2"> <p>I segnali sono bit di dati passati ad <span class="keyword"> Audience Manager</span> in base all'attività dell'utente. Queste vengono trasmesse come <a href="../../reference/key-value-pairs-explained.md"> coppie chiave-valore</a>. La chiave source è una costante che non viene modificata. Consente di classificare il valore di origine che può cambiare. Consultate <a href="../../features/derived-signals.md"> Segnali derivati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcevalue</span> </p> </td> 
   <td colname="col2"> <p>Il valore source è una variabile passata come coppia <a href="../../reference/key-value-pairs-explained.md"> chiave-valore</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Indica quando un segmento può iniziare a essere inviato a una destinazione. Utilizza <tt>il formato aaaa-mm</tt> -dd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetkey</span> </p> </td> 
   <td colname="col2">La chiave utilizzata nel segnale derivato. Consultate <a href="../../features/derived-signals.md"> Segnali derivati</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetvalue</span> </p> </td> 
   <td colname="col2"> <p>Il valore passato con un tasto segnale derivato. Consultate <a href="../../features/derived-signals.md"> Segnali derivati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitaliani</span> </p> </td> 
   <td colname="col2"> <p>Un ID passato a una destinazione basata su cookie. Per una destinazione basata su cookie, questa è la chiave in una coppia <a href="../../reference/key-value-pairs-explained.md"> chiave-valore</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitrule/segmentrule</span> </p> </td> 
   <td colname="col2"> <p>La regola effettiva della caratteristica o del segmento utilizzata per raccogliere i dati. Una richiesta in massa restituisce le regole create in <span class="keyword"> Audience Manager</span> con il generatore di regole <a href="../../features/traits/about-trait-builder.md"> di caratteristica</a> o il <a href="../../features/segments/segment-builder.md"> generatore di regole del segmento</a>. Potete anche utilizzare questi strumenti per creare regole e applicarle in massa quando aggiornate un segmento o una caratteristica. </p> <p>Vedi anche <a href="../../reference/bulk-management-tools/bulk-rules.md"> Crea o aggiorna regole caratteristiche e regole segmento</a>. </p> </td> 
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
   <td colname="col2"> <p>La chiave in una <a href="../../reference/key-value-pairs-explained.md"> coppia chiave-valore</a> passata a una destinazione del cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

