---
description: I componenti di Gestione tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Dynamic Tag Manager e Adobe Launch), DIL, Akamai e il database di controllo.
seo-description: I componenti di Gestione tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Dynamic Tag Manager e Adobe Launch), DIL, Akamai e il database di controllo.
seo-title: Componenti per la gestione dei tag
solution: Audience Manager
title: Componenti per la gestione dei tag
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Componenti per la gestione dei tag{#tag-management-components}

I componenti di Gestione tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Dynamic Tag Manager e Adobe Launch), DIL, Akamai e il database di controllo.

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

Il portale client è l'interfaccia utente principale per la gestione di tag e dati. I clienti utilizzano il portale per lavorare con tag, creare caratteristiche e segmenti, impostare le destinazioni e monitorare le prestazioni delle campagne con i report.

## Contenitore DIL/TIM {#dil-tim}

Il [!UICONTROL DIL] contenitore consente di distribuire [!DNL Audience Manager] il codice di raccolta dati al sito Web. [!UICONTROL TIM] è Gestione dell'inserimento tag obsoleta. Non viene più utilizzato da [!DNL Audience Manager]. Al contrario, puoi utilizzare Gestione [tag](https://marketing.adobe.com/resources/help/en_US/dtm/) dinamica o l' [!DNL Audience Manager] estensione in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) per configurare e generare il codice contenitore che inserisci nelle pagine del tuo inventario. Il [!UICONTROL DTM] contenitore funziona con [!UICONTROL Data Information Library (DIL)] per raccogliere i dati dal sito e inviarli al [!DNL Audience Manager].

## Libreria di integrazione dei dati (DIL) {#dil}

La [Data Information Library](../../dil/dil-overview.md) (DIL) è un modulo API indipendente che raccoglie i dati dal sito Web. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta dei dati, l'integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina. [!UICONTROL DIL] esegue queste azioni automaticamente. Inoltre, [!UICONTROL DIL] è compatta. Si tratta di una libreria di codici indipendente che consente di ridurre la quantità di codice necessaria per raccogliere le informazioni. Infine, [!UICONTROL DIL] ti aiuta a integrarti [!DNL Audience Manager] con altri prodotti in [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utilizza [Akamai](https://www.akamai.com/html/about/index.html) per ospitare e distribuire il codice del contenitore dalla nostra piattaforma di gestione tag denominata [!UICONTROL TIM (Tag Insertion Manager)]. Tuttavia, la distribuzione del codice con [!UICONTROL TIM] è stata gradualmente eliminata a favore di [!UICONTROL Adobe Dynamic Tag Management] e [!UICONTROL Adobe Launch].

## Database di controllo {#control-database}

Database di controllo:

* Elabora l'input del client dal portale (ad esempio, creazione di caratteristiche e destinazioni).
* Trasmette i dati ad Akamai, che include i dati utilizzati per creare il modello contenitore e la destinazione per pubblicare iFrame.
* Restituisce i dati per i sistemi di reporting dell'interfaccia utente.

