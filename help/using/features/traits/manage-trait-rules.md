---
description: In Generatore di caratteristiche, il Generatore di espressioni consente di creare e testare regole che stabiliscano i requisiti di qualificazione dell'audience. Le regole sono composte da coppie chiave-valore come "color == blue" o "price > 100". Gli operatori di confronto stabiliscono la relazione tra chiavi e valori. Le espressioni booleane determinano la relazione tra i gruppi di regole.
seo-description: In Generatore di caratteristiche, il Generatore di espressioni consente di creare e testare regole che stabiliscano i requisiti di qualificazione dell'audience. Le regole sono composte da coppie chiave-valore come "color == blue" o "price > 100". Gli operatori di confronto stabiliscono la relazione tra chiavi e valori. Le espressioni booleane determinano la relazione tra i gruppi di regole.
seo-title: Gestione delle regole delle caratteristiche
solution: Audience Manager
title: Gestione delle regole delle caratteristiche
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---


# Gestione delle regole delle caratteristiche {#managing-trait-rules}

In [!UICONTROL Trait Builder], [!UICONTROL Expression Builder] consente di creare e sottoporre a test regole che stabiliscano i requisiti di qualificazione dell&#39;audience. Le regole sono coppie chiave-valore come `color == blue` o `price > 100`. Gli operatori di confronto stabiliscono la relazione tra chiavi e valori. [!DNL Boolean] le espressioni determinano la relazione tra i gruppi di regole.

<!-- c_tb_rules.xml -->

## Caratteristiche principali delle regole del segnale

![](assets/manage-trait-rules.png)

1. Le schede **[!UICONTROL Expression Builder]** o **[!UICONTROL Code View]** forniscono una panoramica delle regole nella caratteristica. La **[!UICONTROL Expression Builder]** scheda consente di creare regole con campi e menu a discesa. Consente di **[!UICONTROL Code View]** creare regole scrivendo manualmente tali espressioni come codice. L&#39;illustrazione qui sopra mostra una caratteristica semplice composta da un segnale che valuta i dati per una condizione valida in cui un codice Product Key è uguale a un valore specifico, in questo caso `color == "blue"`.

1. I campi e i controlli di questa sezione consentono di creare segnali da coppie chiave-valore e impostare la relazione tra di essi con un operatore di confronto. Sono necessari una chiave, un operatore e un valore.
1. Consente di [!UICONTROL Data Explorer Options] eseguire il backfill delle realizzazioni delle caratteristiche per i segnali.
   >[!NOTE]
   >
   >Questa opzione è disponibile solo per [!UICONTROL Data Explorer] i clienti. Per informazioni, contattate il vostro consulente Adobe.
1. Questa sezione mostra una stima delle realizzazioni delle caratteristiche per gli ultimi 7 giorni, per i segnali definiti in [!UICONTROL Expression Builder], per le caratteristiche con backfill e non-back.
   >[!NOTE]
   >
   >Questa opzione è disponibile solo per [!UICONTROL Data Explorer] i clienti. Per informazioni, contattate il vostro consulente Adobe.
1. I campi di prova consentono di convalidare combinazioni di regole di segnale o [!DNL URL]di utilizzare per l&#39;invio di dati a  Audience Manager.

## Creare una regola di caratteristica {#create-trait-rule}

Le regole (o espressioni) sono costituite da singoli o gruppi di coppie chiave-valore. Gli operatori di confronto impostano la relazione tra coppie chiave-valore. Per creare una regola, fornire una chiave, un valore, selezionare un operatore e fare clic **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Completare i campi richiesti nella **[!UICONTROL Basic Information]** sezione *prima* di creare le regole sulle caratteristiche.

1. Espandete la sezione e inserite una chiave e un nome di valore. **[!UICONTROL Trait Expression]** Questo crea un *`signal`*.
   >[!NOTE]
   >
   >Includete il `c_` prefisso (o qualsiasi altra convenzione di denominazione) per la variabile chiave se le chiamate dell’evento inviano dati a [!DNL Audience Manager] tale sintassi.
1. Selezionare un operatore [di](../../features/traits/trait-comparison-operators.md) confronto dal **[!UICONTROL Operator]** menu a discesa. L&#39;operatore di confronto valuta la relazione tra gli elementi di un segnale.
   >[!NOTE]
   >
   >L&#39; [!DNL Boolean] operatore stabilisce il rapporto tra più segnali [!UICONTROL OR] all&#39;interno ** di un gruppo e non può essere modificato.
1. Clic **[!UICONTROL Add Rule]**. La regola salvata viene visualizzata nell&#39;area di lavoro caratteristiche sopra i campi di immissione dati.

### Esempio {#example-trait-rule}

Nell&#39;esempio seguente, un utente ha creato una nuova regola per le caratteristiche basata sull&#39;ID prodotto. Per creare questa regola, l&#39;utente ha fornito la chiave `productkey` collegata con un operatore uguale ( `==`) al valore `2093`.
![](assets/tb_sample_rule1.png)

Facendo clic **[!UICONTROL Add Rule]** si salva e si sposta la caratteristica nell’ [!UICONTROL Expression Builder] area di lavoro.

![](assets/tb_sample_rule2.png)

## Creare un nuovo gruppo di regole {#create-rule-group}

Questa procedura descrive come creare un nuovo gruppo di regole.

<!-- t_tb_new_rule_group.xml -->

La caratteristica deve contenere almeno due regole prima di poter creare un nuovo gruppo di regole.

1. Portate il cursore sulla regola da spostare per evidenziarla.
1. Passate il puntatore del mouse sul bordo della regola evidenziata.
In questo modo la regola viene separata automaticamente dal gruppo corrente e spostata in un nuovo gruppo.
   >[!NOTE]
   >
   >Se spostate una regola in modo involontario, trascinatela di nuovo nel gruppo originale.
1. Selezionare un [!DNL Boolean] operatore ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) dal menu a discesa per impostare la relazione tra i gruppi di regole.

## Sposta regole tra i gruppi {#move-rules-between-groups}

Per spostare una regola, fate clic e trascinatela in un altro gruppo.

## Modifica di una caratteristica {#edit-trait}

Questa procedura descrive come modificare una caratteristica.

<!-- t_tb_edit.xml -->

1. Nel [!UICONTROL Traits] dashboard, passate il mouse sulla **[!UICONTROL Actions]** colonna relativa alla caratteristica da modificare. Vengono visualizzate le icone di gestione delle caratteristiche.
1. Fate clic sulla matita per modificare la caratteristica.

   ![](assets/tb_edit_trait.png)

## Eliminazione di una regola caratteristica {#delete-trait}

Questa procedura descrive come eliminare una regola per le caratteristiche.

<!-- t_tb_delete_rule.xml -->

1. Nel [!UICONTROL Traits] dashboard, passare il mouse sulle [!UICONTROL Actions] colonne per la caratteristica da modificare e fare clic sull&#39;icona della matita. Vengono visualizzate le icone di gestione delle caratteristiche.
1. Expand the [!UICONTROL Trait Expression] section.
1. Passate il puntatore del mouse sulla regola da eliminare e fate clic sull&#39;icona X. La regola viene eliminata immediatamente.

>[!MORELIKETHIS]
>
>* [Creare un nuovo gruppo di regole](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Sposta regole tra i gruppi](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Creare una regola di caratteristica](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Eliminazione di una regola caratteristica](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Sposta regole tra i gruppi](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

