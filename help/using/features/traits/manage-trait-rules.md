---
description: Nel Generatore di caratteristiche, il Generatore espressioni consente di creare e testare regole che determinano i requisiti di qualifica dell'audience. Le regole sono coppie chiave-valore quali "color = = blue" o "price > 100". Gli operatori di confronto stabiliscono la relazione tra chiavi e valori. Le espressioni booleane determinano la relazione tra gruppi di regole.
seo-description: Nel Generatore di caratteristiche, il Generatore espressioni consente di creare e testare regole che determinano i requisiti di qualifica dell'audience. Le regole sono coppie chiave-valore quali "color = = blue" o "price > 100". Gli operatori di confronto stabiliscono la relazione tra chiavi e valori. Le espressioni booleane determinano la relazione tra gruppi di regole.
seo-title: Gestione delle regole di caratteristica
solution: Audience Manager
title: Gestione delle regole di caratteristica
uuid: 827 d 4567-2 b 6 f -411 e-bd 5 c -9735 c 916291 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Gestione delle regole di caratteristica {#managing-trait-rules}

In [!UICONTROL Trait Builder], puoi [!UICONTROL Expression Builder] creare e testare regole che determinano i requisiti di qualifica dell&#39;audience. Le regole sono coppie chiave-valore, ad esempio `color == blue` o `price > 100`. Gli operatori di confronto stabiliscono la relazione tra chiavi e valori. [!DNL Boolean] Le espressioni determinano la relazione tra gruppi di regole.

<!-- c_tb_rules.xml -->

## Funzioni principali di regole di segnale descritte

![](assets/manage-trait-rules.png)

1. Le **[!UICONTROL Expression Builder]****[!UICONTROL Code View]** schede forniscono una panoramica delle regole nella caratteristica. La **[!UICONTROL Expression Builder]** scheda consente di creare regole con campi e menu a discesa. Consente **[!UICONTROL Code View]** di creare regole scrivendo manualmente tali espressioni come codice. L&#39;illustrazione qui sopra mostra una caratteristica semplice composta da un segnale che valuta i dati per una condizione di qualificazione in cui la chiave del prodotto corrisponde a un valore specifico, in questo caso `color == "blue"`.

1. I campi e i controlli di questa sezione consentono di creare segnali da coppie chiave-valore e impostare la relazione tra di essi con un operatore di confronto. Sono necessari una chiave, un operatore e un valore.
1. Consente [!UICONTROL Data Explorer Options] di riempire le implementazioni delle caratteristiche per i segnali.
   >[!NOTE]
   >
   >Questa opzione è disponibile solo per [!UICONTROL Data Explorer] i clienti. Per informazioni dettagliate, contattate il consulente Adobe.
1. Questa sezione mostra una stima delle caratteristiche delle caratteristiche per gli ultimi 7 giorni, per i segnali definiti in [!UICONTROL Expression Builder], per tratti con smartphone e non compilati.
   >[!NOTE]
   >
   >Questa opzione è disponibile solo per [!UICONTROL Data Explorer] i clienti. Per informazioni dettagliate, contattate il consulente Adobe.
1. I campi di prova consentono di convalidare combinazioni di regole di segnale o quelle [!DNL URL]che desideri utilizzare per inviare dati ad Audience Manager.

## Creare una regola Caratteristica {#create-trait-rule}

Le regole (o espressioni) sono costituite da singoli o gruppi di coppie chiave-valore. Gli operatori di confronto definiscono la relazione tra coppie chiave-valore. Per creare una regola, fornite una chiave, un valore, selezionate un operatore e fate clic **[!UICONTROL Add Rule]** su.

<!-- t_tb_create_rules.xml -->

Completate i campi richiesti nella **[!UICONTROL Basic Information]** sezione *prima* di creare le regole per le caratteristiche.

1. Espandete la **[!UICONTROL Trait Expression]** sezione e immettete una chiave e un nome di valore. Viene creata *`signal`*una.
   >[!NOTE]
   >
   >Includete il `c_` prefisso (o qualsiasi altra convenzione di denominazione) per la variabile key se le chiamate dell&#39;evento inviano dati all [!DNL Audience Manager] &#39;utilizzo di tale sintassi.
1. Selezionate un [operatore di confronto](../../features/traits/trait-comparison-operators.md) dal **[!UICONTROL Operator]** menu a discesa. L&#39;operatore di confronto valuta la relazione tra gli elementi di un segnale.
   >[!NOTE]
   >
   >[!DNL Boolean][!UICONTROL OR] L&#39;operatore stabilisce la relazione tra più segnali *all&#39;interno* di un gruppo e non può essere modificato.
1. Fai clic su **[!UICONTROL Add Rule]**. La regola salvata viene visualizzata nell&#39;area di lavoro delle caratteristiche sopra i campi di immissione dati.

### Esempio {#example-trait-rule}

Nell&#39;esempio seguente, un utente ha creato una nuova regola caratteristica basata sull&#39;ID prodotto. Per creare questa regola, l&#39;utente ha fornito al valore la chiave `productkey` collegata con un operatore uguale a ( `==`) `2093`.![](assets/tb_sample_rule1.png)


Facendo clic **[!UICONTROL Add Rule]** su di esso viene salvata e spostata la caratteristica nell&#39; [!UICONTROL Expression Builder] area di lavoro.

![](assets/tb_sample_rule2.png)

>[!MORE_ LIKE_ THIS]
>
>* [Creare un nuovo gruppo di regole](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Sposta regole tra gruppi](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eliminare una regola Caratteristica](../../features/traits/manage-trait-rules.md#delete-trait)


## Creare un nuovo gruppo di regole {#create-rule-group}

Questa procedura descrive come creare un nuovo gruppo di regole.

<!-- t_tb_new_rule_group.xml -->

Per poter creare un nuovo gruppo di regole, devi includere almeno due regole.

1. Portate il cursore sulla regola da spostare per evidenziarla.
1. Passa il cursore del mouse sul bordo della regola evidenziato.
La regola viene separata automaticamente dal gruppo corrente e la sposta in un nuovo gruppo.
   >[!NOTE]
   >
   >Se lo spostate non intenzionalmente, trascinate una regola sul gruppo originale.
1. Selezionate un [!DNL Boolean] operatore ( [!UICONTROL AND][!UICONTROL OR][!UICONTROL AND NOT],) dal menu a discesa per impostare la relazione tra i gruppi di regole.

>[!MORE_ LIKE_ THIS]
>
>* [Creare una regola Caratteristica](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Sposta regole tra gruppi](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eliminare una regola Caratteristica](../../features/traits/manage-trait-rules.md#delete-trait)


## Sposta regole tra gruppi {#move-rules-between-groups}

Per spostare una regola, fate clic su di essa e trascinatela in un altro gruppo.

>[!MORE_ LIKE_ THIS]
>
>* [Creare una regola Caratteristica](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Creare un nuovo gruppo di regole](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Eliminare una regola Caratteristica](../../features/traits/manage-trait-rules.md#delete-trait)


## Modificare una caratteristica {#edit-trait}

Questa procedura descrive come modificare una caratteristica.

<!-- t_tb_edit.xml -->

1. Nel [!UICONTROL Traits] dashboard, passate il mouse sulla **[!UICONTROL Actions]** colonna per la caratteristica da modificare. Vengono visualizzate le icone di gestione delle caratteristiche.
1. Fate clic sulla matita per modificare la caratteristica.

   ![](assets/tb_edit_trait.png)

## Eliminare una regola Caratteristica {#delete-trait}

Questa procedura descrive come eliminare una regola caratteristica.

<!-- t_tb_delete_rule.xml -->

1. Nel [!UICONTROL Traits] dashboard, passate il mouse sulle [!UICONTROL Actions] colonne della caratteristica da modificare e fate clic sull&#39;icona matita. Vengono visualizzate le icone di gestione delle caratteristiche.
1. Espandete [!UICONTROL Trait Expression] la sezione.
1. Passate il mouse sulla regola da eliminare e fate clic sull&#39;icona X. La regola viene eliminata immediatamente.