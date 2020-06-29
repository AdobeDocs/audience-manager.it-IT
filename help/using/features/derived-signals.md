---
description: Un segnale derivato qualifica i visitatori del sito per caratteristiche aggiuntive basate su una caratteristica già vista. In altre parole, è possibile derivare una caratteristica aggiuntiva da una caratteristica attualmente esposta anche se un utente non ha mai visto la nuova caratteristica prima.
seo-description: Un segnale derivato qualifica i visitatori del sito per caratteristiche aggiuntive basate su una caratteristica già vista. In altre parole, è possibile derivare una caratteristica aggiuntiva da una caratteristica attualmente esposta anche se un utente non ha mai visto la nuova caratteristica prima.
seo-title: Segnali derivati
solution: Audience Manager
title: Segnali derivati
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 0%

---


# Segnali derivati {#derived-signals}

Un visitatore [!UICONTROL derived signal] qualificato per caratteristiche aggiuntive in base a una caratteristica già vista. In altre parole, è possibile derivare una caratteristica aggiuntiva da una caratteristica attualmente esposta anche se un utente non ha mai visto la nuova caratteristica prima.

<!-- c_tb_derived_signal.xml -->

## Finalità dei segnali derivati

In [!DNL Audience Manager], potete creare una relazione tra i segnali (o le regole di caratteristica) passati durante una chiamata dell&#39;evento ad altri segnali o caratteristiche specificati. Ad esempio, si supponga che una chiamata evento passi in un segnale composto dal valore chiave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] collega il segnale a qualsiasi altro strumento creato con [!UICONTROL derived signals] lo strumento. Anche se i segnali associati possono essere qualsiasi valore chiave specificato, sono più utili se collegati a segnali esistenti già configurati come [!UICONTROL Trait Builder] regole. Ad esempio, nell&#39;illustrazione seguente, quando un&#39;azione utente attiva il segnale [!DNL "product = new car"] che l&#39;utente può anche qualificarsi per le caratteristiche definite dai segnali chiave-valore di destinazione.

![](assets/derived_signal_example.png)

## Posizione dei segnali derivati

Creare e gestire [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** dalla navigazione della barra laterale.

## Creare un segnale derivato {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. Selezionate **[!UICONTROL Derived Signals]** dal [!UICONTROL Tools] menu.
1. Fornisci un
   * *(Facoltativo)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Clic **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Il limite di caratteri per i [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key]e [!UICONTROL Target Value] i campi è di 228 caratteri.

## Modifica di un segnale derivato {#edit}

<!-- t_tb_edit_derived.xml -->

Per modificare un [!UICONTROL derived signal]:

1. Passa il mouse sul segnale, quindi fai clic **[!UICONTROL Edit]**.
2. Apportate le modifiche necessarie al codice, alla chiave o al valore, quindi fate clic su **[!UICONTROL Save]**.

## Eliminare un segnale derivato {#delete}

<!-- t_tb_delete_derived.xml -->

Per eliminare un [!UICONTROL derived signal]segnale, passate il mouse sul segnale, quindi fate clic **[!UICONTROL Delete]**.
