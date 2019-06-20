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


# Componenti gestione tag{#tag-management-components}

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

## Portale client {#client-portal}

Il portale dei client è l&#39;interfaccia utente principale (interfaccia utente) per i tag e la gestione dei dati. I clienti usano il portale per lavorare con i tag, creare caratteristiche e segmenti, impostare destinazioni e monitorare le prestazioni delle campagne con i rapporti.

## Contenitore DIL/TIM {#dil-tim}

[!UICONTROL DIL] Il contenitore consente di distribuire [!DNL Audience Manager] il codice di raccolta dati sul sito Web. [!UICONTROL TIM] è il manager inserimento tag obsoleto. Non viene più utilizzato [!DNL Audience Manager]da. Invece, puoi utilizzare [Gestione tag dinamica](https://marketing.adobe.com/resources/help/en_US/dtm/) o l&#39; [!DNL Audience Manager] estensione in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) per configurare e generare il codice contenitore inserito sulle pagine dell&#39;inventario. [!UICONTROL DTM] Il contenitore funziona con il [!UICONTROL Data Information Library (DIL)] metodo per raccogliere dati dal sito e inviarli [!DNL Audience Manager]a.

## Libreria di integrazione dei dati (DIL) {#dil}

La libreria Informazioni [sui dati (DIL)](../../dil/dil-overview.md) è un modulo API autonomo che raccoglie dati dal sito Web. [!UICONTROL DIL] aiuta a eliminare la necessità di scrivere codici speciali per la raccolta di dati, l&#39;integrazione, i valori dei cookie di lettura e il recupero dei dati delle pagine. [!UICONTROL DIL] esegue queste azioni automaticamente. Inoltre, è [!UICONTROL DIL] compatta. Si tratta di una libreria di codici standalone che consente di ridurre la quantità di codice necessaria per raccogliere informazioni. Infine [!UICONTROL DIL] , ti aiuta a integrare [!DNL Audience Manager] con altri prodotti in [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utilizza [Akamai](https://www.akamai.com/html/about/index.html) per ospitare e fornire codice contenitore dalla nostra piattaforma di gestione tag nota come [!UICONTROL TIM (Tag Insertion Manager)]. Tuttavia, la distribuzione di codice con [!UICONTROL TIM] è stata graduale a favore [!UICONTROL Adobe Dynamic Tag Management] e [!UICONTROL Adobe Launch].

## Database Database {#control-database}

Database di controllo:

* Elabora l&#39;input client dal portale (ad esempio, la creazione di caratteristiche e destinazioni).
* Trasmette dati ad Akamai, che includono dati utilizzati per creare il modello contenitore e l&#39;iframe di pubblicazione della destinazione.
* Restituisce i dati per i sistemi di reporting dell&#39;interfaccia utente.

