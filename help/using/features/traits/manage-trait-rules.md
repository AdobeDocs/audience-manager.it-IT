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


# Managing Trait Rules {#managing-trait-rules}

In [!UICONTROL Trait Builder], the [!UICONTROL Expression Builder] lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as `color == blue` or `price > 100`. Gli operatori di confronto stabiliscono la relazione tra chiavi e valori. [!DNL Boolean] Le espressioni determinano la relazione tra gruppi di regole.

<!-- c_tb_rules.xml -->

## Funzioni principali di regole di segnale descritte

![](assets/manage-trait-rules.png)

1. The **[!UICONTROL Expression Builder]** or **[!UICONTROL Code View]** tabs provide an overview of the rules in your trait. The **[!UICONTROL Expression Builder]** tab lets you create rules with fields and drop-down menus. The **[!UICONTROL Code View]** lets you create rules by manually writing those expressions as code. The illustration above shows a simple trait composed of a signal that evaluates data for a qualifying condition where a product key equals a specific value, in this case `color == "blue"`.

1. I campi e i controlli di questa sezione consentono di creare segnali da coppie chiave-valore e impostare la relazione tra di essi con un operatore di confronto. Sono necessari una chiave, un operatore e un valore.
1. The [!UICONTROL Data Explorer Options] allow you to backfill trait realizations for your signals.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Per informazioni dettagliate, contattate il consulente Adobe.
1. This section shows you an estimation of trait realizations for the past 7 days, for the signals defined in the [!UICONTROL Expression Builder], for backfilled and non-backfilled traits.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Per informazioni dettagliate, contattate il consulente Adobe.
1. The test fields let you validate combinations of signal rules or the [!DNL URL]s that you want to use when sending data to Audience Manager.

## Create a Trait Rule {#create-trait-rule}

Le regole (o espressioni) sono costituite da singoli o gruppi di coppie chiave-valore. Gli operatori di confronto definiscono la relazione tra coppie chiave-valore. To create a rule,provide a key, a value, select an operator, and click **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Complete the required fields in the **[!UICONTROL Basic Information]** section *before* creating trait rules.

1. Expand the **[!UICONTROL Trait Expression]** section and enter a key and value name. This creates a *`signal`*.
   >[!NOTE]
   >
   >Include the `c_` prefix (or any other naming convention) for key variable if your event calls send data to [!DNL Audience Manager] using that syntax.
1. Select a [comparison operator](../../features/traits/trait-comparison-operators.md) from the **[!UICONTROL Operator]** dropdown. L'operatore di confronto valuta la relazione tra gli elementi di un segnale.
   >[!NOTE]
   >
   >[!DNL Boolean][!UICONTROL OR] L'operatore stabilisce la relazione tra più segnali *all'interno* di un gruppo e non può essere modificato.
1. Fai clic su **[!UICONTROL Add Rule]**. La regola salvata viene visualizzata nell'area di lavoro delle caratteristiche sopra i campi di immissione dati.

### Esempio {#example-trait-rule}

Nell'esempio seguente, un utente ha creato una nuova regola caratteristica basata sull'ID prodotto. To build this rule, the user provided the key `productkey` linked with an equals operator ( `==`) to the value `2093`.
![](assets/tb_sample_rule1.png)

Clicking **[!UICONTROL Add Rule]** saves and moves the trait into the [!UICONTROL Expression Builder] workspace.

![](assets/tb_sample_rule2.png)

>[!MORE_ LIKE_ THIS]
>
>* [Creare un nuovo gruppo di regole](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Sposta regole tra gruppi](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eliminare una regola Caratteristica](../../features/traits/manage-trait-rules.md#delete-trait)


## Create a New Rule Group {#create-rule-group}

Questa procedura descrive come creare un nuovo gruppo di regole.

<!-- t_tb_new_rule_group.xml -->

Per poter creare un nuovo gruppo di regole, devi includere almeno due regole.

1. Portate il cursore sulla regola da spostare per evidenziarla.
1. Passa il cursore del mouse sul bordo della regola evidenziato.
La regola viene separata automaticamente dal gruppo corrente e la sposta in un nuovo gruppo.
   >[!NOTE]
   >
   >Se lo spostate non intenzionalmente, trascinate una regola sul gruppo originale.
1. Select a [!DNL Boolean] operator ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) from the drop-down menu to set the relationship between the rule groups.

>[!MORE_ LIKE_ THIS]
>
>* [Creare una regola Caratteristica](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Sposta regole tra gruppi](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Eliminare una regola Caratteristica](../../features/traits/manage-trait-rules.md#delete-trait)


## Move Rules Between Groups {#move-rules-between-groups}

Per spostare una regola, fate clic su di essa e trascinatela in un altro gruppo.

>[!MORE_ LIKE_ THIS]
>
>* [Creare una regola Caratteristica](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Creare un nuovo gruppo di regole](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Eliminare una regola Caratteristica](../../features/traits/manage-trait-rules.md#delete-trait)


## Edit a Trait {#edit-trait}

Questa procedura descrive come modificare una caratteristica.

<!-- t_tb_edit.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the trait you want to edit. Vengono visualizzate le icone di gestione delle caratteristiche.
1. Fate clic sulla matita per modificare la caratteristica.

   ![](assets/tb_edit_trait.png)

## Delete a Trait Rule {#delete-trait}

Questa procedura descrive come eliminare una regola caratteristica.

<!-- t_tb_delete_rule.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the [!UICONTROL Actions] columns for the trait you want to edit and click the pencil icon. Vengono visualizzate le icone di gestione delle caratteristiche.
1. Expand the [!UICONTROL Trait Expression] section.
1. Passate il mouse sulla regola da eliminare e fate clic sull'icona X. La regola viene eliminata immediatamente.