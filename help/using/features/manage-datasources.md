---
description: Per creare una nuova origine dati, vai a Dati audience > Origini dati > Aggiungi nuovo e completa i passaggi per ogni sezione descritta qui. Per creare un'origine dati sono necessarie autorizzazioni di amministratore.
keywords: cdf; feed dati personalizzato
seo-description: Per creare una nuova origine dati, vai a Dati audience > Origini dati > Aggiungi nuovo e completa i passaggi per ogni sezione descritta qui. Per creare un'origine dati sono necessarie autorizzazioni di amministratore.
seo-title: Creare un'origine dati
solution: Audience Manager
title: Creare un'origine dati
uuid: 4 df 65 bcb -9 ad 9-4 b 72-a 71 e -8918 b 43 d 4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Gestisci origini dati {#manage-data-sources}

## Creare un&#39;origine dati {#create-data-source}

Per creare una nuova origine dati, vai a **[!UICONTROL Audience Data > Data Sources > Add New]** e completa i passaggi per ogni sezione descritta qui. Per creare un&#39;origine dati sono necessarie autorizzazioni di amministratore.

<!-- create-datasource.xml -->

>[!TIP]
>
>Consultate [Impostazioni origine dati e Opzioni](../features/datasources-list-and-settings.md#settings-menu-options) menu per le descrizioni di questi diversi controlli.

## Dettagli origine dati {#details}

Per completare la [!UICONTROL Data Source Details] sezione:

1. Denominate l&#39;origine dati.
1. *(Facoltativo)* Descrivete l&#39;origine dati. Una descrizione concisa consente di definire il ruolo o lo scopo dell&#39;origine dati.
1. Fornite un codice di integrazione. In genere, i codici di integrazione sono facoltativi. Sono necessari quando si desidera:

   * [Crea un&#39;origine dati cross-device](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Usa il [servizio Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Utilizzare le regole di unione [profilo](../features/profile-merge-rules/merge-rules-start.md).

1. Scegliete un **[!UICONTROL ID Type]**. Le opzioni Tipo ID includono:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obbligatorio per creare un [!UICONTROL Profile Merge Rule]). Nota, per alcuni clienti questa selezione mostra le **[!UICONTROL ID Definition]** opzioni.

1. Scegliete un **[!UICONTROL ID Definition]** &#39;opzione. Le opzioni includono:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Controlli sull&#39;esportazione dei dati {#export-controls}

[I controlli sull&#39;esportazione dei dati](../features/data-export-controls.md) sono regole di classificazione facoltative che puoi applicare a un&#39;origine dati e a una destinazione. Essi non potranno inviare dati a una destinazione quando questa azione viola una privacy dei dati o utilizzano l&#39;accordo. Ignorate questa sezione se non utilizzate [!UICONTROL Data Export Controls].

## Impostazioni origine dati {#settings}

Queste impostazioni determinano in che modo un&#39;origine dati viene identificata, utilizzata e condivisa. Potete inoltre attivare la generazione di rapporti degli errori per i file di dati in entrata. Per completare la [!UICONTROL Data Source Settings] sezione:

1. Seleziona una [!UICONTROL Data Source Setting] casella di controllo per applicare un&#39;opzione alla tua origine dati.
2. Fai clic su **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Impostazioni origine dati e Opzioni menu](../features/datasources-list-and-settings.md#settings-menu-options)


## Eliminare un&#39;origine dati {#delete-data-source}

<!-- t_datasource_delete.xml -->

Eliminare un&#39;origine dati non più necessaria.

>[!NOTE]
>
>Tenete presente le seguenti limitazioni:
>
>* Non puoi eliminare una [caratteristica di tipo Pubblico attivo o Origine dati](../features/traits/client-activity-synced-audience-traits.md).
>* Per i clienti che usano Adobe Analytics: Audience Manager non consente di eliminare le origini dati create automaticamente dalle suite [!DNL Analytics] di rapporti. Utilizzate il [servizio core](https://marketing.adobe.com/resources/help/en_US/mcloud/) per demappare queste origini dati.


1. Fate clic **[!UICONTROL Audience Data]** su &gt; **[!UICONTROL Data Sources]**.
1. Seleziona la casella di controllo accanto a una o più origini dati.
Potete utilizzare la [!UICONTROL Search] casella per individuare le origini dati desiderate se disponete di un elenco lungo.
1. Fate clic ![](assets/icon_trash.png)su, quindi confermate l&#39;eliminazione.