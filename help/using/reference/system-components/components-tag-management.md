---
description: ' componenti di gestione tag Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Dynamic Tag Manager e  lancio del Adobe Experience Platform), DIL, Akamai e il database di controllo.'
seo-description: ' componenti di gestione tag Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Dynamic Tag Manager e  lancio del Adobe Experience Platform), DIL, Akamai e il database di controllo.'
seo-title: Componenti per la gestione dei tag
solution: Audience Manager
title: Componenti per la gestione dei tag
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 1%

---


# Componenti per la gestione dei tag{#tag-management-components}

 componenti di gestione tag Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Dynamic Tag Manager e  lancio del Adobe Experience Platform), DIL, Akamai e il database di controllo.

<!-- 

c_comptag.xml

 -->

 Audience Manager contiene i seguenti componenti:

* [Portale client](../../reference/system-components/components-tag-management.md#client-portal)
* [Contenitore DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Libreria informazioni dati (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Database di controllo](../../reference/system-components/components-tag-management.md#control-database)

## Portale client {#client-portal}

Il portale client è l&#39;interfaccia utente principale per la gestione di tag e dati. I clienti utilizzano il portale per lavorare con tag, creare caratteristiche e segmenti, impostare le destinazioni e monitorare le prestazioni delle campagne con i report.

## Contenitore DIL/TIM {#dil-tim}

Il [!UICONTROL DIL] contenitore consente di distribuire [!DNL Audience Manager] il codice di raccolta dati al sito Web. [!UICONTROL TIM] è Gestione dell&#39;inserimento tag obsoleta. Non viene più utilizzato da [!DNL Audience Manager]. Al contrario, potete utilizzare Gestione [tag](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) dinamica o l&#39; [!DNL Audience Manager] estensione in [Lancio](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Adobe Experience Platform per configurare e generare il codice contenitore che inserite nelle pagine del magazzino. Il [!UICONTROL DTM] contenitore funziona con [!UICONTROL Data Information Library (DIL)] per raccogliere i dati dal sito e inviarli al [!DNL Audience Manager].

## Libreria di integrazione dei dati (DIL) {#dil}

La [Data Information Library](../../dil/dil-overview.md) (DIL) è un modulo API indipendente che raccoglie i dati dal sito Web. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta dei dati, l&#39;integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina. [!UICONTROL DIL] esegue queste azioni automaticamente. Inoltre, [!UICONTROL DIL] è compatta. Si tratta di una libreria di codici indipendente che consente di ridurre la quantità di codice necessaria per raccogliere le informazioni. Infine, [!UICONTROL DIL] è utile [!DNL Audience Manager] integrare altri prodotti nell&#39;Experience Cloud [!DNL Adobe] .

## Akamai {#akamai}

[!DNL Audience Manager] utilizza [Akamai](https://www.akamai.com/html/about/index.html) per ospitare e distribuire il codice del contenitore dalla nostra piattaforma di gestione tag denominata [!UICONTROL TIM (Tag Insertion Manager)]. Tuttavia, la distribuzione del codice con [!UICONTROL TIM] è stata gradualmente eliminata a favore di [!DNL Adobe Dynamic Tag Management] e [!DNL Adobe Experience Platform Launch].

## Database di controllo {#control-database}

Database di controllo:

* Elabora l&#39;input del client dal portale (ad esempio, creazione di caratteristiche e destinazioni).
* Trasmette i dati ad Akamai, che include i dati utilizzati per creare il modello contenitore e per pubblicare l&#39;iFrame di destinazione.
* Restituisce i dati per i sistemi di reporting dell&#39;interfaccia utente.

