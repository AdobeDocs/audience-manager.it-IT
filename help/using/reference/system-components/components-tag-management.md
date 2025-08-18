---
description: I componenti per la gestione dei tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Adobe Experience Platform Launch), DIL, Akamai e il database di controllo.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Componenti Tag Management
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Componenti Tag Management{#tag-management-components}

I componenti per la gestione dei tag di Audience Manager includono il portale client, Adobe Tag Manager (obsoleto a favore di Tag Adobe Experience Platform), DIL, Akamai e il database di controllo.

<!-- 

c_comptag.xml

 -->

Audience Manager contiene i seguenti componenti:

* [Portale client](../../reference/system-components/components-tag-management.md#client-portal)
* [Contenitore DIL/TIM](../../reference/system-components/components-tag-management.md#dil-tim)
* [Libreria informazioni dati (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Database di controllo](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

Il portale client è l’interfaccia utente principale per la gestione dei tag e dei dati. I clienti utilizzano il portale per lavorare con i tag, creare caratteristiche e segmenti, impostare le destinazioni e monitorare le prestazioni delle campagne con i rapporti.

## Contenitore DIL/TIM {#dil-tim}

Il contenitore [!UICONTROL DIL] consente di distribuire il codice di raccolta dati [!DNL Audience Manager] nel sito Web. [!UICONTROL TIM] è Tag Insertion Manager obsoleto. Non è più utilizzato da [!DNL Audience Manager]. Puoi invece utilizzare l&#39;estensione [!DNL Audience Manager] in [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) per configurare e generare il codice contenitore inserito nelle pagine del tuo inventario.

## Data Integration Library (DIL) {#dil}

La [Data Information Library](../../dil/dil-overview.md) (DIL) è un modulo API autonomo che raccoglie dati dal sito Web. [!UICONTROL DIL] elimina la necessità di scrivere codice speciale per la raccolta dati, l&#39;integrazione, la lettura dei valori dei cookie e il recupero dei dati della pagina. [!UICONTROL DIL] esegue queste azioni automaticamente. Inoltre, [!UICONTROL DIL] è compatto. Si tratta di una libreria di codice autonoma che consente di ridurre la quantità di codice necessario per raccogliere le informazioni. Infine, [!UICONTROL DIL] ti aiuta a integrare [!DNL Audience Manager] con altri prodotti nell&#39;Experience Cloud [!DNL Adobe].

## Akamai {#akamai}

[!DNL Audience Manager] utilizza [Akamai](https://www.akamai.com/us/en/about/) per ospitare e consegnare il codice contenitore dalla piattaforma di gestione dei tag [!UICONTROL TIM (Tag Insertion Manager)]. Tuttavia, la distribuzione del codice con [!UICONTROL TIM] è stata gradualmente eliminata a favore di [!DNL Adobe Experience Platform Tags].

## Database di controllo {#control-database}

Il database di controllo:

* Elabora l’input del client dal portale (ad esempio, creando caratteristiche e destinazioni).
* Trasmette i dati ad Akamai, che include i dati utilizzati per generare il modello di contenitore e l’iFrame di pubblicazione della destinazione.
* Restituisce i dati per i sistemi di reporting dell’interfaccia utente.
