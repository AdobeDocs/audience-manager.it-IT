---
description: Domande e problemi comuni relativi a prodotto e funzioni.
keywords: cookie di audience manager
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: Domande frequenti su funzioni e funzionalità del prodotto
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 87%

---

# Domande frequenti su funzioni e funzionalità del prodotto{#product-features-and-functions-faq}

Domande e problemi comuni relativi a prodotto e funzioni.

 

<!-- 

faq_features_functions.xml

 -->

**Qual è il mio ID organizzazione e come posso trovarlo?**

L’*`Organization ID`* è un ID univoco che consente ad [!DNL Audience Manager] e [!DNL Adobe Experience Cloud] di identificare la tua organizzazione. È composto da una stringa alfanumerica di 24 caratteri sensibile a maiuscole e minuscole seguita da [!UICONTROL @AdobeOrg].

Per esempio, un *`Organization ID`* ha questo aspetto: `1FD6776A524453CC0A490D44@AdobeOrg`.

L’*`Organization ID`* viene utilizzato dall’API [DIL](../dil/dil-overview.md) di Audience Manager, da [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) e da altre soluzioni [!DNL Experience Cloud]. Gli utenti con autorizzazioni di amministratore possono trovare l’*`Organization ID`* in [!DNL Adobe Admin Console]. Consulta [Administration - User Management FAQ](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it).

 

**Posso creare caratteristiche o destinazioni in blocco?**

Sì. Consulta [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Gli strumenti [!UICONTROL Bulk Management Tools] *non sono* supportati da [!DNL Audience Manager]. Sono forniti solo per comodità e come cortesia. Per modifiche in blocco, ti consigliamo invece di utilizzare le [API di Audience Manager](../api/api.md).

 

**Durante l&#39;esportazione di un ID bulk in una destinazione, mancano alcuni ID cliente. Perché succede?**

Quando un ID dispositivo ([AAM UUID](../reference/ids-in-aam.md)) è collegato a più ID CRM ([DPUUID](../reference/ids-in-aam.md)), viene esportato solo il mapping più recente. Per questo motivo è possibile che venga esportato un numero di ID dispositivo inferiore al previsto.

 

**[!DNL Audience Manager] può ridurre la necessità di tag o pixel di terze parti e migliorare i tempi di caricamento delle pagine?**

Se [!DNL Audience Manager] è integrato con il tuo partner dati di terze parti, puoi sostituire i suoi pixel e tag con una chiamata ID server-to-server ad [!DNL Audience Manager]. In questo caso, [!DNL Audience Manager] attiverebbe una singola chiamata ID la prima volta che vede un utente e sincronizzerebbe tali informazioni con il tuo partner di terze parti. Questo elimina la necessità di effettuare più chiamate pixel da ogni pagina. La riduzione delle chiamate pixel può migliorare i tempi di caricamento delle pagine.

 

**Mi sono iscritto a un feed di dati. Dove vengono memorizzati i dati?**

Il feed di dati e tutte le caratteristiche in esso contenute vengono visualizzati come sottocartelle e caratteristiche in [!DNL Audience Manager]. Vai a **[!UICONTROL Audience Data > Traits]** ed espandi la cartella [!UICONTROL 3rd-Party Data] per visualizzare le caratteristiche o creare segmenti e modelli con tali dati.

 

**Che cosa è [!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager utilizzava [!UICONTROL Tag Insertion Manager] (TIM) per creare e gestire [!UICONTROL data collection code (DIL)]. Questa funzionalità è obsoleta ed è stata sostituita prima da [!UICONTROL Dynamic Tag Manager (DTM)] e successivamente da [!DNL Adobe Experience Platform Tags]. Per ulteriori informazioni, vedere [Tag Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it).

 

**Quali sono le differenze tra Modelli algoritmici e Raccomandazioni sulle caratteristiche? Quando dovrei usare uno o l’altro?**

**Modelli algoritmici**

I Modelli algoritmici non solo individuano le caratteristiche più influenti, ma assegnano inoltre agli utenti un punteggio in base a tali caratteristiche e a ciascun utente un punteggio individuale. In seguito puoi creare caratteristiche algoritmiche per eseguire il targeting degli utenti. Con i controlli di precisione e portata nel Generatore di caratteristiche, puoi specificare di quali utenti desideri effettuare il targeting tra tutti coloro che hanno le caratteristiche influenti.

I Modelli algoritmici ti consentono di selezionare gli utenti a diversi livelli di precisione e di verificare in Audience Lab quale gruppo di utenti effettua le migliori conversioni. Consulta il caso d’uso dettagliato in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

In Modelli algoritmici, il modello viene eseguito ogni 8 giorni e aggiorna gli utenti qualificati per le caratteristiche algoritmiche.

**Raccomandazioni sulle caratteristiche**

Le Raccomandazioni sulle caratteristiche sono un modo rapido per ottenere informazioni su altre caratteristiche simili a quelle utilizzate in un segmento.

Dovresti utilizzare le Raccomandazioni sulle caratteristiche quando:

* Hai bisogno di informazioni rapide durante la creazione di un segmento;
* Utilizzi segmenti per campagne brevi o quando desideri eliminare rapidamente il pubblico che effettua la conversione;
* Stai cercando di massimizzare la portata.

 

**C’è qualche differenza tra i segmenti di Adobe Analytics e Audience Manager?**

Sì, leggi [Understanding Segments in Analytics and Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=it) per una descrizione dettagliata delle differenze.
