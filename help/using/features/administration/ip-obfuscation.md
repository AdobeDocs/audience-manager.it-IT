---
description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
seo-description: La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.
solution: Audience Manager
title: Offuscamento dell’indirizzo IP
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 22%

---


# Offuscamento dell’indirizzo IP {#ip-obfuscation}

Utilizzate questa funzione per oscurare gli indirizzi IP raccolti in  Audience Manager.

## Panoramica e metodologia {#overview-and-methodology}

La vostra azienda potrebbe voler offuscare l’indirizzo IP in molti paesi a causa delle normative globali sulla privacy. Audience Manager consente di offuscare gli indirizzi IP dei visitatori su base globale o paese per paese.

### Metodo di offuscamento IP

In base ai principi di &quot;Privacy By Design&quot;, Adobe Audience Manager consente ai clienti di abilitare l&#39;offuscamento IP dall&#39;interfaccia utente, a livello globale in tutte le aree geografiche o per specifici paesi. Quando si attiva questa impostazione, l&#39;ultimo ottetto (l&#39;ultima parte) dell&#39;indirizzo IP viene eliminato immediatamente quando l&#39;indirizzo IP viene assimilato  Audience Manager.  Audience Manager scarta questa parte dell&#39;indirizzo IP prima dell&#39;elaborazione (inclusa la prima di qualsiasi ricerca geografica facoltativa o registrazione dell&#39;indirizzo IP). Ad esempio:

* Prima dell&#39;offuscamento: `255.255.255.255`
* Dopo l&#39;offuscamento: `255.255.255.0`

Vedi anche, Raccolta di indirizzi IP e offuscamento di indirizzi IP nella nostra sezione [Privacy](/help/using/overview/data-security-and-privacy/data-privacy.md)dei dati.

## Requisiti di offuscamento indirizzo IP {#ip-obfuscation-requirements}

L&#39;offuscamento dell&#39;indirizzo IP è disponibile solo per  account amministratore Audience Manager. Consultate [Creazione di utenti](/help/using/features/administration/administration-overview.md#create-users) per comprendere come assegnare privilegi di amministratore a un utente.

>[!NOTE]
>
> A causa dell&#39;elevato volume di dati elaborati da  Audience Manager, le modifiche dell&#39;oscuramento IP possono richiedere fino a 4 ore per entrare in vigore, dal momento in cui aggiornate le impostazioni.

## Configura offuscamento indirizzo IP {#configure-ip-obfuscation}

Seguite i passaggi indicati di seguito per configurare l&#39;offuscamento degli indirizzi IP.

1. Accedete a  Audience Manager con un account amministratore e passate a **Amministrazione > Privacy**.
2. Scegliere il tipo di offuscamento IP che si desidera utilizzare.
   1. **Soffocare tutti gli indirizzi IP:** selezionate questa opzione affinché  Audience Manager offuschi l&#39;ultimo ottetto di tutti gli indirizzi IP del visitatore, a prescindere dalla regione da cui provengono.
   2. **Indirizzi IP offuscati per paesi specifici:** selezionate questa opzione affinché  Audience Manager offuschi l’ultimo ottetto di indirizzi IP visitatore per specifici paesi. Utilizzate il campo **Elenco paesi** o il campo di **ricerca** corrispondente per individuare i paesi per cui abilitare l&#39;offuscamento IP, quindi fate clic sull&#39;icona + per aggiungerli all&#39;elenco **Selezionato per offuscamento** . Dopo aver aggiunto tutti i paesi richiesti all&#39;elenco **Selezionato per offuscamento** , fare clic su **Salva**.

![](assets/ip-obfuscation.png)

## Disattiva offuscamento indirizzo IP {#disable-ip-obfuscation}

Per disabilitare l&#39;offuscamento dell&#39;indirizzo IP a livello globale, andate a **Amministrazione > Privacy**, selezionate **Non offuscare gli indirizzi** IP e fate clic su **Salva**.

Per disattivare l&#39;offuscamento dell&#39;indirizzo IP per specifici paesi, individua i paesi nell&#39;elenco **Selezionato per offuscamento** , quindi fai clic sulla loro icona **X** corrispondente. Click **Save** when you&#39;re done.

## Concetti correlati {#related-concepts}

* [Privacy dei dati](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Video sull&#39;offuscamento dell&#39;indirizzo IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

