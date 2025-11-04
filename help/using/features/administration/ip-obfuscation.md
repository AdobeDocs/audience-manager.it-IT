---
description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: Offuscamento indirizzo IP
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 12%

---

# Offuscamento indirizzo IP {#ip-obfuscation}

Utilizza questa funzione per offuscare gli indirizzi IP raccolti in Audience Manager.

## Panoramica e metodologia {#overview-and-methodology}

La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.

### Metodologia di offuscamento dell’IP

Seguendo i principi di &quot;Privacy By Design&quot;, Adobe Audience Manager consente ai clienti di abilitare l’offuscamento dell’IP dall’interfaccia utente, sia a livello globale in tutte le aree geografiche che per specifici paesi. Quando abiliti questa impostazione, l’ultimo ottetto (l’ultima parte) dell’indirizzo IP viene eliminato immediatamente quando l’indirizzo IP viene acquisito in Audience Manager. Audience Manager elimina questa parte dell’indirizzo IP prima dell’elaborazione (incluso prima di qualsiasi ricerca geografica facoltativa o registrazione dell’indirizzo IP). Ad esempio:

* Prima dell&#39;offuscamento: `255.255.255.255`
* Dopo offuscamento: `255.255.255.0`

Vedi anche Raccolta di indirizzi IP e offuscamento degli indirizzi IP nella [sezione Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md).

### Precendenza offuscamento IP {#precedence}

[L&#39;offuscamento dell&#39;IP a livello di stream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=it#create) ha la precedenza su qualsiasi opzione di offuscamento dell&#39;IP impostata in Audience Manager e viene applicata a tutti gli indirizzi IP. Qualsiasi ricerca di geolocalizzazione eseguita da Audience Manager è influenzata dall&#39;opzione [!UICONTROL IP obfuscation] a livello di flusso di dati. Una ricerca di geolocalizzazione in Audience Manager, basata su un IP completamente offuscato, darà luogo a un’area sconosciuta e tutti i segmenti basati sui dati di geolocalizzazione risultanti non verranno realizzati.

## Requisiti di offuscamento degli indirizzi IP {#ip-obfuscation-requirements}

L’offuscamento dell’indirizzo IP è disponibile solo per gli account amministratore di Audience Manager. Consulta [Creare utenti](/help/using/features/administration/administration-overview.md#create-users) per informazioni su come assegnare privilegi di amministratore a un utente.

>[!NOTE]
>
> A causa dell’elevato volume di dati elaborati da Audience Manager, l’entrata in vigore delle modifiche di offuscamento dell’IP può richiedere fino a 4 ore, dal momento in cui vengono aggiornate le impostazioni.

## Configurare l’offuscamento dell’indirizzo IP {#configure-ip-obfuscation}

Per configurare l’offuscamento dell’indirizzo IP, segui la procedura riportata di seguito.

1. Accedi ad Audience Manager con un account amministratore e passa a **Amministrazione > Privacy**.
2. Scegli il tipo di offuscamento dell’IP che desideri utilizzare.
   1. **Offusca tutti gli indirizzi IP:** seleziona questa opzione affinché Audience Manager offuschi l&#39;ultimo ottetto di tutti gli indirizzi IP dei visitatori, indipendentemente dalla regione di origine.
   2. **Offusca indirizzi IP per paesi specifici:** seleziona questa opzione affinché Audience Manager offuschi l&#39;ultimo ottetto degli indirizzi IP dei visitatori per paesi specifici. Utilizza il **elenco di paesi** o il campo **Ricerca** corrispondente per trovare i paesi per cui abilitare l&#39;offuscamento dell&#39;IP, quindi fai clic sull&#39;icona + per aggiungerli all&#39;elenco **Selezionati per offuscamento**. Dopo aver aggiunto tutti i paesi richiesti all&#39;elenco **Selezionati per offuscamento**, fai clic su **Salva**.

![](assets/ip-obfuscation.png)

## Disabilita offuscamento indirizzo IP {#disable-ip-obfuscation}

Per disabilitare l&#39;offuscamento degli indirizzi IP a livello globale, vai a **Amministrazione > Privacy**, seleziona **Non offuscare gli indirizzi IP** e fai clic su **Salva**.

Per disabilitare l&#39;offuscamento degli indirizzi IP per paesi specifici, individua i paesi nell&#39;elenco **Selezionati per offuscamento**, quindi fai clic sull&#39;icona **X** corrispondente. Al termine, fai clic su **Salva**.

## Concetti correlati {#related-concepts}

* [Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Dimostrazione video offuscamento indirizzo IP

>[!VIDEO](https://video.tv.adobe.com/v/27218/)
