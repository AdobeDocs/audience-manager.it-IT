---
description: I componenti per la gestione dei tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Experience Platform Launch), DIL, Akamai e il database di controllo.
seo-description: I componenti per la gestione dei tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Experience Platform Launch), DIL, Akamai e il database di controllo.
seo-title: Componenti di Tag Management
solution: Audience Manager
title: Componenti di Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 'Componenti di sistema '
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 4%

---

# Componenti di Tag Management{#tag-management-components}

I componenti per la gestione dei tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Experience Platform Launch), DIL, Akamai e il database di controllo.

<!-- 

c_comptag.xml

 -->

L’Audience Manager contiene i seguenti componenti:

* [Portale client](../../reference/system-components/components-tag-management.md#client-portal)
* [Contenitore DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Libreria di informazioni sui dati (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Database di controllo](../../reference/system-components/components-tag-management.md#control-database)

## Portale client {#client-portal}

Il portale client è l’interfaccia utente principale per la gestione di tag e dati. I clienti utilizzano il portale per lavorare con tag, creare caratteristiche e segmenti, impostare destinazioni e monitorare le prestazioni della campagna tramite i rapporti.

## Contenitore DIL/TIM {#dil-tim}

Il contenitore [!UICONTROL DIL] consente di distribuire il codice di raccolta dati [!DNL Audience Manager] sul sito web. [!UICONTROL TIM] è il gestore dell’inserimento tag obsoleto. Non viene più utilizzato da [!DNL Audience Manager]. Al contrario, utilizza l’estensione [!DNL Audience Manager] in [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) per configurare e generare il codice contenitore inserito nelle pagine del tuo inventario.

## Libreria di integrazione dei dati (DIL) {#dil}

La [Libreria informazioni dati](../../dil/dil-overview.md) (DIL) è un modulo API autonomo che raccoglie dati dal tuo sito web. [!UICONTROL DIL] aiuta a eliminare la necessità di scrivere codice speciale per la raccolta dei dati, l’integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina. [!UICONTROL DIL] esegue automaticamente queste azioni. Inoltre, [!UICONTROL DIL] è compatto. Si tratta di una libreria di codici indipendente che aiuta a ridurre la quantità di codice necessario per raccogliere le informazioni. Infine, [!UICONTROL DIL] ti aiuta a integrare [!DNL Audience Manager] con altri prodotti nell&#39;Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] utilizza l’host  [](https://www.akamai.com/us/en/about/) Akamaito e consegna il codice contenitore dalla nostra piattaforma di gestione dei tag nota come  [!UICONTROL TIM (Tag Insertion Manager)]. Tuttavia, la distribuzione del codice con [!UICONTROL TIM] è stata gradualmente eliminata a favore di [!DNL Adobe Experience Platform Launch].

## Database di controllo {#control-database}

Database di controllo:

* Elabora l’input del client dal portale (ad esempio, creazione di caratteristiche e destinazioni).
* Trasmette i dati ad Akamai, che include i dati utilizzati per creare il modello di contenitore e la destinazione per la pubblicazione dell’iFrame.
* Restituisce i dati per i sistemi di reporting dell’interfaccia utente.
