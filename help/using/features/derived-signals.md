---
description: Un segnale derivato qualifica i visitatori del sito per caratteristiche aggiuntive in base a una caratteristica che hanno già visto. In altre parole, è possibile derivare una qualifica aggiuntiva per le caratteristiche da una caratteristica attualmente esposta anche se un utente non ha mai visto la nuova caratteristica prima.
seo-description: Un segnale derivato qualifica i visitatori del sito per caratteristiche aggiuntive in base a una caratteristica che hanno già visto. In altre parole, è possibile derivare una qualifica aggiuntiva per le caratteristiche da una caratteristica attualmente esposta anche se un utente non ha mai visto la nuova caratteristica prima.
seo-title: Segnali derivati
solution: Audience Manager
title: Segnali derivati
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: 'Caratteristiche '
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 2%

---

# Segnali derivati {#derived-signals}

Una [!UICONTROL derived signal] qualifica i visitatori del sito per caratteristiche aggiuntive basate su una caratteristica già vista. In altre parole, è possibile derivare una qualifica aggiuntiva per le caratteristiche da una caratteristica attualmente esposta anche se un utente non ha mai visto la nuova caratteristica prima.

<!-- c_tb_derived_signal.xml -->

## Finalità dei segnali derivati

In [!DNL Audience Manager] puoi creare una relazione tra i segnali (o le regole delle caratteristiche) trasmessi durante una chiamata dell&#39;evento ad altri segnali o caratteristiche specificati. Ad esempio, si supponga che una chiamata evento passi in un segnale composto dal valore chiave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] collega quel segnale a tutti gli altri creati con lo  [!UICONTROL derived signals] strumento. Anche se i segnali associati possono essere qualsiasi valore chiave specificato, sono più utili se collegati a segnali esistenti già configurati come regole [!UICONTROL Trait Builder]. Ad esempio, nell’illustrazione seguente, quando un’azione utente genera il segnale [!DNL "product = new car"], l’utente può anche qualificarsi per le caratteristiche definite dai segnali di chiave e valore target.

![](assets/derived_signal_example.png)

## Posizione dei segnali derivati

Crea e gestisci [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** dalla navigazione della barra laterale.

## Creare un segnale derivato {#create}

<!-- t_tb_create_derived.xml -->

Per creare un [!UICONTROL derived signal]:

1. Seleziona **[!UICONTROL Derived Signals]** dal menu [!UICONTROL Tools].
1. Fornisci un:
   * *(Facoltativo)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Clic **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Il limite di caratteri per i campi [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] e [!UICONTROL Target Value] è di 228 caratteri.

## Modificare un segnale derivato {#edit}

<!-- t_tb_edit_derived.xml -->

Per modificare un elemento [!UICONTROL derived signal]:

1. Passa il puntatore del mouse sul segnale, quindi fai clic su **[!UICONTROL Edit]**.
2. Apporta le modifiche necessarie al codice, alla chiave o al valore, quindi fai clic su **[!UICONTROL Save]**.

## Eliminare un segnale derivato {#delete}

<!-- t_tb_delete_derived.xml -->

Per eliminare un [!UICONTROL derived signal], passa il puntatore del mouse sul segnale, quindi fai clic su **[!UICONTROL Delete]**.
