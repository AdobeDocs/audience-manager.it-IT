---
description: I componenti per la gestione dei tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Experience Platform Launch), DIL, Akamai e il database di controllo.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Componenti di Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---

# Componenti di Tag Management{#tag-management-components}

I componenti di gestione dei tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Experience Platform Tags), DIL, Akamai e il database di controllo.

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

La [!UICONTROL DIL] implementazione dei contenitori [!DNL Audience Manager] codice di raccolta dati sul sito web. [!UICONTROL TIM] è il gestore dell’inserimento tag obsoleto. Non viene più utilizzato da [!DNL Audience Manager]. Invece, puoi utilizzare la [!DNL Audience Manager] estensione in [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) per configurare e generare il codice contenitore inserito nelle pagine del tuo inventario.

## Libreria di integrazione dei dati (DIL) {#dil}

La [Libreria di informazioni sui dati](../../dil/dil-overview.md) (DIL) è un modulo API autonomo che raccoglie dati dal sito web. [!UICONTROL DIL] aiuta a eliminare la necessità di scrivere codice speciale per la raccolta dei dati, l’integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina. [!UICONTROL DIL] esegue automaticamente queste azioni. Inoltre, [!UICONTROL DIL] è compatto. Si tratta di una libreria di codici indipendente che aiuta a ridurre la quantità di codice necessario per raccogliere le informazioni. Infine, [!UICONTROL DIL] consente di integrare [!DNL Audience Manager] con altri prodotti [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] utilizza [Akamai](https://www.akamai.com/us/en/about/) per ospitare e consegnare il codice contenitore dalla nostra piattaforma di gestione tag denominata [!UICONTROL TIM (Tag Insertion Manager)]. Tuttavia, distribuisci il codice con [!UICONTROL TIM] è stato gradualmente eliminato a favore di [!DNL Adobe Experience Platform Tags].

## Database di controllo {#control-database}

Database di controllo:

* Elabora l’input del client dal portale (ad esempio, creazione di caratteristiche e destinazioni).
* Trasmette i dati ad Akamai, che include i dati utilizzati per creare il modello di contenitore e la destinazione per la pubblicazione dell’iFrame.
* Restituisce i dati per i sistemi di reporting dell’interfaccia utente.
