---
description: I componenti Gestione tag Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Dynamic Tag Manager e Adobe Launch), DIL, Akamai e il database di controllo.
seo-description: I componenti Gestione tag Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Dynamic Tag Manager e Adobe Launch), DIL, Akamai e il database di controllo.
seo-title: Componenti gestione tag
solution: Audience Manager
title: Componenti gestione tag
uuid: e 5059478-6 ba 7-4 e 1 a-afec-e 41 ad 7 a 27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Tag Management Components{#tag-management-components}

I componenti Gestione tag Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Dynamic Tag Manager e Adobe Launch), DIL, Akamai e il database di controllo.

<!-- 

c_comptag.xml

 -->

Audience Manager contiene i seguenti componenti:

* [Portale client](../../reference/system-components/components-tag-management.md#client-portal)
* [Contenitore DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Libreria dati dati (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Database Database](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

Il portale dei client è l'interfaccia utente principale (interfaccia utente) per i tag e la gestione dei dati. I clienti usano il portale per lavorare con i tag, creare caratteristiche e segmenti, impostare destinazioni e monitorare le prestazioni delle campagne con i rapporti.

## DIL/TIM Container {#dil-tim}

[!UICONTROL DIL] Il contenitore consente di distribuire [!DNL Audience Manager] il codice di raccolta dati sul sito Web. [!UICONTROL TIM] è il manager inserimento tag obsoleto. It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. [!UICONTROL DTM] Il contenitore funziona con il [!UICONTROL Data Information Library (DIL)] metodo per raccogliere dati dal sito e inviarli [!DNL Audience Manager]a.

## Libreria di integrazione dei dati (DIL) {#dil}

The [Data Information Library](../../dil/dil-overview.md) (DIL) is a self-contained API module that collects data from your website. [!UICONTROL DIL] aiuta a eliminare la necessità di scrivere codici speciali per la raccolta di dati, l'integrazione, i valori dei cookie di lettura e il recupero dei dati delle pagine. [!UICONTROL DIL] esegue queste azioni automaticamente. Additionally, [!UICONTROL DIL] is compact. Si tratta di una libreria di codici standalone che consente di ridurre la quantità di codice necessaria per raccogliere informazioni. Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utilizza [Akamai](https://www.akamai.com/html/about/index.html) per ospitare e fornire codice contenitore dalla nostra piattaforma di gestione tag nota come [!UICONTROL TIM (Tag Insertion Manager)]. However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## Control Database {#control-database}

Database di controllo:

* Elabora l'input client dal portale (ad esempio, la creazione di caratteristiche e destinazioni).
* Trasmette dati ad Akamai, che includono dati utilizzati per creare il modello contenitore e l'iframe di pubblicazione della destinazione.
* Restituisce i dati per i sistemi di reporting dell'interfaccia utente.

