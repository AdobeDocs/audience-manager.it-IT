---
description: In Generatore di caratteristiche, il Generatore di espressioni consente di creare e testare regole che stabiliscono i requisiti di qualificazione del pubblico. Le regole sono costituite da coppie chiave-valore come "colore == blu" o "prezzo &gt; 100". Gli operatori di confronto stabiliscono la relazione tra chiavi e valori. Le espressioni booleane determinano la relazione tra i gruppi di regole.
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: Gestione delle regole delle caratteristiche
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 0%

---

# Gestione delle regole delle caratteristiche {#managing-trait-rules}

In [!UICONTROL Trait Builder], [!UICONTROL Expression Builder] consente di creare e testare regole che stabiliscono i requisiti di qualificazione del pubblico. Le regole sono costituite da coppie chiave-valore come `color == blue` o `price > 100`. Gli operatori di confronto stabiliscono la relazione tra chiavi e valori. [!DNL Boolean] espressioni determinano la relazione tra gruppi di regole.

<!-- c_tb_rules.xml -->

## Descrizione delle funzioni principali delle regole del segnale

![](assets/manage-trait-rules.png)

1. Le schede **[!UICONTROL Expression Builder]** o **[!UICONTROL Code View]** forniscono una panoramica delle regole nella caratteristica. La scheda **[!UICONTROL Expression Builder]** consente di creare regole con campi e menu a discesa. **[!UICONTROL Code View]** consente di creare regole scrivendo manualmente tali espressioni come codice. L&#39;illustrazione precedente mostra una caratteristica semplice composta da un segnale che valuta i dati per una condizione di idoneità in cui un codice Product Key è uguale a un valore specifico, in questo caso `color == "blue"`.

1. I campi e i controlli di questa sezione consentono di creare segnali da coppie chiave-valore e di impostare la relazione tra di essi con un operatore di confronto. È necessario specificare una chiave, un operatore e un valore.
1. [!UICONTROL Data Explorer Options] consente di retrocompilare le realizzazioni delle caratteristiche per i segnali.

   >[!NOTE]
   >
   >Questa opzione è disponibile solo per i clienti [!UICONTROL Data Explorer]. Contatta il tuo consulente Adobe per ulteriori dettagli.

1. Questa sezione mostra una stima delle realizzazioni delle caratteristiche per gli ultimi 7 giorni, per i segnali definiti in [!UICONTROL Expression Builder], per le caratteristiche precompilate e non precompilate.

   >[!NOTE]
   >
   >Questa opzione è disponibile solo per i clienti [!UICONTROL Data Explorer]. Contatta il tuo consulente Adobe per ulteriori dettagli.

1. I campi di test ti consentono di convalidare combinazioni di regole di segnale o i [!DNL URL] che desideri utilizzare quando invii dati ad Audience Manager.

## Creare una regola di caratteristiche {#create-trait-rule}

Le regole (o espressioni) sono costituite da singoli o gruppi di coppie chiave-valore. Gli operatori di confronto impostano la relazione tra coppie chiave-valore. Per creare una regola, fornisci una chiave, un valore, seleziona un operatore e fai clic su **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Completa i campi obbligatori nella sezione **[!UICONTROL Basic Information]** *prima* di creare le regole delle caratteristiche.

1. Espandere la sezione **[!UICONTROL Trait Expression]** e immettere una chiave e un nome di valore. Verrà creato un *`signal`*.

   >[!NOTE]
   >
   >Includi il prefisso `c_` (o qualsiasi altra convenzione di denominazione) per la variabile chiave se le chiamate dell&#39;evento inviano i dati a [!DNL Audience Manager] utilizzando tale sintassi.

1. Seleziona un operatore di confronto [&#128279;](../../features/traits/trait-comparison-operators.md) dal menu a discesa **[!UICONTROL Operator]**. L’operatore di confronto valuta la relazione tra gli elementi in un segnale.

   >[!NOTE]
   >
   >L&#39;operatore [!DNL Boolean] [!UICONTROL OR] stabilisce la relazione tra più segnali *all&#39;interno di un gruppo* e non può essere modificato.

1. Fare clic su **[!UICONTROL Add Rule]**. La regola salvata viene visualizzata nell’area di lavoro delle caratteristiche sopra i campi di immissione dei dati.

### Esempio {#example-trait-rule}

Nell’esempio seguente, un utente ha creato una nuova regola di caratteristiche in base all’ID prodotto. Per generare questa regola, l&#39;utente ha fornito la chiave `productkey` collegata con un operatore uguale a ( `==`) al valore `2093`.

![](assets/tb_sample_rule1.png)

Facendo clic su **[!UICONTROL Add Rule]**, la caratteristica viene salvata e spostata nell&#39;area di lavoro [!UICONTROL Expression Builder].

![](assets/tb_sample_rule2.png)

## Crea un nuovo gruppo di regole {#create-rule-group}

Questa procedura descrive come creare un nuovo gruppo di regole.

<!-- t_tb_new_rule_group.xml -->

La caratteristica deve contenere almeno due regole prima di poter creare un nuovo gruppo di regole.

1. Spostare il cursore sulla regola che si desidera spostare per evidenziarla.
1. Passa il puntatore del mouse sul bordo della regola evidenziato.

   In questo modo la regola viene automaticamente separata dal relativo gruppo corrente e spostata in un nuovo gruppo.

   >[!NOTE]
   >
   >Se si sposta una regola involontariamente, trascinarla nuovamente nel gruppo originale.

1. Selezionare un operatore [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) dal menu a discesa per impostare la relazione tra i gruppi di regole.

## Sposta regole tra gruppi {#move-rules-between-groups}

Per spostare una regola, fare clic su di essa e trascinarla in un altro gruppo.

## Modificare una caratteristica {#edit-trait}

Questa procedura descrive come modificare una caratteristica.

<!-- t_tb_edit.xml -->

1. Nel dashboard [!UICONTROL Traits], passa il cursore del mouse sulla colonna **[!UICONTROL Actions]** per la caratteristica da modificare. Vengono visualizzate le icone di gestione delle caratteristiche.
1. Fai clic sulla matita per modificare la caratteristica.

   ![](assets/tb_edit_trait.png)

## Eliminare una regola di caratteristiche {#delete-trait}

Questa procedura descrive come eliminare una regola delle caratteristiche.

<!-- t_tb_delete_rule.xml -->

1. Nel dashboard [!UICONTROL Traits], passa il puntatore del mouse sulle colonne [!UICONTROL Actions] della caratteristica che desideri modificare e fai clic sull&#39;icona della matita. Vengono visualizzate le icone di gestione delle caratteristiche.
1. Espandere la sezione [!UICONTROL Trait Expression].
1. Passa il puntatore del mouse sulla regola da eliminare e fai clic sull’icona X. La regola viene eliminata immediatamente.

>[!MORELIKETHIS]
>
>* [Crea un nuovo gruppo di regole](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Sposta regole tra gruppi](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Creare una regola di caratteristiche](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Eliminare una regola di caratteristiche](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Sposta regole tra gruppi](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
