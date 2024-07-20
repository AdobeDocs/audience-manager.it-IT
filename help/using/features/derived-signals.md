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
source-wordcount: '261'
ht-degree: 0%

---

# Segnali derivati {#derived-signals}

[!UICONTROL derived signal] qualifica i visitatori del sito per caratteristiche aggiuntive in base a una caratteristica già vista. In altre parole, una qualifica aggiuntiva può essere derivata da una caratteristica attualmente esposta anche se un utente non ha mai visto la nuova caratteristica prima.

<!-- c_tb_derived_signal.xml -->

## Scopo dei segnali derivati

In [!DNL Audience Manager] è possibile creare una relazione tra i segnali (o regole di caratteristiche) trasmessi durante una chiamata evento ad altri segnali o caratteristiche specificati. Si supponga, ad esempio, che una chiamata evento passi in un segnale composto dal valore chiave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] collegherebbe il segnale a tutti gli altri creati con lo strumento [!UICONTROL derived signals]. Anche se i segnali associati possono essere qualsiasi valore chiave specificato, sono più utili se collegati a segnali esistenti già impostati come regole [!UICONTROL Trait Builder]. Ad esempio, nell&#39;illustrazione seguente, quando un&#39;azione dell&#39;utente attiva il segnale [!DNL "product = new car"], l&#39;utente può anche qualificarsi per le caratteristiche definite dai segnali chiave e valore di destinazione.

![](assets/derived_signal_example.png)

## Posizione dei segnali derivati

Crea e gestisci [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** dalla navigazione tramite la barra laterale.

## Creare un segnale derivato {#create}

<!-- t_tb_create_derived.xml -->

Per creare un [!UICONTROL derived signal]:

1. Selezionare **[!UICONTROL Derived Signals]** dal menu [!UICONTROL Tools].
1. Fornisci:
   * *(Facoltativo)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Fare clic su **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Il limite di caratteri per i campi [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] e [!UICONTROL Target Value] è di 228 caratteri.

## Modificare un segnale derivato {#edit}

<!-- t_tb_edit_derived.xml -->

Per modificare un [!UICONTROL derived signal]:

1. Passa il puntatore del mouse sul segnale, quindi fai clic su **[!UICONTROL Edit]**.
2. Apportare le modifiche necessarie al codice, alla chiave o al valore, quindi fare clic su **[!UICONTROL Save]**.

## Eliminare un segnale derivato {#delete}

<!-- t_tb_delete_derived.xml -->

Per eliminare un [!UICONTROL derived signal], passa il cursore sul segnale, quindi fai clic su **[!UICONTROL Delete]**.
