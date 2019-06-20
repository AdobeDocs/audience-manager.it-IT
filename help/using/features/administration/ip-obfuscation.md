---
description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
seo-description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
solution: Audience Manager
title: Offuscamento dell’indirizzo IP
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# Offuscamento dell’indirizzo IP {#ip-obfuscation}

Utilizzate questa funzione per offuscare gli indirizzi IP raccolti in Audience Manager.

## Panoramica e metodologia {#overview-and-methodology}

La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.

### Metodologia offuscamento IP

In base ai principi di &quot;Privacy by Design&quot;, Adobe Audience Manager consente ai clienti di abilitare l&#39;offuscamento IP dall&#39;interfaccia utente, a livello globale in tutte le aree geografiche o per paesi specifici. Quando abilitate questa impostazione, l&#39;ultimo ottetto (l&#39;ultima parte) dell&#39;indirizzo IP viene eliminato immediatamente quando l&#39;indirizzo IP viene trasferito in Audience Manager. Audience Manager elimina questa parte dell&#39;indirizzo IP prima dell&#39;elaborazione (inclusa la ricerca geografica facoltativa o la registrazione dell&#39;indirizzo IP). Ad esempio:

* Prima dell&#39;offuscamento: `255.255.255.255`
* Dopo l&#39;offuscamento: `255.255.255.0`

See also, Collecting IP addresses and IP Address Obfuscation in our [Data Privacy section](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Requisiti di offuscamento indirizzo IP {#ip-obfuscation-requirements}

L&#39;offuscamento dell&#39;indirizzo IP è disponibile solo per gli account amministratore di Audience Manager. Consultate [Creazione di](/help/using/features/administration/administration-overview.md#create-users) privilegi di amministratore per un utente.

>[!NOTE]
>
> A causa dell&#39;elevato volume di dati elaborati da Audience Manager, le modifiche di offuscamento IP possono richiedere fino a 4 ore, dal momento in cui aggiornate le impostazioni.

## Configurare l&#39;oscuramento dell&#39;indirizzo IP {#configure-ip-obfuscation}

Effettuate le seguenti operazioni per configurare l&#39;offuscamento dell&#39;indirizzo IP.

1. Accedi ad Audience Manager con un account amministratore e vai a **Amministrazione &gt; Privacy**.
2. Scegliete il tipo di oscuramento dell&#39;IP che desiderate usare.
   1. **Oscurate tutti gli indirizzi IP:** Selezionate questa opzione affinché Audience Manager offri l&#39;ultimo ottetto di tutti gli indirizzi IP visitatore, indipendentemente dall&#39;area da cui originano.
   2. **Offuscare gli indirizzi IP per paesi specifici:** selezionate questa opzione affinché Audience Manager offri l&#39;ultimo ottetto degli indirizzi IP visitatore per paesi specifici. Usate l&#39; **elenco dei paesi** o il campo **di ricerca** corrispondente per trovare i paesi per abilitare l&#39;offuscamento IP, quindi fate clic sull&#39;icona + per aggiungerli all&#39;elenco **selezionato per offuscamento** . Dopo aver aggiunto tutti i paesi richiesti all&#39;elenco **Selezionato per offuscamento** , fai clic **su Salva**.

![](assets/ip-obfuscation.png)

## Disattiva offuscamento indirizzo IP {#disable-ip-obfuscation}

Per disattivare l&#39;offuscamento dell&#39;indirizzo IP a livello globale, andate a **Amministrazione &gt; Privacy**, selezionate **Non offuscare gli indirizzi IP** e fate clic **su Salva**.

Per disattivare l&#39;offuscamento dell&#39;indirizzo IP per paesi specifici, individuate i paesi nell&#39;elenco **Selezionato per offuscamento** , quindi fate clic sull&#39;icona **X** corrispondente. Al termine, fate clic **su Salva** .

## Concetti correlati {#related-concepts}

* [Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Dimostrazione video offuscamento indirizzo IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=ita)

