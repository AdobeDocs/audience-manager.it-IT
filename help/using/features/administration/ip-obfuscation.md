---
description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
seo-description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
solution: Audience Manager
title: Offuscamento dell’indirizzo IP
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# Offuscamento dell’indirizzo IP {#ip-obfuscation}

Utilizzate questa funzione per oscurare gli indirizzi IP raccolti in Audience Manager.

## Panoramica e metodologia {#overview-and-methodology}

La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.

### Metodo di offuscamento IP

In base ai principi di "Privacy By Design", Adobe Audience Manager consente ai clienti di abilitare l’offuscamento IP dall’interfaccia utente, a livello globale per tutte le aree geografiche o per specifici paesi. Quando abilitate questa impostazione, l'ultimo ottetto (l'ultima parte) dell'indirizzo IP viene immediatamente eliminato quando l'indirizzo IP viene assimilato in Audience Manager. Audience Manager ignora questa parte dell'indirizzo IP prima dell'elaborazione (inclusa prima di qualsiasi ricerca geografica facoltativa o registrazione dell'indirizzo IP). Ad esempio:

* Prima dell'offuscamento: `255.255.255.255`
* Dopo l'offuscamento: `255.255.255.0`

Vedi anche, Raccolta di indirizzi IP e offuscamento di indirizzi IP nella nostra sezione [Privacy](/help/using/overview/data-security-and-privacy/data-privacy.md)dei dati.

## Requisiti di offuscamento indirizzo IP {#ip-obfuscation-requirements}

L'offuscamento dell'indirizzo IP è disponibile solo per gli account amministratore di Audience Manager. Consultate [Creazione di utenti](/help/using/features/administration/administration-overview.md#create-users) per comprendere come assegnare privilegi di amministratore a un utente.

>[!NOTE]
>
> A causa dell'elevato volume di dati elaborati da Audience Manager, le modifiche dell'offuscamento IP possono richiedere fino a 4 ore per entrare in vigore, dal momento in cui aggiornate le impostazioni.

## Configura offuscamento indirizzo IP {#configure-ip-obfuscation}

Seguite i passaggi indicati di seguito per configurare l'offuscamento degli indirizzi IP.

1. Accedete ad Audience Manager con un account amministratore e passate a **Amministrazione &gt; Privacy**.
2. Scegliere il tipo di offuscamento IP che si desidera utilizzare.
   1. **** Soffocare tutti gli indirizzi IP: selezionate questa opzione affinché Audience Manager offuschi l’ultimo ottetto di tutti gli indirizzi IP dei visitatori, a prescindere dalla regione di origine.
   2. **** Indirizzi IP offuscati per paesi specifici: selezionate questa opzione affinché Audience Manager offuschi l’ultimo ottetto di indirizzi IP dei visitatori per specifici paesi. Utilizzate il campo **Elenco paesi** o il campo di **ricerca** corrispondente per individuare i paesi per cui abilitare l'offuscamento IP, quindi fate clic sull'icona + per aggiungerli all'elenco **Selezionato per offuscamento** . Dopo aver aggiunto tutti i paesi richiesti all'elenco **Selezionato per offuscamento** , fare clic su **Salva**.

![](assets/ip-obfuscation.png)

## Disattiva offuscamento indirizzo IP {#disable-ip-obfuscation}

Per disabilitare l'offuscamento dell'indirizzo IP a livello globale, andate a **Amministrazione &gt; Privacy**, selezionate **Non offuscare gli indirizzi** IP e fate clic su **Salva**.

Per disattivare l'offuscamento dell'indirizzo IP per specifici paesi, individua i paesi nell'elenco **Selezionato per offuscamento** , quindi fai clic sulla loro icona **X** corrispondente. Click **Save** when you're done.

## Concetti correlati {#related-concepts}

* [Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Video sull'offuscamento dell'indirizzo IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=ita)

