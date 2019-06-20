---
description: Un segnale derivato qualifica i visitatori del sito per caratteristiche aggiuntive basate su una caratteristica già visualizzata. In altre parole, è possibile derivare ulteriori caratteristiche di caratteristica da una caratteristica attualmente visualizzata anche se un utente non ha mai visto il nuovo tratto.
seo-description: Un segnale derivato qualifica i visitatori del sito per caratteristiche aggiuntive basate su una caratteristica già visualizzata. In altre parole, è possibile derivare ulteriori caratteristiche di caratteristica da una caratteristica attualmente visualizzata anche se un utente non ha mai visto il nuovo tratto.
seo-title: Segnali derivati
solution: Audience Manager
title: Segnali derivati
uuid: e 52600 e 3-26 d 1-4607-9 b 96-afd 6086 a 252 d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Segnali derivati {#derived-signals}

A [!UICONTROL derived signal] qualifica i visitatori del sito per caratteristiche aggiuntive basate su una caratteristica già visualizzata. In altre parole, è possibile derivare ulteriori caratteristiche di caratteristica da una caratteristica attualmente visualizzata anche se un utente non ha mai visto il nuovo tratto.

<!-- c_tb_derived_signal.xml -->

## Finalità dei segnali derivati

In [!DNL Audience Manager], potete creare una relazione tra segnali (regole di caratteristica) trasmesse durante una chiamata evento ad altri segnali o caratteristiche specificati. Ad esempio, supponiamo che una chiamata evento passi in un segnale composto dal valore chiave [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] collegare il segnale a qualsiasi altro creato con lo [!UICONTROL derived signals] strumento. Anche se i segnali associati possono essere valori chiave specificati, sono più utili se collegati a segnali esistenti già impostati come [!UICONTROL Trait Builder] regole. Ad esempio, nell&#39;illustrazione seguente, quando un&#39;azione utente preme il segnale [!DNL "product = new car"] che può essere qualificata anche per le caratteristiche definite dai segnali chiave e valore di destinazione.

![](assets/derived_signal_example.png)

## Posizione dei segnali derivati

Create e gestite [!UICONTROL derived signals] i contenuti nella **[!UICONTROL Tools > Derived Signals]** barra laterale.

## Creare un segnale derivato {#create}

<!-- t_tb_create_derived.xml -->

Per creare [!UICONTROL derived signal]:

1. Selezionate **[!UICONTROL Derived Signals]** dal [!UICONTROL Tools] menu.
1. Specificate un:
   * *(Facoltativo)*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Fai clic su **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Il limite di caratteri per [!UICONTROL Source Key]i campi [!UICONTROL Source Value][!UICONTROL Target Key], e [!UICONTROL Target Value] è 228 caratteri.

## Modificare un segnale derivato {#edit}

<!-- t_tb_edit_derived.xml -->

Per modificare un [!UICONTROL derived signal]:

1. Passate il mouse sul segnale, quindi fate clic **[!UICONTROL Edit]**.
2. Apportate le modifiche necessarie a codice, chiave o valore, quindi fate clic **[!UICONTROL Save]** su.

## Eliminare un segnale derivato {#delete}

<!-- t_tb_delete_derived.xml -->

Per eliminare un [!UICONTROL derived signal], passate il mouse sul segnale, quindi fate clic **[!UICONTROL Delete]** su.
