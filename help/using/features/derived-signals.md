---
description: Un segnale derivato qualifica i visitatori del sito per caratteristiche aggiuntive in base a una caratteristica già vista. In altre parole, una qualifica aggiuntiva può essere derivata da una caratteristica attualmente esposta anche se un utente non ha mai visto la nuova caratteristica prima.
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: Segnali derivati
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 1%

---

# Segnali derivati {#derived-signals}

A [!UICONTROL derived signal] qualifica i visitatori del sito per caratteristiche aggiuntive basate su una caratteristica già vista. In altre parole, una qualifica aggiuntiva può essere derivata da una caratteristica attualmente esposta anche se un utente non ha mai visto la nuova caratteristica prima.

<!-- c_tb_derived_signal.xml -->

## Scopo dei segnali derivati

In entrata [!DNL Audience Manager], puoi creare una relazione tra i segnali (o regole di caratteristiche) trasmessi durante una chiamata evento ad altri segnali o caratteristiche specifici. Ad esempio, supponiamo che una chiamata evento passi in un segnale composto dal valore chiave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] collega il segnale a qualsiasi altro utente creato con [!UICONTROL derived signals] strumento. Anche se i segnali associati possono essere qualsiasi valore chiave specificato, sono più utili se collegati a segnali esistenti già impostati come [!UICONTROL Trait Builder] regole. Ad esempio, nell’illustrazione seguente, quando un’azione dell’utente attiva il segnale [!DNL "product = new car"] l’utente può anche qualificarsi per le caratteristiche definite dai segnali chiave e valore di target.

![](assets/derived_signal_example.png)

## Posizione dei segnali derivati

Creare e gestire [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** dalla navigazione tramite barra laterale.

## Creare un segnale derivato {#create}

<!-- t_tb_create_derived.xml -->

Per creare un [!UICONTROL derived signal]:

1. Seleziona **[!UICONTROL Derived Signals]** dal [!UICONTROL Tools] menu.
1. Fornisci:
   * *(Facoltativo)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Clic **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Limite di caratteri per [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key], e [!UICONTROL Target Value] è di 228 caratteri.

## Modificare un segnale derivato {#edit}

<!-- t_tb_edit_derived.xml -->

Per modificare un [!UICONTROL derived signal]:

1. Passa il puntatore sul segnale, quindi fai clic su **[!UICONTROL Edit]**.
2. Apporta le modifiche richieste a codice, chiave o valore, quindi fai clic su **[!UICONTROL Save]**.

## Eliminare un segnale derivato {#delete}

<!-- t_tb_delete_derived.xml -->

Per eliminare un [!UICONTROL derived signal], passa il puntatore sul segnale, quindi fai clic su **[!UICONTROL Delete]**.
