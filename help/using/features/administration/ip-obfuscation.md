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

## Overview and Methodology {#overview-and-methodology}

La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.

### Metodologia offuscamento IP

In base ai principi di "Privacy by Design", Adobe Audience Manager consente ai clienti di abilitare l'offuscamento IP dall'interfaccia utente, a livello globale in tutte le aree geografiche o per paesi specifici. Quando abilitate questa impostazione, l'ultimo ottetto (l'ultima parte) dell'indirizzo IP viene eliminato immediatamente quando l'indirizzo IP viene trasferito in Audience Manager. Audience Manager elimina questa parte dell'indirizzo IP prima dell'elaborazione (inclusa la ricerca geografica facoltativa o la registrazione dell'indirizzo IP). Ad esempio:

* Before obfuscation: `255.255.255.255`
* After obfuscation: `255.255.255.0`

See also, Collecting IP addresses and IP Address Obfuscation in our [Data Privacy section](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP Address Obfuscation Requirements {#ip-obfuscation-requirements}

L'offuscamento dell'indirizzo IP è disponibile solo per gli account amministratore di Audience Manager. See [Create Users](/help/using/features/administration/administration-overview.md#create-users) to understand how to assign administrator privileges for a user.

>[!NOTE]
>
> A causa dell'elevato volume di dati elaborati da Audience Manager, le modifiche di offuscamento IP possono richiedere fino a 4 ore, dal momento in cui aggiornate le impostazioni.

## Configure IP Address Obfuscation {#configure-ip-obfuscation}

Effettuate le seguenti operazioni per configurare l'offuscamento dell'indirizzo IP.

1. Log in to Audience Manager with an administrator account and go to **Administration &gt; Privacy**.
2. Scegliete il tipo di oscuramento dell'IP che desiderate usare.
   1. **Oscurate tutti gli indirizzi IP:** Selezionate questa opzione affinché Audience Manager offri l'ultimo ottetto di tutti gli indirizzi IP visitatore, indipendentemente dall'area da cui originano.
   2. **Offuscare gli indirizzi IP per paesi specifici:** selezionate questa opzione affinché Audience Manager offri l'ultimo ottetto degli indirizzi IP visitatore per paesi specifici. Use the **List of Countries** or the corresponding **Search** field to find the countries to enable IP obfuscation for, and click the + icon to add them to the **Selected for Obfuscation** list. Once you've added all the required countries to the **Selected for Obfuscation** list, click **Save**.

![](assets/ip-obfuscation.png)

## Disable IP Address Obfuscation {#disable-ip-obfuscation}

To disable IP address obfuscation globally, go to **Administration &gt; Privacy**, select **Do not obfuscate IP addresses**, and click **Save**.

To disable IP address obfuscation for specific countries, find the countries in the **Selected for Obfuscation** list, then click their corresponding **X** icon. Click **Save** when you're done.

## Concetti correlati {#related-concepts}

* [Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Dimostrazione video offuscamento indirizzo IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=ita)

